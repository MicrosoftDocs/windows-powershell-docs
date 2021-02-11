---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VMSan
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 921570C5-850F-45CA-A32F-4019AAD2EFB7
---

# Remove-VMSan

## SYNOPSIS
Removes a virtual storage area network (SAN) from a Hyper-V host.

## SYNTAX

```
Remove-VMSan [-ComputerName <String[]>] [-Name] <String[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMSan** cmdlet removes a virtual storage area network (SAN) from a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\> Remove-VMSan -Name Production
```

Removes the virtual storage area network named Production from the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies a Hyper-V host from which the virtual storage area network (SAN) is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual storage area network (SAN) to be removed from the Hyper-V host.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: SanName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the removed virtual machine storage area network.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.Powershell.VMSan** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

