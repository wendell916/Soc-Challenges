# Task 1
# Collecting logs from windows powershell 
By default, Windows does not log commands executed in PowerShell and Command Prompt (CMD) to the Event Viewer. In this challenge, we will configure logging to capture and review executed commands, enhancing visibility for auditing and security monitoring.
# Enable logging for windows powershell
* Start menu > Local Security Policy 
* Computer Configuration > Administrative Templates > Windows Components > Windows PowerShell
* Turn on Module Logging
* Turn on Powershell Script Block Logging
* Turn on Script Execution
* Turn on Powershell Transcription
* Apply


# Attack simulation and detection
Run the following command  windows powershell and cmd 
``
curl "https://google.com"
``
This command is used for transferring data across different protocols like https,http,ftp,etc
# Detect the powershell attack in Event Viewer
* Open Event Viewer
* Navigate to > Applications and Services Logs > Microsoft > Windows > PowerShell > Operational
* Click Filter Current Log and enter Event ID 4104 (Execute a Remote Command).
* Locate the entry showing the execution of the Get-LocalUser command.
![image](https://github.com/user-attachments/assets/184c4ffa-87d7-40b2-8d26-82eef047ccc0)


# Task 2
# Identify and analyse windows login events and understand how to differentiate successful and failed login using windows event viewer and windows powershell.

# Stimulate Login events
* Win + L ( Firstly successful log in your machine correctly and then try log in with incorrect passwords)
* Filter the event viewer logs with the following events IDs and you view the events.
* 4624 = Logon successful
* 4625 > Logon failure
* Powershell can also be used to view both login and failed events
  For the purposes of detection, I am going to use it for windows powershell for the possible detection of  bruteforce attacks.
  NB:Powershell must be run with admin priviledges
* If you see multiple failed attempts for the same account within a short time, it might indicate brute-force activity.
``
Get-WinEvent -LogName Security | Where-Object { $_.Id -eq 4625 } | Select-Object TimeCreated, Message

``  
![Uploading image.png…]()


  
  
