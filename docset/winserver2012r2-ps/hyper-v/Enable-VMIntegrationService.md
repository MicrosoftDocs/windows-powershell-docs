---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Enable-VMIntegrationService
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5BB80A43-60A6-41D1-B249-FFE7C4C8C3C9
---

# Enable-VMIntegrationService

## SYNOPSIS
Enables an integration service on a virtual machine.

## SYNTAX

### VMName (Default)
```
Enable-VMIntegrationService [-Name] <String[]> [-VMName] <String[]> [-Passthru] [-ComputerName <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMIntegrationService
```
Enable-VMIntegrationService [-VMIntegrationService] <VMIntegrationComponent[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMObject
```
Enable-VMIntegrationService [-Name] <String[]> [-VM] <VirtualMachine[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
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
Specifies the name of the integration service to be enabled.

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
Specifies that a **Microsoft.HyperV.PowerShell.IntegrationService** object is to be passed through to the pipeline representing the integration service to be enabled.

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
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMIntegrationService
Specifies the integration service to be enabled.

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
Specifies the name of the virtual machine on which the integration service is to be enabled.

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

