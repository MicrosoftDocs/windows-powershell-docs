---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespace.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/set-dfsnroot?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsnRoot
---

# Set-DfsnRoot

## SYNOPSIS
Changes settings for a DFS namespace.

## SYNTAX

```
Set-DfsnRoot [-Path] <String> [[-EnableSiteCosting] <Boolean>] [[-EnableInsiteReferrals] <Boolean>]
 [[-EnableAccessBasedEnumeration] <Boolean>] [[-EnableRootScalability] <Boolean>]
 [[-EnableTargetFailback] <Boolean>] [[-Description] <String>] [[-State] <State>]
 [[-TimeToLiveSec] <UInt32>] [[-GrantAdminAccounts] <String[]>] [[-RevokeAdminAccounts] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The **Set-DfsnRoot** cmdlet changes settings for a Distributed File System (DFS) namespace.

You can use this cmdlet to enable or disable the following settings:

- **Site costing**
- **In-site referrals**
- **Access-based enumeration**
- **Root scalability**
- **Target failback**

You can also add or change a descriptive comment, change the state of the DFS namespace, or set the
Time to Live (TTL) interval for referrals.

To manage the DFS namespace, you can use this cmdlet to grant or revoke permissions to users or user
groups. Users who have these permissions can add, remove, and modify namespace folders and folder
targets for the DFS namespace.

For more information about DFS namespaces, see
[Overview of DFS Namespaces](https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Change root scalability and TTL

```powershell
Set-DfsnRoot -Path '\\Contoso\AccountingResources' -EnableRootScalability $true -TimeToLiveSec 900
```

This command modifies settings for the DFS namespace that has the path
`\\Contoso\AccountingResources`. The command enables root scalability, which allows the DFS
namespace server to poll domain controllers for updates. The command also sets the referral TTL
interval to 900 seconds.

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

### -Description

Specifies a description for a DFS namespace.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: desc

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableAccessBasedEnumeration

Indicates whether a DFS namespace uses Access-based enumeration. If this value is `$true`, a DFS
namespace server shows a user only the files and folders that the user can access.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: abe, abde

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableInsiteReferrals

Indicates whether a DFS namespace server provides a client only with referrals that are in the same
site as the client. If this value is `$true`, a DFS namespace server provides only in-site
referrals. If this value is `$false`, the DFS namespace server provides in-site referrals first,
then other referrals.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: insite

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableRootScalability

Indicates whether a DFS namespace uses root scalability mode. If this value is `$true`, DFS
namespace servers connect to the nearest domain controllers for periodic namespace updates. If this
value is `$false`, the servers connect to the primary domain controller (PDC) emulator.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: RootScalability, rootscale

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableSiteCosting

Indicates whether a DFS namespace uses cost-based selection. If a client cannot access a folder
target in-site, a DFS namespace server selects the least resource-intensive alternative. If you
provide a value of `$true` for this parameter, the DFS namespace favors high-speed links over wide
area network (WAN) links.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: SiteCosting, sitecost

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableTargetFailback

Indicates whether a DFS namespace uses target failback. If a client attempts to access target link
on a server and that server is not available, the client fails over to another referral. If this
value is `$true`, once the first server becomes available again, the client fails back to the first
server. If this value is `$false`, the DFS namespace server does not require the client to fail back
to the preferred server.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: failback, TargetFailback

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GrantAdminAccounts

Specifies an array of accounts. This cmdlet grants management permissions the users and user groups
specified for the DFS namespace. Users can add, remove, and modify namespace folders and folder
targets.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: GrantAdmin, GrantAdminAccess

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Specifies a path for the root of a DFS namespace.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RootPath, root, namespace, NamespaceRoot

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RevokeAdminAccounts

Specifies an array of accounts. This cmdlet removes management permissions for the users and user
groups specified for the DFS namespace.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: RevokeAdmin, RevokeAdminAccess

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State

Specifies the state of the DFS namespace root. The acceptable values for this parameter are:

- `Online`
- `Offline`

Clients do not receive referrals for a DFS namespace folder that is offline. If you set a namespace
root to a value of `Offline`, the entire namespace becomes inaccessible.

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.DfsNamespaceRootTarget.State
Parameter Sets: (All)
Aliases:
Accepted values: Offline, Online

Required: False
Position: 7
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

### -TimeToLiveSec

Specifies a TTL interval, in seconds, for referrals. Clients store referrals to root targets for
this length of time. The default TTL interval for root referrals is 300 seconds.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: ttl, TimeToLive

Required: False
Position: 8
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

### System.Boolean

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DfsNamespace.State

### System.UInt32

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-DfsnRoot](./Get-DfsnRoot.md)

[New-DfsnRoot](./New-DfsnRoot.md)

[Remove-DfsnRoot](./Remove-DfsnRoot.md)
