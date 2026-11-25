---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsNamespaceRootTarget.cdxml-help.xml
Module Name: DFSN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsn/get-dfsnroottarget?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsnRootTarget
---

# Get-DfsnRootTarget

## SYNOPSIS
Gets settings for root targets of a DFS namespace.

## SYNTAX

```
Get-DfsnRootTarget [-Path] <String> [[-TargetPath] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The **Get-DfsnRootTarget** cmdlet gets settings for root targets of a Distributed File System (DFS)
namespace. You can specify a DFS namespace path to see all the root targets for that namespace. You
can specify a namespace path and a target path to see settings for a single root target.

For more information about DFS namespaces, see
[Overview of DFS Namespaces](https://technet.microsoft.com/library/cc730736) on TechNet.

## EXAMPLES

### Example 1: Get root targets for a DFS namespace

```powershell
Get-DfsnRootTarget -Path '\\Contoso\AccountingSoftware'
```

This command gets the DFS namespace root targets for the namespace that has the path
`\\Contoso\AccountingSoftware`.

### Example 2: Get a specified root target

```powershell
Get-DfsnRootTarget -Path '\\Contoso\AccountingSoftware' -TargetPath '\\Contoso-FS\Software'
```

This command gets a single root target, specified by using the path `\\Contoso\AccountingSoftware`
and the target path `\\Contoso-FS\Software`.

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

### -Path

Specifies a path for the root folder of a DFS namespace.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DfsPath, NamespaceRoot

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetPath

Specifies a path for the root folder target of a DFS namespace. This cmdlet gets settings for the
root target that has the path specified.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Target, DfsTarget, RootTargetPath

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

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

## NOTES

## RELATED LINKS

[New-DfsnRootTarget](./New-DfsnRootTarget.md)

[Remove-DfsnRootTarget](./Remove-DfsnRootTarget.md)

[Set-DfsnRootTarget](./Set-DfsnRootTarget.md)
