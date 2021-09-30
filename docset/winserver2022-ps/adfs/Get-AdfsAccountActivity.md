---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 09/30/2021
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfsaccountactivity?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsAccountActivity
---

# Get-AdfsAccountActivity

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Identity (Default)
```
Get-AdfsAccountActivity [-Identity] <String> [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Upn
```
Get-AdfsAccountActivity -UserPrincipalName <String> [-Server <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Identity
{{ Fill Identity Description }}

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
{{ Fill Server Description }}

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

### -UserPrincipalName
{{ Fill UserPrincipalName Description }}

```yaml
Type: String
Parameter Sets: Upn
Aliases:

Required: True
Position: Named
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
