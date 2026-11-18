# TryHackMe: Offensive Security Intro

**Platform:** TryHackMe  
**Room:** Offensive Security Intro  
**Category:** Cybersecurity / Web Application Security  
**Difficulty:** Beginner  
**Environment:** Simulated banking website (FakeBank)  
**Status:** Completed

## 1. Overview

This was my first hands-on cybersecurity practice through TryHackMe.

The exercise introduced me to basic offensive security concepts by simulating an attack against a fictional online banking website called FakeBank.

The objective was to explore the website, discover hidden administrative pages, identify an insecurely exposed function, and understand how poor access control can create security vulnerabilities.

Through this exercise, I gained introductory experience with web reconnaissance, directory enumeration, and identifying potential security weaknesses in a web application.

## 2. Learning Objectives

The main concepts explored during this exercise were:

- Understanding the fundamentals of offensive security.
- Learning how to perform basic web reconnaissance.
- Using directory enumeration to discover hidden website endpoints.
- Identifying exposed administrative pages.
- Understanding authentication and access control weaknesses.
- Recognising the security risks of improperly protected web functions.

## 3. Lab Environment & Tools

| Component | Description |
|---|---|
| TryHackMe | Online cybersecurity learning platform |
| FakeBank | Simulated banking web application |
| Mozilla Firefox | Accessing and interacting with the target website |
| Terminal | Executing reconnaissance commands |
| DIRB | Directory enumeration tool |

## 4. Step-by-Step Lab Procedure

### Step 1: Launch the Lab Environment

Started the simulated desktop environment using the **View Site** button provided in TryHackMe.

The browser opened the FakeBank website at:

`http://fakebank.thm`

I explored the banking dashboard and identified the account information, including the account number (8881) and its negative balance.

### Step 2: Perform Directory Enumeration

Opened the terminal in the simulated desktop environment and used DIRB to scan the target website for hidden directories and pages.

Command used:

```bash
dirb http://fakebank.thm
```

**Purpose:**

Directory enumeration helps identify website resources and endpoints that may not be directly accessible through the website's navigation menu.

### Step 3: Identify the Hidden Administrative Page

Reviewed the directory enumeration results and discovered an additional endpoint:

`/bank-transfer`

This revealed a hidden banking transfer page that was not linked from the main website.

**Key observation:**

The discovery demonstrated how hidden website directories and endpoints can be identified through automated enumeration.

### Step 4: Access the Banking Transfer Page

Returned to Mozilla Firefox and manually appended `/bank-transfer` to the website URL.

Full URL:

`http://fakebank.thm/bank-transfer`

The page displayed a staff banking transfer form without requiring authentication.

This highlighted a potential access control vulnerability: sensitive administrative functionality was accessible without a proper login process.

### Step 5: Execute the Simulated Transaction

Following the lab instructions, used the exposed transfer functionality to perform a transaction:

| Field | Value |
|---|---|
| Sender Account | 2276 |
| Receiving Account | 8881 |
| Transfer Amount | $2,000 |

After submitting the transaction, the account balance became positive.

A confirmation pop-up appeared with the completion flag:

`BANK-HACKED`

<em>This activity was performed entirely within TryHackMe's simulated environment.</em>

## 5. Key Findings

The exercise demonstrated several important security concepts:

**1. Exposed Administrative Endpoints**

Administrative pages should not be accessible simply because someone knows their URL.

**2. Insufficient Authentication**

The banking transfer functionality was accessible without requiring proper authentication.

**3. Weak Access Control**

Sensitive operations should be restricted to authorised users with appropriate permissions.

**4. Directory Enumeration**

Automated tools such as DIRB can help security professionals identify publicly accessible website directories and endpoints.

## 6. Skills & Knowledge Gained

Through this exercise, I gained introductory exposure to:

- Basic Linux terminal usage.
- Directory enumeration using DIRB.
- Web application reconnaissance.
- Identifying hidden website endpoints.
- Understanding authentication mechanisms.
- Recognising access control vulnerabilities.
- Understanding basic offensive security methodology.

## 7. Personal Takeaways

This exercise helped me understand how seemingly small security weaknesses can expose sensitive website functionality.

One of my biggest takeaways was that a website does not necessarily become secure just because certain pages are hidden from its navigation menu.

I also learned how directory enumeration can help uncover resources that are not immediately visible to website visitors.

As my first practical cybersecurity exercise, this gave me a better understanding of how offensive security techniques are used to identify vulnerabilities and why proper authentication and access control are important in web application security.
**Lab Status:** Completed  
**Learning Journey:** Cybersecurity Fundamentals
