---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsapplicationgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsApplicationGroup
---

# Remove-AdfsApplicationGroup

## SYNOPSIS
Removes an application group.

## SYNTAX

### ApplicationGroupIdentifier (Default)
```
Remove-AdfsApplicationGroup [-TargetApplicationGroupIdentifier] <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Name
```
Remove-AdfsApplicationGroup [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationGroupObject
```
Remove-AdfsApplicationGroup [-TargetApplicationGroup] <ApplicationGroup> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsApplicationGroup** cmdlet removes an application group from Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -TargetApplicationGroup
Specifies the application group to remove.

```yaml
Type: ApplicationGroup
Parameter Sets: ApplicationGroupObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetApplicationGroupIdentifier
Specifies the ID of the target application group to remove.

```yaml
Type: String
Parameter Sets: ApplicationGroupIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the application group to remove.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### Microsoft.IdentityServer.Management.Resources.ApplicationGroup

ApplicationGroup objects are received by the *TargetApplicationGroup* parameter.

### System.String

String objects are received by the *TargetApplicationGroupIdentifier* and *TargetName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.ApplicationGroup

Returns the removed ApplicationGroup object when the PassThru parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Disable-AdfsApplicationGroup](./Disable-AdfsApplicationGroup.md)

[Enable-AdfsApplicationGroup](./Enable-AdfsApplicationGroup.md)

[Get-AdfsApplicationGroup](./Get-AdfsApplicationGroup.md)

[New-AdfsApplicationGroup](./New-AdfsApplicationGroup.md)

[Set-AdfsApplicationGroup](./Set-AdfsApplicationGroup.md)

