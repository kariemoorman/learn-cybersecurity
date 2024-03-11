## AppSec: Application Security

### Table of Contents
- [API Security](#api-security)


----

## API Security
- [3 Pillars of API Security](#3-pillars-of-api-security)
- [Securing API Servers](#securing-api-servers)
- [OWASP API Top 10](#owasp-api-top-10)

<br>

### 3 Pillars of API Security

<details>
  <summary> <b>Governance: Developing Secure APIs</b> </summary>
  
  <ul>
    <li><b>Benefits: </b>Establish consistency, Set expectations, Establishing standard processes, Enforcing security</li>
    <li><b>Awareness: </b>Know your APIs (e.g., infrastructure), Know your data (e.g., access), Know your risks</li>
    <ul>
      <li>Get Full Inventory of APIs: Purpose, Owner, Documentation</li>
      <li>Standardize & Enforce API Deployment Process: Ensure APIs are deployed after proper validation and approval, Enforce governance via Gateway & Marketplace</li>
      <li>Mandate API Documentation: Ensure APIs are consistent and reusable, Define documentation requirements</li>
      <li>Create API Development Standards: Style guides, Authentication requirements, Versioning, PII tracking</li>
      <li>Threat Modeling: 
        <ul>
          <li>Identify: APIs, Business flows, Data, Access Paths</li>
          <li>Assess: Vulnerabilities, Logic flaws, Access controls, 3rd party risk</li>
          <li>Probability: Examine likelihood of attack</li>
          <li>Impact: Understand Damage, Loss, Consequences of attack</li>
          <li>Mitigation: Develop a plan to address the risk</li>
        </ul>
      </li>
    </ul>
    <li><b>Policy: </b>Engineering process (e.g., dev & deploy), API documentation, Style guides</li>
    <ul>
      <li>Design Guides: Promote Governance, Consistency</li>
        <ul>
          <li>Authentication: type (basic, token, certificate), how to implement</li>
          <li>Authorization: Who has access to what, Enforcement policies</li>
          <li>Naming Conventions: URIs as nouns, Methods as verbs, Pluralization, Hierarchy, Case, Language, No jargon/abbreviations</li>
          <li>Error Codes: Status codes, Reference ID, Human readable messages</li>
          <li>Versioning: When to implement vs. not, Version types</li>
          <li>Units, Formats, Standards: Date/time formats, Timezones</li>
        </ul>
    </ul>
  </ul>
</details>

<details>
  <summary> <b>Testing: Ensuring APIs are Free from Flaws</b> </summary>

<ul>
  <li><b>API-First Testing: </b> Evaluate the API layer independent from the Web/Mobile App layer.</li>
  <li><b>API Pentesting Regiment:</b> Reconnaissance, Scanning, Endpoint Analysis, Authentication, Authorization, Assets Management, Injection, Mass Assignment, Rate-Limiting</li>
  <li><b>PenTesting Categories:</li>
    <ul>
      <li>API Security: Unsecure Endpoints, Authentication exploits, Enumeration, DOS & Rate-limiting, Missing TLS/SSL issues, Fuzzing/Injection, Fuzzing/Input validation, Server-side resource forgery, Server properties leaks</li>
      <li>Data Security: Access Control, Excessive/Sensitive data exposure, PII/PHI/PCI-DSS data, File/Directory exposure, Encryption At-Rest, Data exfiltration</li>
      <li>Business Logic: Cross-account access, API function abuse, Role-based access control, Pen-testing</li>
    </ul>
</ul>

</details>

<details>
  <summary> <b>Monitoring: Discovering Threats in Production</b> </summary>

<ul>
  <li><b>Runtime Protection: </b>Policy enforcement, Authentication, Traffic filtering</li>
  <li><b>Threat Detection: </b>Fraudulent traffic, Distributed attacks, Incident response </li>
  <li><b>Control Validation: </b>Verify API controls, Uncover anomalies</li>
  <li><b>Monitoring Approaches:</b>
    <ul>
      <li>Proactive (Blocking): API Gateway, Web App Firewall</li>
      <li>Reactive (Alerting): Logging, SIEM, Runtime API Threat Management</li>
    </ul>
  </li>
  <li><b>API Discovery:</b>
    <ul>
      <li>Monitoring can aid API inventory efforts: Identify API endpoints in use, Discover undocumented/unknown APIs</li>
      <li>Comprehensive discovery requires more resources: API Gateway, WAP, Code repository, Application testing, Crawling</li>
      <li>Reliance on traffic-based discovery misses: Internal API traffic unseen by traffic analysis tool, Pre-prod APIs, Unexercised endpoints</li>
    </ul>
  </li>
  <li><b>Limitations of Monitoring:</b>
    <ul>
      <li>Difficult to get full visibility: Requires sensors at every network segment</li>
      <li>High false-positive rate on threat detection: Live traffic contains limited context</li>
      <li>SaaS-based monitoring requres data share with 3rd parties: Increased privacy concern, bandwidth requirements</li>
      <li>Traffic-blocking solutions (e.g., firewalls) add latency</li>
    </ul>
  </li>
</ul>

</details>

<br>

### Securing API Servers 

 <details>
  <summary> <b>CORS (Cross-Origin Resource Sharing</b> </summary>
  <ul>
    <li>CORS is a collection of browser controls set by web servers. CORS defines what responses are allowed (e.g., POST, GET, DELETE), and from where (e.g., UI): Origins, Credentials, Methods, Headers</li>
    <li>Why use CORS?
      <ul>
        <li>You have an API or web server with assets you want to protect (e.g., user data, intellectual property, branding).</li>
        <li>You don't want anyone to impersonate you.</li>
      </ul>
    </li>
  </ul>
 </details>

<br>

### [OWASP API Top 10](https://owasp.org/API-Security/editions/2023/en/0x11-t10/)

<table>
  <tr>
    <th>Number</th>
    <th>Name</th>
    <th>Description</th>
    <th>Risk Exposure</th>
    <th>Example</th>
    <th>Prevention</th>
  </tr>
  <tr>
    <td align='center' valign='top'>API1</td>
    <td valign='top'>BOLA: Broken Object-Level Authorization</td>
    <td valign='top'>Authorization issue; manipulation of API to access data/objects belonging to other users. Most damaging, and most difficult to detect in one's own applications.</td>
    <td valign='top'>Can lead to data loss, disclosure, data manipulation.</td>
    <td valign='top'><ul><li>Attacker authenticates as User A, then retrieves data on User B.</li></ul></td>
    <td valign='top'><ul><li>Define data access policies and implement associated controls.</li><li>Enforce data access controls at application logic layer.</li><li>Implement automated testing to find BOLA flaws.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API2</td>
    <td valign='top'>Broken Authentication</td>
    <td valign='top'>Weak/poor authentication creates application vulnerability: missing security controls, poorly impelemented controls.</td>
    <td valign='top'>Account Takeover, Data Theft, Unauthorized Transactions</td>
    <td valign='top'><ul><li>Weak password requirements.</li><li>Credential stuffing: brute force ID/PW.</li><li>No captcha/rate limiting/lockout.</li><li>Non-validation of token expiration.</li><li>Insecure password storage.</li></ul></td>
    <td valign='top'><ul><li>Define authentication policies and standards; follow best practices</li><li>Implement continuous testing.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API3</td>
    <td valign='top'>Broken Object Property Level Authorization</td>
    <td valign='top'>Exploitation of API endpoints via reading/modifying object values. "Mass Assignment": ability to update account objects, and "Excessive Data Exposure": unnecessarily revealing sensitive data.</td>
    <td valign='top'>Revealing protected user data.</td>
    <td valign='top'><ul><li>User is able to set "account-type=premium".</li><li>User search endpoint returns excessive, unnecessary details (e.g., PII data).</li></ul></td>
    <td valign='top'><ul><li>Ensure user can only access legitimate, permitted fields.</li><li>Return only minimum amount of data required for the task-specific use case.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API4</td>
    <td valign='top'>Unrestricted Resource Consumption</td>
    <td valign='top'>Abuse of APIs due to high volumes of API calls, large requests, etc. (formerly "lack of resources and rate limiting").</td>
    <td valign='top'>Denial of Service (DOS), Performance impact, Mass data harvesting, Mass data loss</td>
    <td valign='top'><ul><li>Missing/inadequate rate controls to throttle or meter request volume per user account and per client.</li><li>Execution timeouts.</li><li>Max memory allocation.</li><li>Max number of files, upload size.</li><li>Excessive operations in single request.</li><li>Excessive records returned in single request.</li></ul></td>
    <td valign='top'><ul><li>Implement traffic controls.</li><li>Test effectiveness of controls.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API5</td>
    <td valign='top'>Broken Function-level Authorization</td>
    <td valign='top'>Abuse of API functionality to improperly modify objects (e.g., CREATE, UPDATE, DELETE). Often involves replacing passive methods (e.g., GET) with active (PUT, DELETE).</td>
    <td valign='top'>Can lead to privilege escalation, Can be exploited to modify account details</td>
    <td valign='top'><ul><li>Modify parameters: "role=admin".</li><li>Delete an invoice.</li><li>Set account balance to $0.</li><li>Set GPA to 4.0.</li></ul></td>
    <td valign='top'><ul><li>Identify functions that expose high sensitivity capability and develop controls to limit access.</li><li>Implement continuous release testing to ensure proper behavior.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API6</td>
    <td valign='top'>Unrestricted Access to Sensitive Business Flows</td>
    <td valign='top'>Typically a result of application logic flaw. Abuse of a legitimate business workflow through excessive, automated use. Rate limiting, captchas not always effective against fraudulent traffic. Rapid IP rotation, clearing cookies and other, distributed attacks make detection difficult.</td>
    <td valign='top'>Loss of critical business activity</td>
    <td valign='top'><ul><li>Mass, automated ticket purchasing.</li><li>High volume referral bonuses.</li></ul></td>
    <td valign='top'><ul><li>Identify critical business workflows.</li><li>Implement fraudulent traffic detection and control.</li><li>Setup and automate testing of control mechanisms.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API7</td>
    <td valign='top'>Server-Side Request Forgery</td>
    <td valign='top'>Exploiting URL inputs to make a request to a malicious, 3rd party server.</td>
    <td valign='top'>Potential data leaks, SSRF creates a channel for malicious requests, data access or other fraudulent activity.</td>
    <td valign='top'><ul><li>Local file injection.</li><li>Malware downloaded from malicious site.</li><li>User submits (e.g., http://localhost/api/user-data).</li></ul></td>
    <td valign='top'><ul><li>Validate and sanitize ALL user-supplied information, including URL parameters.</li><li>Ensure communication permitted with trusted resources only.</li><li>Test URL validation effectiveness (e.g., fuzzing).</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API8</td>
    <td valign='top'>Security Misconfiguration</td>
    <td valign='top'>Encompasses a lack of hardening to unnecessary services.</td>
    <td valign='top'>Misconfigurations can expose sensitive user data, Potential for full server compromise (e.g., Log4J)</td>
    <td valign='top'><ul><li>Lack of security hardening.</li><li>Improperly configured permissions.</li><li>Missing security patches.</li><li>Unncessary features enabled.</li><li>Missing TLS.</li><li>CORS policy missing/improperly set.</li></ul></td>
    <td valign='top'><ul><li>Implement hardening procedures.</li><li>Routinely review configurations.</li><li>Implement automated, continuous security testing.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API9</td>
    <td valign='top'>Improper Inventory Management</td>
    <td valign='top'>Unauthorized API access via old, unused API version, or thorugh trusted 3rd parties.</td>
    <td valign='top'>Data/account theft via unretired APIs, Exposure to sensitive data via improperly secured 3rd party APIs</td>
    <td valign='top'><ul><li>Old versions of APIs.</li><li>Unpatched endpoints.</li><li>Endpoints with weaker security.</li><li>Outdated documentation.</li><li>Unnecessarily exposed endpoints.</li><li>API access via 3rd party.</li></ul></td>
    <td valign='top'><ul><li>Deploy/manage all APIs in Gateway.</li><li>Define rules for versioning and retirement.</li><li>Periodically audit 3rd party access.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API10</td>
    <td valign='top'>Unsafe Consumption of APIs</td>
    <td valign='top'>Exposures that occur via use of 3rd party APIs, which are generally trusted. However, 3rd parties can be exploited and used to attack all downstream APIs that rely on them.</td>
    <td valign='top'>Data theft, breach, account takeover</td>
    <td valign='top'><ul><li>Attacker inserts malicious address data to validation site used by Client.</li><li>Client fails too validate data and gets exploited.</li></ul></td>
    <td valign='top'><ul><li>Validate data returned by 3rd party APIs.</li><li>Evaluate security controls of 3rd party APIs.</li><li>Encrypt all API communications.</li><li>Maintain approved list of known locations integration APIs may be redirected, and routinely validate this list.</li></ul></td>
  </tr>
</table>
