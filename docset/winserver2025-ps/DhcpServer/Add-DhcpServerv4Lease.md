---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerv4Lease_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4lease?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerv4Lease
---

# Add-DhcpServerv4Lease

## SYNOPSIS
Adds a new IPv4 address lease in the DHCP server service.

## SYNTAX

```
Add-DhcpServerv4Lease [-IPAddress] <IPAddress> [-ScopeId] <IPAddress> [-ClientId] <String>
 [-AddressState <String>] [-HostName <String>] [-Description <String>] [-ComputerName <String>] [-PassThru]
 [-DnsRR <String>] [-DnsRegistration <String>] [-ClientType <String>] [-LeaseExpiryTime <DateTime>]
 [-NapCapable <Boolean>] [-NapStatus <String>] [-ProbationEnds <DateTime>] [-PolicyName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerv4Lease** cmdlet adds a new IPv4 address lease on the Dynamic Host Configuration Protocol (DHCP) server service.
This cmdlet is only supported for DHCP server service that runs on Windows Server® 2012.
This cmdlet is for testing purposes only.

## EXAMPLES

### Example 1: Add an Ipv4 lease on the DHCP server service
```
PS C:\> Add-DhcpServerv4Lease -IPAddress 10.10.10.11 -ScopeId 10.10.10.0 -ClientId F0-DE-F1-7A-00-5E -LeaseExpiryTime "2012-01-28 01:38:13Z" -HostName "MyComputer.contoso.com"
```

This example adds an IPv4 address lease for the IPv4 address 10.10.10.11 on the DHCP server service that runs on the local computer.

## PARAMETERS

### -AddressState
Specifies the state of the IPv4 Address lease.
The acceptable values for this parameter are: Offered, Active, Declined, Expired, and Inactive.
The default value is Active.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Active, Declined, Expired, ActiveReservation, InactiveReservation

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -ClientId
Specifies the client identifier (ID) to be set on the IPv4 address lease.
Windows clients use the MAC address as the client ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientType
Specifies the type of the client.
The acceptable values for this parameter are: Unspecified, DHCP, BootP, Both, Reservation, and None.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: UnSpecified, Dhcp, BootP, None, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer that runs the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -Description
Specifies the description string to be set on the IPv4 address lease.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsRR
Indicates the type of DNS record to be registered by the DHCP server service for this lease.
The acceptable values for this parameter are:

- PTR.
Only PTR record to be registered by the DHCP server service.
- AandPTR.
Both A and PTR records to be registered by the DHCP server service.
- NoRegistration.
No DNS registration is performed by the DHCP server service.
If the dynamic DNS is turned off on the DHCP server service, this parameter is set to NoRegistration.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: A, PTR, AandPTR, NoRegistration

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsRegistration
Indicates the status of the DNS registration of the lease.
The acceptable values for this parameter are:

- Complete.
  - For an active lease, registration of the required records, as specified by the *DnsRR* parameter value of PTR or AandPTR, is complete.
  - For an expired lease, deletion of the required records is complete.
- Pending.
  - For an active lease, registration of the required records, as specified by the *DnsRR* parameter value of PTR or AandPTR, is pending.
  - For an expired lease, deletion of the required records is pending.
- Not applicable.
  - If the *DnsRR* parameter is set to NoRegistration, such as when no dynamic DNS registration is to be performed by the DHCP server service, this parameter is set to Not applicable.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Complete, Pending, NotApplicable

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostName
Specifies the DNS host name of the client for which the IP address lease to add.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPAddress
Specifies the IPv4 address for which the IPv4 address lease record to add on the DHCP server service.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LeaseExpiryTime
Specifies the expiry time of the IPv4 address lease.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NapCapable
Indicates that the client is network access protection (NAP) capable.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NapStatus
Specifies the NAP status of the client.
The acceptable values for this parameter are: NoQuarantine, RestrictedAccess, DropPacket, Probation, Exempt, DefaultQuarSetting, and NoQuarInfo.
The default value is NoQuarantine.

If you specify this parameter as Probation and a probation period is not specified, this cmdlet returns an error.

If you do not specify this parameter or specified it as something other than Probation and probation period is not specified, the probation period to set to 0.

If you do not specify this parameter and a probation period is specified, this parameter is set to Probation.

If you do not specify this parameter or specify it  something other than Probation and the *ProbationEnds* parameter is specified, this cmdlet returns an error.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: FullAccess, RestrictedAccess, DropPacket, InProbation, Exempt, DefaultQuarantineSetting, NoQuarantineInfo

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

### -PolicyName
Specifies the name of the policy to be set on the IPv4 address lease record that is added.

The DHCP server service does not check whether the policy specified exists on the server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProbationEnds
Specifies the end-time of probation to be set on the IPv4 address lease record.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScopeId
Specifies the subnet mask to be set on the IPv4 address lease record that is added.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Lease
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4Lease
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerv4Lease](./Get-DhcpServerv4Lease.md)

[Remove-DhcpServerv4Lease](./Remove-DhcpServerv4Lease.md)

