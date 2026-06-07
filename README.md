># TryHackMe - Phishing Analysis Fundamentals Walkthrough

## Introduction

Phishing Analysis Fundamentals is a beginner-friendly TryHackMe room that introduces the basics of email analysis, email headers, phishing indicators, and attachment investigation. The room teaches how attackers use emails to trick users into revealing sensitive information.

---

## Task 1 – Anatomy of an Email Address

Learn the basic structure of an email address:

* Username
* @ Symbol
* Domain Name

### Example

Email: `hatsalesman@tryhatme.com`

**Answer:** `tryhatme.com`

---

## Task 2 – Email Protocols

Understand the protocols used in email communication.

### Answers

1. Which protocol sends emails?

   * **SMTP**

2. Which service looks up mail servers?

   * **DNS**

3. Which protocol synchronizes emails across multiple devices?

   * **IMAP**

---

## Task 3 – Email Headers

Open `email1.eml` in Thunderbird and view the message source using:

`View → Message Source` or `Ctrl + U`

### Findings

* Subject: **Help protect your budget by protecting your home**
* X-Originating-IP: **43.255.56.161**

This demonstrates how email headers contain valuable information such as sender details, IP addresses, and authentication results.

<img width="947" height="886" alt="image" src="https://github.com/user-attachments/assets/0b5bae7d-7b6b-4020-b588-1a4445841f94" />

---

## Task 4 – Email Body and Attachments

Open `email2.txt` and inspect the attachment information.

### Findings

* Content-Type: **application/pdf**
* Filename: **zmqpalgh.pdf**
<img width="654" height="521" alt="image" src="https://github.com/user-attachments/assets/23e03620-7cff-4ca4-8ddc-c416b6bbdbbb" />

The attachment was encoded in Base64 format.


### Decoding

The Base64 content was decoded using CyberChef and converted back into a PDF document.

### Hidden Flag
<img width="1280" height="615" alt="image" src="https://github.com/user-attachments/assets/f3d05601-ad63-4ecd-924d-6e38ff175f06" />

<img width="421" height="139" alt="image" src="https://github.com/user-attachments/assets/96ccf0fb-f74b-475e-9158-889f11fc03cd" />

```text
THM{BENIGN_PDF_ATTACHMENT}
```

---

## Task 5 – Types of Phishing

The room explains common phishing techniques:

* Spam
* Phishing
* Spear Phishing
* Whaling
* Smishing
* Vishing

### Common Indicators

* Urgent language
* Spoofed sender addresses
* Suspicious links
* Malicious attachments
* Requests for sensitive information

---

## Task 6 – Investigating a Phishing Email

Open `email3.eml` and analyze the message source.

### Findings
<img width="900" height="842" alt="image" src="https://github.com/user-attachments/assets/64dcbf9a-740d-478b-b036-bc649ae30656" />
<img width="633" height="502" alt="image" src="https://github.com/user-attachments/assets/12becf1c-470a-49b8-9b64-8d841f300ec6" />


**Spoofed Organization**

* Home Depot

**Sender Email**

* [support@teckbe.com](mailto:support@teckbe.com)

**Defanged X-Originating-IP**

* 103[.]234[.]236[.]83

**Authentication Results Server**

* atlas102.free.mail.gq1.yahoo.com

### Analysis

The email impersonated Home Depot while using an unrelated sender domain. This is a common phishing technique used to trick users into believing the email is legitimate.

---

## Task 7 – Conclusion

The room covered:

* Email structure
* Email protocols
* Email headers
* Email body analysis
* Attachment reconstruction
* Phishing indicators
* Real-world phishing investigation

### Final Answer

**BEC = Business Email Compromise**

---

## Summary

This room provides a strong foundation in phishing analysis by teaching how to inspect email headers, analyze attachments, identify spoofed senders, and recognize common phishing techniques. The practical investigation of phishing emails helps build essential skills required for SOC Analyst and Blue Team roles.


<img width="1125" height="731" alt="image" src="https://github.com/user-attachments/assets/e60b4b5e-ec71-42e4-a80a-ab0a97aaa06f" />
