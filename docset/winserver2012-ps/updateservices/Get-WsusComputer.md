---
author: Kateyanne
external help file: WSUS_Cmdlets.xml
manager: dansimp
Module Name: UpdateServices
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/updateservices/get-wsuscomputer?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WsusComputer

## SYNOPSIS
Gets the Windows Server Update Services (WSUS) computer object that represents the client computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WsusComputer [-All] [-UpdateServer <IUpdateServer>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WsusComputer [-ComputerTargetGroups <StringCollection>]
 [-ComputerUpdateStatus <WsusUpdateInstallationState>]
 [-ExcludedInstallationStates <UpdateInstallationStates[]>] [-FromLastReportedStatusTime <DateTime>]
 [-FromLastSyncTime <DateTime>] [-IncludedInstallationStates <UpdateInstallationStates[]>]
 [-IncludeDownstreamComputerTargets] [-IncludeSubgroups] [-NameIncludes <String>]
 [-RequestedTargetGroupNames <StringCollection>] [-ToLastReportedStatusTime <DateTime>]
 [-ToLastSyncTime <DateTime>] [-UpdateServer <IUpdateServer>]
```

## DESCRIPTION
The **Get-WsusComputer** cmdlet retrieves one or more computers based on the specified filtering criteria such as operating system, computer name, update installation status, last reported status time, and etcetera.

If the Get-WsusServer cmdlet is run and the resulting IUpdateServer object is piped into this cmdlet, then the specified server will be used rather than the local server.

This cmdlet can be piped into the Add-WsusComputer cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusComputer -All
Computer                      IP Address                    Operating System              Last Status Report 
--------                      ----------                    ----------------              ------------------ 
contoso                       XXXX:XXXX:XX:X:XXXX:XXX:XXXX:  Windows Server 2008           6/2/2010 12:00:00 AM 
                              XXXX                          Enterprise Edition (full 
                                                            installation)
```

This example gets all client computers.

### EXAMPLE 2
```
PS C:\> Get-WsusComputer -NameIncludes contoso
Computer                      IP Address                    Operating System              Last Status Report 
--------                      ----------                    ----------------              ------------------ 
contoso                       XXXX:XXXX:XX:X:XXXX:XXX:XXXX:  Windows Server 2008           6/2/2010 12:00:00 AM 
                              XXXX                          Enterprise Edition (full 
                                                            installation)
```

This example gets the client computer whose name includes contoso.

### EXAMPLE 3
```
PS C:\> Get-WsusComputer -FromLastReportedStatusTime 6/1/10 -ToLastReportedStatusTime 6/30/10
Computer                      IP Address                    Operating System              Last Status Report 
--------                      ----------                    ----------------              ------------------ 
contoso                       XXXX:XXXX:XX:X:XXXX:XXX:XXXX:  Windows Server 2008           6/2/2010 12:00:00 AM 
                              XXXX                          Enterprise Edition (full 
                                                            installation)
```

This example gets all client computers with a last reported status date and time between June 1, 2010 and June 30, 2010.

## PARAMETERS

### -All
Specifies that all computers are to be returned.
The information displayed includes the computer name, IP address, operating system, and last status report time.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerUpdateStatus
Specifies the computer update state as represented in the WSUS Console user interface.
The acceptable values for this parameter are:

 -- FailedOrNeeded 

 -- InstalledNotApplicableOrNoStatus 

 -- Failed 

 -- InstalledNotApplicable 

 -- NoStatus 

 -- Any

```yaml
Type: WsusUpdateInstallationState
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludedInstallationStates
Specifies the installation states to exclude.
The acceptable values for this parameter are:

 -- All 

 -- Downloaded 

 -- Failed 

 -- Installed 

 -- InstalledPendingReboot 

 -- NotApplicable 

 -- NotInstalled 

 -- Unknown

```yaml
Type: UpdateInstallationStates[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromLastReportedStatusTime
Specifies the earliest reported status time.
This parameter can be used in combination with the **ToLastReportedStatusTime** parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromLastSyncTime
Specifies the earliest last synchronization time for which to search.
This parameter can be used in combination with the **ToLastSynchTime** parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeSubgroups
Specifies that the **ComputerTargetGroups** parameter should include descendant groups.
This value has no impact if the **ComputerTargetGroups** parameter is not used.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludedInstallationStates
Specifies the installation states to include.
The acceptable values for this parameter are:

 -- All 

 -- Downloaded 

 -- Failed 

 -- Installed 

 -- InstalledPendingReboot 

 -- NotApplicable 

 -- NotInstalled 

 -- Unknown

```yaml
Type: UpdateInstallationStates[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToLastReportedStatusTime
Specifies the latest reported status time.
This parameter can be used in combination with the **FromLastReportedStatusTime** parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToLastSyncTime
Specifies the latest last synchronization time for which to search.
This parameter can be used in combination with the **FromLastSynchTime** parameter in order to create a date range to use in the search.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer
Specifies the object that contains the WSUS server.
This value is obtained by calling the Get-WsusServer cmdlet and piping the resulting IUpdateServer object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases: Server

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.UpdateServices.Commands.IUpdateServer
IUpdateServer

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-WsusComputer](./Add-WsusComputer.md)

[Get-WsusServer](./Get-WsusServer.md)

