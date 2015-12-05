#Hypertext Transfer Protocol (HTTP/1.1)
* RFC Used:	 7231, 7230
* Tested against:	 Simple HTTP python server

##Required configuration

1. Server IP (server_ip) - IP address of the target HTTP server
2. Server Port (server_port) - Port number of the target HTTP server
3. Timeout (timeout) - How long to wait in milliseconds for incoming data. This is used on both client and reflector
4. Publisher on Client (client_publisher) - Publisher on fuzz_client TcpClient, SslClient
5. Publisher on Server (server_publisher) - Publisger on reflector TcpListener, SslListener
6. UserAgent (user_agent,user_agent_mutable_flag)
   * user_agent	- UserAgent by user
   * user_agent_mutable_flag - Flag to enable or disable fuzzing of User Agent Header (true or false)
7. Host (host,host_mutable_flag)
   * host - Host by User
   * host_mutable_flag - Flag to enable or disable fuzzing of Host Header (true or false)
8. Referer
   * referer - Referer given by user
   * referer_mutable_flag - Flag to enable or disable fuzzing of Referer Header (true or false) 
	* referer_minoccurs - minOccurs flag can be either 0 or 1 depending on whether user wants to fuzz or not
9. Authentication (username,password,authentication_mutable_flag,authentication_minoccurs)
   * username - Username for authentication
   * password - Password for authentication
   * authentication_mutable_flag - Flag to enable or disable fuzzing of authentication header (true or false) 
   * authentication_minoccurs - minOccurs flag can be either 0 or 1 depending on whether user wants to fuzz or not	
10. Content Boby
   * content_body_mutable_flag - Flag to enable or disable fuzzing of Content Body in Http Request Header (true or false)
   * content_body_minoccurs - minOccurs flag can be either 0 or 1 depending on whether user wants to fuzz or not
	
To get the pcap traces run "tcpdump -i test host ##server_ip## and tcp and port ##server_port##" on source or sink namespace
