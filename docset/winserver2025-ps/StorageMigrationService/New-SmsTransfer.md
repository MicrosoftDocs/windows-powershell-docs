---
external help file: Microsoft.StorageMigration.Commands.dll-Help.xml
Module Name: StorageMigrationService
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagemigrationservice/new-smstransfer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmsTransfer
---

# New-SmsTransfer

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
New-SmsTransfer -DestinationCredential <PSCredential> [-SourceCredential <PSCredential>]
 [-TransferType <TransferType>] [-MaxDuration <Int32>] [-FileRetryIntervalInSec <Int32>]
 [-FileRetryCount <Int32>] [-ExcludeDataSecurity] [-ExcludeLocalPrincipals]
 [-SecurityMigrationOption <SecurityMigrationOptions>] [-SkipMovePreExisting]
 [-ChecksumType <TransferChecksumType>] [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>]
 [-Credential <PSCredential>] [-SourceHostUsername <String>] [-SourceHostPassword <SecureString>]
 [-SourceHostPrivateKey <SecureString>] [-SourceHostPassphrase <SecureString>]
 [-SourceHostFingerprint <String>] [-Overwrite] [-OverrideTransferValidation <Boolean>] [-Force]
 [-Name] <String> [<CommonParameters>]
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

### -ChecksumType
{{ Fill ChecksumType Description }}

```yaml
Type: System.Nullable`1[Microsoft.StorageMigration.Commands.TransferChecksumType]
Parameter Sets: (All)
Aliases: CHK
Accepted values: None, Crc64, SHA256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -DestinationCredential
{{ Fill DestinationCredential Description }}

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: DCR

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeDataSecurity
{{ Fill ExcludeDataSecurity Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: EDS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeLocalPrincipals
{{ Fill ExcludeLocalPrincipals Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ELP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileRetryCount
{{ Fill FileRetryCount Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: FRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileRetryIntervalInSec
{{ Fill FileRetryIntervalInSec Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: FRI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{ Fill Force Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxDuration
{{ Fill MaxDuration Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MD

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

### -OverrideTransferValidation
{{ Fill OverrideTransferValidation Description }}

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Overwrite
{{ Fill Overwrite Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityMigrationOption
{{ Fill SecurityMigrationOption Description }}

```yaml
Type: System.Nullable`1[Microsoft.StorageMigration.Service.Contracts.SecurityMigrationOptions]
Parameter Sets: (All)
Aliases: SMO
Accepted values: MigrateAndRenameConflictingAccounts, MigrateAndMergeConflictingAccounts, SkipSecurityMigration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipMovePreExisting
{{ Fill SkipMovePreExisting Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceCredential
{{ Fill SourceCredential Description }}

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: SCR

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHostFingerprint
{{ Fill SourceHostFingerprint Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SHFP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHostPassphrase
{{ Fill SourceHostPassphrase Description }}

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases: SHPP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHostPassword
{{ Fill SourceHostPassword Description }}

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases: SHPW

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHostPrivateKey
{{ Fill SourceHostPrivateKey Description }}

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases: SHPK

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceHostUsername
{{ Fill SourceHostUsername Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SHU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferType
{{ Fill TransferType Description }}

```yaml
Type: Microsoft.StorageMigration.Commands.TransferType
Parameter Sets: (All)
Aliases: TT
Accepted values: Copy, Move

Required: False
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
