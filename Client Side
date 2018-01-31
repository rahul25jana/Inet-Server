/* Rahul Janardhanan
 Inet - Client
 */
// Header Files

import java.io.*; // Package containing standard Input and Output Library
import java.net.*; // Package containing standard Java_Networking Source, Library

public class InetClient{			// Class Definition
	public static void main (String args[]) {	// main function() with string as parameter
		String serverName;			// "serverName" is used as string
		if (args.length < 1) serverName = "127.0.0.1";	// Assigning IP address as mentioned in the class
		else serverName = args[0];			// server will directly set up IP address(by passing)
		System.out.println("Updated Rahul's Inet_Client, 1.8....\n");		// Shown -  client screen
		System.out.println("Using server: " + serverName + ", Port: 54321");	// CLient using the specified port and server name
		BufferedReader in = new BufferedReader(new InputStreamReader(System.in));	 // new Filtered layer, assigned to system input, user can read 
		try {				// block
			String name;
			do {
				System.out.print
				("Type a hostname or an IP address, (quit) to end: ");		// prints for the client to enter details
				System.out.flush ();					// flushes immediate out buffer content
				name = in.readLine ();				// reading single line of data
				if (name.indexOf("quit") < 0)		// index function is used to check string "name" that was passed
					getRemoteAddress(name, serverName);
			} while (name.indexOf("quit") < 0); //	index function will check and returns, loop is stopped
			System.out.println (" Process was cancelled upon user request.");	// Prints
		} catch (IOException x) {x.printStackTrace ();}		// catches if there some exceptions seen
	}
static String toText (byte ip[]) { /* Make portable for 128 bit format */
	StringBuffer result = new StringBuffer ();
	for (int i = 0; i < ip.length; ++ i) {
		if (i > 0) result.append (".");
		result.append (0xff & ip[i]);
	}
	return result.toString ();
}


static void getRemoteAddress (String name, String serverName){		// Parameterized function for client
	Socket sock;		// type socket
	BufferedReader fromServer; // reads texts from server's input
	PrintStream toServer;	// prints various data of output in server
	String textFromServer;			// stores messages from server
	try{
	
		sock = new Socket(serverName, 54321);		// new socket created, passed name and port number
	
		fromServer =
				new BufferedReader(new InputStreamReader(sock.getInputStream())); /// new buffered, invoked and connected to so i/p stream
		toServer = new PrintStream(sock.getOutputStream());	//	directs / sends IP address

		toServer.println(name); toServer.flush(); // passing name to server

		for (int i = 1; i <=3; i++){
			textFromServer = fromServer.readLine();			//server sends message and get stores, reading line of data
			if (textFromServer != null) System.out.println(textFromServer); //checks for the condition null. then prints message
		}
		sock.close();		// connection of socket is closed
	} catch (IOException x) {  // end catch block, catches any exceptions seen
		System.out.println ("Socket error."); // prints
		x.printStackTrace ();
	}
  }
}
