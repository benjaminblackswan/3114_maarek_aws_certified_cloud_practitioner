## 14. IAM Introduction: Users, Groups, Policies

IAM is a global service

Groups only contain users, it can not contain other groups

users do not have to belong to a group.

A user can belong to multiple groups.

<img width="1065" height="249" alt="image" src="https://github.com/user-attachments/assets/2da83114-ac81-499b-9308-4d4132109d75" />

Users or Groups can be assigned JSON documents called policies.

Policies define permissions, use **least privilege prinicple**

## 15. IAM Users & Groups Hands On

if you see Account ID when you click on the your name in the top right, it means you are using the **Root Account**

<img width="788" height="476" alt="image" src="https://github.com/user-attachments/assets/09493613-e961-46da-8721-5e8cedc243be" />

create an IAM user

IAM user is easier than user in Identity Center

<img width="1484" height="134" alt="image" src="https://github.com/user-attachments/assets/3ca78cec-5935-415c-8d54-3b8cb32c35df" />

<img width="1413" height="903" alt="image" src="https://github.com/user-attachments/assets/4286656c-69e5-4b09-b5dc-fd1b321cf965" />

create a new group 

<img width="1454" height="246" alt="image" src="https://github.com/user-attachments/assets/b962e9fe-e6b5-4800-860f-20ce1f841a33" />

<img width="1436" height="266" alt="image" src="https://github.com/user-attachments/assets/46ff9c38-67ad-4ef6-b505-e31f8c2cea28" />

add a key-value pair

<img width="1428" height="626" alt="image" src="https://github.com/user-attachments/assets/93a66e11-7c74-40b7-8590-fa9a84c38715" />

To see which policy is attached to a User Group

<img width="1324" height="595" alt="image" src="https://github.com/user-attachments/assets/b8d08cb4-0f18-4030-8347-36e5c53685ff" />

The policy of a user should be the same as a group the user is in.

<img width="1253" height="248" alt="image" src="https://github.com/user-attachments/assets/99b0fca7-581e-448e-b32b-3289e2f3d2b0" />


edit your AWS account Alias to make your IAM users sign in more easily

<img width="458" height="277" alt="image" src="https://github.com/user-attachments/assets/8a21cc72-193b-45d6-8513-c70ec61a8cf0" />

This will then update the sign in URL with the updated account alias

https://benjaminblackswan.signin.aws.amazon.com/console

paste this in a new browser, the account alias will already be in the field, sign in with the Stephane IAM account you just created.

<img width="398" height="551" alt="image" src="https://github.com/user-attachments/assets/b57634ca-3b4a-47ec-87eb-62a04ec9e873" />


if you look at the top right, IAM users have IAM user under the Account ID, root user does not.

<img width="449" height="466" alt="image" src="https://github.com/user-attachments/assets/6bc87005-6202-403a-b5fd-71cf4cb04608" />

## 16. AWS Console Simultaneous Sign-in

multi-session support allows you to sign into multiple AWS accounts on the same browser.

https://aws.amazon.com/about-aws/whats-new/2025/01/aws-management-console-simultaneous-sign-in-multiple-accounts/


## 17. IAM Policies

in Root, Remove *Stephane* from *Admin* group

Then Stephane user will not be able to have **Access Management**.

<img width="1466" height="672" alt="image" src="https://github.com/user-attachments/assets/d51a0264-9137-44e4-b242-ca19291b4a46" />

This time we are going to attach Policy directly to *Stephane*, instead of adding *Stephane* to a group.

In Root: 

<img width="1165" height="304" alt="image" src="https://github.com/user-attachments/assets/2826bdcb-c345-4a7e-9b02-84353fd2f4c9" />
<img width="1161" height="201" alt="image" src="https://github.com/user-attachments/assets/a791048f-c58f-49a9-807c-025df63e77d5" />

Search for **IAMReadOnlyAccess**

<img width="1181" height="224" alt="image" src="https://github.com/user-attachments/assets/d6ac9b01-6f94-444f-b005-365b21e7c970" />

Policy attached to Stephane

<img width="1172" height="260" alt="image" src="https://github.com/user-attachments/assets/2cad4d15-5a6c-41b3-83c9-996ec50be3e5" />

## create a new group

create a new group called *3114_developers* and give it the AlexaForBusinessDeviceSetup policy


<img width="1251" height="358" alt="image" src="https://github.com/user-attachments/assets/c613e9fa-39dc-4da9-87a4-8af168fadc72" />

Then add *Stephane* to the this group.

Now check that Stephane should have three policies attached to it.

<img width="1467" height="695" alt="image" src="https://github.com/user-attachments/assets/0f10e146-33d8-489e-b837-745d5daed6be" />


## lets look at Policies

lets look at AdministratorAccess policy


<img width="1159" height="398" alt="image" src="https://github.com/user-attachments/assets/d9d53085-5a24-4668-8006-ab96b7b9e6b9" />


 **AdministratorAccess** policy has all the permissions, currently 448 permissions as of 2025-10-08

<img width="1318" height="491" alt="image" src="https://github.com/user-attachments/assets/57eb9a55-6f74-4097-b28a-d7d4170be55c" />

<img width="1134" height="185" alt="image" src="https://github.com/user-attachments/assets/7e58cb79-b231-4408-b36d-914c1e22db1d" />


as you can see, this policy gives all action to all resources, therefore this policy has the highest level of access in AWS.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
```

have a look at the **IAMreadonlyAccess**



```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "iam:GenerateCredentialReport",
                "iam:GenerateServiceLastAccessedDetails",
                "iam:Get*",
                "iam:List*",
                "iam:SimulateCustomPolicy",
                "iam:SimulatePrincipalPolicy"
            ],
            "Resource": "*"
        }
    ]
}
```

## create your own policy

<img width="1175" height="86" alt="image" src="https://github.com/user-attachments/assets/ad9b8419-8d03-4ce3-a9b2-393559be2dab" />

Delete the 3114_Developers group and remove the IAMreadonlyAccess policy from *Stephane* user.


# 19. IAM MFA Overview

There are two defence for users, password and MFA.

In Root: Go to password policy

<img width="1503" height="440" alt="image" src="https://github.com/user-attachments/assets/b4eb9b3c-3f1d-4d27-b435-d2cbf17692a7" />


Lets add the following condition in password policy

<img width="1476" height="694" alt="image" src="https://github.com/user-attachments/assets/1e131f87-7732-4b7f-8809-ebb757d6e241" />

# 21. AWS Access Keys, CLI and SDK

do not share access key.

Open Command Prompt and type `aws --version` to see the current version of AWS CLI installed, and compare it against
https://raw.githubusercontent.com/aws/aws-cli/v2/CHANGELOG.rst

<img width="502" height="206" alt="image" src="https://github.com/user-attachments/assets/d34636b9-f014-4530-bb1e-074f5c3dbb6a" />


# 25. AWS CLI Hands On

Go to `Security Credentials`

<img width="314" height="528" alt="image" src="https://github.com/user-attachments/assets/eb1970ef-b430-402b-af9a-21045c653d91" />

<img width="1172" height="230" alt="image" src="https://github.com/user-attachments/assets/3dbfb2d4-000f-417f-8681-a317db0a0b04" />

Choose CLI option

store the Access Key and secret in a safe place, the following access key will be destroyed after this lesson.

<img width="792" height="72" alt="image" src="https://github.com/user-attachments/assets/a25c9bd9-da3e-4dfc-8170-a9a12c46fe46" />

in the AWS CLI 
type `aws configure`

```
AWS Access Key ID [****************EIA6]: AKIAYYYYYYYYYYYYYYYYYYYYYYY (to be deleted)
AWS Secret Access Key [****************PdRb]: Ly0EvXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (to be deleted)
Default region name [ap-southeast-2]: ap-southeast-2
Default output format [text]: json
```
**ap-southeast-2** is for Sydney, refer to https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html

json as default ouput format as it is much more human readable than text, if you get <img width="329" height="31" alt="image" src="https://github.com/user-attachments/assets/0ca728a4-1a16-45ef-a54f-730fa2026046" /> it means, you did not choose text or json for output format type.

run `aws iam list-users`

<img width="603" height="475" alt="image" src="https://github.com/user-attachments/assets/bf09d9e3-bbac-42a1-bbc5-ef045122f00c" />

if we remove user *stephane*'s permission, and the run same code, we get

<img width="1156" height="98" alt="image" src="https://github.com/user-attachments/assets/c47cabfc-4d43-4ec7-9506-6806f3513c22" />

























































































































































































































