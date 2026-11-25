---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/get-wmssystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsSystem
---

# Get-WmsSystem

## SYNOPSIS
Gets MultiPoint Server system information.

## SYNTAX

```
Get-WmsSystem [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WmsSystem** cmdlet gets Windows MultiPoint Server system information.

## EXAMPLES

### Example 1: Get system information
```
PS C:\> Get-WmsSystem
AttemptingToConnect        : False
RetryAttemptToConnect      : False
ProtocolVersion            : 1
WmsServerVersion           : 10.0.10586.0
WmsClientVersion           : 10.0.10586.0
NetJoinStatus              : NetSetupDomainName
DomainOrWorkgroupName      : TestDomain
SystemMode                 : Normal
DiskProtectionMode         : NotInstalled
ConnectionString           :
ConnectionCount            : 1
LicenseCount               : 0
State                      : Connected
ConnectionError            : 0
ConnectionErrorMessage     :
ComputerName               : Test1
WindowsEdition             : Windows Server 2016 Standard
IsVirtualMachine           : False
ManagedSystemsType         : MultiPointServers
MonitoringSystemType       : Include
IsSingleSessionPerUser     : True
MultiPointServers          : {}
PersonalComputers          : {}
CloudServers               : {}
ExcludedMultiPointServers  : {}
ExcludedPersonalComputers  : {}
ExcludedCloudServers       : {}
IPAddresses                :
ManagedServers             :
ExcludedManagedServers     : {}
IsSQMOn                    : True
IsWatsonOn                 : True
IsIPPerSessionEnabled      : False
IsChatEnabled              : True
HasNonLoopbackAdapter      : True
IsDesktopMonitoringAllowed : True
IsWmsSvcRunning            : True
IsScheduledUpdateEnabled      : False
ScheduleUpdateRunWU           : False
ScheduleUpdateCustomScript    :
MaxTimeAllowedForCustomScript : 0
ScheduledUpdatesReturnState   : __SUR_FIRST
TimeToScheduleUpdates         : 0
IsAllowRemoteManagementOn     : True
BootToConsoleMode             : False
SuppressPrivacyNotification   : False
SystemImage                   :
```

This command gets MultiPoint Server system information.

## PARAMETERS

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsSystem

## NOTES

## RELATED LINKS

[Add-WmsSystem](./Add-WmsSystem.md)

[Remove-WmsSystem](./Remove-WmsSystem.md)

[Restart-WmsSystem](./Restart-WmsSystem.md)

[Search-WmsSystem](./Search-WmsSystem.md)

[Set-WmsSystem](./Set-WmsSystem.md)

[Stop-WmsSystem](./Stop-WmsSystem.md)

