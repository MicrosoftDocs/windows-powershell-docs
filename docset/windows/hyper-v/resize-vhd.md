---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: kenwith
author: kenwith
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
title: Resize-VHD
ms.reviewer:
ms.assetid: 958902EA-0FBB-474D-82BD-4FA8B44017F2
---

# Resize-VHD

## SYNOPSIS
Resizes a virtual hard disk.

## SYNTAX

### Size (Default)
```
Resize-VHD [-Path] <String[]> [-SizeBytes] <UInt64> [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MinimumSize
```
Resize-VHD [-Path] <String[]> [-ToMinimumSize] [-AsJob] [-Passthru] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resize-VHD** cmdlet resizes a virtual hard disk.
This cmdlet lets you shrink or expand the size of a virtual hard disk, but the shrink operation is allowed only on VHDX virtual hard disks.
The shrink operation fails if it would shrink the virtual disk to less than its minimum size (available through the VHDX object's **MinimumSize** property).

**Resize-VHD** is an offline operation; the virtual hard disk must not be attached when the operation is initiated.

## EXAMPLES

### Example 1
```
PS C:\> Resize-VHD -Path c:\BaseVHD.vhd -SizeBytes 1TB
```

Expands the VHDX to 1 terabyte (assuming that the previous size was less than the new size prior to the command).

### Example 2
```
PS C:\> Resize-VHD -Path c:\BaseVHDX.vhdx -SizeBytes 1TB
```

Shrinks the VHDX to one terabyte (assuming that the virtual hard disk object associated with the file path has a **MinimumSize** less than or equal to 1TB).

### Example 3
```
PS C:\> Resize-VHD -Path c:\BaseVHDX.vhdx -ToMinimumSize
```

Shrinks the VHDX to its minimum possible size.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.

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
Specifies one or more Hyper-V hosts on which a virtual hard disk is to be resized.
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

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual hard disk to be resized.

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

### -Path
Specifies the path to the virtual hard disk that is to be resized.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SizeBytes
Specifies the size to which the virtual hard disk is to be resized.

```yaml
Type: UInt64
Parameter Sets: Size
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToMinimumSize
Specifies that the virtual hard disk is to be resized to its minimum possible size.

```yaml
Type: SwitchParameter
Parameter Sets: MinimumSize
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
