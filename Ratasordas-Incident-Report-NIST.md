# **Ratasordas Technologies: Post-Incident Report and Strategic Plan**

### **Project Overview**

This document serves as a post-incident report and strategic plan for Ratasordas Technologies, a fictional SaaS company specializing in a wordless, graphic-based app. The project analyzes a recent security incident that rendered the company's app unusable and provides strategic recommendations for improving the company's security posture using the National Institute of Standards and Technology (NIST) Cybersecurity Framework 2.0.

### **Incident Narrative**

The security event began when a known threat actor was spotted on company premises by the CEO. The person was quickly escorted out by security. The cybersecurity team was alerted and began proactive monitoring for any unusual activity. The next morning, the team discovered that none of the app's graphics were displaying for users, rendering the application useless.

Upon investigation, the team determined that the point of failure was the application developer's server. The malicious actor had gained unauthorized access to this server and deleted the graphics. The developer was contacted immediately and secured the server. With the server secured, the graphics team worked with the developer to re-upload the images from a backup on a separate server partition.

In the **post-incident review**, the team found that the server's security settings were configured for non-critical assets and lacked Multi-Factor Authentication (MFA), which allowed the threat actor to gain access.

### **Incident Analysis: The Core Functions**

The following sections provide a tactical analysis of the incident, using the six core functions of the NIST framework: **Govern**, **Identify**, **Protect**, **Detect**, **Respond**, and **Recover**.

### **Incident Timeline**

| Date/Time | Event |
| :---- | :---- |
| **June 13, 2021 12:40 pm** | Threat actor was identified on company premises. |
| **June 13, 2021 1:10 pm** | Threat actor was physically escorted from the premises. |
| **June 13, 2021 1:30 pm** | The cybersecurity team received a debriefing on the threat actor and initiated proactive monitoring. |
| **June 14, 2021 7:12 am** | A cybersecurity analyst discovered that the application was non-functional. |
| **June 14, 2021 7:32 am** | The first user complaints regarding the application's functionality were received. |
| **June 14, 2021 8:30 am** | The point of failure was located on the developer's server, and the developer was immediately contacted. |
| **June 14, 2021 8:45 am** | The developer's server was successfully secured. |
| **June 17, 2021 10:38 am** | The application's graphics were fully restored, and the app was back in service. |

### **1\. Govern**

The govern function focuses on how an organization makes and carries out its cybersecurity risk management decisions at a strategic level.

* **Analysis:** This incident exposed a significant lack of governance, particularly regarding third-party vendor relationships. The company's policy allowed a contractor to manage a critical server with insufficient security controls. It was a failure of oversight to proactively define security expectations and ensure they were met.  
* **Risk:** Without a formal governance policy, the company remains exposed to third-party vulnerabilities that could lead to significant financial loss and reputational damage.

**Strategic Recommendations:** We will establish a formal **vendor risk management (VRM) program** to ensure all third-party vendors and contractors adhere to a minimum set of security requirements, including mandatory **Multi-Factor Authentication (MFA)** and a server hardening policy. **This process will be proactive, with the organization setting clear security expectations for all assets based on their criticality, rather than relying on vendors to make that determination.**

### **2\. Identify**

The identify function is about understanding assets, potential risks, and the business environment.

* **Type of Attack:** This was a **targeted attack** involving **data manipulation** and **indirect denial of service**. The attacker corrupted data (the graphics), which in turn rendered the application unusable, effectively denying service to all users.  
* **Affected Assets:** The primary affected asset was the **application's image data**, hosted on the contractor's server. This in turn rendered the public-facing application useless.  
* **Vulnerability:** The root cause of the incident was a lack of **MFA** on the server and its insecure configuration, which allowed the threat actor to gain unauthorized access and delete the graphics.

**Strategic Recommendations:** We will conduct a comprehensive asset inventory and classification, identifying all critical assets and the systems that support them. We will then perform a full vulnerability scan on all internal and third-party systems to identify and remediate any potential weaknesses.

### **3\. Protect**

The protect function focuses on implementing safeguards to mitigate risks.

* **Preventative Measures:** The incident could have been prevented by a more robust security posture. The lack of **MFA** and the use of settings common for non-critical assets were the primary failures.  
* **Controls Implemented Post-Incident:** The application developer immediately implemented **MFA** and hardened the server using **end-to-end encryption**, which are vital steps to prevent a similar attack in the future.

**Strategic Recommendations:** We will implement a policy of **zero trust** for all internal and third-party systems. This means no user, even a verified one, is trusted by default. Access will be granted on a least-privilege basis and verified continuously.

### **Cybersecurity Training Plan**

This is a proposed security training plan for Ratasordas Technologies, designed to address the human element of security and prevent future incidents like the recent data manipulation attack. The plan is a key component of the strategic recommendations from the post-incident report.

* **Phishing and Social Engineering**  
  * **Objective:** To teach employees how to identify and report phishing attempts, a common entry point for malicious actors.  
  * **Content:** This training will include interactive modules on recognizing suspicious emails, identifying social engineering tactics, and the importance of not clicking on unknown links or downloading suspicious attachments.  
  * **Frequency:** Quarterly. The training will be followed by simulated phishing tests to measure employee readiness and identify areas for improvement.  
* **Third-Party Risk Management**  
  * **Objective:** To educate employees on their role in managing third-party risks, especially when interacting with contractors and vendors.  
  * **Content:** This module will cover the importance of vetting third-party access, not sharing credentials, and understanding the company's vendor risk management (VRM) program. It will also emphasize the need to report any unusual activity or behavior from a third party.  
  * **Frequency:** Annually.  
* **Data Handling and Access Control**  
  * **Objective:** To reinforce the principles of **least privilege** and secure data handling.  
  * **Content:** This training will focus on the importance of only accessing data necessary for one's job and the proper handling of sensitive data. It will also cover the company's password policy and the importance of using **Multi-Factor Authentication (MFA)** on all critical assets.  
  * **Frequency:** Annually, with a mandatory review of the policy every six months.  
* **Incident Reporting**  
  * **Objective:** To empower employees to be the first line of defense by knowing how to report a potential security incident.  
  * **Content:** This training will provide a clear, step-by-step guide on what constitutes a security incident and the proper channels for reporting it. The training will emphasize that all potential incidents, no matter how small, should be reported immediately.  
  * **Frequency:** As needed, with an annual refresher.

This comprehensive training plan, combined with the technical and procedural improvements outlined in the incident report, will significantly strengthen Ratasordas Technologies' overall security posture.

### **4\. Detect**

The detect function is about identifying the occurrence of a security incident.

* **Detection Method:** The incident was initially detected through **external observation**, as users likely reported that the app's graphics were not loading. The cybersecurity staff, already on high alert due to the threat actor's presence, proactively confirmed the issue.  
* **New Capabilities:** The team’s post-incident actions demonstrated a strong ability to investigate. By analyzing the application, they were able to pinpoint the exact **point of failure** (the developer's server) and determine the root cause of the issue.

**Strategic Recommendations:** We will implement a centralized logging and monitoring system for all critical assets, including third-party ones. This will enable real-time alerting on unusual activity, such as a large number of file deletions or changes in a critical database.

### **5\. Respond**

The respond function is about taking action regarding a detected security incident.

* **Initial Response:** The team’s response was swift and effective. Key actions included:  
  * Removing the employee's access to critical digital assets.  
  * Placing the cybersecurity staff on alert.  
  * Identifying the application developer's server as the point of failure.  
* **Containment:** The most critical containment action was communicating with the developer to **secure the server**, which stopped the unauthorized access.

**Strategic Recommendations:** We will create a formal, written **Incident Response Plan (IRP)** that includes a clear chain of command and communication protocols. This plan will include specific procedures for third-party incidents and a list of key contacts for all external partners.

### **6\. Recover**

The recover function focuses on restoring services after an incident.

* **Recovery Actions:** The recovery process was successful because a **backup of all critical files was on the company's master hard drive and its assets backup system**. The graphics team then worked with the developer to re-upload the images from this internal backup. The re-upload process, however, took three days.  
* **Time to Recovery:** While the recovery was successful, the team should analyze the time it took to restore the app's functionality to establish a baseline **Recovery Time Objective (RTO)** for future incidents.

**Strategic Recommendations:** We will ensure all critical assets, including those managed by third-party contractors, have a formal, tested backup and recovery plan. We will also perform regular **disaster recovery tests** to ensure that all teams can quickly and efficiently restore data from a backup.

### **Lessons Learned**

* **Strategic Governance Failure:** The incident highlighted a critical failure in governance. We learned that we cannot rely on a third-party vendor to determine the criticality of an asset. The wordless nature of our app makes graphics a high-priority asset, and as such, we must be proactive in setting and enforcing security expectations for all vendors.  
* **Operational Process Failure:** The three-day recovery time was not due to a technical failure but a process failure. The lack of a standardized naming convention for graphics meant the team had to manually match and re-upload each file, which was a time-consuming and inefficient process.  
* **Business Impact and Remediation:** This delay was unacceptable from a business perspective, as it rendered our core product unusable and likely led to a loss of user trust and potential revenue. A new policy has since been implemented to use a standardized naming nomenclature for all graphics. This change allows for a near-immediate recovery in the future, dramatically reducing the potential for business disruption.

### **Skills Demonstrated**

This project showcases a range of cybersecurity and professional skills:

* **Incident Response:** The ability to respond to a live security incident by identifying, containing, and recovering from an attack.  
* **Threat Analysis:** Understanding the attack vector and the vulnerabilities that were exploited.  
* **Vendor Risk Management:** Recognizing the importance of a formal process for managing third-party security.  
* **Strategic Planning:** Translating a security event into a strategic, long-term plan for improving security posture.  
* **NIST Framework Application:** Using an industry-standard framework to structure and analyze a cybersecurity incident.  
* **Business Acumen:** Understanding the impact of a security incident on a company's business operations and brand reputation.
