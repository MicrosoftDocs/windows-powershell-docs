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
ms.assetid: 996C2F77-E67E-49D1-AFDB-37AA0FB19E75
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-AppvServerConnectionGroupPackage
---

# Remove-AppvServerConnectionGroupPackage

## SYNOPSIS
(Cmdlet applicable starting in App-V 5.0 SP3) Removes a package from a connection group.

## SYNTAX

### ByObject
```
Remove-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] <SerializableConnectionGroup>
 [[-AppvServerPackage] <PackageVersion>] [-PackageName <String>] [-PackageVersion <String>] [-PackageID <Guid>]
 [-PackageVersionID <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByName
```
Remove-AppvServerConnectionGroupPackage [-ConnectionGroupName] <String> [[-AppvServerPackage] <PackageVersion>]
 [[-ConnectionGroupVersion] <Int32>] [-PackageName <String>] [-PackageVersion <String>] [-PackageID <Guid>]
 [-PackageVersionID <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByGUID
```
Remove-AppvServerConnectionGroupPackage [-ConnectionGroupID] <Guid> [[-ConnectionGroupVersionID] <Guid>]
 [[-AppvServerPackage] <PackageVersion>] [-PackageName <String>] [-PackageVersion <String>] [-PackageID <Guid>]
 [-PackageVersionID <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppvServerConnectionGroupPackage** cmdlet removes a package from a connection group.

## EXAMPLES

### 1:
```

```

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

### -AppvServerPackage
Specifies an **AppVServerPackage** object.

```yaml
Type: PackageVersion
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ConnectionGroupID
Specifies the GUID of the connection group.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: GroupID

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionGroupName
Specifies the name of the connection group.

```yaml
Type: String
Parameter Sets: ByName
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionGroupVersion
Specifies the version of the connection group.

```yaml
Type: Int32
Parameter Sets: ByName
Aliases: Version

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionGroupVersionID
Specifies the GUID of the connection group version.

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: VersionID

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageID
Specifies the GUID that uniquely identifies the package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageName
Specifies the name of the package.

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

### -PackageVersion
Specifies the version of the package.

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

### -PackageVersionID
Specifies the GUID that uniquely identifies the version of the package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### Microsoft.AppV.Server.AppVMgmtDataTypes.SerializableConnectionGroup, Microsoft.AppV.Server.AppVMgmtDataTypes.PackageVersion

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-AppvServerConnectionGroupPackage](./Add-AppvServerConnectionGroupPackage.md)

[Set-AppvServerConnectionGroupPackage](./Set-AppvServerConnectionGroupPackage.md)


