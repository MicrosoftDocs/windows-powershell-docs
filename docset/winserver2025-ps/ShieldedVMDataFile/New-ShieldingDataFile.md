---
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMDataFile
online version: https://learn.microsoft.com/powershell/module/shieldedvmdatafile/new-shieldingdatafile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ShieldingDataFile
---

# New-ShieldingDataFile

## SYNOPSIS
Creates a shielding data file.

## SYNTAX

### ShieldedTemplateParameterSet
```
New-ShieldingDataFile [-ShieldingDataFilePath] <String> [-Owner] <Guardian>
 [-VolumeIDQualifier] <VolumeIDQualifier[]> [-AnswerFile] <NamedFileContent>
 [[-OtherFile] <NamedFileContent[]>] [[-Guardian] <Guardian[]>] [-Policy <FabricPolicyValue>] [-WhatIf]
 [-Confirm]
```

### ExistingVMParameterSet
```
New-ShieldingDataFile [-ShieldingDataFilePath] <String> [-Owner] <Guardian> [[-OtherFile] <NamedFileContent[]>]
 [[-Guardian] <Guardian[]>] [-Policy <FabricPolicyValue>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The **New-ShieldingDataFile** cmdlet creates a shielding data file for use in provisioning a shielded virtual machine.
The shielding data file contains information about which fabrics the VM can run on, which template disks can be used, the security policy, and files such as the specialization answer file.

The specialization answer file and any additional files you add to the shielding data file will be encrypted until a shielded VM is provisioned.

## EXAMPLES

### Example 1
```
PS C:\> $owner = Get-HgsGuardian -Name Owner
PS C:\> $hoster = Get-HgsGuardian -Name MyHostingProvider
PS C:\> $viq = New-VolumeIDQualifier -VolumeSignatureCatalogFilePath 'C:\temp\trustedtemplate.vsc' -VersionRule Equals
PS C:\> New-ShieldingDataFile -ShieldingDataFilePath 'C:\temp\shieldingdata.pdk' -Owner $owner -Guardian $hoster -VolumeIDQualifier $viq -AnswerFile 'C:\temp\unattend.xml'
```

Creates a shielding data file using the "Owner" and "MyHostingProvider" guardians and a single volume ID qualifier representing the trusted template disk.

## PARAMETERS

### -AnswerFile
Path to an XML file containing specialization information needed to automatically set up the OS in a shielded VM.
For Windows VMs, this file is typically the unattend.xml file.
The file varies for Linux distributions based on the specialization agent installed in the template disk.

```yaml
Type: NamedFileContent
Parameter Sets: ShieldedTemplateParameterSet
Aliases: WindowsUnattendFile

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guardian
One or more HGS guardian objects representing fabrics trusted to run your virtual machine.

```yaml
Type: Guardian[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OtherFile
Additional files (limited to 384KB) that should be encrypted at rest and copied to a provisioned virtual machine.

```yaml
Type: NamedFileContent[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
The guardian object containing the certificates of the VM owner.
Only the VM owner can modify the shielding data file in the future.

```yaml
Type: Guardian
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Policy
Specifies the security policy for the resulting VM.
The EncryptionSupported policy allows all normal VM devices, while the shielded policy adds additional protections to the VM, prevents basic console access and requires live migration traffic to be encrypted.

```yaml
Type: FabricPolicyValue
Parameter Sets: (All)
Aliases:
Accepted values: Shielded, EncryptionSupported

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShieldingDataFilePath
Specifies the path where the newly created shielding data file should be saved.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeIDQualifier
One or more **VolumeIDQualifier** objects representing template disks trusted for shielded VM deployment.

```yaml
Type: VolumeIDQualifier[]
Parameter Sets: ShieldedTemplateParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Windows.HardenedFabric.Cmdlets.Common.Guardian
Microsoft.Windows.HardenedFabric.Cmdlets.Common.VolumeIDQualifier[]
Microsoft.Windows.HardenedFabric.Cmdlets.Common.NamedFileContent
Microsoft.Windows.HardenedFabric.Cmdlets.Common.NamedFileContent[]
Microsoft.Windows.HardenedFabric.Cmdlets.Common.Guardian[]
Microsoft.Windows.HardenedFabric.Cmdlets.Common.FabricPolicyValue


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

