---
lab:
    title: '01 - Manage Azure Active Directory Identities'
    module: 'Module 01 - Identity'
---

# Lab 01 - Manage Azure Active Directory Identities

# Student lab manual

## Lab scenario

In order to allow Contoso users to authenticate by using Azure AD, you have been tasked with provisioning users and group accounts. Membership of the groups should be updated automatically based on the user job titles. You also need to create a test Azure AD tenant with a test user account and grant that account limited permissions to resources in the Contoso Azure subscription.

## Objectives

In this lab, you will:

+ Task 1: Create and configure Azure AD users
+ Task 2: Create Azure AD groups with assigned and dynamic membership
+ Task 3: Create an Azure Active Directory (AD) tenant
+ Task 4: Manage Azure AD guest users 

## Estimated timing: 30 minutes

## Instructions

### Exercise 1

#### Task 1: Create and configure Azure AD users

In this task, you will create and configure Azure AD users.

1. In the Azure portal, search for and select **Azure Active Directory**.

2. On the Azure Active Directory blade, scroll down to the **Manage** section, click **User settings**, and review available configuration options.

3. On the Azure Active Directory blade, in the **Manage** section, click **Users**, and then click your user account to display its **Profile** settings. 

4. Click **edit**, in the **Settings** section, set **Usage location** to **United States** and save the change.

    >**Note**: This is necessary in order to assign an Azure AD Premium P2 license to your user account later in this lab.

5. Navigate back to the **Users - All users** blade, and then click **+ New user**.

6. Create a new user with the following settings (leave others with their defaults):

    | Setting | Value |
    | --- | --- |
    | User name | **az104-01a-aaduser1** |
    | Name | **az104-01a-aaduser1** |
    | Let me create the password | enabled |
    | Initial password | **Pa55w.rd124** |
    | Usage location | **United States** |
    | Job title | **Cloud Administrator** |
    | Department | **IT** |

    >**Note**: **Copy to clipboard** the full **User Principal Name** (user name plus domain). You will need it later in this task.

7. In the list of users, click the newly created user account to display its blade.

8. Review the options available in the **Manage** section and note that you can identify the Azure AD roles assigned to the user account as well as the user account's permissions to Azure resources.

9. In the **Manage** section, click **Assigned roles**, then click **+ Add assignment** button and assign the **User administrator** role to **az104-01a-aaduser1**.

    >**Note**: You also have the option of assigning Azure AD roles when provisioning a new user.

10. Open an **InPrivate** browser window and sign in to the [Azure portal](https://portal.azure.com) using the newly created user account. When prompted to update the password, change the password for the user.

    >**Note**: Rather than typing the user name (including the domain name), you can paste the content of Clipboard.

11. In the **InPrivate** browser window, in the Azure portal, search for and select **Azure Active Directory**.

    >**Note**: While this user account can access the Azure Active Directory tenant, it does not have any access to Azure resources. This is expected, since such access would need to be granted explicitly by using Azure Role-Based Access Control. 

12. In the **InPrivate** browser window, on the Azure AD blade, scroll down to the **Manage** section, click **User settings**, and note that you do not have permissions to modify any configuration options.

13. In the **InPrivate** browser window, on the Azure AD blade, in the **Manage** section, click **Users**, and then click **+ New user**.

14. Create a new user with the following settings (leave others with their defaults):

    | Setting | Value |
    | --- | --- |
    | User name | **az104-01a-aaduser2** |
    | Name | **az104-01a-aaduser2** |
    | Let me create the password | enabled |
    | Initial password | **Pa55w.rd124** |
    | Usage location | **United States** |
    | Job title | **System Administrator** |
    | Department | **IT** |

15. Sign out as the az104-01a-aaduser1 user from the Azure portal and close the InPrivate browser window.

#### Task 2: Create Azure AD groups with assigned and dynamic membership

In this task, you will create Azure Active Directory groups with assigned and dynamic membership.

16. Back in the Azure portal where you are signed in with your user account, navigate back to the **Overview** blade of the Azure AD tenant and, in the **Manage** section, click **Licenses**.

    >**Note**: Azure AD Premium P1 or P2 licenses are required in order to implement dynamic groups.

17. In the **Manage** section, click **All products**.

18. Click **+ Try/Buy** and activate the free trial of Azure AD Premium P2.

19. Refresh the browser window to verify that the activation was successful. 

20. From the **Licenses - All products** blade, select the **Azure Active Directory Premium P2** entry, and assign all license options of Azure AD Premium P2 to your user account and the two newly created user accounts.

21. In the Azure portal, navigate back to the Azure AD tenant blade and click **Groups**.

22. Use the **+ New group** button to create a new group with the following settings:

    | Setting | Value |
    | --- | --- |
    | Group type | **Security** |
    | Group name | **IT Cloud Administrators** |
    | Group description | **Contoso IT cloud administrators** |
    | Membership type | **Dynamic User** |

    >**Note**: If the **Membership type** drop-down list is grayed out, refresh the browser page.

