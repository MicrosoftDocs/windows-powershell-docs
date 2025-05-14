---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/remove-hgsattestationtpmhost?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HgsAttestationTpmHost
---

# Remove-HgsAttestationTpmHost

## SYNOPSIS
Removes a guarded host with TPM 2.0 from the Attestation service in HGS.

## SYNTAX

```
Remove-HgsAttestationTpmHost [-Name] <String> [-PolicyVersion <PolicyVersion>] [-Stage] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HgsAttestationTpmHost** cmdlet removes a guarded host from the Attestation service in Host Guardian Service (HGS).
Use this cmdlet for hosts that have trusted platform module (TPM) 2.0 hardware, and that were added by using the **Add-HgsAttestationTpmHost** cmdlet.

## EXAMPLES

### Example 1: Remove a TPM host
```
PS C:\> Remove-HgsAttestationTpmHost -Name "TpmHost21"
```

This command removes a host named TpmHost21 from the Attestation service.

## PARAMETERS

### -Name
Specifies the friendly name of the guarded host that this cmdlet removes from the Attestation service.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PolicyVersion
Reserved for future use.

```yaml
Type: PolicyVersion
Parameter Sets: (All)
Aliases:
Accepted values: None, PolicyVersion1503, PolicyVersion1704

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stage
Reserved for future use.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-HgsAttestationTpmHost](./Add-HgsAttestationTpmHost.md)

[Get-HgsAttestationTpmHost](./Get-HgsAttestationTpmHost.md)

