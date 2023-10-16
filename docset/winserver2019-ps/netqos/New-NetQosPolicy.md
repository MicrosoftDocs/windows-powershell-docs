---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosPolicy.cdxml-help.xml
Module Name: NetQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netqos/new-netqospolicy?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetQosPolicy
---

# New-NetQosPolicy

## SYNOPSIS
Creates a new network QoS policy.

## SYNTAX

### ByIP5Tuple (Default)
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>]
 [-IPDstPrefixMatchCondition <String>] [-UserMatchCondition <String>] [-AppPathNameMatchCondition <String>]
 [-IPProtocolMatchCondition <Protocol>] [-IPSrcPrefixMatchCondition <String>]
 [-IPSrcPortMatchCondition <UInt16>] [-IPSrcPortStartMatchCondition <UInt16>]
 [-IPSrcPortEndMatchCondition <UInt16>] [-IPDstPortMatchCondition <UInt16>]
 [-IPDstPortStartMatchCondition <UInt16>] [-IPDstPortEndMatchCondition <UInt16>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByIPWellKnownPort
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-UserMatchCondition <String>]
 [-AppPathNameMatchCondition <String>] [-IPProtocolMatchCondition <Protocol>] -IPPortMatchCondition <UInt16>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNetworkDirectPort
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] -PriorityValue8021Action <SByte> -NetDirectPortMatchCondition <UInt16>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByURI
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-DSCPAction <SByte>] [-ThrottleRateActionBitsPerSecond <UInt64>]
 -URIMatchCondition <String> [-URIRecursiveMatchCondition <Boolean>] [-IPDstPrefixMatchCondition <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByCluster
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-Cluster]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BySMB
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-SMB]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNFS
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-NFS]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiveMigration
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-LiveMigration]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByISCSI
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-iSCSI]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByFCOE
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] -PriorityValue8021Action <SByte> [-FCOE] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDefault
```
New-NetQosPolicy [-PolicyStore <String>] [-Name] <String> [-Default] [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NetQosPolicy** cmdlet creates a new network Quality of Service (QoS) policy.
A QoS policy consists of two main parts: match conditions also known as filters, and actions.
Match conditions such as the name by which an application is run in Windows Server® 2012 and later or a TCP port number decide to what traffic the policy is relating.
Parameters such as *DSCPAction* and *ThrottleRateAction* determine how the policy is to handle the matched traffic.
Besides match conditions and actions, there are also some general parameters such as *NetworkProfile* and *Precedence* that the users can customize for a QoS policy.

A list of well-known match conditions, or filters, in the form of parameters is provided: *FCoE*, *Cluster* (3343), *LiveMigration* (6600), *iSCSI* (3260), *NFS* (2049), and *SMB* (445).
Each of them matches a well-known TCP port specified in the brackets.
The only exception is *FCoE*, which matches EtherType 0x8906.
These filters must be used alone for filtering purpose.
In other words, they cannot be mixed with other match condition parameters.

QoS policies can be stored in multiple locations.
Users can choose a location by specifying the *PolicyStore* parameter.
If the *PolicyStore* parameter is not specified, then the new policy is added to local computer (localhost).
If a policy is stored in ActiveStore, then the policy will not persist after reboot.

## EXAMPLES

### Example 1: Create a QoS policy
```
PS C:\> New-NetQosPolicy -Name "SMB Policy" -SMB -PriorityValue8021Action 3
Name           : SMB Policy 
Owner          : Group Policy (Machine) 
NetworkProfile : All 
Precedence     : 127 
Template       : SMB 
PriorityValue  : 3
```

This command creates a QoS policy named SMB Policy that classifies SMB traffic and tags it with 802.1p priority value of 3.
The *SMB* parameter is a built-in filter that matches TCP port 445, which is reserved for SMB.

### Example 2: Create a QoS policy that matches an application
```
PS C:\> New-NetQosPolicy -Name "FTP" -AppPathNameMatchCondition "ftp.exe" -ThrottleRateActionBitsPerSecond 1MB -PolicyStore ActiveStore
Name           : FTP 
Owner          : PowerShell / WMI 
NetworkProfile : All 
Precedence     : 127 
AppPathName    : ftp.exe 
ThrottleRate   : 1.049 MBits/sec
```

This command creates a QoS policy named FTP that matches an application path at ftp.exe and throttles the traffic at 8,000,000 bits per second.
This policy is ActiveStore.
This means that it is not persistent after restart of the computer.

### Example 3: Create a QoS policy that matches traffic to a subnet
```
PS C:\> New-NetQosPolicy -Name "Backup" -IPDstPrefixMatchCondition "10.1.1.176/28" -NetworkProfile Domain -DSCPAction 40
Name           : Backup 
Owner          : Group Policy (Machine) 
NetworkProfile : Domain 
Precedence     : 127 
IPProtocol     : Both 
IPDstPrefix    : 10.1.1.176/28 
DSCPValue      : 40
```

This command creates a QoS policy named Backup that matches traffic sent to 10.1.1.176/28 subnet and tags it with DSCP value of 40.
This policy is effective only on traffic sent on a domain-joined network adapter.

### Example 4: Create a QoS policy that matches traffic sent to a port
```
PS C:\> New-NetQosPolicy -Name "HTTP" -IPPort 80 -IPProtocol TCP -ThrottleRateActionBitsPerSecond 10MB
Name           : HTTP 
Owner          : Group Policy (Machine) 
NetworkProfile : All 
Precedence     : 127 
IPProtocol     : TCP 
IPPort         : 80 
ThrottleRate   : 10.486 MBits/sec
```

This command creates a QoS policy that matches TCP traffic sent to port 80 and rate-limits it at 80,000,000 bits per second.

### Example 5: Create a default QoS policy
```
PS C:\> New-NetQosPolicy -Name "Wildcard" -Default -MinBandwidthWeightAction 30
Name               : wildcard 
Owner              : Group Policy (Machine) 
NetworkProfile     : All 
Precedence         : 127 
Template           : Default 
MinBandwidthWeight : 30
```

This command creates a QoS policy named Wildcard that catches all the traffic that does not match a specific QoS policy and assigns a minimum bandwidth weight of 30 to such traffic.

### Example 6: Create a QoS policy that matches return traffic from an application
```
PS C:\> New-NetQosPolicy -Name "IIS" -URIMatchCondition "http://training" -ThrottleRateActionBitsPerSecond 500KB
Name           : IIS 
Owner          : Group Policy (Machine) 
NetworkProfile : Domain 
Precedence     : 127 
URI            : http://training/ 
URIRecursive   : False 
ThrottleRate   : 516.096 KBits/sec
```

This command creates a QoS policy named IIS that matches return traffic from an HTTP server application with the specified URI and rate limit the return traffic at 4,000,000 bits per second.

## PARAMETERS

### -AppPathNameMatchCondition
Specifies the name by which an application is run, such as `application.exe` or `%ProgramFiles%\application.exeapplication`.

```yaml
Type: String
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort
Aliases: AppPathName, ApplicationName, app

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
Specifies the Microsoft Windows Cluster service, which uses the Cluster network driver TCP/UDP port 3343.

```yaml
Type: SwitchParameter
Parameter Sets: ByCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DSCPAction
Specifies the differentiated services code point (DSCP) value.
The acceptable values for this parameter are: 0 through 63.

```yaml
Type: SByte
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort, ByURI, ByCluster, BySMB, ByNFS, ByLiveMigration, ByISCSI, ByDefault
Aliases: DSCPValue, DSCP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default
Specifies a wildcard filter that can be used to capture all traffic that is not matched by any other filter.
One use case is that a user can create a QoS policy for a specific application using the *AppPathNameMatchCondition* parameter and create another QoS policy for all other applications using this parameter.
Another use case is that a user can create several QoS policies, each of which specifies a minimum bandwidth action for the filtered traffic, and create one additional policy using this parameter to assign a minimum bandwidth action for all other traffic.

```yaml
Type: SwitchParameter
Parameter Sets: ByDefault
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FCOE
Specifies the Fibre Channel over Ethernet (FCoE), which uses a dedicated EtherType 0x8914.
If this parameter is specified, then the Windows Server® 2012 and later will instruct the network adapters in the computer that support FCoE to match the FCoE packets and apply the action specified in the policy.

```yaml
Type: SwitchParameter
Parameter Sets: ByFCOE
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPDstPortEndMatchCondition
Specifies the last port in a range of destination ports to be used to match the network traffic.
This parameter must be used in conjunction with the *IPDstPortStartMatchCondition* parameter.
The value of this parameter also must be larger than the value of the *IPDstPortStartMatchCondition* parameter.

```yaml
Type: UInt16
Parameter Sets: ByIP5Tuple
Aliases: IPDstPortEnd

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPDstPortMatchCondition
Specifies the exact destination port to be used to match the network traffic.
The filter of a QoS policy can be based on either a single port or a range of ports.
To specify a single destination port, use this parameter.
To specify a range of destination ports, use both the *IPDstPortStartMatchCondition* and the *IPDstPortEndMatchCondition* parameters.

```yaml
Type: UInt16
Parameter Sets: ByIP5Tuple
Aliases: IPDstPort, DestinationPort, dp, dstport, destport

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPDstPortStartMatchCondition
Specifies the first port in a range of destination ports to be used to match the network traffic.
This parameter must be used in conjunction with the *IPDstPortEndMatchCondition* parameter.
The value of this parameter also must be smaller than the value of the *IPDstPortEndMatchCondition* parameter.

```yaml
Type: UInt16
Parameter Sets: ByIP5Tuple
Aliases: IPDstPortStart

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPDstPrefixMatchCondition
Specifies the destination IP address, optionally with a network prefix, such as `1.2.3.4`, `3ffe:ffff::1`, `192.168.1.0/24`, or `fe80::1234/48`.

```yaml
Type: String
Parameter Sets: ByIP5Tuple, ByURI
Aliases: IPDstPrefix, DestinationAddress, da, dst, dstaddr, dstip, dest, destaddr, destip

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPPortMatchCondition
Specifies the port to be used to match the network traffic, it can be either source port or destination port.
If either the source port or the destination port in a packet matches the value of this parameter, then the QoS policy will apply to the packet.
Usually this is a well-known port that a client uses to communicate with a server.
With this parameter specified, the same QoS policy can be configured on both the clients and the servers and apply to the traffic in both directions.
For example, specifying the IPPortMatchCondition parameter value of 80 matches HTTP traffic sent by both HTTP clients and HTTP servers.

```yaml
Type: UInt16
Parameter Sets: ByIPWellKnownPort
Aliases: IPPort, port

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPProtocolMatchCondition
Specifies the IP protocol to be used to match the network traffic.
The acceptable values for this parameter are: TCP, UDP, or Both.
If this parameter is unspecified, then Both is the default condition.
The QoS policy will apply to both TCP and UDP traffic.

```yaml
Type: Protocol
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort
Aliases: IPProtocol, Protocol
Accepted values: None, TCP, UDP, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPSrcPortEndMatchCondition
Specifies the last port in a range of source ports to be used to match the network traffic.
This parameter must be used in conjunction with the *IPSrcPortStartMatchCondition* parameter.
The value of this parameter also must be larger than the value of the *IPSrcPortStartMatchCondition* parameter.

```yaml
Type: UInt16
Parameter Sets: ByIP5Tuple
Aliases: IPSrcPortEnd

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPSrcPortMatchCondition
Specifies the exact source port to be used to match the network traffic.
The filter of a QoS policy can be based on either a single port or a range of ports.
To specify a single source port, use this parameter.
To specify a range of source ports, use both the *IPSrcPortStartMatchCondition* and the *IPSrcPortEndMatchCondition* parameters.

```yaml
Type: UInt16
Parameter Sets: ByIP5Tuple
Aliases: IPSrcPort, SourcePort, sp, srcport

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSrcPortStartMatchCondition
Specifies the first port in a range of source ports to be used to match the network traffic.
This parameter must be used in conjunction with the *IPSrcPortEndMatchCondition* parameter.
The value of this parameter also must be smaller than the value of the *IPSrcPortEndMatchCondition* parameter.

```yaml
Type: UInt16
Parameter Sets: ByIP5Tuple
Aliases: IPSrcPortStart

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPSrcPrefixMatchCondition
Specifies the source IP address, optionally with a network prefix, such as `1.2.3.4`, `3ffe:ffff::1`, `192.168.1.0/24`, or `fe80::1234/48`.

```yaml
Type: String
Parameter Sets: ByIP5Tuple
Aliases: IPSrcPrefix, SourceAddress, sa, src, srcaddr, srcip

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiveMigration
Specifies the Microsoft live migration, which uses the well-known TCP port 6600.

```yaml
Type: SwitchParameter
Parameter Sets: ByLiveMigration
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinBandwidthWeightAction
Specifies a numerical value for minimum bandwidth that a flow should get relatively.
The actual bandwidth a flow gets will depend on the weights assigned to other flows in the computer.
The acceptable values for this parameter are: 1 through 100.

```yaml
Type: Byte
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort, ByCluster, BySMB, ByNFS, ByLiveMigration, ByISCSI, ByDefault
Aliases: MinBandwidthWeight, minbww, weight

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NFS
Specifies the network file system, which uses the dedicated TCP port 2049.

```yaml
Type: SwitchParameter
Parameter Sets: ByNFS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the QoS policy name.
This name must be unique for a QoS policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetDirectPortMatchCondition
Specifies the network direct port to be used to match the network traffic.
Network Direct uses an independent port space from the TCP or UDP port space.
Windows Server 2012 and later will send a Network Direct policy to a network adapter only if the network adapter supports Network Direct.

```yaml
Type: UInt16
Parameter Sets: ByNetworkDirectPort
Aliases: NetDirectPort, ndport, networkdirectport

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkProfile
Specifies the profile, or connection type, of a network, such as Domain.
The acceptable values for this parameter are: Domain, Public, Private, or All.
If this parameter is not specified, then the QoS policy will be effective when a computer is connected on any type of connection.

```yaml
Type: NetworkProfile
Parameter Sets: (All)
Aliases: 
Accepted values: Domain, Public, Private, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the location of the policy that is stored.
The acceptable values for this parameter are:

- ActiveStore 
- COMPUTERNAME
- GPO:COMPUTERNAME
 -- GPO:DOMAIN\GPONAME
 -- LDAP://LDAP-URL

If a policy is stored in ActiveStore, then the policy does not persist after restart.

```yaml
Type: String
Parameter Sets: (All)
Aliases: store

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Precedence
Specifies the priority of a QoS policy.
A higher priority policy will trump a lower priority policy in case the policies are conflicting.
The acceptable values for this parameter are: 0 through 255.
255 represents the highest priority and 0 represents the lowest.
If not specified, then the default value is 127.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PriorityValue8021Action
Specifies the IEEE 802.1p value.
The acceptable values for this parameter are: 0 through 7.

```yaml
Type: SByte
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort, ByCluster, BySMB, ByNFS, ByLiveMigration, ByISCSI, ByDefault
Aliases: PriorityValue, PriorityValue8021, pri, dot1p

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SByte
Parameter Sets: ByNetworkDirectPort, ByFCOE
Aliases: PriorityValue, PriorityValue8021, pri, dot1p

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SMB
Specifies the server message block, which uses the dedicated TCP port 445.

```yaml
Type: SwitchParameter
Parameter Sets: BySMB
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleRateActionBitsPerSecond
Specifies a throttle rate in bits per second to set the maximum bandwidth that can be consumed.

```yaml
Type: UInt64
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort, ByURI, ByCluster, BySMB, ByNFS, ByLiveMigration, ByISCSI, ByDefault
Aliases: ThrottleRateAction, ThrottleRate, Throttle, maxbw

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URIMatchCondition
Specifies the URI to match.
Only a HTTP URL is currently supported, such as `http://myhost`, `https://*/training`, `http://myhost:8080/training`, or `https://myhost:*/training`.
The QoS policy will only apply to the traffic sent from HTTP server applications to HTTP clients in response to the requests from the client for the specified URI.

```yaml
Type: String
Parameter Sets: ByURI
Aliases: URI, url

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URIRecursiveMatchCondition
Specifies that all subdirectories and files following the URI specified in the *URIMatchCondition* parameter are to be included.
This parameter can be specified only if the *URIMatchCondition* parameter is specified.

```yaml
Type: Boolean
Parameter Sets: ByURI
Aliases: URIRecursive, urlrecursive, recursive

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserMatchCondition
Specifies the user or group name in Active Directory, such as `contoso\DavidChew`.
This parameter is usually specified with another filtering parameter such as the *AppPathNameMatchCondition* parameter.

```yaml
Type: String
Parameter Sets: ByIP5Tuple, ByIPWellKnownPort
Aliases: User, sid

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -iSCSI
Specifies the internet small computer system interface (iSCSI), which uses the dedicated TCP port 3260.

```yaml
Type: SwitchParameter
Parameter Sets: ByISCSI
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosPolicySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The **MSFT_NetQosPolicySettingData** object contains a QoS policy.

## NOTES

## RELATED LINKS

[Get-NetQosPolicy](./Get-NetQosPolicy.md)

[Remove-NetQosPolicy](./Remove-NetQosPolicy.md)

[Set-NetQosPolicy](./Set-NetQosPolicy.md)
