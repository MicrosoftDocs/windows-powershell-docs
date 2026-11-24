---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/remove-hgsattestationhostgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HgsAttestationHostGroup
---

# Remove-HgsAttestationHostGroup

## SYNOPSIS
Removes an attestation policy based on a host group.

## SYNTAX

```
Remove-HgsAttestationHostGroup [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HgsAttestationHostGroup** cmdlet removes an attestation policy that is based on the configuration of an Active Directory host group from Host Guardian Service (HGS).

## EXAMPLES

### Example 1: Remove a host group
```
PS C:\> Remove-HgsAttestationHostGroup -Name "TrustedADHostGroup14"
```

This command removes the host group named TrustedADHostGroup14 from the Attestation service.
If a guarded host belongs to this host group and to no other trusted host group, the host can no longer obtain a new Attestation certificate.

## PARAMETERS

### -Name
Specifies the friendly name of the host group for which this cmdlet removes a policy.

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

[Add-HgsAttestationHostGroup](./Add-HgsAttestationHostGroup.md)

[Get-HgsAttestationHostGroup](./Get-HgsAttestationHostGroup.md)

