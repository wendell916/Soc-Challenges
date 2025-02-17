# Day 1
# Challenge1: Collecting logs from windows powershell and cmd command line
By default, Windows does not log commands executed in PowerShell and Command Prompt (CMD) to the Event Viewer. In this challenge, we will configure logging to capture and review executed commands, enhancing visibility for auditing and security monitoring.
# Enable logging for windows powershell
* Start menu > Local Security Policy 
* Computer Configuration > Administrative Templates > Windows Components > Windows PowerShell
* Turn on Module Logging
* Turn on Powershell Script Block Logging
* Turn on Script Execution
* Turn on Powershell Transcription
* Apply

# Enable logging for cmd 
* Navigate to Computer Configuration > Administrative Templates > System > Audit
* Enable the policy setting "Ïnclude the command line process creation"

# Attack simulation and detection
``
Run any command of your choice both in the windows powershell and cmd eg . netstat
``
