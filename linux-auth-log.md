### Auth.log analysis

In linux, the file(/var/log/auth.log) contains authorization information like:
* remote login
* usage of sudo command
* instances where a user password is required for authorization

The file is stored in plain text, and rolled/archived logs will be compressed with gzip. 
The analysis of this file will allow us to track anomalous activities. Some of the use-cases that can be tracked are given below:

#### sudo commands
'sudo' allows a user to execute a command with superuser privileges, or another user (superuser is the default). These are authorization events that you should definitely keep track of from security perspective.
[[screenshot]]

Parsing of this file allows us to see what folder the command was issued from, the user, as well as the command itself! 

#### root session
Aside from sudo logs, which may be used to run a command with elevated privileges,  it is possible to keep track of users  escalating to root. From the logs, one can also find out number of session as well as their durations (opening time/closing time) and these metrics are useful for tracking malicious activities.
[[screenshot]]

#### ssh activity
It is also possible to keep track of ssh remote login activity - how many connection attempts, what is the success and failure rate of ssh connections, set of commands executed once the ssh session is established and so on.
[[screenshot]]

If the number of ssh login failures are execessive, one can block the user on the basis of IP range or ASN numbers or City/Country and filter out the noise in the logs.
