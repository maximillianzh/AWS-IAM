# AWS-IAM Project Overview
I used AWS IAM to create users, set up an account alias, and define permissions through IAM policies to manage access to EC2 instances.

## What is AWS IAM?

AWS IAM (Identity and Access Management) manages user permissions and access to AWS resources. It is crucial for securing resources by controlling who can access what, ensuring only authorized users have the necessary permissions.

## How I'm Using AWS IAM in This Project

In this project, AWS IAM was utilized to:

- Create users
- Set up an account alias
- Define permissions through IAM policies

These steps help manage access to EC2 instances and ensure proper authorization.

## One Thing I Didn't Expect...

I was surprised by how straightforward it was to set up AWS IAM. The AWS IAM interface and JSON policy editor simplified creating and managing permissions, streamlining the process and reducing complexity.

# Tags

Tags are key-value pairs assigned to AWS resources. They are useful for organizing, managing, and searching resources, as well as for tracking costs and applying policies based on specific criteria.

The tag I’ve used on my EC2 instances is called `Env`. The values assigned are `development` and `production`.
![Screenshot 2024-09-08 at 7 45 50 PM](https://github.com/user-attachments/assets/987abe01-6b31-48bc-9ae6-7bed98ea4b24)

# IAM Policies

IAM Policies are documents that define permissions for actions on AWS resources, specifying what actions are allowed or denied, on which resources, and under what conditions.

## The Policy I Set Up

For this project, I’ve set up a policy using JSON.

### Policy Details

The policy created:

1. Allows all EC2 actions on resources tagged with `Env: development`.
2. Allows all EC2 describe actions.
3. Denies the ability to create or delete tags on any EC2 resources.

## JSON Policy Structure

When creating a JSON policy, you need to define its `Effect`, `Action`, and `Resource`:

- **Effect**: Specifies whether the policy allows or denies access.
- **Action**: Lists the specific operations the policy permits or denies.
- **Resource**: Indicates the AWS resources the policy applies to.

## My JSON Policy
![iampolicy](https://github.com/user-attachments/assets/3f8c6c61-4807-4009-ba7d-cad03c353a19)

# Account Alias

An account alias is a custom name you assign to your AWS account, replacing the default numeric ID in the sign-in URL and making it easier to remember and identify your account.

Creating an account alias took me less than 5 minutes.

Now, my new AWS console sign-in URL is: [https://iam-alias-maxzhulenev.signin.aws.amazon.com/console](https://iam-alias-maxzhulenev.signin.aws.amazon.com/console)

![iamalias](https://github.com/user-attachments/assets/b6472010-a4bd-42b2-833b-91577c84a4f9)

# IAM Users and User Groups

## Users

IAM users are individuals or applications that have their own credentials and permissions within an AWS account, allowing them to access and manage AWS resources based on the policies assigned to them.

## User Groups

IAM user groups are collections of IAM users that share the same permissions. Assigning permissions to a group allows all its members to inherit those permissions, simplifying management and access control.

I attached the policy I created to this user group, which means all users in the group will inherit the permissions defined in the policy, enabling them to perform actions as specified.

Here's the updated `README.md` section:

# Logging in as an IAM User

The two primary ways to log in as an IAM user in AWS are:

1. **Using the IAM User Sign-In URL**: Access your AWS account through the specific URL provided by AWS, which includes your account ID and IAM user credentials.

2. **Using the AWS Management Console**: Enter your IAM user credentials (username and password) directly on the AWS Management Console login page, after selecting the IAM user sign-in option.

Once logged in as an IAM user, I noticed restrictions on my access, limiting the actions and resources I could view and manage compared to the root account.
![iamalias](https://github.com/user-attachments/assets/7fc64209-74f2-459b-9af1-2ebe2d42b235)

# Testing IAM Policies

I tested my JSON IAM policy by attempting to stop two EC2 instances.

## Stopping the Production Instance

When I tried to stop the production instance, the operation failed due to insufficient permissions. I need to update my IAM policies to authorize the `ec2:StopInstances` action.

![iamfailedstop1](https://github.com/user-attachments/assets/2cadd79e-c341-4756-bfd2-e58ea31fc82e)


# Testing IAM Policies

## Stopping the Production Instance

When I tried to stop the production instance, the operation failed due to insufficient permissions. I need to update my IAM policies to authorize the `ec2:StopInstances` action.

## Stopping the Development Instance

When I tried to stop the development instance, I successfully initiated the stop process. The instance is now fully stopped with no issues.

![iamstopeed](https://github.com/user-attachments/assets/284fdb32-6e9d-43f4-a7d9-dbba33a702f5)

Here’s the conclusion formatted for Markdown (.md):

### Conclusion

In this AWS IAM project, I effectively leveraged AWS IAM to enhance access management and security for EC2 instances. By creating users, setting up a custom account alias, and defining detailed IAM policies, I ensured secure and organized access control.

**Key Achievements**:
- **Account Alias**: Simplified sign-in with a custom URL, improving account manageability.
- **IAM Policies**: Created policies to regulate access based on resource tags and actions, enhancing control over EC2 instances.
- **Tagging**: Implemented tags to better organize and manage resources, facilitating cost tracking and policy application.
- **Testing**: Validated policy effectiveness by successfully managing instance operations according to permissions, identifying areas for policy improvement.

The project demonstrated how straightforward IAM configuration can be, while also highlighting the importance of precise policy definitions for optimal security and operational efficiency.



