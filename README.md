# Echo-skill-to-control-Directv
This is an attempt to create a amazon echo skill that will control a networked Directv Receiver so that users can control Directv with their voice

This is a hack job on another GitHub Repository: https://github.com/MrEggsalad/Echo-Roku-Voice-Control

=======================
[mawrew19 update]
Open the "index" file and replace with your AppID
If you wish to use the "Test Event" in the Lambda Management console, copy and paste the text of the "TestEvent_Sample.txt" and replace with your AppID.

Login to your developer.amazon.com account and go to the Alexa page.
    Click "Get Started" under the "Alexa Skills Kit"
	Click "Add a new Skill" at the top right.
	Make sure "Custom Interaction Model" is selected
	Give it a Name
	Put in the "Invocation Name".  This is what you will use to "tell" Alexa.
	Click SAVE.  This will generate your ApplicationID and will be used when creating the Lambda Function

Login to your "aws" Management console for Lambda and create a new Function
Once you create a new Lambda Function, do not choose a Blueprint (click Skip). 
Place the index and AlexaSkill files in a zip file and choose to upload.
	Role should be: "lambda_basic_execution"
	Once you select the role, a new browser window will open. Click the "Allow" button in this new window.
	Click "Next" in the  original window to Review the new function.
	Click "Create Function"
	Click on the "Event Source" tab and click "Add Event Source"
	Select the "Alexa Skills Kit" item and Click "Submit"
	
Take note of the ARN value at the top right of the screen.  You will need this in the next step.

Go BACK to your developer.amazon.com account and go to the Alexa page.
    Click "Get Started" under the "Alexa Skills Kit"
    Click "Edit" next to the Skill you already created.
	Click Next
	Copy the Contents of the "IntentSchema" file into the "IntentSchema" text area
	Copy the Contents of the "SampleUtterance" file into the "SampleUtterance" text area
	Click "Next"
	If everything is good, you will now be able to put the ARN value you noted from the Lambda Function you previously created.
	Click on the "Lambda ARN..." bullet and paste that value in.
	Click "No" on the Account Linking for now.
	Click Next.
	If all is good, you will be able be done for now. There is no need to go to the "Publishing Information" 
	
	
