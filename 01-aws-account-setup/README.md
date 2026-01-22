AWS IAM, Identity Centre, and Organisation Setup

This project documents the setup of an AWS Organisation, IAM Identity Centre, and permissions management. It is part of my #MyJourneyToBecomingACloudEngineer.

Project Objectives

Create and configure an AWS Organisation with 3 environment accounts

Designate one account as the root (Management account)

Set up AWS IAM Identity Centre with 5 users

Group users by roles (Admin, Developer, DevOps)

Create and attach permission-set policies to the different groups

Enable account switching through IAM Identity Centre (SSO)

Tools Required

AWS Management Console

IAM Identity Centre

AWS Organisation

Basic AWS accounts with new email addresses

GitHub (for documentation)

Step-by-Step Instructions
Phase 1: AWS Management Account Setup

Open AWS.com
 and sign up with a new email.

Sign in to the AWS Management Console using the root user.

Enable MFA from IAM to secure the account.

Review: This account serves as the management account, securing access with MFA according to AWS best practices.

![AWS IAM MFA setup](images/AWS-IAM-MFA-setup.png)


Phase 2: Create an AWS Organisation

Go to AWS Organizations in the console.

Create three accounts: Development, Staging, Production.

Enable “All features” during setup.

Wait for the organisation to be fully created.

Review: These accounts form the AWS environment structure. MFA is enabled on all accounts.

![AWS Organization Creation](images/aws-organization-creation.png)


Issue Encountered: Unable to add more than one account due to the initial quota. Solution: Requested a limit increase in Service Quotas.

Phase 3: Create Permission Sets

Go to Permission Sets in IAM Identity Centre and create:

Group	Permission Set
Admin-Team	Admin-permission
DevOps-Team	PowerUser-permission, SystemAdmin-permission
Developer-Team	DataScientist-permission

Review: Permission sets ensure users have access only to what is needed for their role.

Screenshots:
![AWS-IAM Permission](images/AWS-IAM Permission.png.jpg)

Phase 4: Create Groups

Navigate to IAM Identity Centre.

Create groups: Admin, DevOps, Developer.

Review: Groups are applied to all AWS accounts in the organisation.

Screenshot:
![IAM Group creation](images/IAM Group creation.png.jpg)

Phase 5: Create Users

Add users to IAM Identity Centre using their emails.

Enable MFA for all users.

Assign users to groups in all accounts.

Review: Users’ access and functionality depend on their group’s permission set.

Screenshots:
![AWS-IAM User creation](images/AWS-IAM User creation.png.jpg)
![IAM Users Creation](images/IAM Users Creation.png.png)

Phase 6: SSO Account Switching

Users can switch between accounts via IAM Identity Centre (SSO).

Switching automatically logs them out from the previous account.

Review: Tested SSO for all users. Only Admin group users have unrestricted access.

Screenshot:


Observations

AWS Organisations initially limits account creation for fresh accounts.

MFA and permission sets enhance security and proper access management.

Summary

This project involved:

Setting up an AWS Organisation with a Management account

Configuring IAM Identity Centre with 5 users and 3 groups

Assigning permission sets for role-based access

Testing account switching via SSO

Despite quota limitations, the setup demonstrates proper AWS governance, security, and user access management.

Screenshots
Step	Screenshot
MFA Setup![AWS IAM MFA setup](images/AWS IAM MFA setup.png.jpg)
AWS Organisation![AWS Organization Creation](images/AWS Organization Creation.png)
Permission Sets![AWS-IAM Permission](images/AWS-IAM Permission.png.jpg)
User Creation![AWS-IAM User creation](images/AWS-IAM User creation.png.jpg)
Users Overview![IAM Users Creation](images/IAM Users Creation.png.png)
Group Creation![IAM Group creation](images/IAM Group creation.png.jpg)
SSO Switch	




