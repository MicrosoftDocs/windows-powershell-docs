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
ms.assetid: D355DBB0-3A96-4C16-93ED-FB754C97896D
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Publish-AppvServerConnectionGroup
---

# Publish-AppvServerConnectionGroup

## SYNOPSIS
Publishes a connection group.

## SYNTAX

### ByObject
```
Publish-AppvServerConnectionGroup [-AppvServerConnectionGroup] <SerializableConnectionGroup> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByName
```
Publish-AppvServerConnectionGroup [-Name] <String> [[-Version] <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByGUID
```
Publish-AppvServerConnectionGroup [-GroupID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Publish-AppvServerConnectionGroup** cmdlet publishes the specified connection group.

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
Specifies the GUID of a specific package group.

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

### AppvServer.AppvServerPackageGroup

## OUTPUTS

## NOTES
* If the cmdlet cannot find the specified package groups  on the server, the cmdlet returns the following error an error: The following package group(s) could not be found on the system. It lists the packages. The cmdlet fails the operation.
* If you do not specify version information, the cmdlet publishes all existing versions of the package group.
* If you do not specify any parameters, the cmdlet publishes all the package groups and subsequent versions on the computer.
* If a specified package group does not have at least one entitlement associated with it, the cmdlet return the following error: The following package group(s) could not be published because no associated entitlement group could be found. The cmdlet returns a list of the package groups and fails the operation for only those specific groups.
* If any of the specified groups are empty, the cmdlet returns the following error: One or more of the provided package groups is empty. The publishing operation has failed. The cmdlet returns a list of the package groups.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


