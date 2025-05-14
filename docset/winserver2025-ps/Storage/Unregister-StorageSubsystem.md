---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageProvider.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/unregister-storagesubsystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-StorageSubsystem
---

# Unregister-StorageSubsystem

## SYNOPSIS
Disconnects from storage subsystems on a remote computer.

## SYNTAX

### ByName (Default)
```
Unregister-StorageSubsystem [-ProviderName] <String[]> [-StorageSubSystemUniqueId <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByUniqueId
```
Unregister-StorageSubsystem -ProviderUniqueId <String[]> [-StorageSubSystemUniqueId <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Unregister-StorageSubsystem -InputObject <CimInstance[]> [-StorageSubSystemUniqueId <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-StorageSubsystem** cmdlet disconnects storage management in Windows Server® 2012 R2 from storage subsystems on a remote computer or remote cluster.
When you disconnect from a storage subsystem, you cannot use the management node to remotely manage the storage subsystem.

## EXAMPLES

### Example 1: Disconnect from storage subsystems on a remote computer
```
PS C:\> Unregister-StorageSubsystem -ProviderName "Provider16"
```

This command disconnects Windows Server® 2012 from the storage subsystems that the storage provider named Provider16 manages on the remote computer.

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

### -Force
Forces the command to run without asking for user confirmation.

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
The cmdlet disconnects from the storage subsystems that are managed by the storage provider that you specify.

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
The cmdlet disconnects from the storage subsystems that are managed by the storage provider that you specify.
Windows Server® 2012 retains the provider ID through computer restarts.

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

### -StorageSubSystemUniqueId
Specifies the unique ID of the storage subsystem in the system.
The cmdlet disconnects from the storage subsystem that you specify.
Windows Server® 2012 retains the storage subsystem ID through computer restarts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: UniqueId

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageProvider
You can use the pipeline operator to pass an array of MSFT_StorageProvider objects to the *InputObject* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can use the pipeline operator to pass an MSFT_StorageSubsystem object to this cmdlet, which maps the UniqueID property by name to the *StorageSubsystemUniqueID* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
If you specify the *PassThru* parameter, this cmdlet returns an object that represents the storage providers that you disconnected.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Register-StorageSubsystem](./Register-StorageSubsystem.md)

