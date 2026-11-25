---
external help file: Microsoft.StorageMigration.Commands.dll-Help.xml
Module Name: StorageMigrationService
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagemigrationservice/get-smstransferpairing?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmsTransferPairing
---

# Get-SmsTransferPairing

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Computer Pairing (Default)
```
Get-SmsTransferPairing [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>]
 [-Credential <PSCredential>] [-Name] <String> [<CommonParameters>]
```

### Excluded Shares
```
Get-SmsTransferPairing -ComputerName <String> [-ExcludeSMBShares] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [-Name] <String> [<CommonParameters>]
```

### VolumePairings
```
Get-SmsTransferPairing -ComputerName <String> [-VolumePairings] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [-Name] <String> [<CommonParameters>]
```

### TieredAFSVolumeSettings
```
Get-SmsTransferPairing -ComputerName <String> [-TieredAFSVolumeSettings] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [-Name] <String> [<CommonParameters>]
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

### -ComputerName
{{ Fill ComputerName Description }}

```yaml
Type: System.String
Parameter Sets: Excluded Shares, VolumePairings, TieredAFSVolumeSettings
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
{{ Fill Credential Description }}

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: C

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeSMBShares
{{ Fill ExcludeSMBShares Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Excluded Shares
Aliases: ES

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -OrchestratorComputerName
{{ Fill OrchestratorComputerName Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OCN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrchestratorPort
{{ Fill OrchestratorPort Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TieredAFSVolumeSettings
{{ Fill TieredAFSVolumeSettings Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TieredAFSVolumeSettings
Aliases: TAVS

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumePairings
{{ Fill VolumePairings Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: VolumePairings
Aliases: VP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
