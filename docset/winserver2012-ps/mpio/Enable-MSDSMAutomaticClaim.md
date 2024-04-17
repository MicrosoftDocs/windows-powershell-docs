---
external help file: MPIO_Cmdlets.xml
Module Name: MPIO
online version: https://learn.microsoft.com/powershell/module/mpio/enable-msdsmautomaticclaim?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-MSDSMAutomaticClaim

## SYNOPSIS
Enables MSDSM to automatically claim SAN disks for MPIO.

## SYNTAX

```
Enable-MSDSMAutomaticClaim [-BusType] <String>
```

## DESCRIPTION
The **Enable-MSDSMAutomaticClaim** cmdlet enables a Microsoft Device Specific Module (MSDSM) to automatically claim storage area network (SAN) disks for Microsoft Multipath I/O (MPIO) for a bus type.

You need to specify a valid bus type, either serial attached storage (SAS) and Internet Small Computer System Interface (iSCSI).
You can enable MSDSM to automatically claim both SAS and iSCSI disks.
Run the cmdlet twice, once for SAS, once for iSCSI.

## EXAMPLES

### Example 1: Enable automatic claims for iSCSI
```
PS C:\> Enable-MSDSMAutomaticClaim -BusType iSCSI
```

This command enables  MSDSM to automatically claim resources with an iSCSI bus type.
Specify SAS instead of iSCSI to enable for an SAS bus type.

## PARAMETERS

### -BusType
Specifies a bus type.
The cmdlet enables MSDSM to automatically SAN disks for this bus type.
The acceptable values for this parameter are: SAS and iSCSI.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-MSDSMAutomaticClaim](./Disable-MSDSMAutomaticClaim.md)

[Get-MSDSMAutomaticClaimSettings](./Get-MSDSMAutomaticClaimSettings.md)

