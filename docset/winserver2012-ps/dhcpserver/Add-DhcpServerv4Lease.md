---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/add-dhcpserverv4lease?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DhcpServerv4Lease

## SYNOPSIS
Adds a new IPv4 address lease in the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Add-DhcpServerv4Lease [-ScopeId] <IPAddress> [-IPAddress] <IPAddress> [-ClientId] <String>
 [-AddressState <String>] [-AsJob] [-CimSession <CimSession[]>] [-ClientType <String>] [-ComputerName <String>]
 [-Description <String>] [-DnsRegistration <String>] [-DnsRR <String>] [-HostName <String>]
 [-LeaseExpiryTime <DateTime>] [-NapCapable <Boolean>] [-NapStatus <String>] [-PassThru] [-PolicyName <String>]
 [-ProbationEnds <DateTime>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DhcpServerv4Lease** cmdlet adds a new IPv4 address lease on the Dynamic Host Configuration Protocol (DHCP) server service.
This cmdlet is only supported for DHCP server service running on Windows Server® 2012.
This cmdlet is for testing purposes only.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-DhcpServerv4Lease -IPAddress 10.10.10.11 -ScopeId 10.10.10.0 -ClientId F0-DE-F1-7A-00-5E -LeaseExpiryTime "2012-01-28 01:38:13Z" -HostName MyComputer.contoso.com
```

This example adds an IPv4 address lease for the IPv4 address 10.10.10.11 on the DHCP server service running on the local computer.

## PARAMETERS

### -AddressState
Specifies the state of the IPv4 Address lease.
The acceptable values for this parameter are: Offered, Active, Declined, Expired, or Inactive.
The default value is Active.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
The acceptable values for this parameter are: Unspecified, DHCP, BootP, Both, Reservation, or None.

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

### -DnsRegistration
Indicates the status of the DNS registration of the lease. 
The acceptable values for this parameter are:

 - Complete: For an active lease, registration of the required records , as specified by the **DnsRR** parameter value of PTR or AandPTR, is complete. 

 - - For an expired lease, deletion of the required records has been done. 

 - Pending: For an active lease, registration of the required records, as specified by the **DnsRR** parameter value of PTR or AandPTR, is pending. 

 - - For an expired lease, deletion of the required records is pending. 

 - Not applicable: When the **DnsRR** parameter is set to NoRegistration such as when no dynamic DNS registration is to be performed by the DHCP server service, this parameter is set to Not applicable.

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

 - PTR: Only PTR record to be registered by the DHCP server service. 

 - AandPTR: Both A and PTR records to be registered by the DHCP server service. 

 - NoRegistration: No DNS registration is done by the DHCP server service.
If the dynamic DNS is turned off on the DHCP server service, then this parameter is set to NoRegistration.

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

### -HostName
Specifies the DNS host name of the client for which the IP address lease is to be added.

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
Specifies the IPv4 Address for which the IPv4 address lease record is to be added on the DHCP server service.

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
The acceptable values for this parameter are: True or False.

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
The acceptable values for this parameter are: NoQuarantine, RestrictedAccess, DropPacket, Probation, Exempt, DefaultQuarSetting, or NoQuarInfo.
The default value is NoQuarantine. 

If this parameter is specified as Probation and a probation period is not specified, then this cmdlet will return an error. 

If this parameter is not specified or is specified as something other than Probation and probation period is not specified, then the probation period to set to 0. 

If this parameter is not specified and probation period is specified, then this parameter is set to Probation. 

If this parameter is not specified or is specified as something other than Probation and the **ProbationEnds** parameter is specified, then this cmdlet will return an error.

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
Specifies the name of the policy to be set on the IPv4 address lease record being added. 
Note: The DHCP server service does not check whether the policy specified exists on the server.

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

The default value is 0.

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
Specifies the subnet mask to be set on the IPv4 address lease record being added.

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

