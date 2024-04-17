---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdsessioncollectionconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDSessionCollectionConfiguration
---

# Set-RDSessionCollectionConfiguration

## SYNOPSIS
Modifies configuration options for an existing session collection.

## SYNTAX

### Default (Default)
```
Set-RDSessionCollectionConfiguration [-CollectionName] <String> [-CollectionDescription <String>]
 [-UserGroup <String[]>] [-ClientDeviceRedirectionOptions <RDClientDeviceRedirectionOptions>]
 [-MaxRedirectedMonitors <Int32>] [-ClientPrinterRedirected <Boolean>] [-RDEasyPrintDriverEnabled <Boolean>]
 [-ClientPrinterAsDefault <Boolean>] [-TemporaryFoldersPerSession <Boolean>]
 [-BrokenConnectionAction <RDBrokenConnectionAction>] [-TemporaryFoldersDeletedOnExit <Boolean>]
 [-AutomaticReconnectionEnabled <Boolean>] [-ActiveSessionLimitMin <Int32>]
 [-DisconnectedSessionLimitMin <Int32>] [-IdleSessionLimitMin <Int32>] [-AuthenticateUsingNLA <Boolean>]
 [-EncryptionLevel <RDEncryptionLevel>] [-SecurityLayer <RDSecurityLayer>]
 [-LoadBalancing <RDSessionHostCollectionLoadBalancingInstance[]>] [-CustomRdpProperty <String>]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### DisableUserProfileDisk
```
Set-RDSessionCollectionConfiguration [-CollectionName] <String> [-DisableUserProfileDisk]
 [-ConnectionBroker <String>] [<CommonParameters>]
```

### EnableUserProfileDisk
```
Set-RDSessionCollectionConfiguration [-CollectionName] <String> [-EnableUserProfileDisk]
 [-IncludeFolderPath <String[]>] [-ExcludeFolderPath <String[]>] [-IncludeFilePath <String[]>]
 [-ExcludeFilePath <String[]>] -MaxUserProfileDiskSizeGB <Int32> -DiskPath <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDSessionCollectionConfiguration** cmdlet modifies configuration options for an existing session collection.
A session collection consists of one or more Remote Desktop Session Host (RD Session Host) servers.
Users can connect to RD Session Host servers in a session collection to run programs, save files, and use resources on those servers.

You can use the New-RDSessionCollection cmdlet to create a session collection.

## EXAMPLES

### Example 1: Disable user profile disk
```
PS C:\> Set-RDSessionCollectionConfiguration -CollectionName "Session Collection 02" -DisableUserProfileDisk -ConnectionBroker "RDCB.Contoso.com"
```

This command configures a session collection to not use a user profile disk for a session collection named Session Collection 02 that has an RD Connection Broker named RDCB.Contoso.com.

### Example 2: Specify a user profile disk with included file and folder
```
PS C:\> Set-RDSessionCollectionConfiguration -CollectionName "Session Collection 09" -EnableUserProfileDisk -MaxUserProfileDiskSizeGB 40 -DiskPath "C:\UserVHDs" -IncludeFolderPath "C:\Resources Folder" -IncludeFileFolderPath "C:\Required Text File.txt" -ConnectionBroker "RDCB.Contoso.com"
```

This command configures a session collection to use a user profile disk for a session collection named Session Collection 09 that has an RD Connection Broker named RDCB.Contoso.com.
The command specifies the maximum size of the user profile disk and its disk path.
The command specifies a path and file to include in the user profile.

### Example 3: Specify a user profile disk with excluded file and folder
```
PS C:\> Set-RDSessionCollectionConfiguration -CollectionName "Session Collection 19" -EnableUserProfileDisk -MaxUserProfileDiskSizeGB 40 -DiskPath "C:\UserVHDs" -ExcludeFolderPath "C:\Local Resources Folder" -ExcludeFilePath "C:\Local Text File.txt" -ConnectionBroker "RDCD.Contoso.com"
```

This command configures a session collection to use a user profile disk for a session collection named Session Collection 19 that has an RD Connection Broker named RDCB.Contoso.com.
The command specifies the maximum size of the user profile disk and its disk path.
The command specifies a path and file to exclude from the user profile.

### Example 4: Configure load balancing
```
PS C:\> $LoadBalanceObjectsArray = New-Object System.Collections.Generic.List[Microsoft.RemoteDesktopServices.Management.RDSessionHostCollectionLoadBalancingInstance]
PS C:\>$LoadBalanceSessionHost1 = New-Object Microsoft.RemoteDesktopServices.Management.RDSessionHostCollectionLoadBalancingInstance( "SessionHostCollection", 50, 200, "RDSH-1.Contoso.com" )
PS C:\> $LoadBalanceObjectsArray.Add($LoadBalanceSessionHost1)
PS C:\> $LoadBalanceSessionHost2 = New-Object Microsoft.RemoteDesktopServices.Management.RDSessionHostCollectionLoadBalancingInstance( "SessionHostCollection", 50, 300, "RDSH-2Contoso.com" )
PS C:\> $LoadBalanceObjectsArray.Add($LoadBalanceSessionHost2)
PS C:\> Set-RDSessionCollectionConfiguration -CollectionName "Session Collection 07" -LoadBalancing $LoadBalanceObjectsArray -ConnectionBroker "RDCB.Contoso.com"
```

This example configures load balancing for a session collection named Session Collection 07 that has an RD Connection Broker server named RDCB.Contoso.com.

The first five commands use standard Windows PowerShell® syntax to create an array of objects to define load balancing guidelines, and store those guidelines in the **$LoadBalanceObjectsArray** variable.
This example configuration uses two RD Session Host servers named RDSH-1.Contoso.com and RDSH-2.Contoso.com

The final command specifies load balancing settings for the session collection that has the name Session Collection 07 and the RD Connection Broker server named RDCB.Contoso.com.
The command uses the array stored in the **$LoadBalanceObjectsArray** variable to specify load balancing behavior.

## PARAMETERS

### -ActiveSessionLimitMin
Specifies the maximum time, in minutes, an active session runs.
After this period, the RD Session Host server ends the session.

```yaml
Type: Int32
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticateUsingNLA
Indicates whether to use Network Level Authentication (NLA).
If this value is $True, Remote Desktop uses NLA to authenticate a user before the user sees a logon screen.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutomaticReconnectionEnabled
Indicates whether the Remote Desktop client attempts to reconnect after a connection interruption.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BrokenConnectionAction
Specifies an action for an RD Session Host server to take after a connection interruption.
The acceptable values for this parameter are:

- None
- Disconnect
- LogOff

```yaml
Type: RDBrokenConnectionAction
Parameter Sets: Default
Aliases:
Accepted values: None, Disconnect, LogOff

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

You can use binary-or to combine two or more values of this enum to specify multiple client device types.

```yaml
Type: RDClientDeviceRedirectionOptions
Parameter Sets: Default
Aliases:
Accepted values: None, AudioVideoPlayBack, AudioRecording, COMPort, PlugAndPlayDevice, SmartCard, Clipboard, LPTPort, Drive, TimeZone

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientPrinterAsDefault
Indicates whether to use the client printer or server printer as the default printer.
If this value is $True, use the client printer as default.
If this value is $False, use the server as default.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientPrinterRedirected
Indicates whether to use client printer redirection, which routes print jobs from the Remote Desktop session to a printer attached to the client computer.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionDescription
Specifies a description of the session collection.

```yaml
Type: String
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a session collection.

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
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
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
Specifies Remote Desktop Protocol (RDP) settings to include in the .rdp files for all Windows Server 2012 RemoteApp programs and remote desktops published in this collection.

```yaml
Type: String
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableUserProfileDisk
Indicates that Remote Desktop does not use a user profile to configure the session collection.

```yaml
Type: SwitchParameter
Parameter Sets: DisableUserProfileDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisconnectedSessionLimitMin
Specifies a length of time, in minutes.
After client disconnection from a session for this period, the RD Session Host ends the session.

```yaml
Type: Int32
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskPath
Specifies a path for the user profile disk.

```yaml
Type: String
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableUserProfileDisk
Indicates that Remote Desktop uses a user profile disk to configure the session collection.
A user profile disk stores user profile information as a separate virtual hard disk in order to persist user profile settings across a pool of virtual desktops.

```yaml
Type: SwitchParameter
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionLevel
Specifies the level of data encryption used for a Remote Desktop session.
The acceptable values for this parameter are:

- 0 - Low.
- 1 - ClientCompatible.
- 2 - High.
- 3 - FipsCompliant.

The default value is ClientCompatible.

```yaml
Type: RDEncryptionLevel
Parameter Sets: Default
Aliases:
Accepted values: None, Low, ClientCompatible, High, FipsCompliant

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExcludeFilePath
Specifies an array of file paths to exclude from a user profile disk.
By default, Remote Desktop creates standard file and folder paths, such as Documents and Music.
Use this parameter to prevent creation of specified file paths.
This parameter overrides any identical values specified in the **IncludeFilePath** or **IncludeFolderPath** parameters.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExcludeFolderPath
Specifies an array of folder paths to exclude from a user profile disk.
By default, Remote Desktop creates standard file and folder paths, such as Documents and Music.
Use this parameter to prevent creation of specified folder paths.
This parameter overrides any identical values specified in the **IncludeFilePath** or **IncludeFolderPath** parameters.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdleSessionLimitMin
Specifies the length of time, in minutes, to wait before an RD Session Host logs off or disconnects an idle session.
The **BrokenConnectionAction** parameter determines whether to log off or disconnect.

```yaml
Type: Int32
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeFilePath
Specifies an array of file paths to include in a user profile disk.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeFolderPath
Specifies an array of folder paths to include in a user profile disk.

```yaml
Type: String[]
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancing
Specifies an array of objects that defines load balancing guidelines for the remote session collection.
Each object specifies the collection name, RD Session Host server name, relative weight to use for that server, and a maximum number of sessions to allow.

```yaml
Type: RDSessionHostCollectionLoadBalancingInstance[]
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRedirectedMonitors
Specifies the maximum number of client monitors that an RD Session Host server can redirect to a remote session.
The highest value for this parameter is 16.

```yaml
Type: Int32
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxUserProfileDiskSizeGB
Specifies the maximum size, in gigabytes, for a user profile disk.

```yaml
Type: Int32
Parameter Sets: EnableUserProfileDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RDEasyPrintDriverEnabled
Specifies whether to enable the Remote Desktop Easy Print driver.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityLayer
Specifies which security protocol to use.
The acceptable values for this parameter are:

- 0 - RDP.
- 1 - Negotiate.
- 2 - SSL.

The default value is Negotiate.

```yaml
Type: RDSecurityLayer
Parameter Sets: Default
Aliases:
Accepted values: RDP, Negotiate, SSL

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemporaryFoldersDeletedOnExit
Specifies whether to delete temporary folders from the RD Session Host server for a disconnected session.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemporaryFoldersPerSession
Specifies whether to use a single folder for temporary files.
If this value is $True, a single folder contains temporary files.
If this value is $False, individual users have separate folders to store temporary files.

```yaml
Type: Boolean
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserGroup
Specifies an array of domain groups and users authorized to connect to the RD Session Host servers in a session collection.

```yaml
Type: String[]
Parameter Sets: Default
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
* The **IncludeFolderPath** and **IncludeFilePath** parameters are mutually exclusive with the **ExcludeFolderPath** and **ExcludeFilePath** parameters.

## RELATED LINKS

[Get-RDSessionCollectionConfiguration](./Get-RDSessionCollectionConfiguration.md)

[Get-RDSessionCollection](./Get-RDSessionCollection.md)

[New-RDSessionCollection](./New-RDSessionCollection.md)

[Remove-RDSessionCollection](./Remove-RDSessionCollection.md)

