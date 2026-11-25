---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdfiletypeassociation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDFileTypeAssociation
---

# Get-RDFileTypeAssociation

## SYNOPSIS
Displays the file extensions associated with a RemoteApp program.

## SYNTAX

```
Get-RDFileTypeAssociation [[-CollectionName] <String>] [-AppAlias <String>] [-AppDisplayName <String[]>]
 [-FileExtension <String>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDFileTypeAssociation** cmdlet displays the file extensions that are associated with a firstref_server_7 RemoteApp program in the Remote Desktop deployment.

## EXAMPLES

### Example 1: Get a file type association by using an alias and a file name extension
```
PS C:\> Get-RDFileTypeAssociation -AppAlias "iexplore" -FileExtension ".html"
```

This command gets a file type association by using the file name extension .html and the RemoteApp program whose alias is iexplore.

### Example 2: Get a file type association by using a collection name and an application display name
```
PS C:\> Get-RDFileTypeAssociation -CollectionName "Session Collection" -AppDisplayName "Note*"
```

This command gets the file type association by using the collection named Session Collection and the names of all RemoteApp programs whose names begin with the word Note.

## PARAMETERS

### -AppAlias
Specifies the alias for the RemoteApp program.
The default alias is the program's filename without the extension.

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

### -AppDisplayName
Specifies the name that users see for the RemoteApp program.

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

### -CollectionName
Specifies the name of the collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD  Connection Broker) server for this Remote Desktop deployment.
Remote users connect to this server to obtain views of available RemoteApp programs, session-based desktops, and virtual desktops.
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
Specifies the file name extension whose associated RemoteApp program appears.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RemoteDesktopServices.Management.FileTypeAssociation

## NOTES

## RELATED LINKS

[Set-RDFileTypeAssociation](./Set-RDFileTypeAssociation.md)

