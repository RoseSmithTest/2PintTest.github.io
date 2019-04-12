# StifleR Network Locations

Once you install the StifleR client on some test systems, they will report to the StifleR server, which will start to populate the Location information based on the data sent back from the clients.

Each ’newly discovered’ location/subnet has a set of default parameters, and for the purposes of testing, there are some configuration changes that should be made to enable optimal performance while testing.

### **Configure Subnet Bandwidth**

On the StifleR server – run the following command from an elevated Command prompt

```text
wmic /namespace:\\root\stifler path Subnets.SubnetId="xxx.xxx.xxx.xxx" set TargetBandwidth=xxxx
```

Where xxx.xxx.xxx.xxx is the subnet ID of your test location and

Xxxx is the target bandwidth that you wish to allow for that subnet in Kilobits. So 1024 = 1 Mbit

The Target Bandwidth is the network bandwidth usage limit that is defined for ALL StifleR clients at that location – so if the limit is set to 4Mbit/S – then the TOTAL bandwidth usage across all clients at that location wil not exceed that limit.

### **Populate Subnet Summary Information**

The summary information for a subnet provides an easy to read description of the subnet in the StifleR dashboards.

Run the following commands from an elevated Command prompt.

```text
wmic /namespace:\\root\stifler path Subnets.SubnetId="192.168.138.0" set Description=”Test
Location”
wmic /namespace:\\root\stifler path Subnets.SubnetId="192.168.138.0" set Town=”SomeTown”
wmic /namespace:\\root\stifler path Subnets.SubnetId="192.168.138.0" set Country=”USA”
```

You can of course substitute the entries above with those of you own choosing.

### **Configure Delivery Optimization**

If you are using Windows 10 Delivery Optimization, StifleR can ensure that the correct Peer to Peer boundaries are respected. In order to configure this capability, run the following command from an elevated command prompt on the Stifler Server.

```text
wmic /namespace:\\root\stifler path Subnets.SubnetId=" xxx.xxx.xxx.xxx " set DODownloadMode=”2”
```

```text
wmic /namespace:\\root\stifler path Subnets.SubnetId=" xxx.xxx.xxx.xxx " set DOGroupID=”99999999-
9999 - 9999 - 999999999999”
```

The DOGroupID must be a unique GUID. You can generate a GUID using PowerShell \(New-GUID command\) or you could copy the guid of the subnet itself and use that.

Once the above parameters are set, the Delivery Optimization clients will only share content with other clients that have the same Group ID.

The quickstart configuration is now complete and you are ready to start testing the functionality of StifleR.

Open the main dashboard on the StifleR server – [http://myserver/stiflerdashboard/\#/all](http://myserver/stiflerdashboard/#/all)

There you should now see the clients that were added in the previous steps. Drill down to your test subnet using the pop-out menu on the left side of the main dashboard to see more detailed info.

