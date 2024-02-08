
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

## d.Import Required Modulus and Initialize an App.
##### ->After you have completed the setup tasks, you can open the directory and start adding code as described in the following index.js file:
        // The Cloud Functions for Firebase SDK to create Cloud Functions and set up triggers.
        const functions = require('firebase-functions/v1');

        // The Firebase Admin SDK to access Firestore.
        const admin = require("firebase-admin");
        admin.initializeApp();
##### ->These lines load the firebase-functions and firebase-admin modules, and initialize the app instance from which Cloud Firestore changes can be done.

## e.Add the addMessage() function
##### ->As mentioned in the above the addMesage function that accepts text value,for that add these lines to index.js
        // Take the text parameter passed to this HTTP endpoint and insert it into
        // Firestore under the path /messages/:documentId/original
        exports.addMessage = functions.https.onRequest(async (req, res) => {
        // Grab the text parameter.
        const original = req.query.text;
        // Push the new message into Firestore using the Firebase Admin SDK.
        const writeResult = await admin
            .firestore()
            .collection("messages")
            .add({ original: original });
        // Send back a message that we've successfully written the message
        res.json({ result: `Message with ID: ${writeResult.id} added.` });
        });
##### ->The addMessage() function is an http end point and it adds the message.

## f.Add the makeUpperCase() function
##### ->Even about these it is mentioned above that it transforms text into Uppercase text.And so we should add lines in the index.js
        // Listens for new messages added to /messages/:documentId/original and creates an
        // uppercase version of the message to /messages/:documentId/uppercase
        exports.makeUppercase = functions.firestore
        .document("/messages/{documentId}")
        .onCreate((snap, context) => {
            // Grab the current value of what was written to Firestore.
            const original = snap.data().original;

            // Access the parameter `{documentId}` with `context.params`
            functions.logger.log("Uppercasing", context.params.documentId, original);

            const uppercase = original.toUpperCase();

            // You must return a Promise when performing asynchronous tasks inside a Functions such as
            // writing to Firestore.
            // Setting an 'uppercase' field in Firestore document returns a Promise.
            return snap.ref.set({ uppercase }, { merge: true });
        });
##### ->The above transform the data or text that is given by the user in the console into uppercase Text.

## 





