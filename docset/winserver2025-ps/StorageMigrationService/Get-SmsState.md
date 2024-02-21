---
external help file: Microsoft.StorageMigration.Commands.dll-Help.xml
Module Name: StorageMigrationService
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagemigrationservice/get-smsstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmsState
---

# Get-SmsState

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### Job Summary (Default)
```
Get-SmsState [-JobSummary] [[-Name] <String>] [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Inventory Config Detail
```
Get-SmsState -ComputerName <String> [-InventoryConfigDetail] [-Name] <String> [-IncludeAllAdapters]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Inventory SMB Detail
```
Get-SmsState -ComputerName <String> [-InventorySMBDetail] [-Name] <String> [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Inventory DFSN Detail
```
Get-SmsState -ComputerName <String> [-InventoryDFSNDetail] [-Name] <String>
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Transfer SMB Detail
```
Get-SmsState -ComputerName <String> [-Name] <String> [-TransferSMBDetail] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Transfer DFSN Detail
```
Get-SmsState -ComputerName <String> [-Name] <String> [-TransferDFSNDetail] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Transfer File Detail
```
Get-SmsState -ComputerName <String> [-Name] <String> [-TransferFileDetail] [-ErrorsOnly]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Transfer Volume Detail
```
Get-SmsState -ComputerName <String> [-Name] <String> [-TransferVolumeDetail]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [-VolumeTypes <VolumeType>] [<CommonParameters>]
```

### Cutover Summary
```
Get-SmsState [-ComputerName <String>] [-Name] <String> [-CutoverSummary] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Get Local User Detail
```
Get-SmsState -ComputerName <String> [-Name] <String> [-GetLocalUsersDetail]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Get Local Groups Detail
```
Get-SmsState -ComputerName <String> [-Name] <String> [-GetLocalGroupsDetail]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Get NasPrescanResult Detail
```
Get-SmsState -NasController <String> [-Name] <String> [-GetNasPrescanResult]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Inventory Summary
```
Get-SmsState [-InventorySummary] [-Name] <String> [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Transfer Summary
```
Get-SmsState [-Name] <String> [-TransferSummary] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [<CommonParameters>]
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
Parameter Sets: Inventory Config Detail, Inventory SMB Detail, Inventory DFSN Detail, Transfer SMB Detail, Transfer DFSN Detail, Transfer File Detail, Transfer Volume Detail, Get Local User Detail, Get Local Groups Detail
Aliases: CN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Cutover Summary
Aliases: CN

Required: False
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

### -CutoverSummary
{{ Fill CutoverSummary Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Cutover Summary
Aliases: CS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorsOnly
{{ Fill ErrorsOnly Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Transfer File Detail
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetLocalGroupsDetail
{{ Fill GetLocalGroupsDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Get Local Groups Detail
Aliases: GLGD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetLocalUsersDetail
{{ Fill GetLocalUsersDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Get Local User Detail
Aliases: GLUD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetNasPrescanResult
{{ Fill GetNasPrescanResult Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Get NasPrescanResult Detail
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllAdapters
{{ Fill IncludeAllAdapters Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Inventory Config Detail
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InventoryConfigDetail
{{ Fill InventoryConfigDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Inventory Config Detail
Aliases: ICD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InventoryDFSNDetail
{{ Fill InventoryDFSNDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Inventory DFSN Detail
Aliases: IDD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InventorySMBDetail
{{ Fill InventorySMBDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Inventory SMB Detail
Aliases: ISD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InventorySummary
{{ Fill InventorySummary Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Inventory Summary
Aliases: IS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobSummary
{{ Fill JobSummary Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Job Summary
Aliases: JS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: System.String
Parameter Sets: Job Summary
Aliases: N

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Inventory Config Detail, Inventory SMB Detail, Inventory DFSN Detail, Transfer SMB Detail, Transfer DFSN Detail, Transfer File Detail, Transfer Volume Detail, Cutover Summary, Get Local User Detail, Get Local Groups Detail, Get NasPrescanResult Detail, Inventory Summary, Transfer Summary
Aliases: N

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -NasController
{{ Fill NasController Description }}

```yaml
Type: System.String
Parameter Sets: Get NasPrescanResult Detail
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TransferDFSNDetail
{{ Fill TransferDFSNDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Transfer DFSN Detail
Aliases: TDD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferFileDetail
{{ Fill TransferFileDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Transfer File Detail
Aliases: TFD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferSMBDetail
{{ Fill TransferSMBDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Transfer SMB Detail
Aliases: TSD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferSummary
{{ Fill TransferSummary Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Transfer Summary
Aliases: TS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferVolumeDetail
{{ Fill TransferVolumeDetail Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Transfer Volume Detail
Aliases: TVD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeTypes
{{ Fill VolumeTypes Description }}

```yaml
Type: Microsoft.StorageMigration.Commands.GetSmsStateCommand+VolumeType
Parameter Sets: Transfer Volume Detail
Aliases: VT
Accepted values: TAFSEnabled, NonTAFSEnabled, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.StorageMigration.Commands.GetSmsStateCommand+VolumeType

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
