# Tampere Formula Student Software Development Guidelines

## Version Control
- All new project repositories for the TFS27 should have their name start with the prefix ```TFS27```. For example: ```TFS27-CAN-Node```.
- The Master/main branch of a project should always include a "ready-to-drive" version of the software in that repository. Use separate development branches during development.
- Development branches should be named with a ```dev-``` prefix. For example: ```dev-read-adc```.
- All repositories must include a ```README.md``` with a description of the software.
- All code changes should be committed to Git, even if the changes are "tunkkausta". Use *descriptive* commit messages.
        Example commit message: "dev-apiReformat: Added new paths to router"
- Make sure your .gitignore file is in order to not push anything extra to the repositories!
- Don't leak .env files with sensitive info! Backup to OneDrive and encrypt it if necessary.

## Further reading and basics of version control
https://tuni.sharepoint.com/:w:/r/sites/TG-tampereuasmotorsport/Jaetut%20asiakirjat/Dept.%20Electrics%20and%20Embedded%20Systems/TFS27/Embedded%20systems/Coding%20rules%20of%20engangement.docx?d=w850cf0e830dd4c9fa19bfd258565cf98&csf=1&web=1&e=eHzX61
