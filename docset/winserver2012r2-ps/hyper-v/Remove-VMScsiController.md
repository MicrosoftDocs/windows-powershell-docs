---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VMScsiController
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
ms.assetid: 8C311C2D-2885-4C2B-8500-F4C0F119D061
---

# Remove-VMScsiController

## SYNOPSIS
Removes a SCSI controller from a virtual machine.

## SYNTAX

### VMName (Default)
```
Remove-VMScsiController [-ComputerName <String[]>] [-VMName] <String[]> [-ControllerNumber] <Int32> [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-VMScsiController [-VMScsiController] <VMScsiController[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMScsiController** cmdlet removes a SCSI controller from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMScsiController -VMName TestVM -ControllerNumber 0 | Remove-VMScsiController
```

Deletes SCSI controller 0 from virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the SCSI controller is to be removed.
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

### -ControllerNumber
Specifies the number of the controller.
The cmdlet removes the SCSI controller that you specify.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMScsiController** object is to be passed through to the pipeline representing the SCSI controller to be removed.

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

### -VMName
Specifies an array of names of virtual machines.
The cmdlet removes an SCSI controller from the virtual machines that you specify.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMScsiController
Specifies the SCSI controller to be removed.

```yaml
Type: VMScsiController[]
Parameter Sets: Object
Aliases: 

Required: True
Position: 0
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
None by default; **VMScsiController** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

