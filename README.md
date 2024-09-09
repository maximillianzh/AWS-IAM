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


