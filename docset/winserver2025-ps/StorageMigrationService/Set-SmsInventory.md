---
external help file: Microsoft.StorageMigration.Commands.dll-Help.xml
Module Name: StorageMigrationService
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagemigrationservice/set-smsinventory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SmsInventory
---

# Set-SmsInventory

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### None (Default)
```
Set-SmsInventory [-SourceCredential <PSCredential>] [-IncludeAdminShares <Boolean>]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [-SourceHostUsername <String>] [-SourceHostPassword <SecureString>] [-SourceHostPrivateKey <SecureString>]
 [-SourceHostPassphrase <SecureString>] [-SourceHostFingerprint <String>] [-Force] [-IncludeDFSN <Boolean>]
 [-IncludeDFSR <Boolean>] [-Name] <String> [<CommonParameters>]
```

### Manual Scan
```
Set-SmsInventory [-ComputerName <String[]>] [-SourceCredential <PSCredential>] [-IncludeAdminShares <Boolean>]
 [-OrchestratorComputerName <String>] [-OrchestratorPort <Int32>] [-Credential <PSCredential>]
 [-SourceHostUsername <String>] [-SourceHostPassword <SecureString>] [-SourceHostPrivateKey <SecureString>]
 [-SourceHostPassphrase <SecureString>] [-SourceHostFingerprint <String>] [-Force] [-IncludeDFSN <Boolean>]
 [-IncludeDFSR <Boolean>] [-Name] <String> [<CommonParameters>]
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
Type: System.String[]
Parameter Sets: Manual Scan
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

### -IncludeAdminShares
{{ Fill IncludeAdminShares Description }}

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases: AS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeDFSN
{{ Fill IncludeDFSN Description }}

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases: DFSN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeDFSR
{{ Fill IncludeDFSR Description }}

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases: DFSR

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
