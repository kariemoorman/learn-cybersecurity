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
    <td align='center' valign='top'>1</td>
    <td valign='top'>BOLA: Broken Object-Level Authorization</td>
    <td valign='top'>Manipulation of API to access data/objects belonging to other users. Most damaging, and most difficult to detect in one's own applications.</td>
    <td valign='top'>Can lead to data loss, disclosure, data manipulation.</td>
    <td valign='top'>Attacker authenticates as User A, then retrieves data on User B.</td>
    <td valign='top'><ul><li>Define data access policies and implement associated controls.</li><li>Enforce data access controls at application logic layer.</li><li>Implement automated testing to find BOLA flaws.</li></ul></td>
  </tr>
  <tr>
    <td align='center' valign='top'>2</td>
    <td valign='top'>Broken Authentication</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'>Instagram, Bumble, T-Mobile, Venmo, Peleton</td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>3</td>
    <td valign='top'>Broken Object Property Level Authorization</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'>Venmo, Optus, Experian</td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>4</td>
    <td valign='top'>Unrestricted Resource Consumption</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'>Venmo, Optus</td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>5</td>
    <td valign='top'>Broken Function-level Authorization</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'>Bumble</td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>6</td>
    <td valign='top'>Server-Side Request Forgery</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>7</td>
    <td valign='top'>Security Misconfiguration</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>8</td>
    <td valign='top'>Lack of Protection from Automated Threats</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>9</td>
    <td valign='top'>Improper Inventory Management</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'>Experian</td>
    <td valign='top'></td>
  </tr>
  <tr>
    <td align='center' valign='top'>10</td>
    <td valign='top'>Unsafe Consumption of APIs</td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
    <td valign='top'></td>
  </tr>
</table>
