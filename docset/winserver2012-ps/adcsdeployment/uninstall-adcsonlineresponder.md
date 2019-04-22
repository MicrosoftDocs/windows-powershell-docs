---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
ms.assetid: DB15EC96-69EF-4303-BD9B-254619C02C4C
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Uninstall-AdcsOnlineResponder

## SYNOPSIS
Uninstalls the Online Responder service.

## SYNTAX

```
Uninstall-AdcsOnlineResponder [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-AdcsOnlineResponder cmdlet removes the Online Responder role service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Uninstall-AdcsOnlineResponder -force
```

Description

-----------

This command removes Online Responder role service without requiring confirmation.

## PARAMETERS

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.OCSP.OnlineResponderResult

## NOTES
* Ensure you run Windows PowerShell® as an administrator. You can use the -force switch to bypass the prompt for confirmation.

  

## RELATED LINKS

[Install-AdcsOnlineResponder](./Install-AdcsOnlineResponder.md)

