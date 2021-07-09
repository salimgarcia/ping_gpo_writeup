# Ping GPO Writeup
Task Description: Create a new GPO (we never edit the default GPOs) that will enable ping on all domain-joined computers.

- Login to Netop VM and open `Group Policy Management`
- Create a new group policy object, then right click it and click edit
- Go to Computer Configuration, Policies, Windows Settings, Security Settings, Windows Defender Firewall, Windows Defender Firewall, Inbound Rules
- Right click the pane on the right and select `New Rule`
- Select `Predefined` and choose `File and Printer Sharing`, then click Next
- Check the box for `File and Printer Sharing (Echo Request - ICMPv4-In)`, then click next
- Select `Allow the connection`, then click finish
- Drag and drop the GPO into Group Policy Management, Forest: mylab.local, Domains, mylab.local
- The GPO will be applied to all machines in the domain
