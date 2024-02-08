
**Table Of Contents**

**Objective**: The guide below shows how to write,test,deploy two functions.
###### ---> An "add message" function that exposes a URL that accepts a text value and writes it to Cloud Firestore.
###### ---> A "make uppercase" function that triggers on a Cloud Firestore write and transforms the text to uppercase.

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
##### ->It shows all the project directories select your project directory.
##### ->Now we should initialize Firestore using "firebase init firestore" in terminal tab,Then it shows indexes and rules then just accept it.
##### ->Now we should initialize the Function using "firebase init function",The n it will ask t choose existed one or create a new one,Choose one.
##### ->Now system gives 2 option for language:TypeScript,JavaScript,We should choose one.
##### ->Initialization is done,Now we need to install the using "npm install".
##### -> Now When we see in the folder we can see all the files related to it.


