---
title: Product Permissions
description: Reference list of the Experience Platform permissions that control access to Marketo Optimizer features, with descriptions and recommended permissions for admin, all-access, and read-only users.
autotag-review: '2026-10-20T17:03:48.312Z'
TQID: 'https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Product permissions

The following permissions control access to features in [!DNL Adobe Marketo Optimizer]. Add them to roles in the _[!UICONTROL Permissions]_ area of [!DNL Adobe Experience Platform]. For detailed information about creating roles and assigning them to users, see [_User access and permissions_](./user-management.md).

The last three columns show the permissions that are recommended for each of the [suggested user types](#suggested-user-types): Admin, All Access User, and Read Only Access User. A check mark (✔) means that the permission is recommended for that user type, and a dash (–) means that it is not. Adjust the recommendations to fit your organization.

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] access requires that you enable a specific sandbox that is provisioned using the following naming convention: `Mktoaep` + [!DNL Marketo Engage] subscription prefix. For example, if your linked [!DNL Marketo Engage] subscription prefix is _AcmeAssoc_, the sandbox required for [!DNL Marketo Optimizer] access is _MktoaepAcmeAssoc_. Add this sandbox to every role.

>[!NOTE]
>
>You must be a system administrator to see the _[!UICONTROL Permissions]_ tile in Experience Platform.

Some permissions apply to features that are not yet available in the product. Administrators can add these permissions now so that users have the applicable access when the features become available.

## Suggested user types {#suggested-user-types}

Use the permission recommendations in the tables on this page as a starting point for the roles that you create. These are suggestions for each type of user. Adjust them to fit your organization.

| Attribute | Admin | All Access User | Read Only Access User |
| --- | ----- | --------------- | --------------------- |
| **Who it is for** | People who set up and manage [!DNL Marketo Optimizer] for your team. | Marketers and operators who work in [!DNL Marketo Optimizer] every day. | People who need to see [!DNL Marketo Optimizer] but not change anything, such as executives, analysts, and auditors. |
| **What they can do** | Everything, including setup and admin settings. | Use every feature: journeys, programs, content, lists, reports, and the assistant. | View journeys, programs, content, lists, and reports, and ask the assistant questions. |
| **Permissions to assign** | Every permission on this page (select **[!UICONTROL Add all]** in the role editor). | The permissions with a ✔ in the _All Access_ column of the tables on this page. | The permissions with a ✔ in the _Read Only_ column of the tables on this page. |
| **Not included** | – | <li>Admin and channel settings<li>Email settings and WhatsApp presets<li>Data usage labels<li>Creating or changing program types and traffic control<li>Creating destinations, sources, and profile settings | <li>Creating, editing, publishing, or exporting<li>Activating audiences to destinations<li>Admin, channel, and email settings<li>Managing destinations, sources, and profile settings |
| **Suggested user group** | Marketo Optimizer Administrators Group | Marketo Optimizer Users Group | Marketo Optimizer Read Only Users Group |
| **Suggested role** | Marketo Optimizer Administrator | Marketo Optimizer All Access User | Marketo Optimizer Read Only Access User |

For the procedure to create these groups and roles, see [Create user groups and roles for suggested user types](./user-management.md#create-suggested-roles).

## Content and assets {#content-assets}

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Assets | Manage B2B Assets | Create, edit, and delete asset files. | ✔ | ✔ | – |
| | Manage B2B Emails | Create, edit, and delete email messages. | ✔ | ✔ | – |
| | Manage B2B Forms | Create, edit, and delete forms. | ✔ | ✔ | – |
| | Manage B2B Fragments | Create, edit, and delete content fragments. | ✔ | ✔ | – |
| | Manage B2B Landing Page | Create, edit, and delete landing pages. | ✔ | ✔ | – |
| | Manage B2B Message Export | Export message reports under the _Email_ section. | ✔ | ✔ | – |
| | Manage B2B Templates | Create, edit, and delete content templates. | ✔ | ✔ | – |
| | Manage B2B Webinars | Create, edit, and delete interactive webinars. | ✔ | ✔ | – |
| | Publish B2B Forms | Publish forms for use in landing pages. | ✔ | ✔ | – |
| | Publish B2B Fragments | Publish content fragments for use in templates, emails, and landing pages. | ✔ | ✔ | – |
| | Publish B2B Landing Page | Publish landing pages. | ✔ | ✔ | – |
| | View B2B Assets | View the Assets library and asset file details. | ✔ | ✔ | ✔ |
| | View B2B Emails | View email messages. | ✔ | ✔ | ✔ |
| | View B2B Forms | View forms. | ✔ | ✔ | ✔ |
| | View B2B Fragments | View content fragments list and details. | ✔ | ✔ | ✔ |
| | View B2B Landing Page | View landing pages. | ✔ | ✔ | ✔ |
| | View B2B Templates | View content templates list and details. | ✔ | ✔ | ✔ |
| | View B2B Webinars | View interactive webinars. | ✔ | ✔ | ✔ |

## Channel configuration and administration {#channels-admin}

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Admin Configurations | Manage B2B Admin Configurations | Configure administration settings, such as digital asset management connections, asset repositories, and events. | ✔ | – | – |
| B2B Channel Configurations | Manage B2B Channels Configurations | Access to the _Channels_ menu item in the left navigation and all channel configuration operations. | ✔ | – | – |
| | Manage B2B Email Settings | Configure email settings. These settings are required before users can send emails. | ✔ | – | – |
| | Manage B2B Forms Preset | Create, edit, and delete form presets. | ✔ | – | – |
| | Manage B2B Landing Page Settings | Configure landing page settings, such as subdomains. | ✔ | – | – |
| | Manage B2B WhatsApp Presets | Create, view, and delete WhatsApp message presets and associated SMS settings. | ✔ | – | – |
| | Manage B2B WhatsApp Settings | Configure WhatsApp channel settings. | ✔ | – | – |
| | Publish B2B Forms Preset | Publish form presets. | ✔ | – | – |
| | View B2B Email Settings | View email settings (subdomains, PTR records, IP pools, suppression lists, seed lists, IP warm-up plans). | ✔ | – | – |
| | View B2B Forms Preset | View form presets. | ✔ | – | – |

## Journeys, programs, and folders {#journeys-programs}

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Folder Tokens | Manage B2B Folder Tokens | Create, edit, and delete tokens on folders. Changes apply to everything in the folder, so assign this separately from _Manage B2B Folders_. | ✔ | ✔ | – |
| | View B2B Folder Tokens | View tokens defined on folders. | ✔ | ✔ | ✔ |
| B2B Folders | Manage B2B Folders | Create, edit, and delete folders. | ✔ | ✔ | – |
| | View B2B Folders | View folders. | ✔ | ✔ | ✔ |
| B2B Journeys | Manage B2B Journey Traffic Control | Configure journey traffic control, including simulating its effect. | ✔ | ✔ | – |
| | Manage B2B Person Journeys | Access to the _Person Journeys_ list and all person journey operations. | ✔ | ✔ | – |
| | Publish B2B Person Journeys | Publish person journeys. | ✔ | ✔ | – |
| | View B2B Journey Traffic Control | View journey traffic control settings. | ✔ | ✔ | ✔ |
| | View B2B Person Journey Reports | View person journey reports, including the _Person Journey Individual_ report. | ✔ | ✔ | ✔ |
| | View B2B Person Journeys | Read-only access to the _Person Journeys_ list and journey details. | ✔ | ✔ | ✔ |
| B2B Program Tokens | Manage B2B Program Tokens | Create, edit, and delete tokens on programs and program types. | ✔ | ✔ | – |
| | View B2B Program Tokens | View tokens defined on programs and program types. | ✔ | ✔ | ✔ |
| B2B Program Types | Manage B2B Program Types | Create, edit, and delete marketing program types. | ✔ | – | – |
| | View B2B Program Types | View marketing program types. | ✔ | – | – |
| B2B Programs | Manage B2B Programs | Create, edit, and delete marketing programs. | ✔ | ✔ | – |
| | View B2B Programs | View marketing programs. | ✔ | ✔ | ✔ |

## Audiences, intent, and destinations {#audiences-intent}

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Destinations | Activate B2B Destinations | Activate audiences to B2B destinations. | ✔ | ✔ | – |
| | Manage B2B Destinations | Create, edit, and delete B2B destinations. | ✔ | ✔ | – |
| | View B2B Destinations | View-only access to B2B destinations. | ✔ | ✔ | ✔ |
| B2B Intent Configuration | Manage B2B Intent Configuration | Create, edit, and delete intent configurations. | ✔ | ✔ | – |
| | View B2B Intent Configuration | View intent configurations (intent weighting models). | ✔ | ✔ | ✔ |
| B2B Organization Rules | Manage B2B Organization Rules | Create, edit, and delete organization rules. | ✔ | ✔ | – |
| | View B2B Organization Rules | View organization rules. | ✔ | ✔ | ✔ |
| B2B Person Lists | Manage B2B Person Lists | Create, edit, and delete person lists, and manage list membership. | ✔ | ✔ | – |
| | View B2B Person Lists | View static and dynamic person lists. | ✔ | ✔ | ✔ |

## Reports, Labs, and chat {#reports-labs-chat}

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Conversational Experience | Manage B2B Conversational Experience | Access to the chat panel and the assistant. Actions in the panel also require the matching feature permission. For example, creating a journey requires _Manage B2B Person Journeys_. See [Chat permissions](#chat-permissions). | ✔ | ✔ | ✔ |
| B2B Labs | Manage B2B Labs | Enable and configure Labs features. | ✔ | ✔ | – |
| | View B2B Labs | View the Labs features that are available and enabled. | ✔ | ✔ | ✔ |
| B2B Reporting | View B2B Embedded Reports | View the reports in the _Reports_ tab. | ✔ | ✔ | ✔ |
| | View B2B Intent Reports | View intent reports. | ✔ | ✔ | ✔ |

## Chat permissions {#chat-permissions}

Chat permissions follow feature-level permissions. _Manage B2B Conversational Experience_ gives access to the [!DNL CX Coworker] chat panel, but it does not grant access to any feature functions. Coworker checks every skill or action in chat against the same permission that the feature needs outside chat: _Manage_ permissions to create, edit, or publish, and _View_ permissions for read-only skills. If a user lacks the feature permission, [!DNL Coworker] cannot perform that action for them. For example, creating a journey requires _Manage B2B Person Journeys_, and listing forms requires _View B2B Forms_.

## External destinations permissions {#external-destinations-permissions}

To provide access to external destinations for users in [!DNL Marketo Optimizer], the following permissions are required. The columns follow the same recommendations for each user type described in [Suggested user types](#suggested-user-types).

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Dashboards | Manage Standard Dashboards | Add custom attributes that are not yet in the data warehouse. | ✔ | ✔ | – |
| | View Standard Dashboards | View-only access to the _Profiles_, _Destinations_, and _Segments_ dashboards. Also enables access to _Dashboards_ in the left navigation. | ✔ | ✔ | ✔ |
| Destinations | Activate Destinations | Activate data to active destinations. _View Destinations_ or _Manage Destinations_ is also required. | ✔ | ✔ | – |
| | Activate Segment without Mapping | Activate audiences to existing destinations without the mapping step. Users can add and remove audiences in activation workflows, but cannot add or remove mapped attributes or identities. _View Destinations_ is also required. | ✔ | ✔ | – |
| | Destination Authoring | Author destinations using the Experience Platform Destination SDK. | ✔ | ✔ | – |
| | Manage and Activate Dataset Destination | View, create, edit, and disable dataset export flows, and activate data to datasets. _View Destinations_ is also required. | ✔ | ✔ | – |
| | Manage Destinations | View, create, and delete destinations connections and destination accounts. | ✔ | ✔ | – |
| | View Destinations | View available destinations in the _Catalog_ tab and authenticated destinations in the _Browse_ tab. | ✔ | ✔ | ✔ |
| Data Governance | Manage B2B Delete Usage Labels | View, create, and delete data usage labels (DULE) applied to datasets and schemas. | ✔ | ✔ | – |
| | Manage Data Usage Policies | View, create, edit, and delete data usage policies. | ✔ | ✔ | – |
| | View Data Usage Policies | View-only access for data usage policies belonging to your organization. | ✔ | ✔ | ✔ |
| Data Ingestion | Manage Sources | View, create, edit, and disable sources. | ✔ | ✔ | – |
| | View Sources | View available sources in the _Catalog_ tab and authenticated sources in the _Browse_ tab. | ✔ | ✔ | ✔ |
| Profile Management | Manage Profile Settings | View and edit all profile settings. | ✔ | ✔ | – |
| | View Profile Settings | View-only access to all profile settings. | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
