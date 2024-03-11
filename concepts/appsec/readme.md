## AppSec: Application Security

### Table of Contents
- [API Security](#api-security)


----

### API Security

#### [OWASP API Top 10](https://owasp.org/API-Security/editions/2023/en/0x11-t10/)

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
    <td valign='top'>Server-Side Request Forgery</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'><ul><li></li></ul></td>
    <td valign='top'><ul><li></li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API7</td>
    <td valign='top'>Security Misconfiguration</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'><ul><li></li></ul></td>
    <td valign='top'><ul><li></li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API8</td>
    <td valign='top'>Lack of Protection from Automated Threats</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'><ul><li></li></ul></td>
    <td valign='top'><ul><li></li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API9</td>
    <td valign='top'>Improper Inventory Management</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'><ul><li></li></ul></td>
    <td valign='top'><ul><li></li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>API10</td>
    <td valign='top'>Unsafe Consumption of APIs</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'><ul><li></li></ul></td>
    <td valign='top'><ul><li></li></ul></td>
  </tr>
</table>
