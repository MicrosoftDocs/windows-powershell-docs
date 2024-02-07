---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/get-wsuscomputer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WsusComputer
---

# Get-WsusComputer

## SYNOPSIS

Gets the WSUS computer object that represents the client computer.

## SYNTAX

### AllComputers (Default)

```powershell
Get-WsusComputer [-UpdateServer <IUpdateServer>] [-All] [<CommonParameters>]
```

### Scoped

```powershell
Get-WsusComputer [-UpdateServer <IUpdateServer>] [-NameIncludes <String>]
 [-ComputerTargetGroups <StringCollection>] [-IncludeSubgroups]
 [-ComputerUpdateStatus <WsusUpdateInstallationState>]
 [-ExcludedInstallationStates <UpdateInstallationStates[]>]
 [-IncludedInstallationStates <UpdateInstallationStates[]>] [-FromLastSyncTime <DateTime>]
 [-ToLastSyncTime <DateTime>] [-FromLastReportedStatusTime <DateTime>] [-ToLastReportedStatusTime <DateTime>]
 [-IncludeDownstreamComputerTargets] [-RequestedTargetGroupNames <StringCollection>] [<CommonParameters>]
```

## DESCRIPTION

The **Get-WsusComputer** cmdlet gets one or more Windows Server Update Services (WSUS) computers based on the specified filtering criteria such as operating system, computer name, update installation status, last reported status time, and etcetera.

If the [Get-WsusServer](./Get-WsusServer.md) cmdlet is run and the resulting **IUpdateServer** object is passed into this cmdlet, then the specified server will be used rather than the local server.

This cmdlet can be passed into the [Add-WsusComputer](./Add-WsusComputer.md) cmdlet.

## EXAMPLES

### Example 1: Get all client computers

```text
PS C:\> Get-WsusComputer -All
Computer                      IP Address                    Operating System              Last Status Report
--------                      ----------                    ----------------              ------------------
contoso                       XXXX:XXXX:XX:X:XXXX:XXX:XXXX: Windows Server 2008           6/2/2010 12:00:00 AM
                              XXXX                          Enterprise Edition (full                                                             installation)
```

This command gets all client computers.

### Example 2: Get client computers that have names that contain a string

```text
PS C:\> Get-WsusComputer -NameIncludes "contoso"
Computer                      IP Address                    Operating System              Last Status Report
--------                      ----------                    ----------------              ------------------
contoso                       XXXX:XXXX:XX:X:XXXX:XXX:XXXX: Windows Server 2008           6/2/2010 12:00:00 AM
                              XXXX                          Enterprise Edition (full
                                                            installation)
```

This command gets the client computer whose name includes contoso.

### Example 3: Get client computers by specifying dates

```text
PS C:\> Get-WsusComputer -FromLastReportedStatusTime 6/1/10 -ToLastReportedStatusTime 6/30/10
Computer                      IP Address                    Operating System              Last Status Report
--------                      ----------                    ----------------              ------------------
contoso                       XXXX:XXXX:XX:X:XXXX:XXX:XXXX: Windows Server 2008           6/2/2010 12:00:00 AM
                              XXXX                          Enterprise Edition (full
                                                            installation)
```

This command gets all client computers with a last reported status date and time between June 1, 2010 and June 30, 2010.

## PARAMETERS

### -All

Specifies that all computers are to be returned. The information displayed includes the computer name, IP address, operating system, and last status report time.

```yaml
Type: SwitchParameter
Parameter Sets: AllComputers
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerTargetGroups

Specifies the list of target group to search.

```yaml
Type: StringCollection
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerUpdateStatus

Specifies the computer update state as represented in the WSUS Console user interface. The acceptable values for this parameter are:

- FailedOrNeeded
- InstalledNotApplicableOrNoStatus
- Failed
- InstalledNotApplicable
- NoStatus
- Any

```yaml
Type: WsusUpdateInstallationState
Parameter Sets: Scoped
Aliases:
Accepted values: NoStatus, InstalledOrNotApplicable, InstalledOrNotApplicableOrNoStatus, Failed, Needed, FailedOrNeeded, Any

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludedInstallationStates

Specifies the installation states to exclude. The acceptable values for this parameter are:

- All
- Downloaded
- Failed
- Installed
- InstalledPendingReboot
- NotApplicable
- NotInstalled
- Unknown

```yaml
Type: UpdateInstallationStates[]
Parameter Sets: Scoped
Aliases:
Accepted values: Unknown, NotApplicable, NotInstalled, Downloaded, Installed, Failed, InstalledPendingReboot, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromLastReportedStatusTime

Specifies the earliest reported status time. This parameter can be used in combination with the _ToLastReportedStatusTime_ parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromLastSyncTime

Specifies the earliest last synchronization time for which to search. This parameter can be used in combination with the _ToLastSynchTime_ parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeDownstreamComputerTargets

Specifies that clients of a downstream server should be included, not clients of this server.

```yaml
Type: SwitchParameter
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeSubgroups

Specifies that the _ComputerTargetGroups_ parameter should include descendant groups. This value has no impact if the _ComputerTargetGroups_ parameter is not used.

```yaml
Type: SwitchParameter
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludedInstallationStates

Specifies the installation states to include. The acceptable values for this parameter are:

- All
- Downloaded
- Failed
- Installed
- InstalledPendingReboot
- NotApplicable
- NotInstalled
- Unknown

```yaml
Type: UpdateInstallationStates[]
Parameter Sets: Scoped
Aliases:
Accepted values: Unknown, NotApplicable, NotInstalled, Downloaded, Installed, Failed, InstalledPendingReboot, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NameIncludes

Specifies the partial name of the computer for which to search.

```yaml
Type: String
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestedTargetGroupNames

Specifies the list of requested target group names for which to search.

```yaml
Type: StringCollection
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToLastReportedStatusTime

Specifies the latest reported status time. This parameter can be used in combination with the _FromLastReportedStatusTime_ parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToLastSyncTime

Specifies the latest last synchronization time for which to search. This parameter can be used in combination with the _FromLastSynchTime_ parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: Scoped
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer

Specifies the object that contains the WSUS server. This value is obtained by calling the [Get-WsusServer](./Get-WsusServer.md) cmdlet and passing the resulting _IUpdateServer_ object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Administration.IUpdateServer

## OUTPUTS

### Microsoft.UpdateServices.Commands.WsusComputer

## NOTES

## RELATED LINKS

[Add-WsusComputer](./Add-WsusComputer.md)

[Get-WsusServer](./Get-WsusServer.md)
