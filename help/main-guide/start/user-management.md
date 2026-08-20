---
title: User Access and Permissions
description: 'Manage user access in the Adobe Admin Console: create user groups, assign product profiles, and set role-based permissions for Marketo Optimizer.'
---
# User access and permissions

After provisioning is complete and sandboxes are bound, complete the following steps to provide [!DNL Marketo Optimizer] access for your team and users.

1. [Create a [!DNL Journey Optimizer B2B Edition] product profile](#create-profile) in the Admin Console (one-time/initial setup only).
1. [Add a user group](#add-user-group) in the Admin Console.
1. [Assign the product profile](#assign-profile) to the user group in the Admin Console.
1. [Add users to the new group](#add-users) in the Admin Console.
1. [Edit built-in roles](#edit-role-permissions) or [create a custom role](#create-a-custom-role) with [!DNL Journey Optimizer B2B Edition] permissions in Adobe Experience Platform.
1. [Add users](#add-users-to-a-role) or [groups](#add-user-groups-to-a-role) to roles in Adobe Experience Platform.

## Configure the product profile {#config-profile}

As an administrator, you can complete these tasks in the Adobe Admin Console, which is a central place to administer and manage your Adobe product licenses and users. In the Admin Console, you can create and manage users in a single location instead of within your various individual solutions. To learn more about its functions and capabilities, refer to the [Admin Console overview](https://helpx.adobe.com/business/enterprise/plan-your-deployment/basic-concepts/admin-console.html) page.

### Access the Admin Console {#admin-console}

Before you can use the Admin Console to administer users within your team, you need to ensure that you can access the Admin Console and have the appropriate permissions.

1. As a system administrator, you should receive multiple emails from Adobe as part of the onboarding process.

   Locate the welcome email that provides the information about the organization name to which you have been granted access.

1. Click the **[!UICONTROL Get started]** link in your welcome email to navigate to the Admin Console. 

   If you cannot find the email, open a browser directly to the Admin Console at [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Log in using your Adobe ID.

   Upon successful login, you see the _Overview_ page of the Adobe Admin Console.

1. If you have access to multiple organizations, ensure that you have logged in to the correct organization.

   To change your organization, click the organization name from the top right corner and choose the organization to which you need access.

1. Select **[!UICONTROL Administrators]** from the _[!UICONTROL Users]_ card to verify that you are a system administrator.

   ![Admin Console overview - click Administrators](./assets/admin-console-overview-administrators.png){width="800" zoomable="yes"}

1. Search by entering your Adobe ID email, username, first, or last name.

   * If your access is correctly configured, the search returns your record. 

   * If the value in the **[!UICONTROL ADMIN ROLE]** column shows `System`, you know that you (or the displayed user) are a system administrator.

### Create the [!DNL Journey Optimizer B2B Edition] product profile {#create-profile}

When granting users access to an Adobe solution, you do not necessarily want to give them full access. Product profiles enable each solution to have its own set of user permissions. Use the Admin Console to assign product profiles.

For more information about using product profiles for user entitlements, see [_Manage product profiles for enterprise users_](https://helpx.adobe.com/business/enterprise/manage-products-and-entitlements/manage-products-and-product-profiles/manage-product-profiles.html){target="_blank"} in the Admin Console documentation.

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or [!DNL Experience Platform] product administrator can perform the following steps from [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Select the **[!UICONTROL Products]** tab.

1. Open the [!DNL Journey Optimizer B2B Edition] instance where you want to add the profile and click **[!UICONTROL New profile]**.

   ![Experience Platform - product profiles for user group](./assets/admin-console-product-profiles.png){width="600" zoomable="yes"}    

1. Enter a product profile name, such as _B2B Users_.

1. Click **[!UICONTROL Next]** and then **[!UICONTROL Save]**.

### Add a user group {#add-user-group}

A user group is a collection of users who are granted a shared set of permissions. You can add or remove users in your user group. The group permissions remain the same while the users within the group change.

For more information about how user groups are used to manage permissions, see [Manage user groups](https://helpx.adobe.com/business/enterprise/manage-users/user-groups.html){target="_blank"} in the Admin Console documentation.

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator can perform the following steps from [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Select the **[!UICONTROL Users]** tab.

1. Choose **[!UICONTROL User Groups]** in the left navigation.

1. Click **[!UICONTROL New user group]** at the top right.

1. Enter a name for the user group, such as _B2B users_ and click **[!UICONTROL Save]**.

   ![Admin console - add user group](./assets/admin-console-new-user-group.png){width="600" zoomable="yes"} 

### Assign the product profile {#assign-profile}

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A product administrator can perform the following steps from [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Click the user group that you created.

1. Select the **[!UICONTROL Assigned product profiles]** tab and click **[!UICONTROL Assign profile]**.

1. Click **+** and add each instance of the following products:

   * [!UICONTROL Adobe Journey Optimizer B2B Edition - Users Profile]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform Data Collection - Default Data Collection All Access]
   * [!UICONTROL Adobe Experience Platform - Default Production All Access]

   ![Admin console - product profiles for user group](./assets/admin-console-product-profiles.png){width="600" zoomable="yes"}   

1. Click **[!UICONTROL Save]**.

### Add users to the new group {#add-users}

For information about user management, see [_Adobe Admin Console users_](https://helpx.adobe.com/business/enterprise/manage-users/users.html){target="_blank"} in the Admin Console documentation.

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or product administrator can perform the following steps from [https://adminconsole.adobe.com](https://adminconsole.adobe.com). A product administrator can add only users that already exist in their organization.

1. If the users are not already members of your organization, add each user:

   * Under _[!UICONTROL Quick links]_, click **[!UICONTROL Add users]**.

   * Enter the user's email address and click **[!UICONTROL Add as new user]**.

      ![Admin console - add user profile for the new group](./assets/admin-console-user-group-add-users.png){width="600" zoomable="yes"}
   
   * Enter the first and last name, then click **[!UICONTROL Save]**.

1. Add each user to the group:

   * Click the user name.

   * In the user details page, scroll to **[!UICONTROL User groups]**.
   
   * Click the _More_ ( **...** ) icon on the left and choose **[!UICONTROL Edit user groups]**.

   * Click the _Add_ ( **+** ) icon below **[!UICONTROL User groups]**.

      ![Admin console - select user group for user](./assets/admin-console-user-edit-user-groups.png){width="600" zoomable="yes"}

   * Select the user group that you created previously and click **[!UICONTROL Apply]**.

   * Click **[!UICONTROL Save]** for the user changes.

## Assign product permissions {#assign-product-permissions}

Permissions are unitary rights that allow you to define the authorizations assigned to a product profile. Each permission is grouped under a capability, such as person journeys or content, representing functionalities in [!DNL Marketo Optimizer].

The _Permissions_ area of Adobe Experience Platform is where administrators can define user roles and access policies to manage access permissions for features and objects within a product application. In this app, you can create and manage roles, as well as assign the desired resource permissions for these roles. Permissions also allow you to manage the sandboxes and users associated with a specific role.

For more information about role permissions in Experience Platform, see [Manage permissions for a role](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"} in the Experience Platform documentation.

1. Go to [experience.adobe.com](https://experience.adobe.com/).

1. In the _[!UICONTROL Quick access]_ panel, select **[!UICONTROL Permissions]**.

   >[!NOTE]
   >
   >If you don't see _[!UICONTROL Permissions]_, you may need to click **[!UICONTROL View all]** and select it from the available applications.

   ![Experience Platform - access Permissions](./assets/aep-permissions.png){width="700" zoomable="yes"}

### Permissions {#permissions}

The following permissions control access to channel configuration, content management, and person journey features in [!DNL Marketo Optimizer]:

| Category | Permission | Description |
| -------- | ----------- | ---------- |
| B2B Channel Configurations | View B2B Email Settings | View email settings (subdomains, PTR records, IP pools, suppression lists, seed lists, IP warm-up plans). |
| | Manage B2B Email Settings | Configure email settings (subdomains, PTR records, IP pools, suppression lists, seed lists, IP warm-up plans). These settings are required before users can send emails.|
| | Manage B2B Channels Configurations | Access to the _Channels_ menu item in the left navigation and all channel configuration operations. |
| | Manage B2B WhatsApp Presets | Create, view, and delete WhatsApp message presets and associated SMS settings. |
| B2B Journeys | Manage B2B Person Journeys | Access to the _Person Journeys_ list and all person journey operations. |
| B2B Assets | View content templates | View content templates list and details. |
| | Manage B2B Templates | Create, edit, and delete content templates. |
| | View B2B Fragments | View content fragments list and details. |
| | Manage B2B Fragments | Create, edit, and delete content fragments. |
| | Publish B2B Fragments | Publish content fragments for use in templates, emails, and landing pages. |
| | View B2B Assets | View the Assets library and asset file details. |
| | Manage B2B Assets | Create, edit, and delete asset files. |
| | View B2B Emails | View email messages. |
| | Manage B2B Emails | Create, edit, and delete email messages. |
| | Manage B2B Message Export | Export message reports under the Email section. |
| Journey Optimizer Library | Manage B2B Library Items | Add and delete saved expressions in the library. |
| Data Governance | Manage B2B Delete Usage Labels | View, create, and delete data usage labels (DULE) applied to datasets and schemas. |
| Sandbox Administration | Manage B2B Packages | Create, export, import, copy, and delete sandbox packages. |

To provide support for external destinations in [!DNL Marketo Optimizer], the following permissions are required:

| Category | Permission | Description |
| -------- | ----------- | ---------- |
| Dashboards | View Standard Dashboards | View-only access to the _Profiles_, _Destinations_, and _Segments_ dashboards. Also enables access to _Dashboards_ in the left navigation and the _Dashboards_ inventory and integrations tab. |
| | Manage Standard Dashboards | Add custom attributes that are not yet in the data warehouse. |
| Destinations | View Destinations | View-only access to view available destinations in the _Catalog_ tab and authenticated destinations in the _Browse_ tab. |
| | Manage Destinations | View, create, and delete destinations connections and destination accounts. |
| | Activate Destinations | Activate data to active destinations. Either _View Destinations_ or _Manage Destinations_ is also required to access this function. |
| | Activate Segment without Mapping | Activate audiences to existing destinations, without displaying the mapping step. Users can add and remove audiences in activation workflows, but cannot add or remove mapped attributes or identities. The _View Destinations_ permission is also required to access this function. |
| | Manage and Activate Dataset Destination | View, create, edit, and disable dataset export flows, as well as activate data to active datasets. The _View Destinations_ permission is also required to access this function. |
| | Destination Authoring | Ability to author destinations using the Adobe Experience Platform Destination SDK. |
| Data Governance | View Data Usage Policies | View-only access for data usage policies belonging to your organization. |
| | Manage Data Usage Policies | View, create, edit, and delete data usage policies. |
| Data Ingestion | View Sources | View-only access to available sources in the _Catalog_ tab and authenticated sources in the _Browse_ tab. |
| | Manage Sources | View, create, edit, and disable sources. |
| Profile Management | View Profile Settings | View-only access to all profile settings. |
| | Manage Profile Settings | View and edit all profile settings. |

<!--

### B2B built-in roles {#b2b-built-in-roles}

When your organization has [!DNL Journey Optimizer B2B Edition] provisioned, Experience Platform includes a set of built-in (default) roles that you can use to manage access to the product capabilities:

| Role | Permissions |
| ---- | ----------- |
| B2B Journey Manager | <li>Manage B2B Journeys <li>Manage B2B Buying Groups <li>Manage B2B Account Lists <li>View B2B Engagement Dashboard <li>View B2B Insights Dashboard |
| B2B Channel Manager | <li>Manage B2B Assets <li>Manage B2B Templates <li>Manage B2B Fragments |
| B2B System Administrator | <li>Manage B2B Channels Configurations <li>Manage B2B Admin Configurations |
| B2B Sales User | <li>View B2B Engagement Dashboard <li>View B2B Buying Groups <li>Access In-CRM Insights |

-->

### Edit role permissions {#edit-role-permissions}

For built-in or custom roles, you can decide at any time to add or delete permissions. If you modify a default or custom role, it impacts every user assigned to the role.

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] access requires that you enable a specific sandbox that is provisioned using the following naming convention: Marketo Engage subscription prefix + Prime. For example, if your linked Marketo Engage subscription prefix is _AcmeAssoc_, the sandbox required for [!DNL Marketo Optimizer] access is _AcmeAssocPrime_.

>[!NOTE]
>
>An Admin Console system administrator can perform these steps.

_To change the permissions for a role:_

1. Select **[!UICONTROL Roles]** in the left navigation.

1. Click the **_B2B Channel Manager_** role name.

1. In the details page, click **[!UICONTROL Edit]** at the top right.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-prime-edit.png){width="800" zoomable="yes"}

   In the role editor, the _[!UICONTROL Resources]_ menu displays the list of resources that apply to the Experience Cloud - Platform powered applications.

1. Select the sandbox provisioned for [!DNL Marketo Optimizer] access (`<Marketo subscription prefix>Prime`).

   ![Experience Platform - add sandboxes for the new role](./assets/aep-permissions-role-prime-sandbox.png){width="800" zoomable="yes"}
   
1. Click the _Add_ icon (**+**) for each of the B2B resources.

   ![Experience Platform - B2B Journeys resource added to Channel Manager role](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. Add the specific permissions for each of the resources, or select **[!UICONTROL Add all]**.

1. Click **[!UICONTROL Save]**.

   <!-- ![Experience Platform - B2B Journeys permissions saved for Channel Manager role](assets/aep-permissions-role-edit-b2b-journeys-done.png){width="700" zoomable="yes"} -->

1. Click **[!UICONTROL Close]** to return to the details page.

### Add users to a role {#add-users-to-a-role}

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or Experience Platform administrator can perform the following steps.

1. Open the role details and select the **[!UICONTROL Users]** tab.

   This tab displays a list of all users assigned to the role.

1. Click **[!UICONTROL Add users]**.

   ![Experience Platform - add users to the role](./assets/aep-permissions-role-prime-add-users.png){width="800" zoomable="yes"}

1. In the _[!UICONTROL Add users]_ dialog, locate and select the users that you want to add to the role.

   * You can use the Search tool to filter the list of users. 

   * Select the checkbox for each user.

   ![Experience Platform - Add users dialog](assets/aep-permissions-role-add-users-dialog.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Save]** when you have selected all the users that you want to add.

### Add user groups to a role {#add-user-groups-to-a-role}

For information about user management, see [_Adobe Admin Console users_](https://helpx.adobe.com/business/enterprise/manage-users/users.html){target="_blank"} in the Admin Console documentation.

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or Experience Platform administrator can perform the following steps.

1. Open the role details and select the **[!UICONTROL User groups]** tab.

   This tab displays a list of all user groups assigned to the role. 

1. Click **[!UICONTROL Add Groups]**.

   ![Experience Platform - add groups to the role](./assets/aep-permissions-role-prime-add-groups.png){width="800" zoomable="yes"}

1. In the _[!UICONTROL Add groups]_ dialog, locate and select the groups that you want to add to the role.

   * You can use the Search tool to filter the list of user groups. 

   * Select the checkbox for each user group.

   ![Experience Platform - Add groups dialog](assets/aep-permissions-role-add-groups-dialog.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Save]** when you have selected all the groups that you want to add.

### Create a custom role {#create-a-custom-role}

![Administrator role requirements](../assets/do-not-localize/icon-admin-user.svg){width="30"} A system administrator or Experience Platform administrator can perform the following steps.

1. Select **[!UICONTROL Roles]** in the left navigation and select **[!UICONTROL Create role]**.

1. In the _[!UICONTROL Create new role]_ dialog, enter a name for the role, such as _B2B Marketers_, and a description (optional).

1. Click **[!UICONTROL Confirm]**.

1. Select the sandbox provisioned for [!DNL Marketo Optimizer] access (`<Marketo subscription prefix>Prime`).

   ![Experience Platform - add sandboxes for the new role](./assets/aep-permissions-role-prime-sandbox.png){width="800" zoomable="yes"}

1. Add B2B product permissions:

   To determine which product capabilities you want for the role, refer to the list of [product permissions](#permissions).

   In the _[!UICONTROL Resources]_ list on the left, locate the B2B items and click the _Add_ (**+**) icon to add each attribute that you want to enable for the role.

   You can enter _B2B_ in the search tool to filter the list for many of the B2B product permissions.

   ![Experience Platform - B2B permissions](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}   

1. Click **[!UICONTROL Save]** at the top right.

1. Go to the role details and select the **[!UICONTROL User groups]** tab.

1. Click **[!UICONTROL Add Groups]**.

1. Select the checkbox next to the user group that you created previously in the Admin Console.

1. Click **[!UICONTROL Save]**.

Your custom role is configured and users in the assigned group can now access the [!DNL Marketo Optimizer] capabilities you selected.
