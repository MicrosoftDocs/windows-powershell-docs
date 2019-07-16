---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-PhysicalExtentAssociation
ms.reviewer:
ms.assetid: 7E63F10C-7D79-46AC-B1A8-41D71D9D43E1
---

# Get-PhysicalExtentAssociation

## SYNOPSIS
Gets the physical disk, storage tier, or virtual disk that is associated with a physical extent.

## SYNTAX

```
Get-PhysicalExtentAssociation -InputObject <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PhysicalExtentAssociation** cmdlet gets the physical disk, storage tier, or virtual disk that is associated with a physical extent.

## EXAMPLES

### Example 1: Get a physical extent association for a physical extent
```
PS C:\>Get-PhysicalExtent -PhysicalDisk (Get-PhysicalDisk -FriendlyName "PhysicalDisk4") | Select-Object -Last 1 | Get-PhysicalExtentAssociation
```

This command uses **Get-PhysicalExtent** to get all physical extents on the physical disk named PhysicalDisk4.
The command passes them to the Select-Object cmdlet by using the pipeline operator.
That common Windows PowerShell cmdlet selects the last physical extent returned.
That physical extent is passed to the current cmdlet, which gets its physical extent association.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PhysicalExtent
You can pass a **PhysicalExtent** object to this cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
This cmdlet returns a **PhysicalDisk** object, if the physical extent is associated with a physical disk.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
This cmdlet returns a **StorageTier** object, if the physical extent is associated with a storage tier.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
This cmdlet returns a **VirtualDisk** object, if the physical extent is associated with a virtual disk.

## NOTES

## RELATED LINKS

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-PhysicalExtent](./Get-PhysicalExtent.md)

