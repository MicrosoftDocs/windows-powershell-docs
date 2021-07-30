---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssmedialibraryinclusion?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssMediaLibraryInclusion
---

# Set-WssMediaLibraryInclusion

## SYNOPSIS
Includes or excludes a shared folder from the Media Library.

## SYNTAX

```
Set-WssMediaLibraryInclusion [-Share] <MediaStreamingSharedFolder> [-Enable] <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMediaLibraryInclusion** cmdlet includes a shared folder in, or excludes a shared folder from, the Media Library for the current server.

## EXAMPLES

### Example 1: Exclude a shared folder from the Media Library
```
PS C:\> $MediaFolders = Get-WssMediaSharedFolder
PS C:\> Set-WssMediaLibraryInclusion -Share $MediaFolders[0] -Enable $False
```

This example excludes a shared folder from the Media Library.
The first command uses the Get-WssMediaSharedFolder cmdlet to get the shared folders for the current server, and then stores them in the **$MediaFolders** variable.
In this example, the server has more than one folder in the Media Library, so **$MediaFolders** contains an array.

The second command excludes a folder from the Media Library.
The command specifies a value of $False for the **Enable** parameter.
The command uses standard array syntax to specify the first member of the array stored in the **$MediaFolders** variable.

## PARAMETERS

### -Enable
Indicates whether the cmdlet includes or excludes the specified folder from the Media Library.
Specify a value of $True to include the folder in the Media Library.
Specify a value of $False to exclude the folder.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Share
Specifies a shared folder on the server.

```yaml
Type: MediaStreamingSharedFolder
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaSharedFolder](./Get-WssMediaSharedFolder.md)

[Get-WssMediaServerEnabled](./Get-WssMediaServerEnabled.md)

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)

