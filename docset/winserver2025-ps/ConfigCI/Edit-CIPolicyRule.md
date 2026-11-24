---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/edit-cipolicyrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Edit-CIPolicyRule
---

# Edit-CIPolicyRule

## SYNOPSIS
This cmdlet is not supported.

## SYNTAX

### FileRule
```
Edit-CIPolicyRule [-Id] <String> [-Name <String>] [-RType <String>] [-FileName <String>] [-Version <String>]
 [-HashPath <String>] -FilePath <String> [<CommonParameters>]
```

### SignerRule
```
Edit-CIPolicyRule [-Id] <String> [-Name <String>] [-RType <String>] [-Root <String>] [-AddEkus <String[]>]
 [-RemoveEkus <String[]>] [-Issuer <String>] [-Publisher <String>] [-OemId <String>]
 [-AddExceptions <String[]>] [-RemoveExceptions <String[]>] -FilePath <String> [<CommonParameters>]
```

## DESCRIPTION
The **Edit-CIPolicyRule** cmdlet is not supported.
Do not use this cmdlet.

## EXAMPLES


## PARAMETERS

### -AddEkus


```yaml
Type: String[]
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddExceptions


```yaml
Type: String[]
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName


```yaml
Type: String
Parameter Sets: FileRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath


```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HashPath


```yaml
Type: String
Parameter Sets: FileRule
Aliases: h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id


```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Issuer


```yaml
Type: String
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name


```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OemId


```yaml
Type: String
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
```yaml
Type: String
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveEkus

```yaml
Type: String[]
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveExceptions

```yaml
Type: String[]
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Root

```yaml
Type: String
Parameter Sets: SignerRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RType
```yaml
Type: String
Parameter Sets: (All)
Aliases: t
Accepted values: Allow, Deny, a, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version


```yaml
Type: String
Parameter Sets: FileRule
Aliases: v

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

