---
external help file: MSMQ_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 43423EEE-4176-4736-A3B6-874A31BA0D15
manager: dansimp
---

# Remove-MsmqCertificate

## SYNOPSIS
Removes the specified personal certificate.

## SYNTAX

```
Remove-MsmqCertificate -InputObject <X509Certificate2[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-MsmqCertificate** cmdlet removes the personal certificates represented by the supplied certificate objects from Active Directory Domain Services, and returns the removed MSMQ certificate.

## EXAMPLES

### Example 1: Remove a personal certificate
```
PS C:\>Get-MsmqCertificate | Remove-MsmqCertificate
```

This command removes a personal certificate objects from Active Directory Domain Services.

## PARAMETERS

### -InputObject
Specifies a certificate object that represents a certificate that is removed from the Active Directory Domain Services.

```yaml
Type: X509Certificate2[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MsmqCertificate](./Get-MsmqCertificate.md)

[Enable-MsmqCertificate](./Enable-MsmqCertificate.md)

