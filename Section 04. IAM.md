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




















































































































































































































































