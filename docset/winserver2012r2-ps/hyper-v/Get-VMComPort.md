---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmcomport?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMComPort
---

# Get-VMComPort

## SYNOPSIS
Gets the COM ports of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMComPort [-VMName] <String[]> [[-Number] <Int32>] [-ComputerName <String[]>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMComPort [-VMSnapshot] <VMSnapshot> [[-Number] <Int32>] [<CommonParameters>]
```

### VMObject
```
Get-VMComPort [[-Number] <Int32>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMComPort** cmdlet gets the COM ports of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMComPort TestVM
```

Gets all COM ports associated with virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMComPort TestVM -Number 2
```

Gets the second COM port associated with virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the COM ports of a virtual machine or snapshot are to be retrieved.
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

### -Number
Specifies the Id (1 or 2) of the COM ports to be retrieved.

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

### -VM
Specifies the virtual machine whose COM ports are to be retrieved.

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
Specifies the name of the virtual machine whose COM ports are to be retrieved.

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
Specifies the snapshot whose COM ports are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.ComPort

## NOTES

## RELATED LINKS

