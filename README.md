# Created from official AL-Go Per Tenant Extension Template
This template repository can be used for managing AppSource Apps for Business Central. Template created from official MS repository by forking 'main' branch (https://github.com/microsoft/AL-Go-PTE).

[![Use this template](https://github.com/microsoft/AL-Go/assets/10775043/ca1ecc85-2fd3-4ab5-a866-bd2e7e80259d)](https://github.com/new?template_name=AL-Go-PTE&template_owner=microsoft)

Please go to https://aka.ms/AL-Go to learn more.

## App development process

- Please **DO NOT** develop your extension in this template repository, instead create a new repository from a template.
- Once you create a new repository from a template - run the **"Create New App" workflow**. It will create a new folder for your app. **Copy contents** of "app" folder to your extension folder.
- "main" branch is a protected branch. You **can't commit directly** to "main" branch. You need to commit changes to your new branch instead, then create a Pull Request and follow Code Review process to merge your changes into "main" branch.
- For your new development branches please use naming like this: **dev/ab/yymmdd-hhmm/d-e-s-c-r-i-p-t-i-o-n**. Where "dev" is a fixed value, "ab" is your initials, "yymmdd-hhmm" is a date - for example "240812-1349", "d-e-s-c-r-i-p-t-i-o-n" is a short description of a change, multiple words separated by "-".
- Use either **Squash** or **Rebase** when merging changes to the "main" branch from Pull Request.
- Must use registered **prefix "SPU"** at the beggining of each new .al object also new fields in extension objects. This property will be checked in VSC and AL-GO build pipeline and will throw an error if missing or incorrect.

## Useful links

- General information about AL-GO for Github: https://github.com/microsoft/AL-Go
- Full list of usable AL-GO settings and parameters: https://github.com/microsoft/AL-Go/blob/main/Scenarios/settings.md
