---
title: "Massive LinkedIn Account Hijacking Campaign: Methods, Evidence and Defense"
date: 2023-08-17T09:00:00+05:30
draft: false
github_link: ""
author: "D0V0"
tags:
  - LinkedIn
  - Credential Stuffing
  - Cyber Threat Intelligence
  - Incident Response
  - CiberSecUNI
  - Stealer
image: /images/font-linkedin-blog.jpg
description: "A massive surge of LinkedIn account hijackings is underway. Learn how attackers are taking control of accounts, the methods behind the breaches, and what you can do to protect yourself."
toc: true
---

## 🚨 Ongoing Threat: LinkedIn Under Attack

Recently, a **global surge of LinkedIn account hijackings** has been reported across social media platforms like Twitter (X), Reddit, Facebook, and even university circles like **CiberSecUNI**.

Cybersecurity firm [Cyberint, a Check Point Company](https://www.linkedin.com/company/cyberint/) highlighted a dramatic spike in account compromises, stating:

> _"Although LinkedIn has yet to release an official statement, support request queues are growing rapidly."_ — *Coral Tayar*

![LinkedIn hacked tweet screenshot](https://media.licdn.com/dms/image/v2/D4E12AQGVr53O-nxB6Q/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1692247319058?e=1750291200&v=beta&t=HjN6p3DHOO2KZhjSZGrXVZa8_Z4OY3dewnAb3d_ZCsw)

---

## 🔎 Alarming Trends and Global Impact

Google Trends confirms a **5000% increase in search queries** for "LinkedIn hacked" and "LinkedIn account recovery" in 2023.

![Google Trends chart](https://media.licdn.com/dms/image/v2/D4E12AQFrgrEe5csXyw/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1692247510189?e=1750291200&v=beta&t=7cfPDOg2TXYGCvOcCdihiBEKV4NR8eXf66dNkvySX8I)

Numerous victims—ranging from tech professionals to journalists—have reported unauthorized access, removal of recovery emails and phone numbers, and long delays in LinkedIn support responses.

---

## 🧠 Attack Methodology: How Are Accounts Being Compromised?

While LinkedIn hasn't issued an official post-mortem, here’s what **CiberSecUNI's Threat Intelligence team** believes:

### Initial Access Vectors

#### 1. **Credential Stuffing**
The **most likely scenario** is the reuse of leaked credentials. Attackers take usernames and passwords from previous breaches (often sold on the dark web) and try them across services—including LinkedIn.

![Credential stuffing explanation](https://media.licdn.com/dms/image/v2/D4E12AQH2ykB6rCfHOQ/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1692248154897?e=1750291200&v=beta&t=pOfoaARR57sLkPTUnoK4pjrldYVQppSX_xvhE3hN9UQ)

> Many hijacked accounts **lacked multi-factor authentication (MFA)** and used weak or reused passwords.

#### 2. **Session Hijacking**
Some cases suggest attackers may be stealing **session cookies** from infected browsers or malicious software downloads.

![Session hijacking diagram](https://media.licdn.com/dms/image/v2/D4E12AQEO2Yji9AITzg/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1692248825024?e=1750291200&v=beta&t=LkdelybbqjYhwQproaQtuOssgOCdLdbWS7-QIPgLNV8)

Once they obtain the victim's session ID, attackers can impersonate a valid session and bypass login credentials altogether.

---

## 🛠 Persistence & Takeover Techniques

Once inside, attackers **immediately update recovery emails**, add MFA methods under their control, and in some cases even **lock the original user out permanently**.

![Example of malicious email update](https://media.licdn.com/dms/image/v2/D4E12AQFphuP9JK7KnQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1692248974765?e=1750291200&v=beta&t=BfLScTkAAb2DfStf6Q8qmeoivBTtrlH4GCDxheEDZt4)

In many scenarios, the attacker adds a secondary email (often from Russian or temporary domains) and changes the name, profile picture, and bio to make recovery even harder.

---

## 🎯 What Are the Attackers Doing?

After hijacking, attackers move into the **exploitation phase**:

- **Extortion**: Demanding ransom to return control of the account.
- **Phishing Campaigns**: Using trusted profiles to spread malware links or fake job offers.
- **Crypto Scams**: Some accounts are transformed into fake influencers promoting scams.

---

## ✅ Recommendations to Protect Yourself

1. **Audit Your Account**  
   Regularly check LinkedIn login locations and active sessions. Revoke any suspicious ones.

2. **Use Unique, Strong Passwords**  
   Avoid names, dates, or reused credentials. Preferably use a trusted **password manager** (not your browser).

3. **Enable 2FA**  
   Activate **two-factor authentication** using an authenticator app—not SMS—for stronger protection.

4. **Check for Data Breaches**  
   Use [haveibeenpwned.com](https://haveibeenpwned.com/) or similar services to know if your email/passwords were leaked.

5. **Be Wary of Suspicious Activity**  
   Any unauthorized password/email change notification should be treated as a red flag.

---

## 📢 Final Thoughts

This campaign shows how **reusing passwords** and not enabling 2FA can make even professional platforms like LinkedIn a soft target. While LinkedIn investigates, your best defense is **proactive account hygiene** and being aware of current threat tactics.

Stay safe and keep your profiles locked down 🔐

---

*Written by D0V0 | CiberSecUNI Team | August 2023*

