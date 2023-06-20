---
external help file: StoragePool.cdxml-help.xml
Module Name: Storage
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/storage/new-storagetier?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StorageTier
---

# New-StorageTier

## SYNOPSIS
Creates a storage tier.

## SYNTAX

### ByFriendlyName (Default)
```
New-StorageTier [-StoragePoolFriendlyName] <String[]> -FriendlyName <String> -MediaType <MediaType>
 [-Description <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
New-StorageTier -StoragePoolUniqueId <String[]> -FriendlyName <String> -MediaType <MediaType>
 [-Description <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByName
```
New-StorageTier -StoragePoolName <String[]> -FriendlyName <String> -MediaType <MediaType>
 [-Description <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
New-StorageTier -InputObject <CimInstance[]> -FriendlyName <String> -MediaType <MediaType>
 [-Description <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-StorageTier** cmdlet creates a storage tier in a storage pool.

## EXAMPLES

### Example 1: Create a storage tier
```
PS C:\> New-StorageTier -StoragePoolFriendlyName "TierPool01" -FriendlyName "Tier11" -MediaType HDD
```

This command creates a storage tier for hard disk drives named Tier11 in the storage pool named TierPool01.

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

### -Description
Specifies a description for the storage tier that you create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for the storage tier.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageTierFriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -MediaType
Specifies the media type of the storage tier.
The cmdlet creates the storage tier for the media type that you specify.
The acceptable values for this parameter are:

- SSD
- HDD

```yaml
Type: MediaType
Parameter Sets: (All)
Aliases: 
Accepted values: HDD, SSD

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies an array of friendly names of storage pools.
The cmdlet creates the storage tier in the storage pools that you specify.

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

### -StoragePoolName
Specifies an array of names of storage pools.
The cmdlet creates the storage tier in the storage pools that you specify.
This human-readable name is not necessarily unique.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StoragePoolUniqueId
Specifies an array of unique IDs, as strings, of storage pools.
The cmdlet creates the storage tiers in the storage pools that have the IDs that you specify.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StoragePoolId

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can use the pipeline operator to pass a MSFT_StoragePool object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/storage/MSFT_StorageTier
This cmdlet outputs an object that represents the storage tier

## NOTES

## RELATED LINKS

[Get-StorageTier](./Get-StorageTier.md)

[Remove-StorageTier](./Remove-StorageTier.md)

[Resize-StorageTier](./Resize-StorageTier.md)

[Set-StorageTier](./Set-StorageTier.md)

