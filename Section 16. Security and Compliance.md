# 183. Shared Responsibility Model

* AWS is responsible for security of the Cloud
* Customers are responsible for security in the Cloud

<img width="715" height="445" alt="image" src="https://github.com/user-attachments/assets/594fc538-6bc0-42a5-ad3c-02908697913c" />

# 184. DDoS Protection: WAF & AWS Shield

* AWS Shield
  - AWS Shied Standard free
  - AWS Shied Advanced 24/7 premium protection.

<img width="634" height="359" alt="image" src="https://github.com/user-attachments/assets/38933497-4d4c-48de-99ff-b5426faf36b9" />

* AWS Web Application Firewall (WAF)
* CloudFront and Route 53

# 185. AWS Network Firewall

protection on the Layer 3 to layer 7

<img width="383" height="572" alt="image" src="https://github.com/user-attachments/assets/0a6b0403-a455-4b84-a1c9-a2a2baa83020" />

# 186. AWS Firewall Manager

For managing security rules in all accounts in an AWS organisation.

# 187. Penetration Testing

you do not need authorisation from AWS if you do pen testing against 8 services.

# 188. Encryption with KMS & CloudHSM

## Data at rest vs. Data in transit

data at rest : data that is current stored.
Data in transit : data currently moving 

We should encrypt our data in both data at rest state and data in transit state.

## Key Management Service

AWS encrypt keys for us, AWS manages the software

## CloudHSM

HSM = hardware security module.

<img width="254" height="259" alt="image" src="https://github.com/user-attachments/assets/ff9037fb-b149-42c9-be4b-0296f8e14bf3" />

AWS provides only the encryption hardware

<img width="408" height="267" alt="image" src="https://github.com/user-attachments/assets/83d1972b-12d4-413e-82b3-c8b9333b738d" />


# 190. AWS Certificate Manager (ACM)

* Used for provision, manage and deploy SSL and TLS certificates

<img width="277" height="595" alt="image" src="https://github.com/user-attachments/assets/2b925dba-3e81-4a89-99e5-2968ba331f1a" />

# 191. AWS Secrets Manager

* for storing secrets
* force rotation of secrets
* automated generation of secrets on rotation

# 192. AWS Artifact

* portal that provides customers with on-demand access to AWS compliance documentation

# 193. Amazon GuardDuty

* Intelligent thread discovery to protect your AWS account.
* uses ML algorithems

<img width="525" height="558" alt="image" src="https://github.com/user-attachments/assets/2fb1699b-1561-4345-b25c-391e3b0957da" />


# 194. Amazon Inspector
Automated security assessments for only EC2 instance, Container images on ECR and Lambda functions.

<img width="280" height="647" alt="image" src="https://github.com/user-attachments/assets/e35529d7-ba36-401a-bbdc-9769a9d87c41" />


# 195. AWS Config

Helps with auditing and recording compliance of AWS resources by recording configurations and change over time.

<img width="429" height="411" alt="image" src="https://github.com/user-attachments/assets/45639b05-fa23-43f7-8e13-818ac60c8c37" />

# 196. Amazon Macie
Macie uses ML to help you identify and alert PII and other sensitive data in your AWS.

<img width="690" height="262" alt="image" src="https://github.com/user-attachments/assets/43115a7a-193c-4e3c-981f-e32c68d9640a" />

# 197. AWS Security Hub
Centralised security tool to manage security across several AWS accounts

<img width="751" height="535" alt="image" src="https://github.com/user-attachments/assets/b173fd16-9c33-4874-9b3c-0309b02b6f23" />

# 198. Amazon Detective
analyse, investigate and quickly identify the root cause of security issue. uses ML.

# 199. AWS Abuse
Send any abuse of AWS services and resources to abuse@amazonaws.com

# 200. Root User Privileges
* change account settings.
* close your AWS account.
* Change or cancel your AWS support plan.
* Register as a seller in the Reserved Instance Marketplace.

# 201. IAM Access Analyzer
* find out which resources are shared externally.
* first define a Zone of Trust, anything outside the zone of trust is considered risk.

<img width="280" height="400" alt="image" src="https://github.com/user-attachments/assets/fcfeecb1-fa86-4668-b684-b5cfe60f4a35" />

# Quiz

<img width="834" height="357" alt="image" src="https://github.com/user-attachments/assets/b95b9306-6a9a-477d-acbd-a4523b235d55" />

<img width="841" height="419" alt="image" src="https://github.com/user-attachments/assets/b8c7d9ad-8ad9-4c71-9a23-401aaf2c71f2" />

<img width="830" height="458" alt="image" src="https://github.com/user-attachments/assets/ac25160c-242f-4e77-a37d-d29671b6060f" />

<img width="829" height="463" alt="image" src="https://github.com/user-attachments/assets/b82ce70e-9fc4-4463-a9ff-55517aba5cf7" />

<img width="836" height="496" alt="image" src="https://github.com/user-attachments/assets/97bad357-be99-4e5b-9859-17d6c4abea38" />

<img width="850" height="439" alt="image" src="https://github.com/user-attachments/assets/c3228fde-0fb8-4219-8270-5cc4351f3d57" />

<img width="832" height="311" alt="image" src="https://github.com/user-attachments/assets/ec422388-18ac-4cdf-9523-97c859e350cb" />

<img width="840" height="433" alt="image" src="https://github.com/user-attachments/assets/925b8843-ca83-4686-9b16-653a32504819" />

<img width="833" height="510" alt="image" src="https://github.com/user-attachments/assets/f2dc058d-397a-4fff-868c-4e0bd6cdd055" />

<img width="839" height="417" alt="image" src="https://github.com/user-attachments/assets/81c60c44-fff4-4e84-acc1-c503c68071f0" />

<img width="851" height="486" alt="image" src="https://github.com/user-attachments/assets/602aed80-894c-485e-807b-90d0591898c7" />

<img width="846" height="472" alt="image" src="https://github.com/user-attachments/assets/e390f5eb-fd5f-47ea-85f5-51d4388dbea1" />

<img width="851" height="522" alt="image" src="https://github.com/user-attachments/assets/9f9f5148-0ce8-4896-ba0f-595ce494c297" />

<img width="856" height="469" alt="image" src="https://github.com/user-attachments/assets/d7c4f1f6-6288-4537-a4aa-7ee92b92949a" />

<img width="883" height="402" alt="image" src="https://github.com/user-attachments/assets/086ead9f-e4ac-44e6-ae14-c9d4c367b53d" />

<img width="829" height="440" alt="image" src="https://github.com/user-attachments/assets/96702a45-4ab4-4fc4-b566-1b4be2b01778" />

<img width="848" height="494" alt="image" src="https://github.com/user-attachments/assets/e59a5d20-6c25-4c18-9161-aa04feccf7b6" />

<img width="862" height="490" alt="image" src="https://github.com/user-attachments/assets/ebd39600-2c3a-44c2-b80a-f50bf9a3da50" />
