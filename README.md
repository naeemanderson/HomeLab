  # ️ Azure HomeLab
**Step by Step homelab**

This project simulates a real-world threat detection scenario by deploying a Windows 10
honeypot in Microsoft Azure. The lab demonstrates how failed login attempts can be collected,
forwarded to Microsoft Sentinel, enriched with GeoIP data, and visualized on an interactive
attack map. It's a practical exercise in cloud security, threat visibility, and log analysis using
Microsoft’s security tools.

**🧰Tools & Technologies**

•Microsoft Azure
•Azure Virtual Machines
•Network Security Groups (NSGs)
•Microsoft Sentinel
•Log Analytics Workspace
•Kusto Query Language (KQL)
•GeoIP Watchlist
•Sentinel Workbooks
---------------------------------------------------------------------------------------------
**Part 1: Create Azure Subscription**
Free tier: Azure Free Account or Pay-as-you-go Account

____________________________________________________________________________
______________
**Part 2: Deploy Honeypot VM**

Deployed Windows 10 VM in Azure
<img width="1448" alt="Screen Shot 2025-06-08 at 5 36 04 PM"
src="https://github.com/user-attachments/assets/09f36ed8-b731-4b6d-ae02-8772b4c091d3" />
Disabled Windows Firewall on the VM

<img width="1460" alt="Screen Shot 2025-06-08 at 5 39 17 PM"
src="https://github.com/user-attachments/assets/b3f0df76-95c1-45ad-a958-d835b862a4fa" />
Delete default RDP rule
<img width="1448" alt="Screen Shot 2025-06-08 at 6 49 40 PM"
src="https://github.com/user-attachments/assets/e235eca7-9faf-4a4e-85e0-7972f1748c68" />
Configured NSG to allow all inbound traffic
--------------------------------------------------------------------------------------------
**Part 3: Login to Remote Desktop
**
Log into RDP using the vm ip address
<img width="1176" alt="Screen Shot 2025-06-08 at 6 50 55 PM"
src="https://github.com/user-attachments/assets/4619a0c4-76cd-400b-a1c2-50ec95aef693" />
Disabled Windows Firewall on the VM
<img width="1084" alt="Screen Shot 2025-06-08 at 6 58 27 PM"
src="https://github.com/user-attachments/assets/0ba49c75-9ee3-45fe-a185-c92e6b6cf582" />
**Part 4: Generate and Inspect Logs**
- Simulated failed login attempts using a fake user: `employee`.
- Logged into the VM and opened **Event Viewer**.
- Located failed login attempts using **Event ID 4625** under Security logs.
<img width="1294" alt="Screen Shot 2025-06-08 at 7 08 48 PM"
src="https://github.com/user-attachments/assets/e386bfe6-4f43-4d0d-9de6-9b91d7bd9bf5" />
<img width="1021" alt="Screen Shot 2025-06-08 at 7 10 58 PM"
src="https://github.com/user-attachments/assets/4a5b1426-a9ed-4abb-8e3e-e918e02daa81" />
---------------------------------------------------------------------------------------------
**Part 5: Enable Log Forwarding**
- Created a **Log Analytics Workspace**.
- <img width="750" alt="Screen Shot 2025-06-08 at 7 17 49 PM"
src="https://github.com/user-attachments/assets/9f3b389f-a5d7-4bc9-8155-f807ad0d4f57" />
- Connected Microsoft **Sentinel** to the workspace.
- <img width="1432" alt="Screen Shot 2025-06-08 at 7 20 09 PM"
src="https://github.com/user-attachments/assets/b41f9d32-dc38-4781-8066-10f37a806f2f" />
- Enabled **Windows Security Events via AMA** (Azure Monitor Agent) connector.
<img width="1421" alt="Screen Shot 2025-06-08 at 7 27 30 PM"
src="https://github.com/user-attachments/assets/70dd6395-4183-4e80-a006-ae8d9f7b9274" />

----------------------------------------------------------------------------------------------
**Part 6: GeoIP Enrichment**
Imported IP-to-Location CSV as a Sentinel Watchlist
Joined log data with geographic metadata
------------------------------------------------------------------------------------------------
**Part 7: Build Attack Map**
<img width="1027" alt="Screen Shot 2025-06-08 at 9 19 40 PM"
src="https://github.com/user-attachments/assets/6eab3fd2-03a9-4cf9-961e-6770847f2662" />
Created Sentinel Workbook
Used custom KQL and JSON to visualize attacker locations
-------------------------------------------------------------------------------------------------
### 💡 What I Learned
- How to provision and secure resources in Azure
- Basics of threat simulation using honeypots
- Working with Microsoft Sentinel and Log Analytics
- Writing KQL queries to analyze security data
- Enriching log data with external watchlists
- Building visual attack maps in Sentinel Workbooks
