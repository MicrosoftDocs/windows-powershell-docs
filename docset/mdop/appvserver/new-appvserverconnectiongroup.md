---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: New-AppvServerConnectionGroup
---

# New-AppvServerConnectionGroup

## SYNOPSIS
Creates an App-V connection group.

## SYNTAX

```
New-AppvServerConnectionGroup -Name <String> [-Priority <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AppvServerConnectionGroup** cmdlet creates an empty Microsoft Application Virtualization (App-V) connection group on the management server.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the package group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
This parameter is applicable only for App-V 5.0 SP3 or any subsequent versions of App-V.
Specifies a value used to resolve conflicts when opening a package that has been added to multiple connection groups.
The connection group with the lowest priority value is used.

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
* This cmdlet returns the new Connection group.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Get-AppvServerConnectionGroup](./Get-AppvServerConnectionGroup.md)

[Grant-AppvServerConnectionGroup](./Grant-AppvServerConnectionGroup.md)

[Publish-AppvServerConnectionGroup](./Publish-AppvServerConnectionGroup.md)

[Remove-AppvServerConnectionGroup](./Remove-AppvServerConnectionGroup.md)

[Set-AppvServerConnectionGroup](./Set-AppvServerConnectionGroup.md)

[Unpublish-AppvServerConnectionGroup](./Unpublish-AppvServerConnectionGroup.md)

[Update-AppvServerConnectionGroup](./Update-AppvServerConnectionGroup.md)


