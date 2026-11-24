---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdvirtualdesktopcollectionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDVirtualDesktopCollectionConfiguration
---

# Set-RDVirtualDesktopCollectionConfiguration

## SYNOPSIS
Changes configuration settings for a virtual desktop collection.

## SYNTAX

### General (Default)
```
Set-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-CollectionDescription <String>]
 [-ClientDeviceRedirectionOptions <RDClientDeviceRedirectionOptions>] [-RedirectAllMonitors <Boolean>]
 [-RedirectClientPrinter <Boolean>] [-SaveDelayMinutes <Int32>] [-UserGroups <String[]>]
 [-AutoAssignPersonalVirtualDesktopToUser <Boolean>] [-GrantAdministrativePrivilege <Boolean>]
 [-CustomRdpProperty <String>] [-ConnectionBroker <String>] [<CommonParameters>]
```

### DisableUserProfileDisks
```
Set-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-DisableUserProfileDisks]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### EnableUserProfileDisks
```
Set-RDVirtualDesktopCollectionConfiguration [-CollectionName] <String> [-EnableUserProfileDisks]
 [-IncludeFolderPath <String[]>] [-ExcludeFolderPath <String[]>] [-IncludeFilePath <String[]>]
 [-ExcludeFilePath <String[]>] -MaxUserProfileDiskSizeGB <Int32> -DiskPath <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDVirtualDesktopCollectionConfiguration** cmdlet changes configuration settings for a virtual desktop collection.

## EXAMPLES

### Example 1: Change the save delay setting for a virtual desktop collection
```
PS C:\> Set-RDVirtualDesktopCollectionConfiguration -ConnectionBroker "rdcb.contoso.com" -CollectionName "Virtual Desktop Pool" -SaveDelayMinutes 5
```

This command changes the save delay setting for the virtual desktop collection named Virtual Desktop Pool that is associated with the RD Connection Broker server named rdcb.contoso.com.
The command specifies a delay of 5 minutes before the server saves a virtual desktop in the virtual desktop collection that is not in use.

### Example 2: Change the user profile disk settings for a virtual desktop collection
```
PS C:\> Set-RDVirtualDesktopCollectionConfiguration -ConnectionBroker "rdcb.contoso.com" -CollectionName "Virtual Desktop Pool" -EnableUserProfileDisks -MaxUserProfileDiskSizeGB 10 -DiskPath "\\RDS-WKS-A27.contoso.com\uvhd"
```

This command enables a user profile disk for the virtual desktop collection named Virtual Desktop Pool.
The command specifies the maximum size of 10 gigabytes for the user profile disk and specifies the path of the user profile disk.

### Example 3: Change settings for a virtual desktop collection
```
PS C:\> Set-RDVirtualDesktopCollectionConfiguration -CollectionName "Virtual Desktop Pool" -CollectionDescription "Virtual Desktop Pool created using PowerShell" -RedirectAllMonitors $False -ConnectionBroker "rdcb.contoso.com" -ClientDeviceRedirectionOptions AudioVideoPlayBack,PlugAndPlayDevice
```

This command changes configuration settings for the virtual desktop collection named Virtual Desktop Pool.
The command adds a description to the virtual desktop collection, specifies that the server redirects a single monitor to the remote session, and specifies that Remote Desktop Services redirect AudioVideoPlayBack and PlugAndPlayDevice client devices to the server in this collection.

## PARAMETERS

### -AutoAssignPersonalVirtualDesktopToUser
Indicates that the server automatically associates virtual desktops with user accounts when you create a new personal virtual desktop collection.

```yaml
Type: Boolean
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientDeviceRedirectionOptions
Specifies a type of client device to be redirected to an RD Session Host server in this session collection.
The acceptable values for this parameter are:

- 0x0000.
None.
- 0x0001.
AudioVideoPlayBack.
- 0x0002.
AudioRecording.
- 0x0004.
COMPort.
- 0x0008.
PlugAndPlayDevice.
- 0x0010.
SmartCard.
- 0x0020.
Clipboard.
- 0x0040.
LPTPort.
- 0x0080.
Drive.
- 0x0100.
TimeZone.

You can use binary-or to combine two or more values of this enumeration to specify multiple client device types.

```yaml
Type: RDClientDeviceRedirectionOptions
Parameter Sets: General
Aliases:
Accepted values: None, AudioVideoPlayBack, AudioRecording, COMPort, PlugAndPlayDevice, SmartCard, Clipboard, LPTPort, Drive, TimeZone

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionDescription
Specifies a description for the collection.

```yaml
Type: String
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a personal virtual desktop collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomRdpProperty
Specifies Remote Desktop Protocol (RDP) settings to include in the .rdp files for all RemoteApp programs and remote desktops that you publish to this collection.

```yaml
Type: String
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableUserProfileDisks
Indicates that the server prevents you from using a user profile disk when you configure the collection.

```yaml
Type: SwitchParameter
Parameter Sets: DisableUserProfileDisks
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskPath
Specifies the path of the user profile disk.

```yaml
Type: String
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableUserProfileDisks
Indicates that the server enables a user profile disk when you configure the collection.
A user profile disk stores user profile information in a separate virtual hard disk and saves user profile settings across pooled virtual desktops.

```yaml
Type: SwitchParameter
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFilePath
Specifies an array of file paths that the server excludes when it creates the user profile disk.

By default, the server creates the standard file and folder paths, for example, Documents and Music.
Use this parameter with or without the **ExcludeFolderPath** parameter to prevent the server from creating file or folder paths.
This parameter overrides any identical values that you specify in the **IncludeFilePath** or **IncludeFolderPath** parameters.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExcludeFolderPath
Specifies an array of folder paths that the server excludes when it creates the user profile disk.

By default, the server creates the standard file and folder paths, for example, Documents and Music.
Use this parameter with or without the **ExcludeFilePath** parameter to prevent the server from creating file or folder paths.
This parameter overrides any identical values that you specify in the **IncludeFilePath** or **IncludeFolderPath** parameters.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GrantAdministrativePrivilege
Indicates whether the server grants administrative privileges to the user account that it assigns to a personal virtual desktop.
This parameter applies only to personal virtual desktop collections.

```yaml
Type: Boolean
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeFilePath
Specifies an array of file paths that the server includes when it creates the user profile disk.

By default, the server creates the standard file and folder paths, for example, Documents and Music.
Use this parameter with or without the **IncludeFolderPath** parameter to create file or folder paths.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeFolderPath
Specifies an array of folder paths that the server excludes when it creates the user profile disk.

By default, the server creates the standard file and folder paths, for example, Documents and Music.
Use this parameter with or without the **IncludeFilePath** parameter to create file or folder paths.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxUserProfileDiskSizeGB
Specifies the maximum size, in gigabytes, for the user profile disk.

```yaml
Type: Int32
Parameter Sets: EnableUserProfileDisks
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedirectAllMonitors
Indicates whether the server redirects all client monitors to the remote session.
Specify $False to redirect a single monitor to the remote session.

```yaml
Type: Boolean
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedirectClientPrinter
Indicates whether the server redirects the client printers to the server printer.

```yaml
Type: Boolean
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveDelayMinutes
Specifies the delay, in minutes, before the server saves a virtual desktop that is not in use.

```yaml
Type: Int32
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserGroups
Specifies an array of user groups that are authorized to connect to the collection.

```yaml
Type: String[]
Parameter Sets: General
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopCollectionConfiguration](./Get-RDVirtualDesktopCollectionConfiguration.md)

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

