---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/select-wssmountvhd?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Select-WssMountVhd

## SYNOPSIS
Selects a VHD from a backup set to mount for a file restore operation.

## SYNTAX

```
Select-WssMountVhd [-BackupSet] <BackupSet> [-Vhd] <MountVhdData>
```

## DESCRIPTION
The **Select-WssMoundVhd** cmdlet selects a virtual hard drive (VHD) from a backup set to mount for a file restore operation.
Each VHD represents a backup volume in the set.

## EXAMPLES

### Example 1: Select a VHD for a restore operation
```
PS C:\> Select-WssMountVhd -BackupSet $ContosoBU122412 -Vhd $ContosoVHD122412
```

This command selects the backup set that is stored in the variable named $ContosoBU122412 from the VHD that is stored in the variable named $ContosoVHD122412.

## PARAMETERS

### -BackupSet
Specifies the backup set from which to restore files.

```yaml
Type: BackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Vhd
Specifies the VHD to mount.

```yaml
Type: MountVhdData
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMountVhd](./Get-WssMountVhd.md)

