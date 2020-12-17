---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: E938807F-DD38-4CE8-A446-97A272E71A92
manager: dansimp
---

# Set-WssMediaLibraryInclusion

## SYNOPSIS
Includes or excludes a shared folder from the Media Library.

## SYNTAX

```
Set-WssMediaLibraryInclusion [-Share] <MediaStreamingSharedFolder> [-Enable] <Boolean>
```

## DESCRIPTION
The **Set-WssMediaLibraryInclusion** cmdlet includes a shared folder in, or excludes a shared folder from, the Media Library for the current server.

## EXAMPLES

### Example 1: Exclude a shared folder from the Media Library
```
PS C:\> $MediaFolders = Get-WssMediaSharedFolder PS C:\>Set-WssMediaLibraryInclusion -Share $MediaFolders[0] -Enable $False
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
Position: 2
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaSharedFolder](./Get-WssMediaSharedFolder.md)

[Get-WssMediaServerEnabled](./Get-WssMediaServerEnabled.md)

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)

