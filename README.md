# Inventory-Tracker
BABBAN GONA (ANDROID)
FOR THE SUPPLY AND DISTRIBUTION APPLICATION
The S&D personnel for the specified region in the web application receives a text message from the website containing the details of the transaction to be made.
The S&D personnel opens the app tailored for Supply and Distribution. After logging in, the S&D personnel can then view all his transactions and their statuses (pending or completed). Upon clicking each transaction, he can view each sub transaction for each transaction. For example, if a transaction’s status is pending and not completed, if he clicks on it, he should see the status of each sub transaction (awaiting confirmation, confirmed, declined and completed). It is only when each sub transaction has been completed that the main transaction will be shown as completed. 
The Create new transaction page first loads up a form for specifying:
•	Warehouse to be taken to or a customer
•	The product
•	The total number of units
Then the person has to enter new sub transactions and specify details for those sub transactions such as:
•	Warehouse to be taken from including its cocoon
•	The unit 
There will be a + button that will loop continuously to add more sub transactions. The critical condition to be met before saving is that the sum of the units of each sub transaction must match the total number of units specified in the beginning. If this condition is met and all other fields are completed, the transaction and sub transactions are saved in the local SQLite database.
After this, the app then sends a message to the Process Control attached to that warehouse or CMP requesting two tokens for each of the sub transactions for that transaction —one token for the sender of the product and one token for the receiver: this is necessary to make sure the same token is not used for both the sending and receiving authentications. The status of each sub transaction then becomes “awaiting confirmation”.
When the security guard at each sending warehouse enters the transaction token for his own end of each respective transaction, the status of the transaction becomes confirmed. When the security guard at the receiving warehouse enters the transaction token for his own end of the transaction, the status of the transaction becomes completed. Also once a token for a transaction it is deleted both from the online database and from the local SQLite to ensure that the tokens can’t be used repeatedly.
A sync status icon is also displayed online to indicate the sync status of each transaction. There will also be a sync option in the toolbar to sync all transactions with the online database.


FOR THE PROCESS CONTROL APPLICATION
The process control officer attached to that CMP receives the text messages requesting for the movements to be made. He then copies each message to the application which then loads the info and shows the process control an option to either accept or decline. On accepting, the app then generates two unique tokens which will never be used again —one for the sending security guard and another for the receiving security guard. The app then sends SMS messages to each security guard containing the two different tokens

BABBAN GONA (WEB APPLICATION)
The web application is to be created for the HQ of Babban Gona. The user, who initiates the transaction will have to log in. The web app would consist of tabs to perform various operations. These include:
1.	Initiate transaction,
2.	View transaction status

Initiate transaction tab
This is intended for the user to input the following details about the transaction:
1.	Product type,
2.	Product name,
3.	Product unit,
4.	Product quantity,
5.	Destination.
It automatically inputs the present date and time as well, the finance member then confirms the transaction and sends the request.
View transaction status tab
This is intended to allow the user view the status of all transactions and it contains the following details:
1.	Details of the staff who initiated the transaction,
2.	Progress of the transaction (Active, Cancelled or Completed), it will only be completed if all sub transactions under each transaction has been completed
3.	Date of initiation.


MODULES FOR S&D
1)	Design of login and activity layouts.
2)	Activities for both creation of a transaction and viewing of a pending transaction.
3)	Composing of the transaction details and transfer to the messaging app to be sent as a text message.
4)	Receipt and extraction of the token from the process control text message. 
5)	 Checking and confirmation of the token received.
6)	Uploading of the transaction details to the server.
MODULES FOR THE PROCESS CONTROL
1)	Design of login and activity layouts.
2)	Copying and extraction of the received S&D text message.
3)	Approval of the transaction and generation of token.
4)	Sending of the token and transaction details as text message to S&D.
MODULES FOR THE WEBSITE
1.	Decision and familiarization of the web platform to be used.
2.	Creation and design of the database to be used by the website.
3.	Design of the web application’s login.
4.	Design of the various tabs for creating and viewing transactions.
5.	Creation or use of an API for sending the text messages to the Supply and Distribution leaders in the various regions where the transaction is to take place.
