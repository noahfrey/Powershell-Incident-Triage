Incident Report — Suspicious PowerShell Execution
=================================================

**Summary**

A PowerShell process was executed with the -ExecutionPolicy Bypass flag, which can indicate attempts to run scripts without standard security controls. Script Block Logging (Event ID 4104) shows the executed command was Get-Process, a benign enumeration command. No malicious behavior was identified.

Event Details

    Event ID 4688: PowerShell launched with:
    powershell.exe -ExecutionPolicy Bypass -NoProfile -WindowStyle Hidden -Command "Get-Process"

    Event ID 4104: Script block logged:
    Get-Process

**Analysis**

The use of -ExecutionPolicy Bypass and -WindowStyle Hidden can be associated with malicious activity, as attackers often use these flags to evade detection. However, the script block content shows only a standard process enumeration command.

There is no evidence of lateral movement, persistence, credential access, or execution of harmful commands.

**Verdict**

Benign — No malicious activity detected. The command executed was non-threatening, and no follow‑up actions are required.

**Non-Technical Summary**

We observed a PowerShell command running with parameters that can sometimes indicate suspicious behavior. After reviewing the full script content, we confirmed the command only listed running processes and did not perform any harmful actions. No further steps are needed at this time.
