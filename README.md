# EQOAGameServer
The /current/ overall eqoa game server, not so complex, complex.

# TCPServerTests

EQOA Account server.
Utilizing TCP server in C#, able to process and interact with a few requests of the client.
- Primarily logging in (Authentication of username/password).
- Creating an account.
- Changing password.
- All other requests should be met with, "This option is disabled in order to bring you content faster. If you feel this is an error,please contact the development team for further assistance."

This is super basic at this time and just automatically processes and accepts these requests.
We have a database utilizing mariadb at this time, to be shared soon.

Functions needing to be added:
- Some SQL Choice (raw? orm?)
- Verifying username/password with sql.
- Authenticating old password and replacing it with new password if correct.
- Receiving create account requests, checking for username availability and writing the information to the database.

# EQOA-Proto-C-Sharp

UDP server implementing the packet framework to handle packet requests up to character select, including creating and deleting characters.
This server implements a keep alive which keeps the server select menu and Character select menu alive for a indefinite amount of time currently.



# Set up

Client setup can be found here: http://wiki.eqoarevival.com/index.php/Client_Setup

For a windows environment, a DNS redirect can be found here: http://wiki.eqoarevival.com/index.php/Server_Setup_Windows#DNS_Server

For a windows environment, A HTTP Server can be found here: http://wiki.eqoarevival.com/index.php/Server_Setup_Windows#HTTP_Server

For Linux environments, A HTTP Server can be used through python's httpserve. Apache can also be used via a more traditional web server setup and seems to be more stable.

Downloading and using Visual studio's, you need to clone the repo. Example of how to do this should be found here: https://docs.microsoft.com/en-us/visualstudio/get-started/tutorial-open-project-from-repo?view=vs-2019
Upon cloning the repo, you should find a config file here -> EQOAGameServer\EQOA_Proto_C-sharp\EQOAProto-C-Sharp\app.config
Modify the config file to have the appropriate IP's for your machine hosting the game server and the database.

Once completed, opening two seperate instances of the repo in Visual Studio's, select and run both solution files from the drop down box.

# Do not run everything on the same machine. At the minimum, the client should be a seperate machine or in a VM box. Otherwise it is likely the client won't connect
