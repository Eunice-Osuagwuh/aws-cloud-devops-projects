AWS IAM Identity Centre and AWS Organisation Setup
Overview

This project demonstrates how to design and implement centralised identity and access management across multiple AWS environments using AWS Organizations and IAM Identity Centre (SSO). The setup follows AWS security best practices, including least privilege access, MFA enforcement, and role-based access control.

The goal was to simulate a real-world enterprise environment with separated accounts for Development, Staging, and Production, while managing users centrally through IAM Identity Centre.

Project Objectives

Create and configure an AWS Organisation

Set up a Management account as the root account

Create multiple environment accounts within the organisation

Configure IAM Identity Centre with multiple users

Group users by role (Admin, DevOps, Developer)

Create and assign permission sets based on job functions

Enable MFA for all users

Test Single Sign On (SSO) account switching and access restrictions

Tools and Services Used

AWS Management Console

AWS Organisations

AWS IAM Identity Centre (SSO)

IAM Permission Sets

Multi-Factor Authentication (MFA)

Separate email addresses for AWS accounts

Architecture Summary

Management Account: Root account used to manage the organisation

Environment Accounts:

Development

Staging

Production (planned but limited by AWS quota)

Identity Management: Centralised via IAM Identity Centre

Access Control: Role-based permission sets

Implementation Steps
Phase 1: Management Account Setup

Created a new AWS account using a dedicated email address

Signed in using the root user

Enabled MFA on the root account

Outcome:
This account served as the Management account for the AWS Organisation and followed AWS security best practices.

Phase 2: AWS Organisation Setup

Navigated to AWS Organizations from the Management account

Created environment accounts for Development and Staging

Selected All Features during organisation setup

Enabled MFA on all created accounts

Outcome:
The organisational structure was successfully created with centralised control from the Management account.

Issue Encountered and Resolution

Problem:
Account creation failed with the error:
“You have exceeded the quota for accounts in your organisation.”

Troubleshooting Steps:

Checked AWS Service Quotas

Submitted a quota increase request

AWS Response:
Account creation was temporarily restricted because the AWS account was newly created to prevent misuse.

Impact:
Production account creation could not be completed at this stage.

Phase 3: Permission Set Creation

The following permission sets were created in IAM Identity Centre:

Admin Permission

PowerUser Permission

SystemAdmin Permission

DataScientist Permission

Group to Permission Mapping
Group	Permission Set
Admin Team	Admin Permission
DevOps Team	PowerUser + SystemAdmin
Developer Team	DataScientist

Outcome:
Each group was granted access strictly aligned with their responsibilities, enforcing the principle of least privilege.

Phase 4: Group Creation

Created the following groups in IAM Identity Centre:

Admin

DevOps

Developer

Outcome:
Groups were available across all accounts in the organisation.

Phase 5: User Creation and Assignment

Created five users using email-based invitations

Enabled MFA for every user

Assigned users to their respective groups

Granted access to available AWS accounts via permission sets

Outcome:
Users could access multiple AWS accounts while remaining restricted to their assigned permissions.

Phase 6: Single Sign On (SSO) Testing

Users logged in via the IAM Identity Centre portal

Tested switching between AWS accounts

Verified automatic logout during account switching

Confirmed access restrictions based on group permissions

Outcome:
SSO worked as expected. Only Admin users had unrestricted access, while DevOps and Developer users were properly limited.

Observations

AWS enforces strict account creation limits on newly created organisations

IAM Identity Centre significantly simplifies user and permission management

Permission sets provide a clear separation of duties across teams

Centralised identity management improves security and operational efficiency

Key Takeaways

AWS Organisations enables scalable multi-account governance

IAM Identity Centre is essential for enterprise-grade access control

MFA and least privilege access are critical security practices

Quota limitations should be considered during early project planning

Project Status

✅ Completed with limitations due to AWS account quota restrictions

