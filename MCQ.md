## 🔍 Minesweeper Web App Security Audit - MCQ 📝

**Instructions:** Choose the best answer for each multiple-choice question.

---

**1.  Which browser Developer Tools tab is MOST useful for observing the files loaded by a web application and their types?** 🌐

    a) Console
    b) Sources
    c) Network  ✅
    d) Application

    *Explanation:* The `Network` tab in browser Developer Tools specifically monitors and records all network requests made by the browser, including files (scripts, stylesheets, images), their types, and loading sequence. This is crucial for understanding what resources a web application is loading.

---

**2.  What type of information can be found in the "Application" (or "Storage") tab of browser Developer Tools for the Minesweeper game?** 💾

    a) JavaScript code of the game
    b) HTTP security headers
    c) Cookies and Local Storage data  ✅
    d) Network requests made by the game

    *Explanation:* The `Application/Storage` tab is designed to inspect client-side storage mechanisms. For the Minesweeper game, it reveals data stored in `Local Storage`, such as game state, settings, and high scores, which is relevant to understanding client-side data persistence.

---

**3.  Which Nmap command is used in the audit guide to perform a fast scan of the Minesweeper web application, focusing on the most common ports?** 💻

    a) `nmap -A -T4 ig97eo8f6hq2dq0e.vercel.app`
    b) `nmap -sV ig97eo8f6hq2dq0e.vercel.app`
    c) `nmap -T4 -F ig97eo8f6hq2dq0e.vercel.app` ✅
    d) `nmap -p 1-65535 ig97eo8f6hq2dq0e.vercel.app`

    *Explanation:* The command `nmap -T4 -F ig97eo8f6hq2dq0e.vercel.app` uses `-T4` for faster timing and `-F` for a fast scan, focusing on well-known ports. This is suitable for a quick reconnaissance in a friendly audit, efficiently identifying common open ports.

---

**4.  According to the audit report, which of the following HTTP security headers was found to be MISSING from the Minesweeper web application's responses?** 🛡️

    a) `X-Frame-Options`
    b) `X-Content-Type-Options`
    c) `Content-Security-Policy` (CSP) ✅
    d) `Referrer-Policy`

    *Explanation:* The audit specifically identified the absence of `Content-Security-Policy` (CSP) and `Strict-Transport-Security` (HSTS) headers.  `Content-Security-Policy` (CSP) is a key header for mitigating client-side attacks like Cross-Site Scripting (XSS), and its absence was a notable finding.

---

**5.  What is the PRIMARY purpose of the `X-Frame-Options: DENY` HTTP security header that was found to be implemented in the Minesweeper web application?** 🖼️

    a) To prevent Cross-Site Scripting (XSS) attacks
    b) To prevent Clickjacking attacks ✅
    c) To enforce HTTPS connections
    d) To prevent MIME-sniffing vulnerabilities

    *Explanation:*  `X-Frame-Options: DENY` is specifically designed to prevent **Clickjacking attacks** by instructing the browser not to allow the webpage to be embedded within a frame (iframe), especially from different origins, thus protecting against UI redress attacks.

---

**6.  Which tool from the audit guide is an automated web application vulnerability scanner used to identify potential security issues in the Minesweeper game?** 🤖

    a) Nmap
    b) Browser Developer Tools
    c) ZAP by Checkmarx  ✅
    d) `View Page Source`

    *Explanation:* `ZAP by Checkmarx (Zed Attack Proxy)` is the designated automated web application security scanner in the audit guide. It is used to perform automated vulnerability scanning and identify potential security weaknesses, complementing manual checks.

---

**7.  What was the RISK level assigned by ZAP to the "Missing Anti-clickjacking Header" alert in the audit report for the Minesweeper application?** ⚠️

    a) High
    b) Medium
    c) Low ✅
    d) Informational

    *Explanation:*  ZAP classified the "Missing Anti-clickjacking Header" alert as **"Low Risk"** in the context of the Minesweeper application.  This suggests that while clickjacking protection is a security best practice, ZAP assessed the immediate risk as low for this specific, simple game, though still worth noting for improvement.

---

**8.  The Minesweeper web application primarily utilizes which type of storage for game data persistence, as identified in the audit?** 🗄️

    a) Server-side database
    b) Cookies
    c) Local Storage ✅
    d) Session Storage

    *Explanation:* Through reconnaissance using browser Developer Tools, the audit identified that the Minesweeper web application uses `Local Storage` to store game state, settings, and high scores directly within the user's browser, providing persistent client-side data storage.

---

**9.  Which security benefit does implementing `Content-Security-Policy` (CSP) HTTP header PRIMARILY provide for a web application?** 🔒

    a) Protection against Clickjacking attacks
    b) Enforcement of HTTPS connections
    c) Mitigation of Cross-Site Scripting (XSS) attacks ✅
    d) Prevention of MIME-sniffing vulnerabilities

    *Explanation:* `Content-Security-Policy` (CSP) is a powerful HTTP header that primarily focuses on mitigating **Cross-Site Scripting (XSS) attacks**. It allows web application owners to control the resources the browser is allowed to load, significantly reducing the attack surface for XSS.

---

**10. In the context of a basic, client-side game like Minesweeper, what is the MOST significant security benefit of implementing security best practices, even if the immediate risks seem low?** 🤔

    a) To achieve compliance with strict regulatory requirements
    b) To prevent server-side database breaches
    c) To demonstrate secure development principles and protect users in a broader sense, setting a good security standard for future, potentially more complex applications. ✅
    d) To dramatically improve the game's performance and loading speed

    *Explanation:* While the immediate security risks for a simple client-side game may be low, implementing security best practices, like CSP and HSTS, is still valuable for **demonstrating secure development principles** and setting a **good security standard**. This proactive approach is essential for building a strong security foundation and mindset that will be crucial for more complex and higher-risk web applications in the future.

---
