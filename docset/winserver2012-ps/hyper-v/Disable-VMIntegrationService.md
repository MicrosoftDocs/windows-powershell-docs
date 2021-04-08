---
author: Kateyanne
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/hyper-v/disable-vmintegrationservice?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-VMIntegrationService

## SYNOPSIS
Disables an integration service on a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-VMIntegrationService [-Name] <String[]> [-VMName] <String[]> [-ComputerName <String[]>] [-Passthru]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-VMIntegrationService [-Name] <String[]> [-VM] <VirtualMachine[]> [-Passthru] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Disable-VMIntegrationService [-VMIntegrationService] <VMIntegrationComponent[]> [-Passthru] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Disable-VMIntegrationService** cmdlet disables an integration service on a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Disable-VMIntegrationService -Name Shutdown,VSS -VMName Test1
```

This example disables the Shutdown and VSS integration services on virtual machine Test1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the integration service on a virtual machine is to be disabled.
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
Specifies the name of the integration service to be disabled.

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
Specifies that a **Microsoft.Virtualization.PowerShell.IntegrationService** object is to be passed through to the pipeline representing the integration service to be disabled.

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
Specifies the virtual machine on which the integration service is to be disabled.

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
Specifies the integration service to be disabled.

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
Specifies the name of the virtual machine on which the integration service is to be disabled.

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



