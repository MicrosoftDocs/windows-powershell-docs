---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-VMScsiController
ms.reviewer:
ms.assetid: AF092B6E-5F46-42E0-8A34-4A27E31608A3
---

# Get-VMScsiController

## SYNOPSIS
Gets the SCSI controllers of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMScsiController [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [[-ControllerNumber] <Int32>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMScsiController [-VMSnapshot] <VMSnapshot> [[-ControllerNumber] <Int32>] [<CommonParameters>]
```

### VMObject
```
Get-VMScsiController [[-ControllerNumber] <Int32>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMScsiController** cmdlet gets the SCSI controllers of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMScsiController -VMName TestVM -ControllerNumber 0
```

Gets SCSI controller 0 from virtual machine TestVM.

### Example 2
```
PS C:\> Get-VM -Name TestVM -ComputerName Development | Get-VMScsiController
```

Gets the SCSI controllers from virtual machine TestVM on Hyper-V host Development.

### Example 3
```
PS C:\> Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMScsiController
```

Gets the SCSI controllers from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the SCSI controllers are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -ControllerNumber
Specifies the number of the SCSI controller to be retrieved.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose SCSI controllers are to be retrieved.

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
Specifies the name of the virtual machine whose SCSI controllers are to be retrieved.

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

### -VMSnapshot
Specifies the snapshot whose SCSI controllers are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: VMCheckpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMScsiController

## NOTES

## RELATED LINKS

