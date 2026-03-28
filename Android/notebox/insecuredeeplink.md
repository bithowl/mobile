Insecure Deep Links in Android: How Apps Get Hacked
Deep links are meant to make life easy.
Tap a link → open a specific screen inside an app.
No navigation. No friction.
But here’s the problem:
If deep links aren’t secured properly… attackers don’t need to break your app.
They just walk in through the front door.
The Story (Hook)
You receive a link on WhatsApp:
mybank://transfer?to=attacker&amount=10000
Looks harmless. Maybe even legit.
You tap it. Your banking app opens…
And suddenly — money is being transferred.
No login screen.
No confirmation.
No warning.
That’s not magic.
That’s an insecure deep link.
What Are Deep Links?
Definition
Deep links allow external sources (browser, apps, emails) to open specific screens inside an Android app.
Types of deep links:
•	Custom Scheme
myapp://profile/123
•	App Links (HTTP/HTTPS)
https://example.com/profile/123
They are defined in AndroidManifest.xml using intent filters.
Why Deep Links Exist
Apps use deep links to:
•	Improve user experience 
•	Enable quick navigation 
•	Support marketing campaigns 
•	Integrate with other apps 
They’re powerful.
But power + no validation = vulnerability.
Where Things Go Wrong
Deep links are external input.
And external input is untrusted.
If apps:
•	Don’t validate parameters 
•	Don’t check authentication 
•	Don’t verify source 
Then attackers can:
→ Trigger internal app logic
→ Bypass security flows
→ Execute actions silently
Common Vulnerability Patterns
1. Missing Authentication Check
Deep link opens a sensitive screen:
myapp://wallet
If the app:
•	Doesn’t check login state 
•	Directly loads the screen 
Attacker can:
→ Bypass authentication
2. Parameter Tampering
Example:
myapp://transfer?to=user123&amount=100
Attacker modifies:
myapp://transfer?to=attacker&amount=10000
If no validation:
→ Unauthorized transaction triggered
3. IDOR via Deep Links
Example:
myapp://profile?id=123
Attacker tries:
myapp://profile?id=124
If no authorization check:
→ Access other users’ data
Classic Insecure Direct Object Reference (IDOR).
4. Open Redirect Abuse
Example:
myapp://redirect?url=https://evil.com
App blindly redirects.
Result:
•	Phishing 
•	Token leakage 
•	Session hijacking 
5. Deep Link + Exported Component Combo
Deep links often hit:
•	Exported Activities 
If both are insecure:
→ Full attack chain unlocked 
Real Attack Flow
1.	Attacker crafts malicious deep link 
2.	Sends via SMS / email / app 
3.	Victim taps link 
4.	App processes it blindly 
5.	Sensitive action executed 
No exploit.
No reverse engineering needed.
Just social engineering + bad validation.
Why This Is Dangerous
•	Works on non-rooted devices 
•	Requires zero technical skill from victim 
•	Often bypasses UI-based protections 
•	Hard to detect 
This is why deep link bugs are:
High impact, low effort vulnerabilities
How Bug Hunters Test Deep Links
Step 1: Find Deep Links
Check:
•	AndroidManifest.xml 
•	Intent filters 
•	Decompiled code 
Step 2: Test Entry Points
Use:
adb shell am start -a android.intent.action.VIEW -d "myapp://test"
Step 3: Fuzz Parameters
Try:
•	Changing IDs 
•	Injecting values 
•	Removing parameters 
•	Adding unexpected inputs 
Step 4: Observe Behavior
Ask:
•	Does it require login? 
•	Can I access other users’ data? 
•	Can I trigger actions directly? 
How Attackers Exploit Deep Links
•	Social engineering (send malicious links) 
•	Combine with phishing 
•	Trigger hidden app functionality 
•	Chain with API vulnerabilities 
Developer Defense Strategy
1.Validate All Inputs
Treat deep link data like:
•	User input 
•	API input 
Never trust it.
2. Enforce Authentication
Before opening sensitive screens:
•	Check login state 
•	Require re-auth if needed 
3. Implement Authorization Checks
Even if user is logged in:
→ Verify access rights
4. Restrict Exported Components
Only expose what is necessary.
5. Use App Links (Verified Domains)
Prefer:
•	HTTPS links with domain verification 
This prevents:
→ Other apps hijacking your links
Why This Matters
Deep links are everywhere:
•	Payments apps 
•	Social media 
•	E-commerce 
•	Banking 
And many apps:
•	Trust them too much 
•	Validate them too little 
For bug hunters:
This is a goldmine.
Quick Recap
•	Deep links allow external access into apps 
•	They are untrusted input 
•	Missing validation = major vulnerabilities 
•	Common issues: IDOR, auth bypass, parameter tampering 
•	Exploitation is simple and impactful 
Final Thought
Deep links are like VIP entry passes.
They’re supposed to make access easier.
But if you don’t check who’s holding the pass…
you’ve just invited the attacker inside.

