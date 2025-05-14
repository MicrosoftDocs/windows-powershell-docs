---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerDsSetting_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/set-dnsserverdssetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DnsServerDsSetting
---

# Set-DnsServerDsSetting

## SYNOPSIS
Modifies DNS Active Directory settings.

## SYNTAX

```
Set-DnsServerDsSetting [-DirectoryPartitionAutoEnlistInterval <TimeSpan>] [-LazyUpdateInterval <UInt32>]
 [-MinimumBackgroundLoadThreads <UInt32>] [-RemoteReplicationDelay <UInt32>] [-ComputerName <String>]
 [-PollingInterval <UInt32>] [-TombstoneInterval <TimeSpan>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DnsServerDsSetting** cmdlet modifies Domain Name System (DNS) Active Directory settings.

Note: If any of the set operations fails, the **Set-DnsServerDsSetting** cmdlet must not terminate.
It must continue to set other operations and display the modified settings.

## EXAMPLES

### Example 1: Set an auto-enlist interval for a directory partition
```
PS C:\> Set-DnsServerDsSetting -DirectoryPartitionAutoEnlistInterval 15.00:00:00 -PassThru

PollingInterval(s)                   : 180
TombstoneInterval                    : 14.00:00:00
DirectoryPartitionAutoEnlistInterval : 15.00:00:00
LazyUpdateInterval(s)                : 3
MinimumBackgroundLoadThreads         : 1
RemoteReplicationDelay(s)            : 30
```

This command sets an auto-enlist interval to 15 days for a directory partition.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -ComputerName
Specifies a DNS server.
The acceptable values for this parameter are: an IPv4 address; an IPv6 address; and any other value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NETBIOS name.

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

### -DirectoryPartitionAutoEnlistInterval
Specifies the interval, during which a DNS server tries to enlist itself in a DNS domain partition and DNS forest partition, if it is not already enlisted.
We recommend that you limit this value to the range one hour to 180 days, inclusive, but you can use any value.
We recommend that you set the default value to one day.
You must set the value 0 (zero) as a flag value for the default value.
However, you can allow zero and treat it literally.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LazyUpdateInterval
Specifies a value, in seconds, to determine how frequently the DNS server submits updates to the directory server without specifying the LDAP_SERVER_LAZY_COMMIT_OID control (\[MS-ADTS\] section 3.1.1.3.4.1.7) at the same time that it processes DNS dynamic update requests.
We recommend that you limit this value to the range 0x00000000 to 0x0000003c.
You must set the default value to 0x00000003.
You must set the value zero to indicate that the DNS server does not specify the LDAP_SERVER_LAZY_COMMIT_OID control at the same time that it processes DNS dynamic update requests.
For more information about LDAP_SERVER_LAZY_COMMIT_OID, see [LDAP_SERVER_LAZY_COMMIT_OID control code](https://technet.microsoft.com/en-us/library/aa366982).

The LDAP_SERVER_LAZY_COMMIT_OID control instructs the DNS server to return the results of a directory service modification command after it is completed in memory but before it is committed to disk.
In this way, the server can return results quickly and save data to disk without sacrificing performance.

The DNS server must send this control only to the directory server that is attached to an LDAP update that the DNS server initiates in response to a DNS dynamic update request.

If the value is nonzero, LDAP updates that occur during the processing of DNS dynamic update requests must not specify the LDAP_SERVER_LAZY_COMMIT_OID control if a period of less than DsLazyUpdateInterval seconds has passed since the last LDAP update that specifies this control.
If a period that is greater than DsLazyUpdateInterval seconds passes, during which time the DNS server does not perform an LDAP update that specifies this control, the DNS server must specify this control on the next update.

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

### -MinimumBackgroundLoadThreads
Specifies the minimum number of background threads that the DNS server uses to load zone data from the directory service.
You must limit this value to the range 0x00000000 to 0x00000005, inclusive.
You must set the default value to 0x00000001, and you must treat the value zero as a flag value for the default value.

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

### -PollingInterval
Specifies how frequently the DNS server polls Active Directory Domain Services (AD DS) for changes in Active Directory-integrated zones.
You must limit the value to the range 30 seconds to 3,600 seconds, inclusive.

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

### -RemoteReplicationDelay
Specifies the minimum interval, in seconds, that the DNS server waits between the time that it determines that a single object has changed on a remote directory server, to the time that it tries to replicate a single object change.
You must limit the value to the range 0x00000005 to 0x00000E10, inclusive.
You must set the default value to 0x0000001E, and you must treat the value zero as a flag value for the default value.

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

### -TombstoneInterval
Specifies the amount of time that DNS keeps tombstoned records alive in Active Directory.
We recommend that you limit this value to the range three days to eight weeks, inclusive, but you can set it to any value in the range 82 hours to 8 weeks.
We recommend that you set the default value to 14 days and treat the value zero as a flag value for the default.
However, you can allow the value zero and treat it literally.

At 2:00 A.M.
local time every day, the DNS server must search all directory service zones for nodes that have the Active Directory **dnsTombstoned** attribute set to True, and for a directory service **EntombedTime** (section 2.2.2.2.3.23 of MS-DNSP) value that is greater than previous directory service **DSTombstoneInterval** seconds.
You must permanently delete all such nodes from the directory server.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerDsSetting

## NOTES

## RELATED LINKS

[DNS Server Integer Properties](https://msdn.microsoft.com/en-us/library/cc422472(v=prot.10))

[[MS-DNSP]: Domain Name Service (DNS) Server Management Protocol Specification](https://msdn.microsoft.com/en-us/library/cc448821(v=prot.10))

[Get-DnsServerDsSetting](./Get-DnsServerDsSetting.md)

