<h1> Client-Chats </h1>
This is a client server based chat application. It is implementation of a chat server using TCP socket. The server will ensure smooth connection between a pair of clients. A client can talk to another client during a session if the requested client is free. The list of connected clients (with the server) with status (BUSY, FREE, etc.) should be shown to a requesting client. The client sends a match request to the server and depending on the availability of the requested client, a separate communication channel may be established between the clients.The chat session can be ended from any side of both clients by sending a goodbye message. The other side is bound to close the chat session upon receiving the goodbye message. But, both the clients remain active in the server’s list and can start chatting on a different session. Only close command from a client terminates a connection between the client and the server. The server runs forever.

<h2> Execution Procedure </h2>
<li> Compile the server.cpp and client.cpp programs on your PC by typing the following
commands inside Linux terminal:
`g++ server.cpp -o s -lpthread`
`g++ client.cpp -o c -lpthread` 
</li>
<li> Open up multiple terminals in your system. (Let’s say 3) </li>
<li> For the first terminal, get the server started up and running. Use the following command
to run the server: ` ./s PORT_NUMBER` </li>
<li> For the second terminal get the first client running using the following:  `./c IP_ADDRESS PORT_NUMBER`</li>
<li> For the third terminal get the second client running using the following:  `./c IP_ADDRESS PORT_NUMBER`</li> 
<li> The following commands are valid when no connection has been established (on the client-side):
<ul> GET (Used for printing the list of all the client-ids connected to the server along with their status - FREE or BUSY). FREE status is displayed for the client who is connected to the server, but not
connected to some other client for chatting. BUSY status is displayed for the client who is connected to the server and chatting with someone else. </ul>
<ul> CONNECT <Client_ID> (It is used to connect the current client with another client who is having FREE status). </ul>
</li>
<li> After the two clients are connected, directly type in the messages that you want to send to the other client and the same can be done from the other side. (Note: You cannot send a message if you are not connected to some client/until your status is FREE). </li> 
<li> In order to end the chatting/ connection with the other client, type #GOODBYE# command inside the client terminal. This results in the disconnection of the two clients.
Note: The clients still remain connected to the server. </li> 
<li> In order to make a client disconnect from the server, type #CLOSE# command inside the terminal of the respective client. This results in the closing of the connection between client and server. </li>
