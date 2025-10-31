---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsserverapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsServerApplication
---

# Remove-AdfsServerApplication

## SYNOPSIS
Removes a server application role from an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Remove-AdfsServerApplication [-TargetIdentifier] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name
```
Remove-AdfsServerApplication [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObject
```
Remove-AdfsServerApplication [-TargetApplication] <ServerApplication> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsServerApplication** cmdlet removes a server application role from an application in Active Directory Federation Services (AD FS).

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

### -TargetApplication
Specifies the server application to remove.

```yaml
Type: ServerApplication
Parameter Sets: ApplicationObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the ID of the server application to remove.

```yaml
Type: String
Parameter Sets: Identifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the server application to remove.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsServerApplication](./Add-AdfsServerApplication.md)

[Get-AdfsServerApplication](./Get-AdfsServerApplication.md)

[Set-AdfsServerApplication](./Set-AdfsServerApplication.md)

