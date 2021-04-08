---
author: Kateyanne
external help file: MSMQ_Cmdlets.xml
manager: dansimp
Module Name: MSMQ
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/msmq/remove-msmqcertificate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

