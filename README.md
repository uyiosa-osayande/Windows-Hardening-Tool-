🛡️ WinGuard — Windows Hardening Tool
PowerShell • Windows 11 Security • Baseline Auditing • Automated Remediation
 
✨ Overview
WinGuard is a PowerShell-based Windows 11 auditing and hardening tool built for my IS2083 Advanced Scripting course.
The tool checks important Windows security settings, identifies weak configurations, applies supported fixes, and produces a report showing the system's security posture.
It was developed and tested inside a Windows 11 Enterprise virtual machine using Oracle VirtualBox.
🔍 What It Does
🔎 Audit	Checks the current system configuration without changing anything
🛠️ Apply	Applies supported security fixes and then re-audits the system
📊 Reporting	Shows PASS/FAIL results, actual values, and an overall security score


The tool organizes checks into two categories:
- 🟦 Microsoft Security Baseline
- 🟪 Advanced Hardening
🛡️ Security Controls
🟦 Microsoft Security Baseline
- ✅ SMBv1 disabled
- ✅ SMB server signing required
- ✅ NTLM hardened
- ✅ User Account Control enabled
- ✅ Minimum password length of 14
- ✅ Account lockout threshold configured
- ✅ Windows Firewall enabled on all profiles
- ✅ Microsoft Defender real-time protection enabled
- ✅ Guest account disabled
- ✅ RDP requires Network Level Authentication
  
🟪 Advanced Hardening
- Microsoft Defender PUA protection
- Attack Surface Reduction rule for Office child processes
- PowerShell Script Block Logging
- LSA Protection (RunAsPPL)
- BitLocker protection status
  
📈 Results
During testing, the tool reached:
Microsoft Security Baseline: 10 of 10 passing
Security Score: 87 / 100
Rating: STRONG
The project also generates timestamped reports that make it easy to compare the system before and after hardening.

💻 Technologies Used
Technology	How I Used It
PowerShell	Security checks, remediation, scoring, and reporting
Windows 11 Enterprise	Target operating system
Oracle VirtualBox	Safe testing environment
Windows Registry	Auditing and modifying security settings
Microsoft Defender	Real-time protection, PUA, and ASR controls
Windows Firewall	Validating and enabling firewall profiles


▶️ How to Run
⚠️ Use a test system or VM. Apply mode changes real Windows security settings.

Open PowerShell as Administrator.
Audit Mode
.\Harden-Windows.ps1
Apply Mode
.\Harden-Windows.ps1 -Mode Apply
If PowerShell blocks local scripts:
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

📁 Project Structure
windows-hardening-tool/
│
├── 🛡️ Harden-Windows.ps1
├── 📖 README.md
│
├── 📂 reports/
│   └── sample-before-after-report.txt
│
└── 📂 screenshots/
    └── security-audit.png
    
🧠 What I Learned
This project gave me hands-on experience with:
- Writing and debugging PowerShell
- Automating Windows security checks
- Reading and modifying registry values
- Working with Microsoft Defender and ASR rules
- Managing Windows Firewall settings
- Understanding the difference between auditing and remediation
- Testing security changes safely inside a virtual machine
- Troubleshooting syntax, execution-policy, and permission issues
- Building readable security reports and scores
  
One of my biggest takeaways was learning to test one control at a time. Running the script after each change made troubleshooting much easier and helped me understand what every security control was actually doing.

🚀 Future Improvements
Some features I would like to add next:
- 🌐 HTML or CSV report exports
- ↩️ An -Undo mode
- 🔐 Additional Microsoft Security Baseline controls
- 🧪 More automated validation checks
- 🔏 PowerShell script signing
- 📊 Severity levels and remediation recommendations
- 
🤖 AI Assistance
AI tools, including ChatGPT, were used as learning and troubleshooting aids to help explain PowerShell syntax, interpret errors, and understand Windows security controls.
All code was reviewed, tested, and validated inside the Windows 11 virtual machine before being included in the project.

👩🏽‍💻 Author
Uyiosa Osayande
Cybersecurity Student
The University of Texas at San Antonio
Built with PowerShell, curiosity, and a lot of debugging. 💻✨

<img width="995" height="564" alt="Screenshot 2026-10-08 111842" src="https://github.com/user-attachments/assets/cec148b0-88e2-462c-9318-a59c55ef955e" />
<img width="1161" height="757" alt="Screenshot 2026-10-07 163441" src="https://github.com/user-attachments/assets/76c37f61-2a66-4260-87f7-8695f8a5e579" />
<img width="568" height="438" alt="Screenshot 2026-10-08 112148" src="https://github.com/user-attachments/assets/39ee7670-f890-4e68-a309-59eded15d2ff" />

