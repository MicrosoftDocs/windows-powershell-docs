---
external help file: StorageEnclosure.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Disable-StorageEnclosureIdentification
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9E1E84BE-96CA-49D9-9748-D3B90EF01267
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-StorageEnclosureIdentification

## SYNOPSIS
Turns off the identification LED on a storage enclosure or the slots for individual disks.

## SYNTAX

### ByFriendlyName (Default)
```
Disable-StorageEnclosureIdentification [-FriendlyName] <String[]> [-SlotNumbers <UInt32[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByUniqueId
```
Disable-StorageEnclosureIdentification -UniqueId <String[]> [-SlotNumbers <UInt32[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disable-StorageEnclosureIdentification -InputObject <CimInstance[]> [-SlotNumbers <UInt32[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-StorageEnclosureIdentification** cmdlet turns off the identification LED on the specified storage enclosure and, optionally, on the slots for individual disks.
Administrators typically use LEDs to locate a physical disk in an enclosure for removal or replacement.
This cmdlet requires a storage enclosure that supports SCSI Enclosure Services (SES).

## EXAMPLES

### Example 1: Disable identification of an enclosure
```
PS C:\>Disable-StorageEnclosureIdentification -FriendlyName "E11"
```

This command disables identification for the enclosure named E11.

### Example 2: Disable identification of specified slot numbers
```
PS C:\>Disable-StorageEnclosureIdentification -FriendlyName "E11" -SlotNumbers @(20, 14)
```

This command disables identification for the slots numbers 20 and 14 of the enclosure named E11.

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
This cmdlet turns off the identification LEDs for the enclosures that the names specify or for slots that belong to the specified enclosures.

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
This cmdlet turns off the identification LEDs for the enclosures that the objects specify or for slots that belong to the specified enclosures.
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

### -PassThru
Returns an array of **StorageEnclosure** objects.
By default, this cmdlet does not generate any output.

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

### -SlotNumbers
Specifies an array of slot numbers.
This cmdlet turns off the identification LEDs for the slots that the numbers identify.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
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
This cmdlet turns off the identification LEDsfor the enclosures that the IDs specify or for slots that belong to the specified enclosures.

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

### MSFT_StorageEnclosure[]
This cmdlet does not generate any output.
If you specify the **Passthru** parameter, the cmdlet returns an array of **MSFT_StorageEnclosure** objects.

## NOTES

## RELATED LINKS

[Enable-StorageEnclosureIdentification](./Enable-StorageEnclosureIdentification.md)

[Get-StorageEnclosure](./Get-StorageEnclosure.md)

[Get-StorageEnclosureVendorData](./Get-StorageEnclosureVendorData.md)

