---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/disable-vmintegrationservice?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-VMIntegrationService
---

# Disable-VMIntegrationService

## SYNOPSIS
Disables an integration service on a virtual machine.

## SYNTAX

### VMName (Default)
```
Disable-VMIntegrationService [-Name] <String[]> [-VMName] <String[]> [-Passthru] [-ComputerName <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMIntegrationService
```
Disable-VMIntegrationService [-VMIntegrationService] <VMIntegrationComponent[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Disable-VMIntegrationService [-Name] <String[]> [-VM] <VirtualMachine[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
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
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
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

### -Name
Specifies the name of the integration service to be disabled.

```yaml
Type: String[]
Parameter Sets: VMName, VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.IntegrationService** object is to be passed through to the pipeline representing the integration service to be disabled.

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
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMIntegrationService
Specifies the integration service to be disabled.

```yaml
Type: VMIntegrationComponent[]
Parameter Sets: VMIntegrationService
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the integration service is to be disabled.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

###  
None by default; **Microsoft.HyperV.PowerShell.IntegrationService** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

