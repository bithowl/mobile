# 🍎 iOS Mobile Penetration Testing & Bug Bounty Resources

Welcome to the **iOS Pentesting & Bug Bounty** repository!  
This repo is a curated collection of tools, resources, techniques, and real-world bug bounty write-ups to help you get started or go deeper into **iOS mobile application security testing**.

---

## 🧭 Overview

Inside this repository, you'll find:

- 🛠️ Tools for static and dynamic analysis of iOS apps
- 📚 Learning resources, books, and courses
- 🐞 Bug bounty reports and write-ups
- ⚙️ Reverse engineering techniques
- 🧪 iOS app testing checklists
- 🔍 Common vulnerabilities in iOS apps
- 📦 Vulnerable apps for practice

---
## 🚀 Getting Started

If you're new to iOS pentesting, follow this roadmap:

1. Understand iOS architecture, sandboxing, and app lifecycle
2. Learn about .ipa files, provisioning profiles, and entitlements
3. Set up a testing environment (e.g., jailbroken device or emulated environment)
4. Perform static and dynamic analysis
5. Use tools like Frida and Objection for runtime testing
6. Read bug bounty reports to understand real-world scenarios

---

## 🛠 Tools for iOS Pentesting

| Tool | Description |
|------|-------------|
| [Frida](https://frida.re/) | Dynamic instrumentation toolkit |
| [Objection](https://github.com/sensepost/objection) | Runtime mobile exploration (no jailbreak needed) |
| [class-dump](http://stevenygard.com/projects/class-dump/) | Dump Objective-C class information |
| [Cycript](http://www.cycript.org/) | Runtime manipulation tool |
| [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF) | Static & dynamic analysis framework |
| [Hopper Disassembler](https://www.hopperapp.com/) | Reverse engineering tool for macOS/iOS apps |
| [Ghidra](https://ghidra-sre.org/) | Open-source reverse engineering platform |
| [iRET](https://github.com/S3cur3Th1sSh1t/iOS-Runtime-Exploration-Toolkit) | Runtime exploration and security assessment |

---

## 📚 Learning Resources

- [OWASP Mobile Security Testing Guide (MSTG)](https://owasp.org/www-project-mobile-security-testing-guide/)
- [iOS Application Security by David Thiel](https://www.manning.com/books/ios-application-security)
- [HackTricks – iOS Pentesting](https://book.hacktricks.xyz/mobile-pentesting/ios-pentesting)
- [The iOS Hacker’s Handbook](https://www.wiley.com/en-us/iOS+Hacker%27s+Handbook-p-9781118204122)
- [PayloadsAllTheThings (iOS)](https://github.com/swisskyrepo/PayloadsAllTheThings)

---
## 🛡 Common Vulnerabilities

- Insecure Data Storage (Keychain, NSUserDefaults)
- Insecure Communication (lack of ATS, MITM)
- Improper Certificate Validation / SSL Pinning
- Sensitive Data in Logs or Screenshots
- Jailbreak Detection Bypass
- Insecure Inter-App Communication (URL Schemes)
- WebView Misuse (JavaScript bridge, insecure content loading)
- Debug Code or Logs in Production

---

## 📱 Practice Apps

| App | Description |
|-----|-------------|
| [iGoat-Swift](https://github.com/OWASP/igoat-swift) | OWASP's iOS testing app in Swift |
| [DVIA-v2](https://github.com/prateek147/DVIA-v2) | Damn Vulnerable iOS App for learning |
| [OWASP iGoat](https://github.com/OWASP/igoat) | Original iGoat Objective-C app |
| [DVIA](https://github.com/appsecco/dvios) *(archived)* | Original Damn Vulnerable iOS App |

---

## 🧩 Bypass Techniques

- SSL Pinning Bypass (Frida scripts, Objection)
- Jailbreak Detection Bypass
- Touch ID / Face ID Bypass (simulating biometric auth)
- Root Detection Evasion
- Runtime Hooking with Frida

---

## 🧾 Cheat Sheets

- [iOS Pentesting Cheatsheet – HackTricks](https://book.hacktricks.xyz/mobile-pentesting/ios-pentesting)
- [Frida iOS Snippets](https://github.com/iddoeldor/frida-snippets)
- [Objection Command Reference](https://github.com/sensepost/objection)

---

## 🤝 Contributing

Contributions are welcome!

If you have:
- Your own write-ups
- New tools or bypass techniques
- Tutorials or blog posts
- Cheat sheets or payloads

Feel free to fork the repo and submit a pull request. Please follow the format and keep things organized.


 ⚠️ **Disclaimer:** This repository is intended for **educational and ethical testing only**.  
 Unauthorized testing on apps or services you do not own is illegal and unethical.

---
