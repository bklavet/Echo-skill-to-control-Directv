# Echo-skill-to-control-Directv
This is the Echo-skill-to-control-Directv skill using a Custom Slot in the Alexa Skill Kit.
I have found this to be a better way of doing things.

The setup for this is almost the same with the exception of adding a custom slot name and then adding the "custom slot values.txt " file.
I have included additional steps to mawrew19's walkthrough below to help make it easier for a first timer.

This is an amazon echo skill that will control a networked Directv Receiver so that users can control Directv with their voice

This is a hack job on another GitHub Repository: https://github.com/MrEggsalad/Echo-Roku-Voice-Control

Thanks to mawrew19, The skill now works!  

=======================
[mawrew19 update]
Open the "index" file and replace with your AppID

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
	Copy the Contents of the "IntentSchema" file into the "IntentSchema" text area from the "custom slot folder" above
	click on the tap labled "Add slot type" by Custom Slot Types. In the window that opens place type Control_List under Enter Type.
	paste the Custom Slot Values.txt file in the "Enter Values" tab, and hit Ok.
	Copy the Contents of the "SampleUtterance" file from the "custom slot folder" above into the "SampleUtterance" text area
	Click "Next"
	If everything is good, you will now be able to put the ARN value you noted from the Lambda Function you previously created.
	Click on the "Lambda ARN..." bullet and paste that value in.
	Click "No" on the Account Linking for now.
	Click Next.
	If all is good, you will be able be done for now. There is no need to go to the "Publishing Information" 
	
	