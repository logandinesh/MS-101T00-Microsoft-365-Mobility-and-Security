# Module 3 - Lab 3 - Exercise 2 - Conduct a Drive-by URL attack using Attack Simulation training

Holly Dickson is concerned that some users at Adatum may require education about selecting URL links to familiar websites that are either fake or have been hacked. This type of attack is known as a Drive-by URL attack. With this type of attack, a target receives an email containing a URL link, and when the target selects the link, they are taken to a website that runs background code whose sole purpose is to gather information about the target or deploy arbitrary code to their device. As part of her pilot project, Holly has decided to use the Microsoft 365 Attack simulation training feature to determine her users' susceptibility to Drive-by URL attacks.

**Note:** At the end of this exercise, you will disable MFA for Holly's account. This will save you from having to enter the second form of authentication when signing in as Holly in any of the remaining labs in this course.


### Task 1: Configure and launch a Drive-by URL attack 

In a Drive-by URL attack, the website attempting to lure the target will typically be a well-known website that has been compromised in some fashion, or a clone of a well-known website itself. The hacker hopes that familiarity with the website builds trust in the target, to the point where the target feels that it's safe to select the URL link. Holly wants to create a Drive-by URL attack using a rip-off of the Tailspin Toys website. Tailspin Toys is a nationally known toy store that is constantly offering promotions on TV and throuhout social media. Holly wants to use this familiarity with the Tailspin Toys namebrand to offer an enticing promotion for free toys as part of her attack simulation training. This will enable her to see how many Adatum employees are susceptible to this type of attack. 

In the prior lab, you created a simulation that was sent to all Adatum users. You also used an existing payload template for the simulation. In this lab exercise, you will only roll out the simulation to Lynne Robbins, and you will create your own custom payload.  

1. You should still be in LON-CL1 and signed in as the **Admin** with a password of **Pa55w.rd**; if not, then sign in now.  

2. After the previous lab exercise, you should still be in the **Microsoft 365 Defender** portal, and you should still be logged in as Holly Dickson; if not, then do so now.

3. In the **Microsoft 365 Defender** portal, you should still be in the **Attack simulation training** page; if not, then in the left-hand navigation pane, under **Email & collaboration**, select **Attack simulation training**.

4. On the **Attack Simulation training** page, Holly wants to conduct a **Drive-by URL** attack in which she will use a URL to gather information about the target and Adatum itself.  <br/>

	In the prior lab exercise, you selected an existing payload template (2 Failed Messages). In this lab, you will create a custom payload. On the menu at the top of the page, select **Payloads**. On the **Payloads** tab, select **+ Create a payload**. This initiates a Payload wizard.

5. On the **Select type** page of the Payload wizard, the **Email** option should be selected by default (if not, select it now). Select **Next**. 

6. On the **Select Technique** page, under the **Drive-by URL** option, select the **View details of Drive-by URL** link. This opens a **Drive-by URL** pane on the right. Review the **Description** and the **Simulation steps** for this type of attack. When you're done, close the **Drive-by URL** pane.

7. On the **Select Technique** page, select the **Drive-by URL** attack type and then select **Next**.

8. On the **Payload name** page, enter the following information: <br/>

	- Email payload name: **Free gift offer**
	- Description: **This payload is for Drive-by URL threats offering free prizes and gifts that are too good to be true**

9. Select **Next**.

10. On the **Configure Payload** page, enter the following information: <br/>

	- Enter name: **Klemen Sic**
	- From email: **klemens@tailspintoys.com**
	- Email subject: **Free toy giveaway promotion from Tailspin Toys**
	- Select a URL you want to be your phishing link: select the drop-down arrow and select **https://www.prizegives.com** from the list of fictitious URLs. 
	- Theme: **Personalized Offer**
	- Industry: **Retail**
	- Current Event: **Yes**
	- Email message: Enter the following text that will be displayed in the body of the email message: **Tailspin Toys is offering you a FREE, one-time only giveaway of a toy of your choice as part of our 25th anniversary celebration! Please click on the following link to select the toy of your choice:** 
	- After entering the prior message, select the **Phishing link** option at the top of the text form (to the right of **Dynamic tag**). In the **Name Phishing Url** dialog box that appears, enter **Free25thAnniversaryGift@tailspintoys.com** in the **Name** field and then select **Confirm**.

	The message should now appear as: 

	Tailspin Toys is offering you a FREE, one-time only gift of the toy of your choice as part of our 25th anniversary celebration! Please click on the following link to select the toy of your choice: **Free25thAnniversaryGift@tailspintoys.com** 

11. Select **Next**.	

12. On the **Add Indicators** page, select the **Add Indicator** button.

13. On the **Add Indicator** pane that appears on the right, enter the following information: <br/>

	- Indicator Name: **Too good to be true offers**
	- Indicator Location: **From the Body of the email**

14. A **Select Text** button will appear. Select this button.

15. In the **Select the required text** pane that appears on the right, drag your cursor from the start of the code block to the end, so that the entire code block is highlighted. This will enable the **Select** button. Select this button. 

16. In the **Indicator Description** field, enter the following text: **Free gifts or other one-time only promotional give-aways**

17. Select inside the **Indicator Preview** to see a preview of the indicator message. Then select outside the **Indicator Preview** field to exit the preview. 

18. Select **Add**.

19. On the **Add Indicators** page, the indicator that you just created should be displayed. Select **Next**.

20. On the **Review Payload** page, review the entered information. If anything needs to be changed, select the appropriate **Edit** option to make the change, or select **Back** to enter any of the information in the Configure section. Once everything is correct, select **Submit**. A few moments will pass and you will receive a confirmation stating **New payload created**. Select **Done**. 

21. On the **Attack simulation training** page, you should still be viewing the **Payloads** tab. Scroll down through the list of payloads to the **Free gift offer** payload that you just created. Review the information. Note that no **Compromised rate (%)** has been determined yet, since the payload hasn't been used in simulation. Once you're done, select the **Overview** tab.

22. On the **Overview** tab of the **Attack simulation training** page, at the bottom of the **Recent Simulations** section, select **Launch a simulation**. This initiates the **Simulation** wizard.

23. On the **Select Technique** page, select the **Drive-by URL** attack type and then select **Next**.

24. On the **Name Simulation** page, provide the following information: <br/>

	- Simulation Name: **Drive by URL - Free offer**
	- Description: **This simulation tests whether users are susceptible to free gift offers from malicious web sites**

25. Select **Next**.

26. On the **Select Payload** page, hover your mouse over **Free gift offer** in the list of payloads and then select the circle that appears to the left of it. Select **Next**. 

27. On the **Target Users** page, select **Include only specific users and groups**, and then select **+Add Users**. 

28. In the **Add Users** pane that appears, in the **Search for Users or Groups** field at the top of the pane, enter **Lynne** and then hit Enter. In the list of users that appears whose name starts with Lynne, select **Lynne Robbins** and then select **Add 1 User(s)**.

29. On the **Target Users** page, Lynne Robbins should be displayed as the targeted user. Select **Next**. 

30. On the **Assign Training** page, under the **Preferences** section, the **Assign training for me (Recommended)** option should be selected by default (if not, select it now). Select the **Due Date** field. In the drop-down menu that appears, select **7 days after Simulation ends** and then select **Next**.

31. On the **Training landing page**, the **Select the landing page option to be used** field should be prefilled with the **Microsoft landing page** option (if not, select it now). Select the **Preview page** button that appears below this field. 

32. The **Microsoft landing page** appears in the pane on the right. This provides an example of what the landing page will look like when someone experiences a phishing attack. Review the features of this landing page, and then close **Microsoft landing page** pane.

33. On the On the **Training landing page**, note the text that appears in the **Header** and **Body** fields. This is the text that you saw when you previewed the Microsoft landing page. Change the values of these fields to something different, and then select the **Preview page** button again. In the **Microsoft landing page** that appears in the pane on the right, you should see the changes that you made to the header and body text fields. Close the **Microsoft landing page** pane when you're done reviewing.

34. Select **Next**.

35. On the **Launch Details** page, select the **Launch this simulation as soon as I'm done** option and then select **Next**.

36. On the **Review Simulation** page, review the entered information. If anything needs to be changed, select the appropriate **Edit** option to make the change. Once everything is correct, select **Submit**. A few moments will pass and you will receive a confirmation stating **Simulation has been scheduled for launch**. Select **Done**.


### Task 2: Review the Drive-by URL attack results

You will now review the results of the Drive-by URL simulation attack that you just launched. In this task, you will verify whether your organization has received the email that you configured in the Attack simulation training. You will then review the results associated with the Drive-by URL attack that you simulated.

1. Switch to the **LON-CL2** VM and log in as the **Admin** with a password of **Pa55w.rd**.

2. In the Edge browser, in the **Outlook** tab in which you are signed in as the MOD Administrator, select the **MA** initials in the upper right-hand corner of the screen. In the **MOD Administrator** window that appears, select **Sign out**.

3. Close all browser tabs except for the **Sign out** tab. In the **Sign out** tab, enter the following URL in the address bar to navigate directly to Outlook on the web: **https://outlook.office365.com**.
 
4. In the **Pick an account** window, select **Use another account**. 

5. In the **Sign in** window, enter **LynnR@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix ID provided by your lab hosting provider), and then in the **Enter password** window, enter **Pa55w.rd** and select **Sign in**. 

6. Close the **Welcome** window.

7. In Lynne's Outlook Inbox, you should see the email that was sent by the Attack Simulator that's from **klemens@tailspintoys.com**. Select the email to open it and review the details in the body of the message. 

	**NOTE!** It can take up to 15 minutes for the email to arrive.  Wait for the email before proceeding.

8. Select the link that is included in the email. Even though you know this is a Drive-by URL attack, this will enable you to see the effect of doing so in the Attack Simulator report that tracks the results of the spear phishing campaign.

9. In the **Sign in** dialog box that appears, enter **LynnR@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix ID provided by your lab hosting provider), and then enter **Pa55w.rd** in the **Enter password** window. Select **Sign in**. 

10. This displays a web page that explains how you have redirected to it as part of a Phishing awareness test being run by your organization. Read through the contents of this page. 

11. Switch back to **LON-CL1**.

12. In your browser session where you are logged in as Holly Dickson, you should still be on the **Attack simulation training** page. If the **Drive by URL - Free offer** simulation does not appear in the **Recent Simulations** list, select the **Refresh** icon to the left of the URL on the address bar. The **Drive by URL - Free offer** simulation should now appear. Select the **Drive by URL - Free offer** simulation to view the diagnostic results that were captured for this simulation.

13. A **Drive by URL - Free offer** page should appear. Review all the information collected for this simulated attack. When you're finished, select the **X** in the upper right-hand corner of the window to close it. 

14. Leave your browser open in LON-CL1 and do not close any of the tabs.


### Task 3: Disable Multi-factor Authentication for the Global Admin

To use Microsoft's Attack simulation training to simulate phishing attacks, Holly enabled Multi-Factor Authentication (MFA) for her user account. Now that she has completed the Attack simulation training test, she wants to disable MFA for her account so that she doesn't have to deal with MFA for the remainder of the pilot project.

1. You should still be logged into **LON-CL1** as the **Admin** account and into Microsoft 365 as Holly Dickson.

2. To disable MFA for Holly Dickson's user account, you must first access the **Active users** list in the Microsoft 365 admin center. If you have the **Microsoft 365 admin center** open in a browser tab, then select that now; otherwise, open a new browser tab, enter **https://portal.office.com** in the address bar, and then on the **Office 365 home** page, select **Admin**. 

3. On the **Microsoft 365 admin center**, in the left-hand navigation pane, select **Users** and then select **Active users**.

4. In the **Active users** window, on the menu bar at the top of the user list, select **Multi-factor authentication**.

5. In the **multi-factor authentication** window, the **users** tab is displayed by default. Select the check box for **Holly Dickson**, and in Holly's properties pane on the right, select **Disable**.

6. On the **Disable multi-factor authentication?** dialog box, select **yes**. 

7. When the **Updates successful** dialog box appears, select **close**. In the **multi-factor authentication** window, verify Holly's MFA Status has changed to **Disabled**. 

8. You must now sign out of Microsoft 365 as Holly and then sign back in as Holly (without MFA). To do so, perform the following steps: <br/>

	- Close your browser session and all browser tabs (to clear your cache).
	- Open a new Edge browser session.
	- Enter the **https://portal.office.com** URL.
	- Sign in as **Holly@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) with a password of **Pa55w.rd**
	- From the **Microsoft Office Home** page, select the **Admin** icon to navigate to the **Microsoft 365 admin center**.
	
	You are now ready to proceed to the next lab exercise.

# Proceed to Lab 3 - Exercise 3
 
