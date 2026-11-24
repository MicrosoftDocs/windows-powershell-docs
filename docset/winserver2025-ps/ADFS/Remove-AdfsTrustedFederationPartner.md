---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfstrustedfederationpartner?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsTrustedFederationPartner
---

# Remove-AdfsTrustedFederationPartner

## SYNOPSIS
Removes a trusted federation partner in AD FS.

## SYNTAX

### Name (Default)
```
Remove-AdfsTrustedFederationPartner [-TargetName] <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FederationPartnerHostName
```
Remove-AdfsTrustedFederationPartner [-TargetFederationPartnerHostName] <Uri> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject
```
Remove-AdfsTrustedFederationPartner [-TargetFederationPartner] <AdfsTrustedFederationPartner> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsTrustedFederationPartner** cmdlet removes a federation partner that is trusted by this instance of Active Directory Federation Services (AD FS).

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

### -TargetFederationPartner
Specifies a federation partner to remove.

```yaml
Type: AdfsTrustedFederationPartner
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetFederationPartnerHostName
Specifies the URI of a federation partner to remove.

```yaml
Type: Uri
Parameter Sets: FederationPartnerHostName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of a federation partner to remove.

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

[Add-AdfsTrustedFederationPartner](./Add-AdfsTrustedFederationPartner.md)

[Get-AdfsTrustedFederationPartner](./Get-AdfsTrustedFederationPartner.md)

[Set-AdfsTrustedFederationPartner](./Set-AdfsTrustedFederationPartner.md)

