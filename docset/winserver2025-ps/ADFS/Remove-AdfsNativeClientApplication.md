---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsnativeclientapplication?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsNativeClientApplication
---

# Remove-AdfsNativeClientApplication

## SYNOPSIS
Removes a native client application role from an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Remove-AdfsNativeClientApplication [-TargetIdentifier] <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Name
```
Remove-AdfsNativeClientApplication [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObject
```
Remove-AdfsNativeClientApplication [-TargetApplication] <NativeClientApplication> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsNativeClientApplication** cmdlet removes a native client application role from an application in Active Directory Federation Services (AD FS).

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
Specifies the native client application to remove.

```yaml
Type: NativeClientApplication
Parameter Sets: ApplicationObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the ID of the native client application to remove.

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
Specifies the name of the native client application to remove.

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

### Microsoft.IdentityServer.Management.Resources.NativeClientApplication

NativeClientApplication objects are received by the *TargetApplication* parameter.

### System.String

String objects are received by the *TargetIdentifier* and *TargetName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.NativeClientApplication

Returns the removed NativeClientApplication object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-AdfsNativeClientApplication](./Add-AdfsNativeClientApplication.md)

[Get-AdfsNativeClientApplication](./Get-AdfsNativeClientApplication.md)

[Set-AdfsNativeClientApplication](./Set-AdfsNativeClientApplication.md)

