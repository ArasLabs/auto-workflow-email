# Automatic Workflow Emails

The Automatic Workflow Email project demonstrates automatic workflow email notifications.

#### How it works
Two email items are attached as OnActivate notifications to All Assignments. The simple email uses the string "${Item/item_number}" to show the controlled item's number property in the body of the email. The other email uses a query string to get properties of both the activity and the controlled item.

## History

Release | Notes
--------|--------
[v1.1.1](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.1.1) | Updated Usage for v12                                        
[v1.1.0](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.1.0) | Updated Tags for TOC List 
[v1.0.1](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.0.1) | Tested 11.0 SP12, SP15. Tested on Edge, Firefox 60 ESR, Chrome.
[v1.0.0](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.0.0) | First release. Tested on Internet Explorer 11, Firefox 38 ESR, Chrome. Though built and tested using Aras 11.0 SP7, this project should function in older releases of Aras 11.0 and Aras 10.0.

#### Supported Aras Versions

Project | Aras
--------|------
[v1.1.1](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.1.1) | 10.0+, 11.0+, 12.0+ 
[v1.1.0](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.1.0) | 10.0+, 11.0+ 
[v1.0.1](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.0.1) | 10.0 SPx, 11.0 SP7+, 11.0 SP12+, 11.0 SP15
[v1.0.0](https://github.com/ArasLabs/auto-workflow-branching/releases/tag/v1.0.0) | 10.0 SPx, 11.0 SP7; Old Community Board Migration

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (current released version preferred)
2. Aras Package Import tool
3. AutoWorkflowEmail import package
4. The Innovator Admin user's email is set to your email address.
5. Aras is configured to send emails, meaning one of the following scenarios:
  * The mail server is configured in `InnovatorServerConfig.xml`:
  ```xml
  <Mail SMTPServer="[SMTP Server IP]"/>
  ```
  * Email debugging is enabled in `InnovatorServerConfig.xml`:
  ```xml
  <operating_parameter key="email_debug_option" value="file"/>
  ```

> Note: If email debugging is enabled in InnovatorServerConfig.xml, all emails will be saved as files in the temp folder (Innovator\Server\temp by default). No emails will be sent to the user's actual email address.

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\AutoWorkflowEmail\Import\imports.mf` file in the Manifest File field.
6. Select **aras.labs.WorkflowAutomationExamples** and **aras.labs.AutoWorkflowEmail** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

You are now ready to login to Aras and try out Automatic Workflow Email notifications.

## Usage

1. Log in to Aras as admin.
2. Navigate to **Workflow Examples** in the table of contents (TOC).
3. Create a new Workflow Email Example item.
4. Click **Done.**  (**Save/Unlock/Close** v11)
5. Navigate to **My Innovator > My Inbasket** in the TOC.
6. Search for the newly created assignment.

If you configured the SMTP server for your Aras instance, you can check your inbox to confirm whether the notification email was sent. If you enabled email debugging instead, check the temp folder. Any email notifications created by Aras will be saved as in the temp folder as text files.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## Credits

Original Aras community project written by Rob McAveney at Aras Corp.

Project rewritten for Aras 11.0 by Alexander Sklyarskiy. @asklyarskiy

Documented and published by Eli Donahue at Aras Labs. @elijdonahue

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
