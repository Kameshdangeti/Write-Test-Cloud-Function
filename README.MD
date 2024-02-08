
**Table Of Contents**

**Objective**: The guide below shows how to write,test,deploy two functions.
---> An "add message" function that exposes a URL that accepts a text value and writes it to Cloud Firestore.
---> A "make uppercase" function that triggers on a Cloud Firestore write and transforms the text to uppercase.

## a.Create a Firebase Project
##### ->Go to Firebase Console in browser and tap on the "Add Project".
##### ->To add Firebase Google Cloud project, enter its project name or select it from the dropdown menu.
##### ->To create a new project, enter the desired project name. You can also edit the project ID displayed below the project name.
##### ->After tapping it will ask permissions for review and accept the terms and conditions,Accept it and click "continue".
##### ->Now Tap "Add Firebase" if you already have the project or else tap on the "Create Project"

## b.Set Up the code in Node.js and FireBase CLI
##### ->Now We should have Node.js to wrie the functions,it is compulsory.
##### ->Next thing we need to setup the firebase CLI for that we need to install it,So to install it,Open Terminal tab and Use this command :
###### ---------->npm install -g firebase-tools.
##### ->If we wnt o update it use the same command again.

## c.Initialize Your Project
##### ->To initialize your project we should use command "Firebase login".