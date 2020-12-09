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
ms.assetid: FCE46BDA-5F36-4146-8C34-5956A8F74C76
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Update-AppvServerConnectionGroup
---

# Update-AppvServerConnectionGroup

## SYNOPSIS
Updates the specified connection group.

## SYNTAX

### ByObject
```
Update-AppvServerConnectionGroup [-AppvServerConnectionGroup] <SerializableConnectionGroup> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByName
```
Update-AppvServerConnectionGroup [-Name] <String> [[-Version] <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AppvServerConnectionGroup** cmdlet updates a connection group.
This cmdlet increments the version of the package group in the server management console.

## EXAMPLES

### Example 1: Update a group
```
PS C:\> Update-AppvServerConnectionGroup -Name "Office" | Set-AppvServerConnectionGroup $Package01 $Package02
```

This command updates the group named Office, and then sets two packages to be in the group.

### Example 2: Get an updated version
```
PS C:\> $Group = Get-AppvServerPackage -PackageGUID A1232ACFD3EF
PS C:\> Update-AppvServerConnectionGroup -Name $Package.Name
```

This example returns an updated version of $Group.
The new version contains no package groups.
Note that $Group could contain multiple versions of the package group, but the cmdlet uses the latest version of the package group to create the new version.

### Example 3: Store an updated version in a variable
```
PS C:\> $Group = Get-AppvServerConnectionGroup -Name "Office"
PS C:\> $Group02 = $Group.Update()
```

This example returns an updated version of $Group, and stores it in $Group02.
The $Group02 variable contains no packages.

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

## OUTPUTS

### AppvServer.AppvServerPackageGroup

## NOTES
* This cmdlet returns an **AppvServerPackageGroup** object that references the updated version of the package group.
* You must specify the name of an existing package group. If the group does not exist, the cmdlet returns the following error: The specified package group could not be found on the system.
* This cmdlet returns an empty package group with its server version incremented. The version GUID will NOT be incremented until you run the **Set-AppvServerPackageGroup** cmdlet.

## RELATED LINKS

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)


