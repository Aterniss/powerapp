# Introduction to Power Apps:

In today's fast-paced digital era, businesses require agile solutions to adapt to changing requirements swiftly. Power Apps, part of Microsoft's Power Platform, is a revolutionary tool that empowers users to create custom applications with ease. Whether you're a business professional, developer, or IT expert, Power Apps provides a seamless environment for building intuitive applications, all without the complexities of traditional coding. Today you will create your own Power App.

# Setup environment

### Step 1: Activate trial version of power platform

Before starting, you need to visit the website: <https://powerapps.microsoft.com> and then click "Try free" in the top-right corner. 


![](/docs/assets/images/register_trial.jpg)

Provide your company email address and click to confirm. If you have already used the trial version before, proceed to Step 2. Otherwise, you can skip this step.


### Step 2: Create an email address for registration (skip this step if you didn't used trial version yet)

Visit the <https://tempail.com/en/> website. In the top section, you will find your temporary email address. Copy the generated email and use it as your company email in the Microsoft registration form. Do not close the tab with your email yet. The confirmation code will be sent, and you will need to enter it in the registration form."
![](/docs/assets/images/temp_email.jpg)
![](/docs/assets/images/pass_the_email.jpg)

### Step 3: Fill the form and complete registration

- In the first step, select the option 'I got it from my organization'. 
- Next, fill out the form with your credentials. In the "Business phone number" field, they do not verify your number.
- In the 'Verification code' field, enter the confirmation code sent to your company email.
- Confirm the checkbox above the next button.
- Click 'Next'.

### Step 4: Confirm your registration

After your credentials are confirmed successfully, click 'Get Started'.

![](/docs/assets/images/confirmation.jpg)


<b>Congratulations, your trial version is active now!</b>

# Create google sheets file

- Go to your Google Drive (which can be on your Devoteam account).
- Click  'My drive' to see the dropdown list.
- Select ``Google Sheets > Blank spreadsheet ``

![](/docs/assets/images/google_drive_create_new.jpg)

- In the Google Sheets file, paste the content of the Customers.xlsx file. [download here](https://drive.google.com/uc?export=download&id=1gH9oSYCVmKRi17muxD4Zy-KgqJwfSmhC)
- Provide a name for your spreadsheet, for example: ``Customers``.
- For now, you can close the Customers sheets.



# Create canvas app

- Click on the following link: <https://make.powerapps.com/> to be redirected to the Power Apps portal." 

![](/docs/assets/images/powerapp_portal.jpg)

- On the left menu, select 'Create,' and then on the right side, click 'More Data Sources'.

![](/docs/assets/images/more_data_sources.jpg)

- In the Connections section, click on 'New Connections'.

![](/docs/assets/images/new_connections.jpg)


- Search for and select 'Google Sheets', then click 'Create'.

![](/docs/assets/images/connector_create.jpg)


- Select your Google account and then click 'Allow'.

- Allow Microsoft Power Platform to access your google account. After that, click 'Allow access' again.

- Under 'Choose a dataset type,' select 'Customers' and then choose the 'Customers' sheet.

![](/docs/assets/images/customers_dataset.jpg)

- Next, select the 'Sheet1' checkbox and click 'Connect.

- If everything was successfully connected, you will see your new application as shown in the picture below.

![](/docs/assets/images/application_created.jpg)

<b>Congratulations! Your app was created! </b>

# Modify Application

### 1. Modify display records.

In this section, we will modify our application to display the customer's first and last name instead of the agent's name.

- First step, on the left-side menu unroll 'BrowseScreen1' > 'BrowseGallery1' and then select 'Title5'.
- Then, on the right-side section select 'Advanced'.
- Find textbox with the label 'text'.
- Change the body of the textbox to: ``$"{ThisItem.FirstName} {ThisItem.LastName}"``

Now you should see this screen:

![](/docs/assets/images/change_name.jpg)

### 2. Modify screen name

In this section, we will modify main screen to display proper name.

- First, select the area labeled 'Sheet1'.
- Then, on the right-hand side, select 'Advanced'.
- In textbox field, change value inside the quotes to: 'Customers'.

After the change, you should see this:

![](/docs/assets/images/edit_screen_name.jpg)

### 3. Modify searching bar

In this section, we will modify search bar to be able to find records by first name, last name or joined date.

- On the left-side menu, select BrowseScreen1, then BrowseGallery1.
- On the right-side, select 'Advanced'.
- Change the 'Items' value to: ``SortByColumns(Search([@Sheet1], TextSearchBox1.Text, "FirstName","LastName","DateJoined"), "AgentName", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))``

![](/docs/assets/images/change_search_option.jpg)

# Publish and test your application

### 1. Publish your app.

"In this section, you will publish your application for global usage. To do this, click the  publish icon ![](/docs/assets/images/publish_icon.jpg) in the top-right corner, and then click 'Publish this version'."


### 2. Try your app.

Now is the final part to try your application.

Visit the <https://make.powerapps.com/>. Click 'Apps' and then select your app and click play. You will be redirected to your app. Now you can try to add, delete, or edit the customers yourself.

Short description:

- ![](/docs/assets/images/refresh_icon.jpg)  click to refresh data.

- ![](/docs/assets/images/sort_icon.jpg)  click to sort the record in alphabetical order.

- ![](/docs/assets/images/add_icon.jpg)   click to add new data based on the current format.


You can also try your application on your mobile phone! To do this, click ![download icon](/docs/assets/images/download_icon.jpg), select your operating system, and follow the instructions.