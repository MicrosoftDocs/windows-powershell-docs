---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageProvider.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-storageprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageProvider
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
Specify a value of Manual for the *RemoteSubsystemCacheMode* parameter to enable caching.
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
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Specifies the input object that is used in a pipeline command.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can use the pipeline operator to pass one or more MSFT_StorageProvider objects to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
If you use the *PassThru* parameter, this cmdlet outputs an object that represents the storage provider for which you changed settings

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

[Get-StorageProvider](./Get-StorageProvider.md)

[New-VirtualDisk](./New-VirtualDisk.md)

