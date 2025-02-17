# Day 1
# Challenge1: Collecting logs from windows powershell 
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

  
