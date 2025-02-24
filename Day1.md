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
![image](https://github.com/user-attachments/assets/273ae2c3-03a3-4175-9de8-5955133a1175)

# Task 2
# Identify and analyse windows login events and understand how to differentiate successful and failed login using windows event viewer and windows powershell.

# Stimulate Login events
* Win + L ( Firstly successful log in your machine correctly and then try log in with incorrect passwords)
* Filter the event viewer logs with the following events IDs
* 4624 = Logon successful
* 4625 > Logon failure
  
  
