---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 93E2E92B-F9CB-4FFF-AAD3-62773A2F193B
manager: dansimp
---

# Get-WssFolder

## SYNOPSIS
Gets an object that represents a folder.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WssFolder [-ID] <Guid>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WssFolder [-Name] <String>
```

## DESCRIPTION
The **Get-WssFolder** cmdlet gets an object that represents a folder.
Specify a GUID for a specific folder.
If you do not specify a GUID, the cmdlet gets **Folder** objects for all the folders on current server.

## EXAMPLES

### Example 1: Get a folder by using a name
```
PS C:\> Get-WssFolder -Name "ProjectsWest"
```

This command gets the folder named ProjectsWest.

## PARAMETERS

### -ID
Specifies the GUID for a folder.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a folder.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Folder

## NOTES

## RELATED LINKS

[Get-WssFolder](./Get-WssFolder.md)

[Set-WssFolder](./Set-WssFolder.md)

[Add-WssFolder](./Add-WssFolder.md)

[Move-WssFolder](./Move-WssFolder.md)

[Remove-WssFolder](./Remove-WssFolder.md)

[Measure-WssFolder](./Measure-WssFolder.md)

