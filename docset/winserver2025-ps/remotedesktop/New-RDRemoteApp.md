---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/new-rdremoteapp?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-RDRemoteApp
---

# New-RDRemoteApp

## SYNOPSIS
Publishes a RemoteApp program to a Remote Desktop deployment.

## SYNTAX

### Session (Default)
```
New-RDRemoteApp [-CollectionName] <String> [-Alias <String>] -DisplayName <String> -FilePath <String>
 [-FileVirtualPath <String>] [-ShowInWebAccess <Boolean>] [-FolderName <String>]
 [-CommandLineSetting <CommandLineSettingValue>] [-RequiredCommandLine <String>] [-UserGroups <String[]>]
 [-IconPath <String>] [-IconIndex <String>] [-ConnectionBroker <String>] [<CommonParameters>]
```

### VirtualDesktop
```
New-RDRemoteApp [-CollectionName] <String> [-Alias <String>] -DisplayName <String> -FilePath <String>
 [-FileVirtualPath <String>] [-ShowInWebAccess <Boolean>] [-FolderName <String>]
 [-CommandLineSetting <CommandLineSettingValue>] [-RequiredCommandLine <String>] [-UserGroups <String[]>]
 [-IconPath <String>] [-IconIndex <String>] -VirtualDesktopName <String> [-ConnectionBroker <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-RDRemoteApp** cmdlet publishes a Windows Server 2012 RemoteApp program to a Remote Desktop deployment, making it available to users.

RemoteApp allows Remote Desktop Services (RDS) to run a program remotely that appears as if it runs locally on a client computer.
A RemoteApp program runs in its own resizable window and has its own entry on the taskbar.

## EXAMPLES

### Example 1: Publish a RemoteApp program
```
PS C:\> New-RDRemoteApp -CollectionName "Session Collection" -DisplayName "Notepad" -FilePath "C:\Windows\System32\Notepad.exe"
```

This command creates a new RemoteApp program in the collection named Session Collection.
The command specifies the display name Notepad and uses the .exe file at the specified file path.

### Example 2: Publish a RemoteApp program with a required argument
```
PS C:\> New-RDRemoteApp -CollectionName "Virtual Desktop Collection" -DisplayName "Bing" -FilePath "C:\Program Files\Internet Explorer\iexplore.exe" -VirtualDesktopName "RDS-WKS-A27" -CommandLineSetting Require -RequiredCommandLine "https://www.bing.com"
```

This command publishes a RemoteApp to the collection named Virtual Desktop Collection.
The command specifies the display name Bing and uses the .exe file at the specified file path.
The command specifies the virtual desktop name RDS-WKS-A27.
This command uses a required command line argument.
This RemoteApp opens the specified browser to go to the specified URL.

## PARAMETERS

### -Alias
Specifies an alias for the RemoteApp program.
If you do not specify an alias, the cmdlet generates one based on the **FilePath** parameter.
This alias must be unique within the collection specified by the **CollectionName** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of the personal virtual desktop collection or session collection.
The cmdlet publishes the RemoteApp program to this collection.

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

### -CommandLineSetting
Specifies whether the RemoteApp program accepts command-line arguments from the client at connection time.
The acceptable values for this parameter are:

- Allow.
Accepts command-line arguments.
- DoNotAllow.
Does not accept command-line arguments.
- Require.
Allows only command-line arguments specified in the **RequiredCommandLine** parameter.

```yaml
Type: CommandLineSettingValue
Parameter Sets: (All)
Aliases:
Accepted values: DoNotAllow, Allow, Require

Required: False
Position: Named
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

### -DisplayName
Specifies a name to display to users for the RemoteApp program.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath
Specifies a path for the executable file for the application.
Do not include any environment variables.
For session collections, this path must be a valid local path on all Remote Desktop Session Host (RD Session Host) servers in the collection.
For virtual desktop collections, this path must be a valid local path on all virtual desktops in the collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileVirtualPath
Specifies a path for the application executable file.
This path resolves to the same location as the value of the **FilePath** parameter, but it can include environment variables.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FolderName
Specifies the name of the folder that the RemoteApp program appears in on the Remote Desktop Web Access (RD Web Access) webpage and in the Start menu for subscribed RemoteApp and Desktop Connections.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IconIndex
Specifies the index within the icon file (specified by the **IconPath** parameter) where the RemoteApp program's icon can be found.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IconPath
Specifies the path to a file containing the icon to display for the RemoteApp program identified by the **Alias** parameter.
This path must not contain any environment variables.
For session collections, the path must be a valid local path on all RD Session Host servers in the collection.
For virtual desktop collections, the path must be a valid local path on all virtual desktops in the collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredCommandLine
Specifies a string that contains command-line arguments that the client can use at connection time with the RemoteApp program.
If you specify this parameter, the **CommandLineSetting** parameter must have a value of Require.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShowInWebAccess
Specifies whether to show the RemoteApp program in the RD Web Access server, and in RemoteApp and Desktop Connections that the user subscribes to.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserGroups
Specifies an array of domain groups and users that can view the RemoteApp in RD Web Access, and in RemoteApp and Desktop Connections.
To allow all users to see a RemoteApp program, provide a value of $Null.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of a virtual desktop.
The icon file specified in the **IconPath** parameter resides in this virtual desktop.
The virtual desktop must be a member of the collection specified by the **CollectionName** parameter.

```yaml
Type: String
Parameter Sets: VirtualDesktop
Aliases: VMName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.RemoteApp

## NOTES

## RELATED LINKS

[Get-RDRemoteApp](./Get-RDRemoteApp.md)

[Remove-RDRemoteApp](./Remove-RDRemoteApp.md)

[Set-RDRemoteApp](./Set-RDRemoteApp.md)

