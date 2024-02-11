---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetQosPolicy.cdxml-help.xml
Module Name: NetQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netqos/set-netqospolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetQosPolicy
---

# Set-NetQosPolicy

## SYNOPSIS
Updates the QoS policy settings.

## SYNTAX

### Query (cdxml) (Default)
```
Set-NetQosPolicy [[-Name] <String[]>] [-PolicyStore <String>] [-NetworkProfile <NetworkProfile>]
 [-Precedence <UInt32>] [-TemplateMatchCondition <Template>] [-UserMatchCondition <String>]
 [-AppPathNameMatchCondition <String>] [-IPProtocolMatchCondition <Protocol>] [-IPPortMatchCondition <UInt16>]
 [-IPSrcPrefixMatchCondition <String>] [-IPSrcPortMatchCondition <UInt16>]
 [-IPSrcPortStartMatchCondition <UInt16>] [-IPSrcPortEndMatchCondition <UInt16>]
 [-IPDstPrefixMatchCondition <String>] [-IPDstPortMatchCondition <UInt16>]
 [-IPDstPortStartMatchCondition <UInt16>] [-IPDstPortEndMatchCondition <UInt16>]
 [-NetDirectPortMatchCondition <UInt16>] [-URIMatchCondition <String>] [-URIRecursiveMatchCondition <Boolean>]
 [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>] [-MinBandwidthWeightAction <Byte>]
 [-ThrottleRateActionBitsPerSecond <UInt64>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetQosPolicy -InputObject <CimInstance[]> [-NetworkProfile <NetworkProfile>] [-Precedence <UInt32>]
 [-TemplateMatchCondition <Template>] [-UserMatchCondition <String>] [-AppPathNameMatchCondition <String>]
 [-IPProtocolMatchCondition <Protocol>] [-IPPortMatchCondition <UInt16>] [-IPSrcPrefixMatchCondition <String>]
 [-IPSrcPortMatchCondition <UInt16>] [-IPSrcPortStartMatchCondition <UInt16>]
 [-IPSrcPortEndMatchCondition <UInt16>] [-IPDstPrefixMatchCondition <String>]
 [-IPDstPortMatchCondition <UInt16>] [-IPDstPortStartMatchCondition <UInt16>]
 [-IPDstPortEndMatchCondition <UInt16>] [-NetDirectPortMatchCondition <UInt16>] [-URIMatchCondition <String>]
 [-URIRecursiveMatchCondition <Boolean>] [-PriorityValue8021Action <SByte>] [-DSCPAction <SByte>]
 [-MinBandwidthWeightAction <Byte>] [-ThrottleRateActionBitsPerSecond <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetQosPolicy** cmdlet modifies an existing Quality of Service (QoS) policy.
Match conditions or actions or general parameters of the policy such as *NetworkProfile* or *Precedence* can be changed.

Users cannot change the location of where an existing QoS policy is stored.
Changing the *PolicyStore* parameter value will fail.

If a policy was created to be in ActiveStore and a user attempts to make it persistent, such as storing the policy on the local computer, the user has to create a new policy and place it on the local computer (localhost).

If the *PolicyStore* parameter is not specified, then the cmdlet will search for and update the policy on the local computer (localhost).

## EXAMPLES

### Example 1: Update a QoS policy to apply to outgoing traffic from a domain-joined adapter
```
PS C:\> Set-NetQosPolicy -Name "SMB Policy" -NetworkProfile Domain
```

This command updates the QoS policy named SMB Policy so that it only applies to traffic that is outgoing from a domain-joined network adapter.

### Example 2: Update the precedence of a policy
```
PS C:\> Get-NetQosPolicy -Name "wildcard" | Set-NetQosPolicy -Precedence 250
```

This command gets the QoS policy named wildcard and updates the precedence of the policy to 250.

### Example 3: Add additional matching conditions
```
PS C:\> Set-NetQosPolicy -Name "Backup" -IPDstPortStart 3501 -IPDstPortEnd 3510
```

This command updates the QoS policy named Backup with additional matching conditions.

### Example 4: Update a QoS policy
```
PS C:\> Set-NetQosPolicy -Name "IIS" -Recursive $True -ThrottleRateActionBitsPerSecond 3000KB
```

This command updates the QoS policy named IIS, so that it applies to the return traffic for both the specified URI and subdirectories and files under the URI.
This cmdlet also sets a new throttling rate at 3,000,000 bytes per second.
An alias for the *ThrottleRateActionBitsPerSecond* parameter is *ThrottleRateAction*.
Another alias is *MaxBw*.

## PARAMETERS

### -AppPathNameMatchCondition
Specifies the name by which an application is run in Windows Server® 2012, such as `application.exe` or `%ProgramFiles%\application.exe`.

```yaml
Type: String
Parameter Sets: (All)
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
A valid DSCP value is in the range between 0 and 63.
In addition, users can enter -1 to remove the DSCP setting from the policy.

```yaml
Type: SByte
Parameter Sets: (All)
Aliases: DSCPValue, DSCP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPDstPortEndMatchCondition
Specifies the last port in a range of destination ports to be used to match the network traffic.
This parameter must be used in conjunction with the *IPDstPortStartMatchCondition* parameter.
The value of this parameter also must be larger than the value of the *IPDstPortStartMatchCondition* parameter.

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
To specify a range of destination ports, use both the *IPDstPortStartMatchCondition* and the *IPDstPortEndMatchCondition* parameters.

```yaml
Type: UInt16
Parameter Sets: (All)
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
For example, specifying this parameter value to 80 matches HTTP traffic sent by both HTTP clients and HTTP servers.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: IPPort, port

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPProtocolMatchCondition
Specifies the IP protocol to be used to match the network traffic.
The acceptable values for this parameter are: TCP, UDP, and Both.
If this parameter is unspecified, then Both is the default value.
The QoS policy will apply to both TCP and UDP traffic.

```yaml
Type: Protocol
Parameter Sets: (All)
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
To specify a range of source ports, use both the *IPSrcPortStartMatchCondition* and the *IPSrcPortEndMatchCondition* parameters.

```yaml
Type: UInt16
Parameter Sets: (All)
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
Aliases: IPSrcPrefix, SourceAddress, sa, src, srcaddr, srcip

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MinBandwidthWeightAction
Specifies a numerical value for minimum bandwidth that a flow should get relatively.
The actual bandwidth a flow gets will depend on the weights assigned to other flows in the computer.
The acceptable values for this parameter are: 1 through 100.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: MinBandwidthWeight, minbww, weight

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
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: 0
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
Aliases: NetDirectPort, ndport, networkdirectport

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
Accepted values: Domain, Public, Private, All

Required: False
Position: Named
Default value: None
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
Parameter Sets: Query (cdxml)
Aliases: store

Required: False
Position: Named
Default value: None
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
A valid 802.1p value is in the range between 0 and 7.
In addition, users can enter -1 to remove the 802.1p priority setting from the policy.

```yaml
Type: SByte
Parameter Sets: (All)
Aliases: PriorityValue, PriorityValue8021, pri, dot1p

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateMatchCondition
Specifies a number of filters built in Windows Server® 2012.
The acceptable values for this parameter are: FCoE, iSCSI, LiveMigration, NFS, SMB, or Cluster.
For more information, see the New-NetQosPolicy cmdlet.

```yaml
Type: Template
Parameter Sets: (All)
Aliases: Template
Accepted values: None, Default, iSCSI, FCoE, SMB, NFS, LiveMigration, Cluster

Required: False
Position: Named
Default value: None
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

### -ThrottleRateActionBitsPerSecond
Specifies a throttle rate in bits per second to set the maximum bandwidth that can be consumed.

```yaml
Type: UInt64
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: URI, url

Required: False
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
Parameter Sets: (All)
Aliases: URIRecursive, urlrecursive, recursive

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserMatchCondition
Specifies the user or group name in Active Directory, such as `contoso\davidchew`.
This parameter is usually specified with other filtering parameter such as the *AppPathNameMatchCondition* parameter.

```yaml
Type: String
Parameter Sets: (All)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.NetQosPolicy.NetworkProfile

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.NetQosPolicy.Template

### System.String

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.NetQosPolicy.Protocol

### System.UInt16

### System.Boolean

### System.SByte

### System.Byte

### System.UInt64

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosPolicySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The **MSFT_NetQosPolicySettingData** object contains a QoS policy.
Only if the *PassThru* parameter is specified does this cmdlet return the **MSFT_NetQosPolicySettingData** object.

## NOTES

## RELATED LINKS

[Get-NetQosPolicy](./Get-NetQosPolicy.md)

[New-NetQosPolicy](./New-NetQosPolicy.md)

[Remove-NetQosPolicy](./Remove-NetQosPolicy.md)

