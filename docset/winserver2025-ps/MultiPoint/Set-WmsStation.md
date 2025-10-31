---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/set-wmsstation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmsStation
---

# Set-WmsStation

## SYNOPSIS
Modifies station information.

## SYNTAX

### FriendlyName
```
Set-WmsStation [-StationId] <UInt32[]> -FriendlyName <String> [-Server <String>] [<CommonParameters>]
```

### AutoLogonEnable
```
Set-WmsStation [-StationId] <UInt32[]> -AutoLogonCredential <PSCredential> [-OverrideAdminWarning]
 [-Server <String>] [<CommonParameters>]
```

### DisableAutoLogon
```
Set-WmsStation [-StationId] <UInt32[]> [-DisableAutoLogon] [-Server <String>] [<CommonParameters>]
```

### RemoteConnection
```
Set-WmsStation [-StationId] <UInt32[]> -SessionHost <String> [-Server <String>] [<CommonParameters>]
```

### RemoteConnectionVM
```
Set-WmsStation [-StationId] <UInt32[]> -VmName <String> [-Server <String>] [<CommonParameters>]
```

### DisableRemoteConnection
```
Set-WmsStation [-StationId] <UInt32[]> [-LocalSessionHost] [-Server <String>] [<CommonParameters>]
```

### DisplayOrientation
```
Set-WmsStation [-StationId] <UInt32[]> -DisplayOrientation <EDisplayOrientationPS> [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-WmsStation** cmdlet modifies station information.
You can use this cmdlet to set the automatic logon and the friendly name for the station.
If you want to enable a user in the Administrator group to auto-logon, specify the *OverrideAdminWarning* parameter.

## EXAMPLES

### Example 1: Set a station
```
PS C:\> $Creds = Get-Credential -UserName "Student01" -Message "Enter desired password"
PS C:\> Set-WmsStation -StationId 1 -FriendlyName -"Patti's Station" -AutoLogonCredential $Creds
```

The first command gets the credentials for Student01, and then stores them in the $Creds variable.

The second command sets the friendly name of station 1 to Patti's Station.
Station 1 is now configured to auto-logon as Student01.

## PARAMETERS

### -AutoLogonCredential
Specifies the automatic logon credentials.
Use Get-Credential cmdlet to get a **PSCredential** object.

```yaml
Type: PSCredential
Parameter Sets: AutoLogonEnable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutoLogon
Disables automatic logon for the station.

```yaml
Type: SwitchParameter
Parameter Sets: DisableAutoLogon
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayOrientation
Specifies the Display Orientation for the station.

```yaml
Type: EDisplayOrientationPS
Parameter Sets: DisplayOrientation
Aliases:
Accepted values: Portrait, Landscape, PortraitFlipped, LandscapeFlipped

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for the station.

```yaml
Type: String
Parameter Sets: FriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalSessionHost
Specifies the local session host.

```yaml
Type: SwitchParameter
Parameter Sets: DisableRemoteConnection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverrideAdminWarning
Indicates that this operation overrides the Administrator warning.
Specify this parameter to enable an Administrator to automatically log on.

```yaml
Type: SwitchParameter
Parameter Sets: AutoLogonEnable
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -SessionHost
Specifies the session host.

```yaml
Type: String
Parameter Sets: RemoteConnection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StationId
Specifies an array of station IDs.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmName
Specifies the virtual machine guest host name for Virtual Desktop Infrastructure (VDI) stations.

```yaml
Type: String
Parameter Sets: RemoteConnectionVM
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32[]

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Clear-WmsStation](./Clear-WmsStation.md)

[Get-WmsStation](./Get-WmsStation.md)

[Join-WmsStation](./Join-WmsStation.md)

[Split-WmsStation](./Split-WmsStation.md)

[Update-WmsStation](./Update-WmsStation.md)

