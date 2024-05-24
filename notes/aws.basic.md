---
id: tge3eghupr1y27orwzsmgkl
title: Basic
desc: ''
updated: 1716336271780
created: 1716124356713
---
# Cue
1. where to see account alias?
2. where to see account ID
3. how to reset password for a user as root?
4. how can you get a email when free tier alert is triggered?
5. how can you set MFA for root user?

<hr />

# Login

## Account Alias & Account ID
/IAM/Dashboard<br >
see AWS Account 

## Reset login password
Only root user can reset password.<br />
To reset;
1. go to IAM
2. click Users on the left nav
3. click user's name
4. click Security credentials tab
5. click Manage console access
6. reset password

# Setting up
## MFA
Setup MFA in IAM.
root user's MFA can be set by going My security credentials link on the IAM top page.

### User
1. Go to IAM/Users
2. click user's name
3. click security credentials tab
4. click Assign MFA device

### Root
1. Go to IAM
2. Click My security credentials in Quick Links card
3. click Assign MFA device

## Billing alert
Setup billing preference to get emails when alert happens or invoice is ready.

1. Go to Account from top right pull down on the header
2. Click Billing Preferences under Preferences and Settings section on the left nav
3. Edit Billing preferences

# Remote Access
## CloudShell
Go to aws console and find cloudShell

## AWS CLI