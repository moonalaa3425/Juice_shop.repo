# Juice_shop.repo
The primary goal of this penetration test was to evaluate the security posture of the organization’s web applications and APIs. Several critical vulnerabilities, including SQL Injection and Cross-Site Scripting (XSS), were discovered. These vulnerabilities pose a high risk to the organization as they could allow unauthorized access to sensitive data and compromise system integrity.
To mitigate these risks, we recommend implementing strict input validation, regular software updates, and periodic security testing. These steps will reduce the likelihood of exploitation and improve the overall security of the system . Since this scenario is based on a gray-box testing approach, where the tester has partial knowledge of the application or system (e.g., having access to some documentation or limited internal information but not full access to  source code . 
This approach provided a comprehensive understanding of potential vulnerabilities from both external and internal perspectives.
Combining automated tools with manual testing ensured accuracy and depth in identifying security weaknesses.


Enumeration to find the admin path is a process where an attacker attempts to discover hidden or secured paths, directories, or files that might allow them to access administrative areas of a website or application. This type of enumeration typically uses automated tools or manual methods to probe the system for potential admin access points. We used the tools (inspect) to find the admin path which was *administration* 
Then we get the access to be an admin in juice shop website



Brute Force on Admin Credentials:
The attacker discovers the admin login page of the application and uses Burp Suite's Intruder tool to perform a brute-force attack. The attacker targets the admin login, using a valid email (e.g., admin@juice-sh.op) and systematically tries different password combinations. Since the application lacks important security measures like rate-limiting or account lockout mechanisms, the attacker is able to send multiple login attempts without any restrictions. Eventually, the attacker successfully guesses the correct password, gaining admin access to the application, which gives them full control over it.


Here’s a simpler explanation of XSS and how you can demonstrate it on Juice Shop:

Cross-Site Scripting (XSS) Attack:

What is XSS?

XSS (Cross-Site Scripting) is a type of vulnerability that allows an attacker to inject malicious scripts into web pages viewed by other users. These scripts run in the user’s browser and can steal sensitive information, like cookies or session data, hijack accounts, or display malicious content.

How the XSS Attack Works:

When a website takes user input (like in a search bar, comment box, or any form), if the website doesn’t properly clean and filter that input, an attacker can insert a script. This script could look something like:

<script>alert('XSS Attack');</script>

When other users visit a page that includes the malicious input, the script will run in their browser. In some cases, this could allow the attacker to steal data or perform actions on behalf of the user.

Exploiting XSS in Juice Shop:

In Juice Shop, we can test for XSS by looking for places where we can enter input, like the search bar or contact form. If the app doesn’t clean this input, we can inject a script that runs when we visit a page.

For example, we might try entering a simple script in a form field like this:

<script>alert('XSS Test');</script>

If Juice Shop doesn’t sanitize the input properly, the alert will pop up in our browser, showing that the attack was successful.

How We Fixed It:

To prevent XSS attacks, websites need to sanitize the input from users. This means that any potentially dangerous scripts are removed or encoded before being shown on the page.
	1.	Sanitization: The app should make sure to remove or change any special characters (like <, >, " and ') in the user input that might allow a script to be executed.
	2.	Escaping Output: When showing the input on the website, it should be escaped so that it’s treated as plain text, not code.
	3.	Content Security Policy (CSP): A security policy that can prevent malicious scripts from running in the first place by restricting which sources of scripts are allowed.

Conclusion:

XSS is a dangerous vulnerability because it can let an attacker run malicious scripts in users’ browsers, leading to data theft or account hijacking. In Juice Shop, we tested how easily a simple script could be injected and executed, and we discussed how important it is for websites to sanitize input and escape output to prevent such attacks. By following these best practices, developers can make their sites safer for users.


Video links explaining the project:

1-
https://drive.google.com/file/d/1iw91xTtEzuY8z4qhomnIEfkb0-so02B9/view?usp=drivesdk

2-
https://drive.google.com/file/d/1_UvUMDCUdCVm-YPPmTd5SplPXLhb-SS4/view?usp=drivesdk

3-
https://drive.google.com/file/d/1fuyUn3fx2ZVqwL-madrSUTSOih-nipYM/view?usp=drivesdk

