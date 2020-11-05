---
external help file: NetQos_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: F946186B-3E5C-4918-A176-266FEFC4EEAB
manager: dansimp
---

# Set-NetQosPolicy

## SYNOPSIS
Updates the Quality of Service (QoS) policy settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NetQosPolicy [[-Name] <String[]>] [-AppPathNameMatchCondition <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-DSCPAction <SByte>] [-IPDstPortEndMatchCondition <UInt16>]
 [-IPDstPortMatchCondition <UInt16>] [-IPDstPortStartMatchCondition <UInt16>]
 [-IPDstPrefixMatchCondition <String>] [-IPPortMatchCondition <UInt16>] [-IPProtocolMatchCondition <Protocol>]
 [-IPSrcPortEndMatchCondition <UInt16>] [-IPSrcPortMatchCondition <UInt16>]
 [-IPSrcPortStartMatchCondition <UInt16>] [-IPSrcPrefixMatchCondition <String>]
 [-MinBandwidthWeightAction <Byte>] [-NetDirectPortMatchCondition <UInt16>] [-NetworkProfile <NetworkProfile>]
 [-PassThru] [-PolicyStore <String>] [-Precedence <UInt32>] [-PriorityValue8021Action <SByte>]
 [-TemplateMatchCondition <Template>] [-ThrottleLimit <Int32>] [-ThrottleRateActionBytesPerSecond <UInt64>]
 [-URIMatchCondition <String>] [-URIRecursiveMatchCondition <Boolean>] [-UserMatchCondition <String>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NetQosPolicy [-AppPathNameMatchCondition <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-DSCPAction <SByte>] [-IPDstPortEndMatchCondition <UInt16>] [-IPDstPortMatchCondition <UInt16>]
 [-IPDstPortStartMatchCondition <UInt16>] [-IPDstPrefixMatchCondition <String>]
 [-IPPortMatchCondition <UInt16>] [-IPProtocolMatchCondition <Protocol>] [-IPSrcPortEndMatchCondition <UInt16>]
 [-IPSrcPortMatchCondition <UInt16>] [-IPSrcPortStartMatchCondition <UInt16>]
 [-IPSrcPrefixMatchCondition <String>] [-MinBandwidthWeightAction <Byte>]
 [-NetDirectPortMatchCondition <UInt16>] [-NetworkProfile <NetworkProfile>] [-PassThru] [-Precedence <UInt32>]
 [-PriorityValue8021Action <SByte>] [-TemplateMatchCondition <Template>] [-ThrottleLimit <Int32>]
 [-ThrottleRateActionBytesPerSecond <UInt64>] [-URIMatchCondition <String>]
 [-URIRecursiveMatchCondition <Boolean>] [-UserMatchCondition <String>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Set-NetQosPolicy** cmdlet modifies an existing Quality of Service (QoS) policy.
Match conditions or actions or general parameters of the policy such as **NetworkProfile** or **Precedence** can be changed.

Users cannot change the location of where an existing QoS policy is stored.
Changing the **PolicyStore** parameter value will fail.

If a policy was created to be in ActiveStore and a user attempts to make it persistent, such as storing the policy on the local computer, the user has to create a new policy and place it on the local computer (localhost).

If the **PolicyStore** parameter is not specified, then the cmdlet will search for and update the policy on the local computer (localhost).

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-NetQosPolicy -Name "SMB Policy" -NetworkProfile Domain
```

This example updates the QoS policy named SMB Policy so that it only applies to traffic that is outgoing from a domain-joined network adapter.

### EXAMPLE 2
```
PS C:\> Get-NetQosPolicy -Name "wildcard" | Set-NetQosPolicy -Precedence 250
```

This example gets the QoS policy named wildcard and updates the precedence of the policy to 250.

### EXAMPLE 3
```
PS C:\> Set-NetQosPolicy -Name "Backup" -IPDstPortStart 3501 -IPDstPortEnd 3510
```

This example updates the QoS policy named Backup with additional matching conditions.

### EXAMPLE 4
```
PS C:\> Set-NetQosPolicy -Name "IIS" -Recursive $true -ThrottleRateActionBytesPerSecond 3000KB
```

This example updates the QoS policy named IIS, so that it applies to the return traffic for both the specified URI and subdirectories and files under the URI.
This cmdlet also sets a new throttling rate at 3,000,000 bytes per second.
Note: An alias for the **ThrottleRateActionBytesPerSecond** parameter is `ThrottleRateAction`.
Another alias is `MaxBw`.

## PARAMETERS

### -AppPathNameMatchCondition
Specifies the name by which an application is run in Windows Server® 2012, such as `application.exe` or `%ProgramFiles%\application.exeapplication`.

```yaml
Type: String
Parameter Sets: (All)
Aliases: App, ApplicationName, AppPathName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DSCPAction
Specifies the differentiated services code point (DSCP) value.
A valid DSCP value is in the range between `0` and `63`.
In addition, users can enter `-1` to remove the DSCP setting from the policy.

```yaml
Type: SByte
Parameter Sets: (All)
Aliases: DSCP, DSCPValue

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specified the object which will be modified by this cmdlet.
The object must be piped to the cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IPDstPortEndMatchCondition
Specifies the last port in a range of destination ports to be used to match the network traffic.
This parameter must be used in conjunction with the **IPDstPortStartMatchCondition** parameter.
The value of this parameter also must be larger than the value of the **IPDstPortStartMatchCondition** parameter.

```yaml
Type: UInt16
Parameter Sets: (All)
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
To specify a range of destination ports, use both the **IPDstPortStartMatchCondition** and the **IPDstPortEndMatchCondition** parameters.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: DestinationPort, Destport, Dp, Dstport, IPDstPort

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPDstPortStartMatchCondition
Specifies the first port in a range of destination ports to be used to match the network traffic.
This parameter must be used in conjunction with the **IPDstPortEndMatchCondition** parameter.
The value of this parameter also must be smaller than the value of the **IPDstPortEndMatchCondition** parameter.

```yaml
Type: UInt16
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: Da, Dest, Destaddr, DestinationAddress, Destip, Dst, Dstaddr, Dstip, IPDstPrefix

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
For example, specifying this parameter value to `80` matches HTTP traffic sent by both HTTP clients and HTTP servers.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: IPPort, Port

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPProtocolMatchCondition
Specifies the IP protocol to be used to match the network traffic.
The acceptable values for this parameter are: TCP, UDP, or Both.
If this parameter is unspecified, then Both is the default value.
The QoS policy will apply to both TCP and UDP traffic.

```yaml
Type: Protocol
Parameter Sets: (All)
Aliases: IPProtocol, Protocol

Required: False
Position: Named
Default value: Both
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPSrcPortEndMatchCondition
Specifies the last port in a range of source ports to be used to match the network traffic.
This parameter must be used in conjunction with the **IPSrcPortStartMatchCondition** parameter.
The value of this parameter also must be larger than the value of the **IPSrcPortStartMatchCondition** parameter.

```yaml
Type: UInt16
Parameter Sets: (All)
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
To specify a range of source ports, use both the **IPSrcPortStartMatchCondition** and the **IPSrcPortEndMatchCondition** parameters.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: IPSrcPort, SourcePort, Sp, Srcport

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSrcPortStartMatchCondition
Specifies the first port in a range of source ports to be used to match the network traffic.
This parameter must be used in conjunction with the **IPSrcPortEndMatchCondition** parameter.
The value of this parameter also must be smaller than the value of the **IPSrcPortEndMatchCondition** parameter.

```yaml
Type: UInt16
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: IPSrcPrefix, Sa, SourceAddress, Src, Srcaddr, Srcip

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinBandwidthWeightAction
Specifies a numerical value for minimum bandwidth that a flow should get relatively.
The actual bandwidth a flow gets will depend on the weights assigned to other flows in the computer.
The acceptable values for this parameter are: 1 through 100.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: MinBandwidthWeight, Minbww, Weight

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the QoS policy name.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetDirectPortMatchCondition
Specifies the network direct port to be used to match the network traffic.
Network Direct uses an independent port space from the TCP or UDP port space.
Windows Server 2012 will send a Network Direct policy to a network adapter only if the network adapter supports Network Direct.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: Ndport, NetDirectPort, Networkdirectport

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkProfile
Specifies the profile, or connection type, of a network.
The acceptable values for this parameter are: Domain, Public, Private, or All.
If this parameter is not specified, then the QoS policy will be effective when a computer is connected on any type of connection.

```yaml
Type: NetworkProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: All
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -PolicyStore
Specifies the location of the policy that is stored.
The acceptable values for this parameter are:

 - ActiveStore 

 - COMPUTERNAME

 - GPO:COMPUTERNAME

 - GPO:DOMAIN\GPONAME

 - LDAP://LDAP-URL

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Store

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Precedence
Specifies the priority of a QoS policy.
A higher priority policy will override a lower priority policy in case the priorities are conflicting.
The acceptable values for this parameter are: 0 through 255.
255 specifies the highest priority and 0 specifies the lowest.
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
A valid 802.1p value is in the range between `0` and `7`.
In addition, users can enter `-1` to remove the 802.1p priority setting from the policy.

```yaml
Type: SByte
Parameter Sets: (All)
Aliases: Dot1p, Pri, PriorityValue, PriorityValue8021

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateMatchCondition
Specifies a number of filters built in Windows Server® 2012.
The acceptable values for this parameter are: FCoE, iSCSI, LiveMigration, NFS, SMB, or.
Note: Refer to the corresponding parameter descriptions for the New-NetQosPolicy cmdlet.

```yaml
Type: Template
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: True (ByPropertyName)
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

### -ThrottleRateActionBytesPerSecond
Specifies a throttle rate, in bytes per second.
This value is also known as maximum bandwidth.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: Maxbw, Throttle, ThrottleRate, ThrottleRateAction

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
Parameter Sets: (All)
Aliases: Uri, Url

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URIRecursiveMatchCondition
Specifies that all subdirectories and files following the URI specified in the **URIMatchCondition** parameter are to be included.
This parameter can be specified only if the **URIMatchCondition** parameter is specified.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Recursive, URIRecursive, Urlrecursive

Required: False
Position: Named
Default value: $false
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserMatchCondition
Specifies the user or group name in Active Directory, such as `contoso\johnj99`.
This parameter is usually specified with other filtering parameter such as the **AppPathNameMatchCondition** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Sid, User

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosPolicySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosPolicySettingData object contains a QoS policy.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosPolicySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_NetQosPolicySettingData object contains a QoS policy.
Only when the **PassThru** parameter is specified will this cmdlet return the MSFT_NetQosPolicySettingData object.

## NOTES

## RELATED LINKS

[Get-NetQosPolicy](./Get-NetQosPolicy.md)

[New-NetQosPolicy](./New-NetQosPolicy.md)

[Remove-NetQosPolicy](./Remove-NetQosPolicy.md)

