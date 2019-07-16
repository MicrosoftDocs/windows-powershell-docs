---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-VHD
ms.reviewer:
ms.assetid: F7C23CF5-FF0B-4D31-B4FA-967409F153D9
---

# Get-VHD

## SYNOPSIS
Gets the virtual hard disk object associated with a virtual hard disk.

## SYNTAX

### Path (Default)
```
Get-VHD [-Path] <String[]> [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

### Disk
```
Get-VHD [-DiskNumber] <UInt32> [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

### VMId
```
Get-VHD [-VMId] <Guid[]> [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VHD** cmdlet gets the virtual hard disk object associated with a virtual hard disk.

## EXAMPLES

### Example 1
```
PS C:\> Get-VHD -Path c:\test\testvhdx.vhdx
```

Gets the virtual hard disk where the path to the virtual hard disk file is c:\test\testvhdx.vhdx.

### Example 2
```
PS C:\> Get-VHD -DiskNumber 6
```

Gets the virtual hard disk attached to the system with disk number 6.

### Example 3
```
PS C:\> Get-VM -VMName TestVM | Select-Object VMId | Get-VHD
```

Gets the virtual hard disk objects associated with virtual machine TestVM, using the pipeline feature for the VMId parameter.

### Example 4
```
PS C:\> Get-VM -VMName testvm | Select-Object vmid | Get-VHD
```

Gets the virtual hard disk objects associated with virtual machine testvm using the pipeline feature for the path parameter.

### Example 5
```
PS C:\> Get-ChildItem c:\test -Recurse |% {$_.FullName} | Get-VHD -ErrorAction SilentlyContinue
```

Gets the virtual hard disk object for all the virtual hard disk files that are contained in the specified directory and its subdirectories.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual hard disk is to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number associated with the virtual hard disk to be retrieved.

```yaml
Type: UInt32
Parameter Sets: Disk
Aliases: Number

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to the virtual hard disk file of the virtual hard disk to be retrieved.
If a filename or relative path is specified, the path is calculated relative to the current working directory.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMId
Specifies the virtual machine identifier of the virtual machine whose virtual hard disks are to be retrieved.

```yaml
Type: Guid[]
Parameter Sets: VMId
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Vhd.PowerShell.VirtualHardDisk

## NOTES

## RELATED LINKS

