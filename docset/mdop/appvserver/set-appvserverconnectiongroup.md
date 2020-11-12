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
ms.assetid: 7695AC88-AC73-4079-B774-51E2A0B18010
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AppvServerConnectionGroup
---

# Set-AppvServerConnectionGroup

## SYNOPSIS
Configures an App-V server package group.

## SYNTAX

### ByName
```
Set-AppvServerConnectionGroup [[-AppvServerPackage] <PackageVersion[]>] [-Name] <String> [-Priority <UInt32>]
 [-Order <Int32[]>] [[-Version] <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObject
```
Set-AppvServerConnectionGroup [[-AppvServerPackage] <PackageVersion[]>]
 [-AppvServerConnectionGroup] <SerializableConnectionGroup> [-Priority <UInt32>] [-Order <Int32[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByGUID
```
Set-AppvServerConnectionGroup [[-AppvServerPackage] <PackageVersion[]>] [-Priority <UInt32>] [-Order <Int32[]>]
 [-GroupID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvServerConnectionGroup** cmdlet sets the packages within the Microsoft Application Virtualization (App-V) specified package group.
The cmdlet modifies the packages in the group, as well as the order of those packages.

The cmdlet returns an **AppvServerConnectionGroup** object.

## EXAMPLES

### Example 1: Modify a package group
```
PS C:\> $P11 = Get-AppvServerPackage -Name "Item03" -Version 1
PS C:\> $P12 = Get-AppvServerPackage -Name "Item14" -Version 2
PS C:\> $P13 = Get-AppvServerPackage -Name "MyGroup" -Version 3
PS C:\> $Group = New-AppvServerConnectionGroup -Name MyGroup
PS C:\> Set-AppvServerConnectionGroup -AppvServerConnectionGroup $Group -AppVServerPackage $P11,$P12,$P13 -Order 2,0,1 -Priority 1,0,1
```

This example sets the new package group, $Group, to contain the packages stored in $P11, $P12, $P13.
The priority and order fields are also added to each respective package in the group.

### Example 2: Modify priority and order properties
```
PS C:\> $Group.GroupedAppvServerPackage[0].priority = 1
PS C:\> $Group.GroupedAppvServerPackage[0].order = 1
PS C:\> Set-AppvServerConnectionGroup $Group
```

This example modifies the priority and order properties of the first package object that was added to the group.
The example applies the modifications to the group by using the **Set-AppvServerPackageGroup** cmdlet.

### Example 3: Modify a package group by using the pipeline operator
```
PS C:\> Get-AppvServerPackage -Name "Office" | Set-AppvServerConnectionGroup -Name "MyGroup" -Version 3
```

This command modifies the package group named MyGroup to contain the Office package.
Although the result of the **Get-AppvServerPackage** cmdlet might contain multiple versions of the package, only the latest version is added to the package group.

### Example 4: Add packages and metadata
```
PS C:\> $Group = New-AppvServerConnectionGroup -Name "MyGroup"
PS C:\> $Group.Set("$Package01, $Package02", "0,0", "1,0")
```

This example creates a group called MyGroup, and then adds $Package01 and $Package02 to the group.
The example includes priority and order metadata for each respective package.

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppvServerPackage
Specifies an array of **AppVServerPackage** objects.

```yaml
Type: PackageVersion[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
Accept pipeline input: True (ByValue)
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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Order
Specifies the order in which a package's virtual environment will be loaded when the package group is invoked on the App-V client.

Specify the order as a comma separated list, with each value corresponding to the list of packages being placed in the group.

If you do not specify this parameter, the order in which the packages are listed will be used as the virtual environment load order.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies a numerical value used to resolve conflicts between Virtual Application Packages that appear in multiple Package Groups.
Valid values are: 0 and 1.
The default value is 0.

Specify the priority as a comma separated list, with each value corresponding to the list of packages being placed in the group.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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
Accept pipeline input: True (ByValue)
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
Accept pipeline input: True (ByValue)
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

### AppvServer.AppvServerPackage, AppvServer.AppvServerConnectionGroup

## OUTPUTS

### AppvServer.AppvServerConnectionGroup

## NOTES
* The cmdlet accepts an ordered list of package groups. This list overwrites the current listing of packages for the specified group and increments the *VersionID* of the package. The server version will NOT be incremented. All existing metadata associated with the package, such as entitlements, are copied over to the new version.
* If the cmdlet cannot find a package group, the cmdlet returns the following error: The specified package group could not be found on the system. The cmdlet fails the entire operation.
* If the cmdlet cannot find any of the specified packages, the cmdlet returns the following error: One or more of the specified packages could not be found on the system. The cmdlet fails the entire operation and returns a listing of the packages.
* If multiple versions of a package group are selected, the latest version will be updated, and its version incremented. The other package groups are ignored.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


