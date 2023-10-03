---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/add-wssdiskstospacespool?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WssDisksToSpacesPool

## SYNOPSIS
Adds physical disks to a storage pool.

## SYNTAX

```
Add-WssDisksToSpacesPool [-Pool] <SpacesPool> [-Disks] <ICollection<Disk>> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-WssDisksToSpacesPool** cmdlet adds physical disks to a storage pool.

## EXAMPLES

### Example 1: Add a physical disk to a storage pool
```
PS C:\>$Disk = Get-WssDisk -ID "26a21bda-a627-11d7-9931-806e6f6e6963" PS C:\>$Pool = Get-WssSpacesPool -ID "13c41bda-a627-22d7-4631-806e6f6e6963" PS C:\> Add-WssDisksToSpacesPool -Disks $Disk -Pool $Pool
```

The first command gets the Disk object that has the ID 26a21bda-a627-11d7-9931-806e6f6e6963, and stores it in the **$Disk** variable.

The second command gets the storage pool that has the ID 13c41bda-a627-22d7-4631-806e6f6e6963, and stores it in the **$Pool** variable.

The third command adds the physical disk stored in the **$Disk** variable to the storage pool stored in the **$Pool** variable.

## PARAMETERS

### -Disks
Specifies the physical disks to add to the storage pool.

```yaml
Type: ICollection<Disk>
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -Pool
Specifies a **StoragePool** object.
To obtain a **StoragePool** object, use theGet-WssSpacesPool cmdlet.

```yaml
Type: SpacesPool
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssSpacesPool](./Get-WssSpacesPool.md)

[Get-WssDisk](./Get-WssDisk.md)

[Get-WssSpacesPool](./Get-WssSpacesPool.md)

