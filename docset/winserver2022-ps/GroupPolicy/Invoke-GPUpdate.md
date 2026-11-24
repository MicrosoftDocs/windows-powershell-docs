---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/invoke-gpupdate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-GPUpdate
---

# Invoke-GPUpdate

## SYNOPSIS

Schedules a remote Group Policy refresh on the specified computer.

## SYNTAX

### NonSyncSet (Default)

```
Invoke-GPUpdate [-AsJob] [-Boot] [[-Computer] <String>] [[-RandomDelayInMinutes] <Int32>] [-Force]
 [-LogOff] [-Target <String>] [<CommonParameters>]
```

### SyncSet

```
Invoke-GPUpdate [-AsJob] [-Boot] [[-Computer] <String>] [[-RandomDelayInMinutes] <Int32>] [-LogOff]
 [-Target <String>] [-Sync] [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-GPUpdate` cmdlet refreshes Group Policy settings, including security settings that are
set on remote computers by scheduling the running of the Gpupdate command on a remote computer. You
can combine this cmdlet in a scripted fashion to schedule the Gpupdate command on a group of
computers.

The refresh can be scheduled to immediately start a refresh of policy settings or wait for a
specified period of time, up to a maximum of 31 days. To avoid putting a load on the network, the
refresh times will be offset by a random delay.

## EXAMPLES

### Example 1: Schedule a Group Policy refresh on the current computer

```powershell
Invoke-GPUpdate
```

This command schedules a Group Policy refresh on the computer on which you are running the
`Invoke-GPUpdate` cmdlet.

### Example 2: Schedule a Group Policy refresh on a remote computer

```powershell
Invoke-GPUpdate -Computer "CONTOSO\COMPUTER-02" -Target "User"
```

This command schedules a Group Policy refresh on a remote computer named `CONTOSO\COMPUTER-02` that
only schedule to update the user policy settings in synchronous mode.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete. The cmdlet immediately returns an object that represents the job and then displays the
command prompt. You can continue to work in the session while the job completes. To manage the job,
use the `*-Job` cmdlets.

To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372)
cmdlet. For more information about Windows PowerShell® background jobs, see
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

### -Boot

Indicates that the cmdlet restarts the computer after the Group Policy settings are applied. This is
required for those Group Policy client side extensions (CSEs) that do not process Group Policy on a
background update cycle, but do process Group Policy at computer startup, for instance, per-computer
Software Installation policy settings.

This parameter has no effect if there are no CSEs called that require a restart.

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

### -Computer

Specifies the name of the computer for which this cmdlet schedules a Group Policy refresh. You can
specify the computer name in one of the following formats:

- Full computer name (FQDN computer name); for example, `computer-01.sales.contoso.com`.

- Fully qualified domain name (FQDN)\computer name; for example, `sales.contoso.com\computer-01`.

- NetBIOS domain name\computer name; for example, `sales\computer-01`.

- Computer name (host name): for example, `computer-01`.

If the computer name is not specified, the computer in which this cmdlet is run will have its Group
Policy settings refreshed.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DNSHostName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NonSyncSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogOff

Indicates that the cmdlet logs off the current user after the policy settings have been updated.
This is required for those Group Policy client-side extensions (CSEs) that do not process Group
Policy on a background update cycle but do process Group Policy when a user logs on. Examples
include per-user Software Installation policy settings and the Folder Redirection extension.

This parameter has no effect if there are no CSEs called that require a logoff.

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

### -RandomDelayInMinutes

Specifies the delay, in minutes, that Task Scheduler waits, with a random factor added to lower the
network load, before running a scheduled Group Policy refresh.

You can specify a delay in from 0 minutes to a maximum of 44640 minutes (31 days):

- A value of 0 causes the Group Policy refresh to run as soon as the gpupdate task has been
  scheduled.

- A value in the range of 1 minute to the maximum value of 44640 minutes cause the Group Policy
refresh to delay the specified number of minutes plus a random offset before starting the Group
Policy refresh.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: RandomnessInMinutes

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sync

Indicates that the cmdlet processes the next foreground Group Policy application to be done
synchronously. Foreground Group Policy applications occur at computer startup and user logon. You
can specify this for the user, computer or both using the **Target** parameter.

On a client computer, by default, Group Policy processes synchronously at computer startup and
asynchronously at user logon.

On a server, by default, Group Policy processes synchronously at computer startup and at user logon.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SyncSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target

Specifies that only the user or computer policy settings are refreshed. By default, both user and
computer policy settings are refreshed.

The acceptable values for this parameter are:

- User
- Computer

If the **Target** parameter is not specified both user and computer policy settings are refreshed.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

This cmdlet does not take any object as input.

## OUTPUTS

### None

This cmdlet does not generate any output.

## NOTES

* This cmdlet does not support scheduling a Group Policy refresh for computers running Windows XP or
  earlier.
* In order to successfully schedule a Group Policy refresh for computers using this cmdlet, the
  following Firewall rules must be set on each client computer to allow the following connections:

- Remote Scheduled Tasks Management (RPC) 
- Remote Scheduled Tasks Management (RPC-ERMAP) 
- Windows Management Instrumentation (WMI-IN)

## RELATED LINKS

