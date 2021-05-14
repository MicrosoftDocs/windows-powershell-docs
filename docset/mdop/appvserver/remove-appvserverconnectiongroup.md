---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Remove-AppvServerConnectionGroup
---

# Remove-AppvServerConnectionGroup

## SYNOPSIS
Removes App-V server connection group.

## SYNTAX

### ByName (Default)
```
Remove-AppvServerConnectionGroup [-Name] <String> [-Force] [[-Version] <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByObject
```
Remove-AppvServerConnectionGroup [-AppvServerConnectionGroup] <SerializableConnectionGroup> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByGUID
```
Remove-AppvServerConnectionGroup [-Force] [-GroupID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppvServerConnectionGroup** cmdlet removes a Microsoft Application Virtualization (App-V) server connection group from the computer.

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

### -Force
Not Specified.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
* Once the package group is removed, its packages remain in other package groups and as part of the library of imported packages on the server.
* If the cmdlet cannot find a specified package, the cmdlet returns the following error: The specified package could not be found on the system. The cmdlet fails the operation.
* If you do not specify version information, the cmdlet acts on all available versions of the group.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


