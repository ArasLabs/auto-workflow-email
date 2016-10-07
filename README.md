# Automatic Workflow Branching

The Automatic Workflow Branching project demonstrates automatic workflow branching based on a property of the controlled item.

#### How it works
A method is attached to an automatic activity as an OnActivate server event.  When the workflow
is started, the automatic activity is activated and the method finds the controlled item.  It
then reads the Plant property, finds the corresponding path and sets that path to be the default.  
The activity then closes and the default path is followed.

## Project Details

**Built Using:** Aras 11.0 SP7
**Browsers Tested:** Internet Explorer 11, Firefox 38 ESR, Chrome

> Though built and tested using Aras 11.0 SP7, this project should function in older releases of Aras 11.0 and Aras 10.0.

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (version 11.0 SPx preferred)
2. Aras Package Import tool
3. AutoWorkflowBranching import package

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\AutoWorkflowBranching\Import\imports.mf` file in the Manifest File field.
6. Select **aras.labs.WorkflowAutomationExamples** and **aras.labs.AutoWorkflowBranching** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

You are now ready to login to Aras and try out Automatic Workflow Branching.

## Usage

1. Log in to Aras as admin.
2. Navigate to **Workflow Examples** in the table of contents (TOC).
3. Create a new Workflow Assignment Example item.
4. Set the Plant property to any of the listed values.
5. Click **Save/Unlock/Close**.
6. Navigate to **My Innovator > My Inbasket** in the TOC.
7. Search for the newly created assignment. The assignment activity should correspond to the chosen Plant on the Workflow Branching Example form.

To review the dynamically created assignment and the paths of the workflow process item, open the Work Item from the assignment. On the item form, select **Views > Workflow** from the main menu to view the workflow process.

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
