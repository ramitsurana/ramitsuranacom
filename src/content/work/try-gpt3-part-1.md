---
title: Try GPT3 - Part -1
publishDate: 2021-05-04 00:00:00
img: /assets/stock-2.jpg
description: Analysis and Observations on GPT3
tags:
  - gpt3
  - chat
  - transformers
  - openai
---

- [What is GPT3 ?](#what-is-gpt3)
- [GPT3 Buzz](#gpt3-buzz)
- [Transformations](#transformations)
  * [Pytorch to Tensorflow](#pytorch-to-tensorflow)
  * [Terraform to Cloudformation](#terraform-to-cloudformation)
  * [Cloudformation to Azure Resource Manager](#cloudformation-to-azure-resource-manager)
- [YAML Format](#yaml-format)
- [Chat](#chat)
  * [Information about Covid 19](#information-about-covid-19)
  * [Mona Lisa](#mona-lisa)
  * [Checking Stock Market Price](#checking-stock-market-price)
  * [General Knowledge Questions](#general-knowledge-questions)
- [Minor Things](#minor-things)
- [References](#references)


## What is GPT3?

GPT3 is a transformer-based NLP model which is built by the OpenAI team. The GPT3 model is unique as it's built upon 175 Billion Parameters which makes it one of the world's largest NLP models to be available for private usage. The GPT3 model is built upon the original architecture of GPT2 with few modifications and large dataset size. If you are looking for some more information regarding the transformers, below is a good video to learn more on it -

<iframe width="560" height="315" src="https://www.youtube.com/embed/TQQlZhbC5ps" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## GPT3 Buzz

If you are on social media, you might find some amazing buzz happening over GPT3. Here are a few excerpts on the same -


<blockquote class="twitter-tweet"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/GPT3?src=hash&amp;ref_src=twsrc%5Etfw">#GPT3</a> is right. On job interviews, you have to talk to the interviewer.<br>Fun fact: 100% of interviewees selected talked at some point with the interviewer. <a href="https://t.co/ag6gI62O1Y">pic.twitter.com/ag6gI62O1Y</a></p>&mdash; Alexis Paques (@AlexisPaques) <a href="https://twitter.com/AlexisPaques/status/1389216139503415303?ref_src=twsrc%5Etfw">May 3, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Generate Detailed Emails from One Line Descriptions (on your mobile)<br><br>I used GPT-3 to build a mobile and web Gmail add-on that expands given brief descriptions into formatted and grammatically-correct professional emails.<br><br>Thanks to <a href="https://twitter.com/OpenAI?ref_src=twsrc%5Etfw">@OpenAI</a> <a href="https://twitter.com/gdb?ref_src=twsrc%5Etfw">@gdb</a> for providing me access. <a href="https://t.co/gPB0K771NF">pic.twitter.com/gPB0K771NF</a></p>&mdash; Samanyou Garg (@SamanyouGarg) <a href="https://twitter.com/SamanyouGarg/status/1297958041262776325?ref_src=twsrc%5Etfw">August 24, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">=GPT3()... the spreadsheet function to rule them all.<br><br>Impressed with how well it pattern matches from a few examples.<br><br>The same function looked up state populations, peoples&#39; twitter usernames and employers, and did some math. <a href="https://t.co/W8FgVAov2f">pic.twitter.com/W8FgVAov2f</a></p>&mdash; 🤖 Paul Katsen (@pavtalk) <a href="https://twitter.com/pavtalk/status/1285410751092416513?ref_src=twsrc%5Etfw">July 21, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Transformations

Amongst a lot of new things that GPT3 can do, it is also able to quite a few transformations which seems impossible for NLP models to perform until a few years ago. I did some testing and experimentation on it.

### Pytorch to Tensorflow

For anyone who is unaware, Pytorch and Tensorflow are state of the art Deep Learning Frameworks built by Google and Facebook. Both of these frameworks are open source and available on GitHub. For this particular challenge, I tried to instruct GPT3 in the playground, to convert some of the python code from Pytorch to Tensorflow. 

Input ⇒

```python
#Pytorch to Tensorflow:
Pytorch: 

import torch
model = torch.nn.Sequential(
torch.nn.Linear(28, 28, input_shape=(28, 28)),
torch.nn.ReLU(),
torch.nn.Linear(128, 10, bias=True))

Tensorflow:
```

Output ⇒

```python
#Pytorch to Tensorflow:
Pytorch: 

import torch
model = torch.nn.Sequential(
torch.nn.Linear(28, 28, input_shape=(28, 28)),
torch.nn.ReLU(),
torch.nn.Linear(128, 10, bias=True))

Tensorflow:

import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt

#Define the model

model = tf.keras.Sequential([
tf.keras.layers.Flatten(),
tf.keras.layers.Dense(128, activation='relu', input_shape=(28, 28)),
tf.keras.layers.Dense(10, activation='softmax')])

#Define the optimizer

optimizer = tf.keras.optimizers.Adam(0.001)
tf.keras.layers.Model.compile(optimizer=optimizer, loss='categorical_crossentropy', metrics=['accuracy'])

#Define the loss function

loss = tf.keras.losses.CategoricalCrossentropy()

#Define
```

As you can see from above, GPT3 not only understands the PyTorch code but also was able to generate the code to Tensorflow with correct syntax. I think I may have underestimated the number of tokens, hence the text that was generated was limited, but it was ample proof that GPT3 is able to perform such conversion.

### Terraform to Cloudformation

For another transformation, I have chosen Cloudformation and Terraform tools which are great tools for developing the Infrastructure as a Code practice. For folks who are not aware, Cloudformation is built by AWS to support building AWS Infrastructure using its services whereas terraform is a multi-cloud enabler tool that supports multi-clouds like AWS, Azure, GCP etc.

Input ⇒

```json
#Cloudformation to Terraform:

Cloudformation: 

{
    "Type": "AWS::IAM::Policy",
    "Properties": {
        "PolicyName": "root",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Action": "*",
                    "Resource": "*"
                }
            ]
        },
        "Roles": [
            {
                "Ref": "RootRole"
            }
        ]
    }
}

Terraform:
```

Output ⇒

```json
#Cloudformation to Terraform:

Cloudformation: 

{
    "Type": "AWS::IAM::Policy",
    "Properties": {
        "PolicyName": "root",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Action": "*",
                    "Resource": "*"
                }
            ]
        },
        "Roles": [
            {
                "Ref": "RootRole"
            }
        ]
    }
}

Terraform:

resource "aws_iam_policy" "root" {

statement {

action = "*"

resources = ["*"]

}

}

resource "aws_iam_role" "root" {

assume_role_policy = "${aws_iam_policy.root.arn}"

}

The above code is a simple example of how to create a role and attach a policy to it.

Cloudformation:

{

"AWSTemplateFormatVersion": "2010-09-09",

"Description": "",

"Resources": {

"MySecurityGroup": {

"Type": "AWS::EC2::SecurityGroup",

"Properties": {

"GroupDescription": "",

"SecurityGroupIngress": [

{

"IpProtocol": "tcp",

"
```

**This is something interesting that happened.** I had set the Response Length to 199, however, the response was lower than the 199 tokens, so why did GPT3 had to respond with this example for the security group? I observed this similar pattern for a few more examples, as per my understanding, it may be due to the GPT3 side that if the number of tokens is higher than the output response required number of tokens, it's trying to generate unnecessary content without any pre-defined output. This can be fixed using the Frequency and Presence penalty option which can be set from the parameters.

This begs another question, can GPT3 understand the different services that different cloud providers have and do changes according to that? Let's try it out.

### Cloudformation to Azure Resource Manager

For this challenge, I have taken the task of converting an AWS based IAM Policy and convert it to Azure IAM Policy.

Input ⇒

```json
#Cloudformation to Azure Resource Manager:
Cloudformation: 
{
    "Type": "AWS::IAM::Policy",
    "Properties": {
        "PolicyName": "root",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Action": "*",
                    "Resource": "*"
                }
            ]
        },
        "Roles": [
            {
                "Ref": "RootRole"
            }
        ]
    }
}

Azure Resource Manager:
```

Output ⇒

```json
#Cloudformation to Azure Resource Manager:
Cloudformation: 
{
    "Type": "AWS::IAM::Policy",
    "Properties": {
        "PolicyName": "root",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Action": "*",
                    "Resource": "*"
                }
            ]
        },
        "Roles": [
            {
                "Ref": "RootRole"
            }
        ]
    }
}

Azure Resource Manager:
{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": [
"*"
],
"Resource": [
"*"
]
}
],
"Roles": [
{
"Ref": "RootRole"
}
]
}

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following is a comparison of the two formats:

The following
```

Unfortunately, GPT3 is not quite there yet. As you could see it's not giving any kind of relevant info to us. The last few words were gibberish and repetitive in nature. I also checked the ARM Template which it does not look like it was able to capture the relevant details.

Another observation, I had was if you accidently put the wrong input instruction sentence something like below ⇒

```json
#Azure Resource Manager to Cloudformation:
Cloudformation: 
{
    "Type": "AWS::IAM::Policy",
    "Properties": {
        "PolicyName": "root",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Action": "*",
                    "Resource": "*"
                }
            ]
        },
        "Roles": [
            {
                "Ref": "RootRole"
            }
        ]
    }
}

Azure Resource Manager: 
```

It will give you the below output ⇒

Output ⇒

```json
#Azure Resource Manager to Cloudformation:
Cloudformation: 
{
    "Type": "AWS::IAM::Policy",
    "Properties": {
        "PolicyName": "root",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Effect": "Allow",
                    "Action": "*",
                    "Resource": "*"
                }
            ]
        },
        "Roles": [
            {
                "Ref": "RootRole"
            }
        ]
    }
}

Azure Resource Manager:
{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": [
"*"
],
"Resource": [
"*"
]
}
],
"Roles": [
{
"Ref": "RootRole"
}
]
}

The following is a list of the most common operations that can be performed using the AWS CLI.

The following is a list of the most common operations that can be performed using the AWS CLI.

The following is a list of the most common operations that can be performed using the AWS CLI.

The following is a list of the most common operations that can be performed using the AWS CLI.

The following is a list of the most common operations that can be performed using the AWS CLI.

The following is a list of the most common operations that can be performed using the AWS
```

It looks like GPT3 tried to simply copy paste the input and present it into the output.

## YAML Format

The inputs that I was providing were all in the JSON format, hence I decided to change it to YAML format.

```json
#Terraform to Cloudformation:
Cloudformation: 

Type: 'AWS::IAM::Policy'
Properties:
  PolicyName: root
  PolicyDocument:
    Version: "2012-10-17"
    Statement:
      - Effect: Allow
        Action: '*'
        Resource: '*'
  Roles:
    - !Ref RootRole

Terraform: 
```

 

Here is the output ⇒

![CFT](/assets/gpt3/terraform-to-cft.png)

After some digging into the GPT3 docs I came to know that currently GPT3 only supports JSON Format. Currently YAML format is not supported, hope this support gets added soon 🤞

## Chat

GPT3 also features a chat option which makes the GPT3 as a bot which responds to any input you ask it. So I tried asking a few questions to GPT3 -

### Information about Covid 19

```python
Human: Is Covid 19 dangerous?
AI: I dont know though there are stories that I read online. The story claims that it is a dangerous drug and produces huge addiction. I found the best information online about that subject.
```

Looks like GPT3 is not aware about Covid 19. It is under the assumption that Covid 19 is a drug and can be addictive.

### Mona Lisa

```python
Human: Where is Mona Lisa?
AI: The Mona Lisa is currently housed in the Louvre Museum in Paris. The museum houses a replica of the famous painting. There is a magnificent crowd to see the famous painting 
on a daily basis.
```

The response is correct. It was able to collect the latest and the most updated information from the Internet. This is very good, since as per wikipedia itself mona lisa has been kept and shifted from one place to another through in different time periods in the history. Ref -[https://en.wikipedia.org/wiki/Mona_Lisa](https://en.wikipedia.org/wiki/Mona_Lisa)

### Checking Stock Market Price

```python
Human: what is the stock market for amazon?
AI: Currently, Amazon is selling at $1,168.85 per share. I found the best info online about that stock.
```

From Google, I found this ⇒

![Stock-Prices](/assets/gpt3/amazon-stock-prices.png)

Looks like it is picking up the the stock price from the older time period.

### General Knowledge Questions

On 17th March 2021, Tanzania's president died due to covid and a few days later Samia Suluhu Hassan was appointed as the President. On 10th April 2021, I tried asking the following question to GPT3- Who is Tanzania President?

Input ⇒

```python
The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, and very friendly.

Human: Hello, who are you?
AI: I am an AI created by OpenAI. How can I help you today?
Human: Who is Tanzania President?
Human: Who is the current president of Tanzania?
```

Here is the output ⇒

```python
The following is a conversation with an AI assistant. The assistant is helpful, creative, clever, and very friendly.

Human: Hello, who are you?
AI: I am an AI created by OpenAI. How can I help you today?
Human: Who is Tanzania President?
AI: The current president of Tanzania is Dr. John Magufuli.  He was sworn in as president in November 2015. I have found the best resources on the internet about Tanzania President.
```

**This response of the GPT3 is outdated and could lead to misinformation which can be an issue.** I tried to rephrase the question by asking - Who is the current president of Tanzania?

```python
Human: Who is the current president of Tanzania?
```

Output ⇒ 

![President](/assets/gpt3/tanzania-president.png)

Since I asked for the current president of Tanzania, this response seems vague and incorrect. I think this maybe due to some minor bias towards the titles which maybe be present on the internet.

**Quick Update** ⇒

**On conversation with one of the OpenAI member I came to know that GPT3 last got updated in August 2020, hence I was observing the outdated results.**

## Minor Things

- If you have trailing spaces between texts, it gives you warnings.
- It many times misclassified my output as Unsafe, especially in cases where I accidentally put incorrect conversion sentence.
- You can report any wrong output or issue by clicking the report issue option in playground.

![Minor](/assets/gpt3/minor-things.png)

## References

- [https://andrewmayneblog.wordpress.com/](https://andrewmayneblog.wordpress.com/)
- [https://gpttools.com/](https://gpttools.com/)
- [https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-policy.html](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-policy.html)

