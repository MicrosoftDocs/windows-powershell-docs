---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/set-rdfiletypeassociation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RDFileTypeAssociation
---

# Set-RDFileTypeAssociation

## SYNOPSIS
Changes the file type association of a RemoteApp program in a Remote Desktop deployment.

## SYNTAX

### Session (Default)
```
Set-RDFileTypeAssociation [-CollectionName] <String> -AppAlias <String> -FileExtension <String>
 -IsPublished <Boolean> [-IconPath <String>] [-IconIndex <String>] [-ConnectionBroker <String>]
 [<CommonParameters>]
```

### VirtualDesktop
```
Set-RDFileTypeAssociation [-CollectionName] <String> -AppAlias <String> -FileExtension <String>
 -IsPublished <Boolean> [-IconPath <String>] [-IconIndex <String>] -VirtualDesktopName <String>
 [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDFileTypeAssociation** cmdlet modifies the file type association of a firstref_server_7 RemoteApp program in a Remote Desktop deployment.

## EXAMPLES

### Example 1: Set a file type association for a virtual desktop collection
```
PS C:\> Set-RDFileTypeAssociation -CollectionName "Virtual Desktop Collection" -AppAlias "iexplore" -FileExtension ".html" -IsPublished $True -VirtualDesktopName "RDS-WKS-A27"
```

This command sets the following options for file type association:

- Collection named Virtual Desktop Collection.
- Remote Desktop application alias of iexplore.
- File name extension of .html to associate with the application.
- Virtual desktop named RDS-WKS-A27.

- Users can see the file name extension.

### Example 2: Set a file type association for a session collection
```
PS C:\> Set-RDFileTypeAssociation -CollectionName "Session Collection" -AppAlias "Notepad" -FileExtension ".txt" -IsPublished $True -IconPath "%windir%\System32\Notepad.exe" -IconIndex 0
```

This command sets these options for file type association:

- Collection named Session Collection.
- Remote Desktop application alias of Notepad.
- File name extension of .txt to associate with the application.

- The icon for the Remote Desktop program Notepad.exe appears in the \System32 subfolder of the Windows folder.
The icon that appears for Notepad is at the first position of the icon file.

## PARAMETERS

### -AppAlias
Specifies the alias for the RemoteApp program.
The default alias is the program's file name without the extension.

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

### -CollectionName
Specifies the name of the session or virtual desktop collection.

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
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
Remote users connect to this server to obtain views of available nextref_server_7 RemoteApp programs, session-based desktops, and virtual desktops.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

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

### -FileExtension
Specifies the file name extension of the file type whose association you change.

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

### -IconIndex
Specifies the index in the icon file for the RemoteApp program icon.
The **IconPath** parameter specifies the icon file.

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

### -IsPublished
Indicates whether users can see the file type association.

Set this parameter to $True if users need to open the RemoteApp that corresponds to a file type by double-clicking a file of that type.

Set this parameter to $False if you do not want to associate files of a particular type with a RemoteApp program on end users' machines.
For example, if you have published Microsoft Word as a RemoteApp, but you want end users to open .docx files in local copies of Wordpad rather than in the RemoteApp Word, set **IsPublished** to $False in the file type association for .docx files.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of the virtual desktop where the icon file whose name is in the **IconPath** parameter appears.
This virtual desktop must belong to the collection whose value is in the **CollectionName** parameter.

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

### Null

## NOTES

## RELATED LINKS

[Get-RDFileTypeAssociation](./Get-RDFileTypeAssociation.md)

