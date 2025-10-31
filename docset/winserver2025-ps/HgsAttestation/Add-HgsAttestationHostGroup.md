---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.RemoteAttestation.Server.PowerShell.dll-Help.xml
Module Name: HgsAttestation
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsattestation/add-hgsattestationhostgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-HgsAttestationHostGroup
---

# Add-HgsAttestationHostGroup

## SYNOPSIS
Adds an attestation policy for an Active Directory host group configuration.

## SYNTAX

### hostGroup
```
Add-HgsAttestationHostGroup -Name <String> -HostGroup <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### sid
```
Add-HgsAttestationHostGroup -Name <String> -Identifier <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HgsAttestationHostGroup** cmdlet adds an Attestation policy that is based on the configuration of an Active Directory host group.
Specify a host group by name or security identifier (SID).

## EXAMPLES

### Example 1: Add a host group
```
PS C:\> Add-HgsAttestationHostGroup -Name "TrustedADHostGroup14" -Identifier $Sid
```

This command adds a host group from the Active Directory fabric to the Attestation service.
The *Identifier* parameter specifies an SID stored in $Sid.
After you run this command, the Attestation service trusts all hosts that belong to this host group to host shielded virtual machines.

## PARAMETERS

### -HostGroup
Specifies the name of a host group on which this cmdlet bases the policy.
Include the domain.

```yaml
Type: String
Parameter Sets: hostGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identifier
Specifies the SID of a host group on which this cmdlet bases the policy.

```yaml
Type: String
Parameter Sets: sid
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the host group.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

[Get-HgsAttestationHostGroup](./Get-HgsAttestationHostGroup.md)

[Remove-HgsAttestationHostGroup](./Remove-HgsAttestationHostGroup.md)

