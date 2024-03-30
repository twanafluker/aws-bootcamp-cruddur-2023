# Week 0 — Billing and Architecture

## Required Tasks

### Install AWS CLI

I used gitpod to install my AWS CLI. I am providing the instructions I used for my configuration of my local machine on Windows.

I did the following steps to install AWS CLI.

I followed the instructions on the [AWS CLI Install Documentation Page](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

I installed the AWS CLI for Windows 10 via command in **Command Prompt**:

```
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
```

I was able to set my AWS CLI credentials using the command 
```
aws configure
```


### Logical Architecture

![Crudder Logical Design](assets/crudder-logical-diagram.png)

[Lucid Charts Share Link](https://lucid.app/lucidchart/f1406570-534f-4d2a-bb5d-ca51167b40e0/edit?viewport_loc=-216%2C-182%2C2209%2C2083%2C0_0&invitationId=inv_c4d0f47d-345d-4f02-a635-783d95dbfbdb)


### Code Example for setting AWS budget

```json
{
    "BudgetLimit": {
        "Amount": "1",
        "Unit": "USD"
    },
    "BudgetName": "Example Tag Budget",
    "BudgetType": "COST",
    "CostFilters": {
        "TagKeyValue": [
            "user:Key$value1",
            "user:Key$value2"
        ]
    },
    "CostTypes": {
        "IncludeCredit": true,
        "IncludeDiscount": true,
        "IncludeOtherSubscription": true,
        "IncludeRecurring": true,
        "IncludeRefund": true,
        "IncludeSubscription": true,
        "IncludeSupport": true,
        "IncludeTax": true,
        "IncludeUpfront": true,
        "UseBlended": false
    },
    "TimePeriod": {
        "Start": 1477958399,
        "End": 3706473600
    },
    "TimeUnit": "MONTHLY"
}
```

