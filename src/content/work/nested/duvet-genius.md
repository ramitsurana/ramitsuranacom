---
title: Storing non-sensitive parameters in a Database
publishDate: 2020-22-01 00:00:00
img: /assets/stock-3.jpg
description: |
  Storing non-sensitive parameters in Dynamodb.
tags:
  - Dynamodb
  - Terraform
  - Jenkins
---

Do you have a huge infrastructure and you are tired of managing releases or fixing hotfixes every once in a while? In one of my past projects, I had this similar issue where maintenance and regular updates to production were becoming hard to follow up and releases took hours if not minutes to prepare and execute. As our features and requirements increase the complexity of the project also increased.

### Solution

While building on one of my solutions, where we typically use Dynamodb for storing information. I  had the idea of using a central location (in our case, dynamodb) to read all the parameter related values. To give a bit of overview of our architecture, we had 3 primary AWS accounts (Dev, Control and Prod) and multiple customer accounts (100+ AWS accounts) linked together working in an orchestration. After using the dynamodb, we ended up using it something like below -


![dynmodb-solution](/assets/storing-params/dynamodb-storing-values.png)

### Sample Dynamodb Schema

```json
{
  "dev": {
    "account_number": "123456789",
    "assume_role": "xxxxxx",
    "admin_email": "xxxxxxxx",
    "region": "us-east-1",
    "pipelines": {
       "instance_size": "t2.micro" 
    }
  },
  "qa": {
    "account_number": "123456789",
    "assume_role": "xxxxxx",
    "admin_email": "xxxxxxxx",
    "region": "us-east-1"
  },
  "prod": {
    "account_number": "123456789",
    "assume_role": "xxxxxx",
    "admin_email": "xxxxxxxx",
    "region": "us-east-1"
  },
  "id": "Netflix"
}
```

### Using Terraform

In terraform, we had approx 90+ variables to work with, changing values for every release for even a few variables was cumbersome and time-consuming. So I ended up, changing the way how we declared and update the variables under variables.tf. Instead of declaring the values in variables terraform file, I started generating the terraform tfvars.json file at run time using some python code and passing the JSON file using the -var-file subcommand at the time of terraform plan or apply. Example -

```text
terraform plan -var-file="sample.tfvars.json"
terraform apply -var-file="sample.tfvars.json"
```

In the python code, I ended up calling the dynamodb table parameter values using boto3 in order to update the values of the variables. This gave me an added benefit to update the dynamodb values and execute the terraform code without doing any code changes.

### Using Serverless Framework

Under our serverless framework usage, we had distributed the workflow into several different microservices. These microservices had different parameter values declared in different YAML files under individual services. Similar to terraform, using simple boto3 and dynamodb I ended up generating the YAML file along with relevant values for individual microservices. Only the default values for each microservices were kept at the codebase. 

## Conclusion

Using simple techniques and solutions like the ones I have shared above helped me to reduce my time for managing infrastructure and deployments and focus more on the feature development and building solutions from an end to end perspective. In following the above approach however there is one caveat, **you need to log the changes made and ensure proper access permissions for the Dynamodb updates in the table.** Also, please ensure only read access to the resources using the dynamodb. In the end, I hope that this post would have helped you. 

Thanks for reading!
