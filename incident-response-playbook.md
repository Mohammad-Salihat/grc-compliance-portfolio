# Incident Response Playbook
**Document Type:** Security Operations Center Playbook  
**Incident Type:** Ransomware Attack  
**Author:** Salihat Mohammad 
**Date:**  
**Organisation:** SecureNow Ltd (Fictional)

---

## About Incident Response

> Incident response is the structured process an organisation follows to detect, contain, and recover from a security incident while minimising damage, cost, and downtime. A formal playbook matters because it converts panic into a sequence of pre-agreed decisions, so people act instead of debating during the worst possible moment to debate. The difference between a company with a playbook and one without is the difference between losing an hour to confusion and losing an hour to action — and in ransomware, every minute of indecision is a minute the malware keeps spreading. Without a plan, the first 60 minutes of a real attack are typically spent on the wrong things: people frantically Googling, arguing about who's in charge, calling each other on the very channel the attacker might be watching, or rebooting infected machines (which can destroy forensic evidence and trigger encryption to finish faster). A playbook exists so that the first 60 minutes are spent doing five or six known-good actions in order, by named people, instead of guessing
---

## About This Incident Type


> Ransomware is malicious software that encrypts files on a victim's systems and demands payment, usually in cryptocurrency, in exchange for a decryption key. It most commonly enters through phishing emails with malicious links or attachments, compromised remote access credentials (especially where MFA is weak or absent), or exploited vulnerabilities in internet-facing software. It is particularly dangerous for SecureNow because the company stores financial data for 40,000 customers in AWS — if the ransomware spreads beyond laptops into that environment, or if data is exfiltrated before encryption (increasingly the norm with "double extortion" ransomware), this becomes both a security incident and a regulatory data breach. The lack of MDM, inconsistent MFA, and absence of any security monitoring also means SecureNow has very little visibility into how far the infection has already spread by the time anyone notices.

---

## SecureNow Ltd - Company Profile

**Company:** SecureNow Ltd  
**Size:** 52 employees, fully remote  
**Sector:** Financial technology (fintech), UK based  
**Infrastructure:** Google Workspace, AWS (hosts customer financial data), Slack, a third party payroll system, a CRM tool  
**Devices:** Mix of company issued laptops and personal devices. No MDM (Mobile Device Management) software is in place, meaning the company cannot remotely wipe or lock devices  
**Security team:** None. The Office Manager handles IT requests. There is no SOC, no SIEM, no dedicated security monitoring  
**Backups:** AWS data is backed up daily. Google Workspace data is not backed up separately outside of Google's own retention. The payroll system vendor manages its own backups but SecureNow has never tested a restore  
**MFA:** Enabled on Google Workspace but optional, 60 percent adoption. No MFA on AWS, CRM, or payroll system  
**Incident history:** A phishing email last year led to one employee clicking a malicious link. No malware was found but the company is not certain because no forensic investigation was done. The employee was asked to change their password  
**Communication:** The company uses Slack for almost all internal communication. There is no alternative communication channel if Slack is compromised  
**Current situation:** It is 7:30am on a Tuesday. The Office Manager has just arrived at her desk and received a message from three employees saying their laptops are showing a red screen with a message demanding payment in Bitcoin to unlock their files. A fourth employee's laptop appears to be unaffected. The Office Manager calls you, the SOC analyst  

---

## Playbook


### Phase 1: Detect and Triage

**Objective:** Confirm the incident is real, understand the initial scope, and establish who is responding.

**Guiding questions before you write your steps:**
- How do you confirm this is ransomware and not a hoax or a software glitch?
- Three laptops are affected. How do you find out if more are affected without triggering further spread?
- The company has no SIEM or security monitoring. What can you actually use to gather information right now?
- Who needs to be notified in the first 15 minutes? Remember, there is no security team

**Your steps for Phase 1:**

| Step | Action | Who | How | Why |
|------|--------|-----|-----|-----|
| 1.1 |Verify ransomware symptoms|Office Manager and affected employees|Request screenshots of ransom notes and collect details on encrypted files and error messages|Visual confirmation of a ransom note with a Bitcoin demand is a strong indicator; screenshots also preserve evidence and avoid further interaction with the infected machine||
| 1.2 |Identify scope: how many devices are actually affected|You (SOC analyst), Office Manager|Call (not Slack/email) every employee — all 52 — and ask a single yes/no question: "Is your screen showing anything unusual?" Maintain a simple shared tracker (spreadsheet, not on a possibly-compromised shared drive)|Phone calls don't rely on infrastructure that might be compromised; a fast headcount establishes scope without waiting for tooling that doesn't exist|
| 1.4 | | | | |
| 1.5 | | | | |

**Your reasoning:** Write 2 to 3 sentences explaining your overall approach in this phase and any judgment calls you made.

> Your answer here

---

### Phase 2: Contain

**Objective:** Stop the ransomware from spreading to more systems and data.

**Guiding questions before you write your steps:**
- The company uses personal devices. You cannot remotely wipe them. What can you do instead?
- Ransomware often spreads through shared network drives. Does SecureNow Ltd have shared drives in Google Workspace or AWS that could be at risk?
- Should you disconnect the affected laptops from the internet immediately? What is the risk of doing that too quickly versus too slowly?
- Slack is potentially compromised or could be used by the attacker to monitor communications. What do you do about this?

**Your steps for Phase 2:**

| Step | Action | Who | How | Why |
|------|--------|-----|-----|-----|
| 2.1 | | | | |
| 2.2 | | | | |
| 2.3 | | | | |
| 2.4 | | | | |
| 2.5 | | | | |

**Your reasoning:** Write 2 to 3 sentences explaining your overall approach in this phase and any judgment calls you made.

> Your answer here

---

### Phase 3: Eradicate

**Objective:** Remove the ransomware from affected systems and identify how it got in.

**Guiding questions before you write your steps:**
- You need to find the root cause. Given the company's history with a phishing click last year and optional MFA, what are the most likely entry points?
- The affected laptops are a mix of company and personal devices. How does this complicate eradication?
- Should you pay the ransom? Think carefully before answering this. There are legal, ethical, and practical dimensions to consider

**Your steps for Phase 3:**

| Step | Action | Who | How | Why |
|------|--------|-----|-----|-----|
| 3.1 | | | | |
| 3.2 | | | | |
| 3.3 | | | | |
| 3.4 | | | | |

**Ransom decision:** Should SecureNow Ltd pay the ransom? Write 4 to 5 sentences arguing your position. Consider: legal guidance in the UK, whether payment guarantees recovery, and what paying signals to attackers.

> Your answer here

---

### Phase 4: Recover

**Objective:** Restore systems and data and return the business to normal operations safely.

**Guiding questions before you write your steps:**
- AWS data is backed up daily. The payroll backups have never been tested. What does that mean for your recovery plan?
- How do you verify that restored systems are clean before connecting them back to the network?
- The business cannot operate if staff cannot access Google Workspace. What is the priority order for recovery?
- 40,000 customers have their financial data on this system. At what point do you tell them something happened?

**Your steps for Phase 4:**

| Step | Action | Who | How | Why |
|------|--------|-----|-----|-----|
| 4.1 | | | | |
| 4.2 | | | | |
| 4.3 | | | | |
| 4.4 | | | | |
| 4.5 | | | | |

**Your reasoning:** Write 2 to 3 sentences explaining your recovery priority decisions.

> Your answer here

---

### Phase 5: Lessons Learned

**Objective:** Understand what happened, why it happened, and how to prevent it happening again.

This is not optional. A company that does not conduct a lessons learned review after an incident is almost certain to have the same incident again.

**Complete the following:**

**Root cause identified:**
What do you believe the most likely entry point was, and what specific weakness made it possible?

> Your answer here

**What went well (if anything):**
Were there any controls or actions that helped limit the damage? Be honest. If nothing went well, say that and explain why.

> Your answer here

**What failed:**
List at least four specific security gaps this incident revealed about SecureNow Ltd.

> Your answer here

**Recommendations:**
For each gap you identified, write one concrete recommendation. Be specific. "Improve security" is not a recommendation. "Enforce MFA on all systems including AWS, CRM, and payroll within 30 days" is a recommendation.

> Your answer here

**Regulatory considerations:**
Under UK GDPR, organisations must report a personal data breach to the ICO within 72 hours of becoming aware of it. Based on what you know about SecureNow Ltd and this incident, does this reporting obligation apply? What happens if they miss the deadline?

> Your answer here

---

## Critical Thinking Questions

Answer each question in 3 to 5 sentences.

**Question 1:** The company uses Slack as its only internal communication channel. During a ransomware incident, attackers sometimes monitor internal communications to understand the response and adapt. What should SecureNow Ltd do about this and why does it matter?

> Your answer here

**Question 2:** The Office Manager is the only person handling IT at this company. During a major incident at 7:30am, she is now being asked to make decisions that would normally require a CISO, legal team, and incident response firm. What does this tell you about the company's security posture and what would you recommend they put in place before the next incident?

> Your answer here

**Question 3:** A journalist contacts SecureNow Ltd asking if they have been hit by ransomware. They heard from a source. The CEO asks you what to say. What do you advise and why?

> Your answer here

---

*Template provided by CyberShift With Funke | Cohort 1 Assignment*
