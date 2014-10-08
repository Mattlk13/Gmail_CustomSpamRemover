Gmail_CustomSpamRemover
=======================

Can remove/delete emails matching with pre-defined criteria in config file. 

* Supports unlimited inboxes. 
* Works on "App Password" for Gmail to minimize security risks.
* Can filter emails based on email ID.
* Can filter emails based on restricted keywords specified in config file.
* Forwards filtered email(s) to the email address specified in the config file before deleting it from user's inbox.

To execute this script, open **config.php** and do the required settings. That would include the following heads -
 
__1) BASE URL -__ Enter the base url of your script directory.

__2) SMTP & EMAIL Settings -__ Enter the required SMTP details and other email settings.

__3) Blocked Keywords Array -__ This is an array containing blocked keywords, that are to be serached in email subject and content. You can add as many as you want.

__4) Blocked Email Addresses Array -__ This is an array of blocked email addresses, that the script will match in sender's email address and in the message content as well.

__5) Email Addresses wih Names, to whom the blocked emails are to be forwarded -__ This is the list of user's to whom the blocked emails would be forwarded with all other details. To add more records copy paste the below line and replace - *email_1@gmail.com* & *Name 1* to the required email address and name, respectivley -
```
$to_email_addresses[] = array( "email_1@gmail.com", "Name 1" );
```

__6) Email Addresses & App Passwords of all users, whose Inboxes are to be scanned -__  This is the list of users, whose Inboxes are to be scanned by the script. To add more records copy paste the below line and replace - *echeck_user_1@gmail.com* & *app_pass_1* to the required email address and app pasword, respectivley -
```
$check_inbox_of[] = array( "echeck_user_1@gmail.com", "app_pass_1" );
```

After doing all the above configurations, execute or schedule cron job for **index.php** (using URL). Please note that the script would process each Inbox at the interval of minimum 90 seconds (approx), so schedule the cronjob interval accordingly depending upon the number of Inboxes to be scanned.
