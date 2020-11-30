---
external help file: StorageEnclosure.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Get-StorageEnclosureVendorData
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 3520523A-5EFA-4D71-ADDA-F6F3DFB88271
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-StorageEnclosureVendorData

## SYNOPSIS
Gets vendor-specific data for an enclosure.

## SYNTAX

### ByFriendlyName (Default)
```
Get-StorageEnclosureVendorData [-FriendlyName] <String[]> -PageNumber <UInt16> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageEnclosureVendorData -UniqueId <String[]> -PageNumber <UInt16> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-StorageEnclosureVendorData -InputObject <CimInstance[]> -PageNumber <UInt16> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageEnclosureVendorData** cmdlet gets vendor-specific data for a storage enclosure.
Specify the enclosure and the SCSI diagnostic page code for the data.

## EXAMPLES

### Example 1: Get information for an enclosure
```
PS C:\>Get-StorageEnclosureVendorData -FriendlyName "E11" -PageNumber 0x2
```

This command gets vendor data for the enclosure named E11.
The cmdlet specifies SCSI diagnostic page code 0x2.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies an array of friendly names.
This cmdlet gets vendor data for the enclosures that the names specify.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies an array of storage enclosures as **CimInstance** objects.
This cmdlet gets vendor data for the specified enclosures.
To obtain a storage enclosure object, use the Get-StorageEnclosure cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PageNumber
Specifies the SCSI diagnostic page code for which this cmdlet gets vendor-specific information.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies an array of IDs.
This cmdlet gets vendor data for the enclosures that the IDs specify.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String[]

## NOTES

## RELATED LINKS

[Get-StorageEnclosure](./Get-StorageEnclosure.md)

[Disable-StorageEnclosureIdentification](./Disable-StorageEnclosureIdentification.md)

[Enable-StorageEnclosureIdentification](./Enable-StorageEnclosureIdentification.md)

