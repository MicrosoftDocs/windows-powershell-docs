---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FileStorageTier.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/set-filestoragetier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FileStorageTier
---

# Set-FileStorageTier

## SYNOPSIS
Assigns a file to a storage tier.

## SYNTAX

### ByDesiredStorageTierFriendlyName (Default)
```
Set-FileStorageTier -FilePath <String> -DesiredStorageTierFriendlyName <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDesiredStorageTier
```
Set-FileStorageTier -FilePath <String> -DesiredStorageTier <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDesiredStorageTierUniqueId
```
Set-FileStorageTier -FilePath <String> -DesiredStorageTierUniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-FileStorageTier** cmdlet assigns a file to a specified storage tier.
Assigning a file to a tier is also called pinning the file to a tier.
To pin a file to a storage tier, the file must be on a volume that is hosted by the same tiered storage space.
If you pin a file that is already assigned to a different tier, the file changes assignment the next time tier optimization takes place.

## EXAMPLES

### Example 1: Pin a file to a storage tier
```
PS C:\> $StorageTier = Get-StorageTier -FriendlyName "Tier07"
PS C:\> Set-FileStorageTier -DesiredStorageTier $StorageTier -FilePath "D:\DataFile06.txt"
```

The first command uses the Get-StorageTier cmdlet to get a storage tier named Tier07, and then stores the tier in the **$StorageTier** variable.

The second command pins the specified file to a storage tier.
The command specifies the storage tier by using the object stored in the **$StorageTier** variable.

### Example 2: Pin a file to a storage tier by using an ID
```
PS C:\> $StorageTier = Get- StorageTier -FriendlyName "Tier07"
PS C:\> Set-FileStorageTier -DesiredStorageTierUniqueId $StorageTier.UniqueId -FilePath "D:\DataFile06.txt"
```

The first command uses the Get-StorageTier cmdlet to get a storage tier named Tier07, and then stores the tier in the **$StorageTier** variable.

The second command pins the specified file to a storage tier.
The command specifies the ID of the storage tier by using the **UniqueID** property of the storage tier object stored in the **$StorageTier** variable.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DesiredStorageTier
Specifies the storage tier, as a **CimInstance** object, to pin a file to.
To obtain a storage tier object, use the Get-StorageTier cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDesiredStorageTier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DesiredStorageTierFriendlyName
Specifies the friendly name of a storage tier to pin a file to.

```yaml
Type: String
Parameter Sets: ByDesiredStorageTierFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DesiredStorageTierUniqueId
Specifies the unique ID, as a string, of a storage tier to pin a file to.

```yaml
Type: String
Parameter Sets: ByDesiredStorageTierUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath
Specifies the full path of a file.
The cmdlet pins the file that you specify to a storage tier.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier

You can use the pipeline operator to pass an MSFT_StorageTier object to the *DesiredStorageTier* parameter.

## OUTPUTS

### None

By default, this cmdlet doesn't return any output.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Clear-FileStorageTier](./Clear-FileStorageTier.md)

[Get-FileStorageTier](./Get-FileStorageTier.md)

[Get-StorageTier](./Get-StorageTier.md)
