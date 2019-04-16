---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Enable-VMIntegrationService

## SYNOPSIS
Enables an integration service on a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-VMIntegrationService [-Name] <String[]> [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-VMIntegrationService [-Name] <String[]> [-VM] <VirtualMachine[]> [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Enable-VMIntegrationService [-VMIntegrationService] <VMIntegrationComponent[]> [-Passthru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-VMIntegrationService** cmdlet enables an integration service on a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Enable-VMIntegrationService -Name Shutdown,VSS -VMName Test1
```

Enables integration services Shutdown and VSS on virtual machine Test1.

### Example 2
```
PS C:\>Get-VMIntegrationService Shutdown,Vss -VMName Test1 | Enable-VMIntegrationService
```

Enables integration services Shutdown and VSS on virtual machine Test1.

### Example 3
```
PS C:\>Get-VM Test1 | Enable-VMIntegrationService Shutdown,VSS
```

Enables integration services Shutdown and VSS on virtual machine Test1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which an integration service is to be enabled.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the integration service to be enabled.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.Virtualization.PowerShell.IntegrationService** object is to be passed through to the pipeline representing the integration service to be enabled.

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

### -VM
Specifies the virtual machine on which the integration service is to be enabled.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMIntegrationService
Specifies the integration service to be enabled.

```yaml
Type: VMIntegrationComponent[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the integration service is to be enabled.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None
Default

### Microsoft.Virtualization.PowerShell.IntegrationService
If **-PassThru** is specified.

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

