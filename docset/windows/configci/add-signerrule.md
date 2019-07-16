---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-SignerRule
ms.reviewer:
ms.assetid: 55153F8F-110A-4D8E-AC99-CFF4E533E023
---

# Add-SignerRule

## SYNOPSIS
Creates a signer rule and adds it to a policy.

## SYNTAX

```
Add-SignerRule -FilePath <String> -CertificatePath <String> [-Kernel] [-User] [-Update] [-Deny]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SignerRule** cmdlet creates a signer rule based on a certificate, and then adds the rule to a Code Integrity policy.
By default, this cmdlet creates allow rules.
Specify at least one scenario for the rule in the policy from the following scenarios: 

- User 
- Kernel 
- Update

## EXAMPLES

### Example 1: Create and add a signer rule for User mode
```
PS C:\> Add-SignerRule -FilePath '.\Policy.xml' -CertificatePath '.\certificate07.cer' -User
```

This command generates a signer rule for the certificate in certificate07.cer.
The command adds the rule to policy.xml for the User mode scenario.

## PARAMETERS

### -CertificatePath
Specifies the path of a certificate (.cer) file that this cmdlet uses for the rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: c

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deny
Indicates that this cmdlet creates a deny rule instead of the default allow rule.

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

### -FilePath
Specifies the path of the policy .xml file to which this cmdlet adds the rule.

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

### -Kernel
Indicates that this cmdlet adds the rule as a Kernel mode rule.
You can add a rule as more than one scenario.

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

### -Update
Indicates that this cmdlet adds the rule as an Update policy signers rule.
You can add a rule as more than one scenario.

Update policy signers rules to determine which signers can sign a policy in signed policy scenario.

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

### -User
Indicates that this cmdlet adds the rule as a User mode rule.
You can add a rule as more than one scenario.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-CIPolicyRule](./New-CIPolicyRule.md)

