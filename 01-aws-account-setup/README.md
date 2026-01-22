## AWS IAM, IDENTITY CENTER, AND ORGANIZATION SETUP

## Project Objectives

- Create and configure an AWS Organisation with 3 environment accounts.
- Make one account the root user (Management account)
- Set up AWS IAM Identity Centre with 5 users.
- Group users by roles ( e.g. Admin, Developer, DevOps).
- Create and attach permission-set policies to the different groups created.
- Switching between accounts within the organisation in the IAM identity centre (SSO) page.

## Tools Required

- New email addresses (i.e., ones that haven’t been used for an AWS account)
- AWS Management Console.
- AWS Organisation
- IAM Identity Centre
- Basic AWS account(s)
- Notion (for documentation)

## Step-by-Step Instructions

### Phase 1: Setting Up an AWS Management Account

Step 1: Open AWS.com and sign up using an email address

Step 2: Sign in to the AWS Management Console using the root user of the account

Step 3: Enable MFA from the IAM

**REVIEW:** This step was used to create the main account, which will serve as the management account for the organisation, and MFA was activated to secure it and comply with AWS best practices. The account was logged in using the root email portal.

![AWS IAM MFA setup](images/AWS-IAM-MFA-setup.png)


### Phase 2: Create an AWS Organisation

Step 1: Go to AWS Organisation in the console (the root user account)

Step 2: Create a Development account

Step 3: Create a Staging account

Step 4: Create Production account

Step 5: Click create and select all features

Step 6: Wait for the organisation to get created

**REVIEW:** This is where the different AWS environments are created that will form the organisation. This is after the management account was created in the previous step. The MFA of all three environment accounts were also enabled to comply with AWS best practices.

### Issues Encountered, Troubleshooting and Solution

- After adding one account, I was
- Unable to add another account, Error message (”You exceeded the quota for accounts in your organisation”)
- Troubleshooting: I checked Service Quotas and requested a limit increase.
- Their response was “ it was restricted to only one account to avoid the misuse of the account since it was still a fresh account.

![AWS Organization Creation](images/aws-organization-creation.png)


### Phase 3: Create Permission Sets  

Permission Sets created in IAM Identity Centre:

Group Permission Set
Admin-Team- Admin-permission
DevOps-Team- PowerUser-permission
Developer-Team- DataScientist-permission

Review: Permission sets ensure users have access only to what is needed for their role.

![AWS IAM Permission](images/aws_iam_permission.png)



### Phase 4: Create 3 Groups (Admin, DevOps and Developer)

Step 1: 3 groups were created from the IAM Identity Centre

**REVIEW:**  The groups were created in all AWS accounts in the organisation.

![IAM Group Creation](images/iam_group_creation.png)


### Phase 5: Create Users on the IAM Identity

Step 1: On the IAM Identity Centre,  users were added, using their email to send password instructions

Step 2: MFA enabled for each user

Step 3: The group was assigned to each user in both AWS environments

Step 4: Each user has access to both AWS environments but is limited to the permission set assigned to their group.

**REVIEW:** Five users were added, and their various groups were assigned to them. Their functionality in the organisation was dependent on the set-permission policies given to the groups they are in.

![IAM User Creation](images/iam_user.png)


### Phase 6: SSO Switch

On the single Sign-on account, the users could switch between both AWS accounts in the organisation with ease; the user was automatically logged out from the previous environment each time there was a switch.

**REVIEW:** This step was tested for each user to see their ease of transition on accounts within the organisation. Their different functionality in the accounts was tested, and they were restricted based on the permission set policies issued to their group. Only the users in the Admin group were unrestricted. This is because the permission set policy given to them allowed them access to everything in the accounts.


### Observation

During the task, I identified a limitation within the AWS Organisation, where it was not possible to create more than two AWS accounts. This constraint affected my ability to scale the setup as initially planned.

### Summary

The project involved setting up an AWS Organisation with a Management account and attempting to add Development, Staging, and Production accounts. IAM Identity Centre was used to manage access for 5 users grouped into Admin, DevOps, and Developer roles. Custom permission sets were created and assigned to these groups. Users were onboarded via IAM Identity Centre, and MFA was enabled. A quota issue restricted the creation of more than one additional AWS account. Role-switching via the SSO portal was tested and resulted in automatic logout upon change. Overall, the setup was completed successfully despite AWS account limitations.











