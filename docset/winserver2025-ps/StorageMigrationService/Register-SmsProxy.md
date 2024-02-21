---
external help file: Microsoft.StorageMigration.Commands.dll-Help.xml
Module Name: StorageMigrationService
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/storagemigrationservice/register-smsproxy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-SmsProxy
---

# Register-SmsProxy

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Register-SmsProxy [-ComputerName] <String> [-ProxyPort <Int32>] [-OrchestratorComputerName <String>]
 [-OrchestratorPort <Int32>] [-Credential <PSCredential>] [-ProxyCredential <PSCredential>] [-EnableFirewall]
 [-Force] [<CommonParameters>]
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
Parameter Sets: (All)
Aliases: CN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -EnableFirewall
{{ Fill EnableFirewall Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: EF

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

### -ProxyCredential
{{ Fill ProxyCredential Description }}

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: PCR

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyPort
{{ Fill ProxyPort Description }}

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: PP

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

### System.Int32

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
