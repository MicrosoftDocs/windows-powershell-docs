---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceServerConfig.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/set-dfsnserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsnServerConfiguration
---

# Set-DfsnServerConfiguration

## SYNOPSIS
Changes settings for a DFS namespace root server.

## SYNTAX

```
Set-DfsnServerConfiguration [-ComputerName] <String> [[-SyncIntervalSec] <UInt32>]
 [[-EnableSiteCostedReferrals] <Boolean>] [[-EnableInsiteReferrals] <Boolean>]
 [[-LdapTimeoutSec] <UInt32>] [[-PreferLogonDC] <Boolean>] [[-UseFqdn] <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The **Set-DfsnServerConfiguration** cmdlet changes settings for a Distributed File System (DFS)
namespace root server. A DFS namespace root server hosts one or more namespace root targets.

You can use this cmdlet to enable in-site referrals or to use cost in organizing referrals for
targets in a site. You can also change the synchronization interval for servers that connect to a
primary domain controller (PDC) emulator and change the Lightweight Directory Access Protocol (LDAP)
time-out. You can specify whether referrals prefer the logon domain controller. You can also specify
whether the server provides referrals as fully qualified domain names (FQDN) or NETBios names.

To see current values for these settings, use the **Get-DfsnServerConfiguration** cmdlet.

## EXAMPLES

### Example 1: Set LDAP time-out for a DFS namespace server

```powershell
Set-DfsnServerConfiguration -ComputerName 'localhost' -LdapTimeoutSec 60
```

This command sets an LDAP time-out value of 60 seconds for the local computer, which is a DFS
namespace server.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the host name or FQDN for the DFS namespace server for which the cmdlet modifies settings.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Server, name, NamespaceServer

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableInsiteReferrals

Indicates whether this server provides only in-site referrals. If you assign a value of `$true`, the
server returns only referrals for targets in the same site as the client. If you assign a value of
`$false`, the server returns in-site referrals and other referrals.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: insite

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableSiteCostedReferrals

Indicates whether the server can use cost-based selection. If you specify a value of `$true`, the
DFS namespace server provides referrals for folder targets to clients in the following order:

- Folder targets in the same site as a client, in random order.
- Folder targets for which the DFS namespace server has information. The referrals for the nearest
  site are first, in random order, followed by the next nearest site, in random order.
- Targets for which DFS namespace server has no site information, in random order.

If you specify a value of `$false`, the DFS namespace server provides referrals for folder targets to
clients in the following order:

- Folder targets in the same site as the client, in random order.
- Other folder targets, in random order.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: Sitecosted, SiteCostedReferrals

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LdapTimeoutSec

Specifies a time-out value, in seconds, for Lightweight Directory Access Protocol (LDAP) requests
for the DFS namespace server.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: LdapTimeout

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PreferLogonDC

Indicates whether to prefer the logon domain controller in referrals. If you specify a value of
`$true` for this parameter, the DFS namespace server places referrals to the computer that hosts the
logon domain controller at the top of the list of referrals.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SyncIntervalSec

Specifies an interval, in seconds. This interval controls how often domain-based DFS namespace root
servers and domain controllers connect to the PDC emulator to get updates of DFS namespace metadata.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: SyncInterval

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseFqdn

Indicates whether a DFS namespace server uses FQDNs in referrals. If this parameter has a value of
`$true`, the server uses FQDNs in referrals. If this parameter has a value of `$false`, the server
uses NetBIOS names. The default for DFS namespace servers is to use NetBIOS names in referrals.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: Fqdn, dfsdnsconfig, UseFullyQualifiedDomainNames

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.UInt32

### System.Boolean

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-DfsnServerConfiguration](./Get-DfsnServerConfiguration.md)
