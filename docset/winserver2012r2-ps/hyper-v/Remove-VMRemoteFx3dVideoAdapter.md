---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VMRemoteFx3dVideoAdapter
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 2477E914-4CF4-4A90-9268-DF440FB6ADD5
---

# Remove-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Removes a RemoteFX 3D video adapter from a virtual machine.

## SYNTAX

### VMName (Default)
```
Remove-VMRemoteFx3dVideoAdapter [-ComputerName <String[]>] [-VMName] <String[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RemoteFXAdapter
```
Remove-VMRemoteFx3dVideoAdapter [-VMRemoteFx3dVideoAdapter] <VMRemoteFx3DVideoAdapter[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### VMObject
```
Remove-VMRemoteFx3dVideoAdapter [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMRemoteFx3dVideoAdapter** cmdlet removes a RemoteFX 3D video adapter from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMRemoteFx3dVideoAdapter -VMName TestVM1,TestVM2
```

Removes the RemoteFX adapter from virtual machines TestVM1 and TestVM2.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a RemoteFX 3D video adapter is to be removed.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **VMRemoteFxVideoAdapter** object is to be to be passed through to the pipeline representing the RemoteFX 3D video adapter to be removed.

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
Specifies the virtual machine from which the RemoteFX 3D video adapter to be removed.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the RemoteFX 3D video adapter is to be removed.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMRemoteFx3dVideoAdapter
Specifies the RemoteFX 3D video adapater to be removed.

```yaml
Type: VMRemoteFx3DVideoAdapter[]
Parameter Sets: RemoteFXAdapter
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
None by default; **VMRemoteFxVideoAdapter** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

