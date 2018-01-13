
# If you live in an apartment or complex where internet is provided (that you are not paying for) This most likely will not work.

# Echo-skill-to-control-Directv

youtube video walkthrough:
Updated video reflecting aws lambda 12/31/17
https://youtu.be/nUdS6siT0zY


original
https://www.youtube.com/watch?v=HRduDp4ip-Y


This is an amazon echo skill that will control a networked Directv Receiver so that users can control Directv with their voice

This is a hack job on another GitHub Repository: https://github.com/MrEggsalad/Echo-Roku-Voice-Control

# If you get errors after running through this tutorial, please refer to this post for troubleshooting steps!!
https://github.com/bklavet/Echo-skill-to-control-Directv/issues/12

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
	Copy the Contents of the "IntentSchema" file into the "IntentSchema" text area
	Copy the Contents of the "SampleUtterance" file into the "SampleUtterance" text area
	Click "Next"
	If everything is good, you will now be able to put the ARN value you noted from the Lambda Function you previously created.
	Click on the "Lambda ARN..." bullet and paste that value in.
	Click "No" on the Account Linking for now.
	Click Next.
	If all is good, you will be able be done for now. There is no need to go to the "Publishing Information" 

# For Custom Slot Setup walkthrough

This is a walkthrough to set up a skill using the contents of the "Custom Slot skill" folder.
	
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
	Copy the Contents of the "IntentSchema" file from the "Custom Slot skill" folder above into the "IntentSchema" text area
	Click on "Add Slot Type" by the section named Custom Slot Type.  Enter Control_List for the "Enter Type" section.  Cut and paste the custom slot values.txt file in the section labled "EnterValues".  Click OK
	Copy the Contents of the "SampleUtterance" file from the "Custom Slot skill" folder above into the "SampleUtterance" text area
	Click "Next"
	If everything is good, you will now be able to put the ARN value you noted from the Lambda Function you previously created.
	Click on the "Lambda ARN..." bullet and paste that value in.
	Click "No" on the Account Linking for now.
	Click Next.
	If all is good, you will be able be done for now. There is no need to go to the "Publishing Information" 
	
	
