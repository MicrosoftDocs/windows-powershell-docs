---
external help file: StorageCmdlets.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Set-StorageTier
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 667677B8-CA32-4242-9E85-425EBBC4572F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-StorageTier

## SYNOPSIS
Modifies a storage tier.

## SYNTAX

### ByUniqueIdNewFriendlyName (Default)
```
Set-StorageTier [-NewFriendlyName <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectDescription
```
Set-StorageTier -InputObject <CimInstance[]> [-Description <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectMediaType
```
Set-StorageTier -InputObject <CimInstance[]> [-MediaType <MediaType>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectNewFriendlyName
```
Set-StorageTier -InputObject <CimInstance[]> [-NewFriendlyName <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameNewFriendlyName
```
Set-StorageTier [-NewFriendlyName <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameMediaType
```
Set-StorageTier [-MediaType <MediaType>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdMediaType
```
Set-StorageTier [-MediaType <MediaType>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByFriendlyNameDescription
```
Set-StorageTier [-Description <String>] [-FriendlyName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueIdDescription
```
Set-StorageTier [-Description <String>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageTier** cmdlet modifies a storage tier.
Use this cmdlet to change the name and description of a storage tier, and to change the media type that is associated with storage tier.

## EXAMPLES

### Example 1: Change the name of a storage tier
```
PS C:\> Set-StorageTier -UniqueId '{49dde1c4-5c34-11e2-8441-00155de88701}' -NewFriendlyName "FastTier"
```

This command changes the friendly name of the storage tier that has the specified ID.

### Example 2: Change the description of a storage tier
```
PS C:\> Get-StorageTier -FriendlyName "FastTier" | Set-StorageTier -Description "This tier denotes fast media in the system"
```

This command uses the Get-StorageTier cmdlet to get the storage tier named FastTier, and then passes the storage tier to the Set-StorageTier cmdlet by using the pipeline operator.
The **Set-StorageTier** cmdlet changes the description of the storage tier to the specified string.

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
Specifies a description for the storage tier.

```yaml
Type: String
Parameter Sets: ByObjectDescription, ByFriendlyNameDescription, ByUniqueIdDescription
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the storage tier to modify.

```yaml
Type: String
Parameter Sets: ByFriendlyNameNewFriendlyName, ByFriendlyNameMediaType, ByFriendlyNameDescription
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the **StorageTier** object to modify.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectDescription, ByObjectMediaType, ByObjectNewFriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MediaType
Specifies a media type for the storage tier.
The cmdlet changes the media type that is associated with the storage tier to the media type that you specify.
The acceptable values for this parameter are:

- SSD
- HDD

```yaml
Type: MediaType
Parameter Sets: ByObjectMediaType, ByFriendlyNameMediaType, ByUniqueIdMediaType
Aliases: 
Accepted values: HDD, SSD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewFriendlyName
Specifies a new friendly name for the storage tier.

```yaml
Type: String
Parameter Sets: ByUniqueIdNewFriendlyName, ByObjectNewFriendlyName, ByFriendlyNameNewFriendlyName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
Specifies the unique ID of the storage tier to modify.

```yaml
Type: String
Parameter Sets: ByUniqueIdNewFriendlyName, ByUniqueIdMediaType, ByUniqueIdDescription
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an array of MSFT_StorageTier objects to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
This cmdlet returns an MSFT_StorageTier object that contains details about the tier such as tier friendly name, media type and size.

## NOTES
* The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (#) provides the namespace and class name for the underlying WMI object.

## RELATED LINKS

[Get-StorageTier](./Get-StorageTier.md)

[New-StorageTier](./New-StorageTier.md)

[Remove-StorageTier](./Remove-StorageTier.md)

[Resize-StorageTier](./Resize-StorageTier.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)


