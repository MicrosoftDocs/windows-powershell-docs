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
ms.assetid: DEDFCD81-E855-4EE9-87E9-162287D95E4D
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Grant-AppvServerConnectionGroup
---

# Grant-AppvServerConnectionGroup

## SYNOPSIS
Entitles a connection group.

## SYNTAX

### ByObject
```
Grant-AppvServerConnectionGroup [-AppvServerConnectionGroup] <SerializableConnectionGroup> [-Groups] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByName
```
Grant-AppvServerConnectionGroup [-Groups] <String[]> [-Name] <String> [[-Version] <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByGUID
```
Grant-AppvServerConnectionGroup [-Groups] <String[]> [-GroupID] <Guid> [[-VersionID] <Guid>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-AppvServerConnectionGroup** cmdlet entitles an existing connection group.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AppvServerConnectionGroup
Specifies the package group object.

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

### -Groups
Specifies an array of strings containing the names of Active Directory groups.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the specified package group.

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
* If the cmdlet cannot find a package group, the cmdlet returns the following error: The specified package group could not be found on the system. The cmdlet fails the operation.
* If you specify an invalid group, the cmdlet returns the following error:  The provided entitlements are not valid. The cmdlet fails the operation.
* If you do not specify version information, the cmdlet operates on all available versions of the group.
* When entitling a package group, the cmdlet adds all entitlements to the individual packages themselves. The cmdlet returns all the packages in the group and any newly added entitlements.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


