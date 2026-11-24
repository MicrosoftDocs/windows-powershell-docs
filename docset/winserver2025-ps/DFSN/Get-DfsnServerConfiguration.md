---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceServerConfig.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/get-dfsnserverconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsnServerConfiguration
---

# Get-DfsnServerConfiguration

## SYNOPSIS
Gets DFS namespace settings for a DFSN root server.

## SYNTAX

```
Get-DfsnServerConfiguration [-ComputerName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The **Get-DfsnServerConfiguration** cmdlet gets Distributed File System (DFS) namespace settings for
a DFS namespace root server. A DFS namespace root server hosts one or more namespace root targets.
You can use this cmdlet to see current settings for a server, and you can use the
**Set-DfsnServerConfiguration** cmdlet to make changes to a server.

## EXAMPLES

### Example 1: Get settings for a server

```powershell
Get-DfsnServerConfiguration -ComputerName "Contoso-FS"
```

```Output
ComputerName              : Contoso-FS
LdapTimeoutSec            :
PreferLogonDC             :
EnableSiteCostedReferrals :
EnableInsiteReferrals     :
SyncIntervalSec           :
UseFqdn                   :
```

This command gets the Retrieves the configuration settings of the DFS namespace server Contoso-FS.

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

Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a
[New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or
[Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
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

Specifies the host name or fully qualified domain name (FQDN) for a DFS namespace server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceServer

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Set-DfsnServerConfiguration](./Set-DfsnServerConfiguration.md)
