---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-AppvServerConnectionGroup
---

# Get-AppvServerConnectionGroup

## SYNOPSIS
Returns connection groups.

## SYNTAX

### ByName (Default)
```
Get-AppvServerConnectionGroup [[-Name] <String>] [[-Version] <Int32>] [<CommonParameters>]
```

### ByGUID
```
Get-AppvServerConnectionGroup [-GroupID] <Guid> [[-VersionID] <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvServerConnectionGroup** cmdlet returns a list of specified connection group objects.

## EXAMPLES

### 1:
```

```

## PARAMETERS

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

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### AppvServer.AppvServerConnectionGroup

## NOTES
* If the cmdlet cannot find the specified package groups, it returns the following error: The following package group(s) could not be found on the system.  It lists the packages.  The cmdlet fails the operation.
* If you do not specify version information, the cmdlet returns all existing versions of the package group.
* If you do not specify any parameters, the cmdlet returns a list of all the package groups and subsequent versions on the computer.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[New-AppvServerConnectionGroup](./New-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


