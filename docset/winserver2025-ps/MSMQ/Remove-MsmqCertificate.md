---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/msmq/remove-msmqcertificate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-MsmqCertificate
---

# Remove-MsmqCertificate

## SYNOPSIS
Removes personal certificates.

## SYNTAX

```
Remove-MsmqCertificate -InputObject <X509Certificate2[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-MsmqCertificate** cmdlet removes personal certificates from Active Directory® Domain Services.
This cmdlet returns the removed Message Queuing (also known as MSMQ) certificate.

## EXAMPLES

### Example 1: Remove all certificates for the current user
```
PS C:\> Get-MsmqCertificate | Remove-MsmqCertificate
```

This command gets the certificates of the current user for all hosts or virtual servers by using the **Get-MsmqCertificate** cmdlet.
The command passes them to the current cmdlet by using the pipeline operator.
The current command removes the certificates.

## PARAMETERS

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

### -InputObject
Specifies an array of certificate objects that represent certificates that this cmdlet removes from Active Directory Domain Services.
This parameter accepts pipeline input.

```yaml
Type: X509Certificate2[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### System.Security.Cryptography.X509Certificates.X509Certificate2[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-MsmqCertificate](./Get-MSMQCertificate.md)

[Enable-MsmqCertificate](./Enable-MSMQCertificate.md)

