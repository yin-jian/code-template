## Step 1
Add "customOrgMetadataTemplates": "https://github.com/yin-jian/code-template" to .sfdx/sfdx-config.json in your project folder.
## Step 2
As the company blocked Github, error message will show when run ```SFDX:Create Apex Class``` in VS Code.  
```"Cannot retrieve default branch for custom templates repository: https://github.com/yin-jian/code-template"```

## Step 3
Create index.js file, and replace the url to the same url in Step 1, then cd to the index.js file folder and run  ```node index.js```.  
```
const crypto = require('crypto');  
const hash = crypto.createHash('md5')  
    .update('https://github.com/yin-jian/code-template')  
    .digest('hex');  
console.log(hash); // my output value is d5206b9b09f32df46c55538502255c55
```
See code  https://github.com/forcedotcom/salesforcedx-templates/blob/main/packages/templates/src/service/gitRepoUtils.ts

## Step 4
Create custom-templates folder under .sfdx folder.
```
C:\Users\xxx\.sfdx\custom-templates
```

## Step 5
Create new folder under custom-templates, folder name is the output value in Step 3
```
C:\Users\xxx\.sfdx\custom-templates\d5206b9b09f32df46c55538502255c55
```

## Step 6
Copy template folders to this new folder
```
C:\Users\xxx\.sfdx\custom-templates\d5206b9b09f32df46c55538502255c55\apexclass\DefaultApexClass.cls
C:\Users\xxx\.sfdx\custom-templates\d5206b9b09f32df46c55538502255c55\apexclass\_class.cls-meta.xml
...
```

## Step 7
Now you can create new apex class in VS Code with template

## Links
* https://github.com/forcedotcom/salesforcedx-templates
* https://developer.salesforce.com/tools/vscode/en/user-guide/byotemplate