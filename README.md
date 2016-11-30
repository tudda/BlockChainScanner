# BlockChainScanner
Tool to find files in the bitcoin blockchain
Setting up the program
------------------------------------------------------------------
- Get the blockchain on your computer
- launch bitcoin so that you make queries to it:
	"C:\Program Files\Bitcoin\bitcoin-qt.exe" -server=1 -rpcuser=user -rpcpassword=password -rpcport=8332 -rpcallowip=0.0.0.0/0 -listen=1

- edit the app.config file with this program and set your bit coin rpc settings



Investigating the block chain
------------------------------------------------------------------

From https://www.reddit.com/r/WhereIsAssange/comments/5e55p3/a_simple_blockchain_decoding_tutorial/

1) Decoding a single transaction
	Click "Single Transaction Viewer" button
	Enter 691dd277dc0e90a462a3d652a1171686de49cf19067cd33c7df0392833fb986a
	Click "Decode" button

	You will see the decoded output of this transaction
	
	It contains text, and then a list of transactions (this list will be used in Example 3)
	
2) Getting a file from a single transaction
	Click "Single Transaction Viewer" button
	Enter 54e48e5f5c656b26c3bca14a8c95aa583d07ebe84dde3b7dd4a78f4e4186e713 
	Click "Decode" button
	You will see on the right hand side "File Type: (.PDF) Adobe Portable Document Format (5000/1)"
	Click "Decode and Get File" button
	You will be prompted to save.  use a filename of test.pdf  and save it wherever you'd like. Hit OK/SAVE
	You will now have a file that you can open and read

3) Combining the output of multiple transactions to a file
	Reprodoce step one, and take the list of transaction ids in the output and save them to a file
	Click "Multi Transaction Viewer" button
	Click "populate list from file", select the text file that has the list of transactions
	They will now be in the list on the left.  Click "Build file from transactions"
	You will be propmted to save.  Enter a location/filename, click Ok/save
	It will decode each transaction and merge them into the file
	Verify the file is valid

	** you could also copy/paste the list of transactions into the textbox instead of saving them to a file
	** if your list of transactions has any wrong transactions, or they are in the wrong order, the file will not combine properly

	


	

Advice for searching
------------------------------------------------------------
1. Sort transactions based on TX Fees. The DMS TX(s) will probably have a high fee associated with it to a) ensure its inclusion in the block (against the spamming attacks we're seeing) and b) draw attention to it. If a transaction contains an OP_RETURN and has an unusually high fee, IT IS WORTH INVESTIGATING.

2. Look for duplicate OP_RETURN data. Provided there wasn't a lone machine setup to post the DMS, it would likely be posted twice or more. Create a script to store transactions in a database. Store block number, date, op_return, fee and amount (if any of the outputs contain "911", also pay attention.)

3. The DMS will likely NOT come from the Wikileaks address (but might go to it). In the event that the server(s) hosting the DMS got compromised, the attacker would have access to that address' private key (and thus all of WikiLeaks' funds).

4. This address might be worth investigating: https://blockchain.info/address/1NquF1c4AuKx9YJtP9SsjGqhazfa72yPBM?offset=100&filter=0
Many OP_RETURNs and all on the 10/16/2016 within a period of a few hours. I have not had the chance to investigate further. 	
	