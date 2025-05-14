---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageProvider.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/register-storagesubsystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Register-StorageSubsystem
---

# Register-StorageSubsystem

## SYNOPSIS
Connects to storage subsystems on a remote computer.

## SYNTAX

### ByName (Default)
```
Register-StorageSubsystem [-ProviderName] <String[]> -ComputerName <String> [-Credential <PSCredential>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Register-StorageSubsystem -ProviderUniqueId <String[]> -ComputerName <String> [-Credential <PSCredential>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### InputObject (cdxml)
```
Register-StorageSubsystem -InputObject <CimInstance[]> -ComputerName <String> [-Credential <PSCredential>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Register-StorageSubsystem** cmdlet connects to storage subsystems on a remote computer or cluster.
In data centers and clustered environments, a management node manages storage on the remote computers.
From the management node, you must connect to the storage subsystems on the remote computer or cluster before you can manage storage on the remote computer.

## EXAMPLES

### Example 1: Register a storage subsystem on a remote computer
```
PS C:\> Register-StorageSubsystem -ProviderName "Storage Spaces Management Provider" -ComputerName "StorageCluster01"
```

This command registers the storage subsystem named Storage Spaces Management Provider  on the computer named StorageCluster01.

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

### -ComputerName
Specifies the name of a remote computer.
Specify the IP address or any value that resolves to an IP address, such as a fully qualified domain name (FQDN), host name, or NetBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object that contains the user credentials for the remote computer.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
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

### -ProviderName
Specifies an array of names of providers.
The cmdlet connects to the storage subsystems that are managed by the storage providers that you specify.

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
The cmdlet connects to the storage subsystems that are managed by the storage providers that you specify.

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
You can use the pipeline operator to pass an MSFT_StorageProvider object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
This cmdlet returns an MSFT_StorageSubsystem object.
You can use this object to perform storage management operations on the remote computer.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[Unregister-StorageSubsystem](./Unregister-StorageSubsystem.md)

