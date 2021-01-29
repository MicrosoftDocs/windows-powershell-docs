---
external help file: StorageTier.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Get-StorageTierSupportedSize
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 0538D68C-02C5-42D3-92FC-BE8DC7825730
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-StorageTierSupportedSize

## SYNOPSIS
Gets the minimum and maximum possible sizes of a storage tier.

## SYNTAX

### ByFriendlyName (Default)
```
Get-StorageTierSupportedSize [-FriendlyName] <String[]> [-ResiliencySettingName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-StorageTierSupportedSize -UniqueId <String[]> [-ResiliencySettingName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
Get-StorageTierSupportedSize -InputObject <CimInstance[]> [-ResiliencySettingName <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageTierSupportSize** cmdlet gets the minimum and maximum possible sizes of a storage tier.
Use this information to create or extend a virtual disk with the specified resiliency setting on a Storage Spaces subsystem.

## EXAMPLES

### Example 1: Get the size estimate for a mirror space
```
PS C:\> Get-StorageTierSupportedSize -FriendlyName "*SSD*" -ResiliencySettingName "Mirror" 
SupportedSizes                  TierSizeMin                  TierSizeMax                  TierSizeDivisor
--------------                  -----------                  -----------                  ---------------
{}                              4294967296                   2130303778816                4294967296
{}                              4294967296                   2130303778816                4294967296
```

This command gets the storage tier supported size estimates for capacity of a Fast (SSD) tier for a mirror space by using the **FriendlyName** and **ResiliencySettingName** parameters.

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
The cmdlet gets the storage tiers that match the names that you specify.

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
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -ResiliencySettingName
Specifies the name of the desired resiliency setting, for example, Simple, Mirror, or Parity.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies an array of unique IDs, as strings.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
You can use the pipeline operator to pass an MSFT_StorageTier object to the InputObject parameter to get the storage tier supported size associated with the StorageTier object.

## OUTPUTS

### System.Management.Automation.PSCustomObject
This cmdlet returns an object that lists the minimum and maximum amounts of space that the specified type of virtual disk could use in the specified storage tier as well as the tier size divisor.
These values are System.UInt64 objects.

## NOTES

## RELATED LINKS

