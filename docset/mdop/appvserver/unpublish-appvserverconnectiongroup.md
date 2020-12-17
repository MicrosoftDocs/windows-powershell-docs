---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 4B04724A-F91A-45A4-9B32-FF8EB8042F26
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Unpublish-AppvServerConnectionGroup
---

# Unpublish-AppvServerConnectionGroup

## SYNOPSIS
Unpublishes connection groups.

## SYNTAX

### ByObject
```
Unpublish-AppvServerConnectionGroup [-AppvServerConnectionGroup] <SerializableConnectionGroup> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByName
```
Unpublish-AppvServerConnectionGroup [-Name] <String> [[-Version] <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByGUID
```
Unpublish-AppvServerConnectionGroup [-GroupID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Unpublish-AppvServerConnectionGroup** cmdlet unpublishes the specified connection groups.

## EXAMPLES

### Example 1: Unpublish one version of a group
```
PS C:\> Unpublish-AppvServerConnectionGroup -Name "OfficePlugIns" -Version 2
```

This command unpublishes version 2 of the single group named OfficePlugIns.

## PARAMETERS

### -AppvServerConnectionGroup
Specifies the connection group object.

```yaml
Type: SerializableConnectionGroup
Parameter Sets: ByObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GroupID
Specifies the GUID of specific package group.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the package group.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Version
The version of the specified package group.

```yaml
Type: Int32
Parameter Sets: ByName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionID
Specifies the version GUID of the package group.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### AppvServer.AppvServerConnectionGroup

## OUTPUTS

## NOTES
* If the cmdlet cannot find the connection groups, the cmdlet returns the following error: The following connection group(s) could not be found on the system. The cmdlet lists the packages. The cmdlet fails the operation.
* If you do not specify version information, the cmdlet unpublishes all existing versions of the package group.
* If you do not specify any parameters, the cmdlet unpublishes all the package groups and subsequent versions on the system.

## RELATED LINKS

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


