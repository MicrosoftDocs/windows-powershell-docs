---
external help file: StorageProvider.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Set-StorageProvider
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A21E382D-B98C-416F-98D0-116229E27106
ms.author: kenwith
ms.reviewer: brianlic
---

# Set-StorageProvider

## SYNOPSIS
Modifies whether to enable the SMP provider cache.

## SYNTAX

### ByName (Default)
```
Set-StorageProvider [-ProviderName] <String[]> [-RemoteSubsystemCacheMode <RemoteSubsystemCacheMode>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByUniqueId
```
Set-StorageProvider -ProviderUniqueId <String[]> [-RemoteSubsystemCacheMode <RemoteSubsystemCacheMode>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-StorageProvider -InputObject <CimInstance[]> [-RemoteSubsystemCacheMode <RemoteSubsystemCacheMode>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageProvider** cmdlet modifies whether to enable the symmetric multiprocessing (SMP) provider cache.
Specify a value of Manual for the **RemoteSubsystemCacheMode** parameter to enable caching.
If you enable the cache on the management node that manages storage on remote computers or clusters, the management node caches remote objects.
This caching can improve enumeration operations, such as the Get-StoragePool cmdlet or the New-VirtualDisk cmdlet.

## EXAMPLES

### Example 1: Enable caching for a provider
```
PS C:\>Set-StorageProvider -ProviderName "Provider87" -RemoteSubSystemCacheMode Manual
```

This command enables caching for a provider.

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

### -PassThru
Returns an object representing the item with which you are working.
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

### -ProviderName
Specifies an array of names of providers.
The cmdlet modifies the providers that you specify.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProviderUniqueId
Specifies an array of unique IDs of providers.
The cmdlet modifies the providers that you specify.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: ProviderId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoteSubsystemCacheMode
Specifies the cache mode for a remote subsystem.
The acceptable values for this parameter are:

- Disable 
- Manual

```yaml
Type: RemoteSubsystemCacheMode
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, ManualDiscovery

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can use the pipeline operator to pass one or more MSFT_StorageProvider objects to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
If you use the **Passthru** parameter, this cmdlet outputs an object that represents the storage provider for which you changed settings

## NOTES

## RELATED LINKS

[Get-StorageProvider](./Get-StorageProvider.md)

[Get-StoragePool](./Get-StoragePool.md)

[New-VirtualDisk](./New-VirtualDisk.md)

