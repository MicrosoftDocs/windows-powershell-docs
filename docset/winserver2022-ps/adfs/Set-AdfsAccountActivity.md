---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 09/30/2021
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsaccountactivity?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAccountActivity
---

# Set-AdfsAccountActivity

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Identity (Default)
```
Set-AdfsAccountActivity [-Identity] <String> [[-AdditionalFamiliarIps] <String[]>] [-Clear] [-Force]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Upn
```
Set-AdfsAccountActivity -UserPrincipalName <String> [[-AdditionalFamiliarIps] <String[]>] [-Clear] [-Force]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### -AdditionalFamiliarIps
{{ Fill AdditionalFamiliarIps Description }}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Clear
{{ Fill Clear Description }}

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

### -Force
{{ Fill Force Description }}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
