import pypandoc

# README content with <br> tags for line breaks
readme_br_content = """
# Windows Firewall Configuration – GUI Steps<br>

## 1. Open the Windows Firewall Configuration Tool<br>
1. Press **Win + S** (search), type **Windows Defender Firewall**, and open it.<br>
2. Click **Advanced settings** in the left panel to open *Windows Defender Firewall with Advanced Security*.<br>

## 2. List Current Firewall Rules<br>
1. In the Advanced Security window, select **Inbound Rules** to view inbound rules.<br>
2. Select **Outbound Rules** to view outbound rules.<br>

## 3. Add a Rule to Block Inbound Traffic on Port 23 (Telnet)<br>
1. In the left pane, click **Inbound Rules**.<br>
2. In the right pane, click **New Rule…**.<br>
3. Choose **Port** and click **Next**.<br>
4. Select **TCP**, enter `23` in the **Specific local ports** field, and click **Next**.<br>
5. Choose **Block the connection** and click **Next**.<br>
6. Select when the rule applies (Domain, Private, Public) and click **Next**.<br>
7. Name the rule (e.g., *Block Telnet*) and click **Finish**.<br>

## 4. Test the Rule<br>
1. On the same computer, open PowerShell and run:<br>
   `Test-NetConnection -Port 23 localhost`<br>
   It should fail to connect.<br>
2. From another computer on the network, you can use a port scanner like **nmap** to confirm that port 23 is blocked.<br>

## 5. Remove the Test Block Rule<br>
1. Go back to **Inbound Rules**.<br>
2. Find the rule named *Block Telnet*.<br>
3. Right-click the rule and select **Delete** to remove it.<br>

## 6. Summary of Firewall Filtering<br>
Windows Firewall is a **stateful host-based firewall** that filters inbound and outbound network traffic.<br>
- By default, inbound connections are blocked unless a rule allows them.<br>
- Outbound traffic is usually allowed.<br>
- It can filter by port, program, protocol, or network profile (Domain, Private, Public).<br>
  
