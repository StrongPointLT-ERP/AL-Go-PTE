# AL-Go Per Tenant Extension Template (_remove this section in newly created repository readme_)
This template repository can be used for managing PTE Apps for Business Central.

[![Use this template](https://github.com/microsoft/AL-Go/assets/10775043/ca1ecc85-2fd3-4ab5-a866-bd2e7e80259d)](https://github.com/new?template_name=AL-Go-PTE&template_owner=microsoft)

- Please **DO NOT** develop your extension in this template repository, instead create a new repository from a template (remove this line in actual extension repository readme). 
- Once you create a new repository from a template - run the **"Create New App" workflow**. It will create a new folder for your app. **Copy contents** of "app" folder to your extension folder (remove this line in actual extension repository readme).
- Please always use repository name prefix **SP-** if you want extension to use SP rulesets (auto-assign code reviews to team members, create pull requests and etc). For AppSource extensions using LS Central please also add a repository name prefix **LSC-**. For customer (PTE) extensions in repository name please use 3-4 character customer prefix, for example **CUST-**.
- Extension naming should follow same logic, just without a dashes "-" between prefixes and words. For example: SP Web Services.

## Examples of repository naming:
1. SP-Web-Services - AppSource extension without LS Central, multiple words separated by dash.
2. SP-LSC-POS-Functionality - AppSource extension with LS Central, multiple words separated by dash.
3. SP-CUST-Base - PTE customer extension, CUST is a customer name prefix in capitals.
4. SP-LSC-CUST-POS-Management - PTE customer extension with LS Central.

# Workflow statuses
TODO

# App Dependencies
TODO add link.

# App development process

- "main" branch is a protected branch. You **can't commit directly** to "main" branch. You need to commit changes to your new branch instead, then create a Pull Request and follow Code Review process to merge your changes into "main" branch.
- In commit message please use prefix **RM#** and redmine ticket number you are working on, for example RM#123456. Auto link will be created and you can navigate directly to redmine system.
- For your new development branches please use naming like this: **dev/ab/yymmdd-hhmm/d-e-s-c-r-i-p-t-i-o-n**. Where "dev" is a fixed value, "ab" is your initials, "yymmdd-hhmm" is a date - for example "240812-1349", "d-e-s-c-r-i-p-t-i-o-n" is a short description of a change, multiple words separated by "-".
- Use **Rebase** when merging changes to the "main" branch from Pull Request.
- You can also **enable auto-merge** if you are not planning to add more commits to the branch. When all checks are passed - your branch will be automatically merged into main branch.
- Must use registered **prefix "SPU"** at the beginning of each new .al object also new fields in extension objects. This property will be checked in VSC and AL-GO build pipeline and will throw an error if missing or incorrect.
- If you already pushed objects with one ID (or fields) and now you did changed some of those ID's to other values. When you will push again and if there is **no release created** - the build pipeline will succeed and your new ID's will be applied. Once a release is created and you try to push commits with ID changes - the build pipeline will fail (**breaking change**). To solve that you will need to write upgrade codeunit.

## App development if LSC module is used

1. Build pipeline in AL-GO as a default is running only with standard BC, meaning that if you need to use LSC module in you extension you must add it separately for each repository.
2. To install LSC module (or any other non standard) and for pipeline to grab it when build is executed you need to create a folder in repository root called "installApps" and add zipped LSC module app.
3. Add parameter "installApps" in AL-Go-Settings.json and specify the path to a zipped file you want to install as extension in pipeline. For example: "installApps": ["installApps/LS Central 24.0.0.zip"]
4. All SP repositories using LS Central must have a prefix **LSC** in their name.

## Useful links

- General information about AL-GO for Github: https://github.com/microsoft/AL-Go
- Full list of usable AL-GO settings and parameters: https://github.com/microsoft/AL-Go/blob/main/Scenarios/settings.md
