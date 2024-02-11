---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HardenedFabric.Cmdlets.dll-Help.xml
Module Name: ShieldedVMTemplate
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/shieldedvmtemplate/protect-templatedisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-TemplateDisk
---

# Protect-TemplateDisk

## SYNOPSIS
Prepares a signed template disk (.VHDX) which can be used to provision new shielded virtual machines.

## SYNTAX

### SpecifyVolumeNameAndVersion (Default)
```
Protect-TemplateDisk -Path <String> -TemplateName <String> -Version <Version> -Certificate <X509Certificate2>
 [-ProtectedTemplateTargetDiskType <ProtectedTemplateTargetDiskType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PopulateFrom
```
Protect-TemplateDisk -Path <String> -PopulateFrom <String> [-TemplateName <String>] [-Version <Version>]
 -Certificate <X509Certificate2> [-ProtectedTemplateTargetDiskType <ProtectedTemplateTargetDiskType>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SpecializedDiskParameterSet
```
Protect-TemplateDisk -Path <String> [-DiskIsAlreadySpecialized] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Protect-TemplateDisk** cmdlet prepares a virtual hard disk to be used for provisioning shielded virtual machines.
The virtual hard disk must use the VHDX format and contain a generalized OS image.
The VHDX will be modified in place, and can only be used with shielded virtual machines after the process is complete.

## EXAMPLES

### Example 1: Prepare a template disk by populating existing values
```
PS C:\>Protect-TemplateDisk -Certificate $certificate -PopulateFrom "ExistingPreparedTemplate.vhdx" -Path "NewTemplate.vhdx" -TemplateName "Windows Server 2016"
```

This command prepares the .vhdx that the *Path* specifies.
The command uses the version information from ExistingPreparedTemplate.vhdx.
The command specifies the template name "Windows Server 2016".

### Example 2: Prepare a template disk by specifying name and version
```
PS C:\>Protect-TemplateDisk -Certificate $certificate -Path "WindowsServer2016-ShieldedTemplate.vhdx" -TemplateName "Windows Server 2016" -Version 1.0.0.0
```

This command prepares the .vhdx that the *Path* specifies.
The command uses the name and version information specified by the *TemplateName* and *Version* parameters.

## PARAMETERS

### -Certificate
Specifies the certificate used to sign metadata including the disk name, version, and hash calculated during the preparation process.
The specified certificate must have a private key installed on the local machine.

```yaml
Type: X509Certificate2
Parameter Sets: SpecifyVolumeNameAndVersion, PopulateFrom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskIsAlreadySpecialized
Indicates the disk has already been prepared as a signed template disk, but its contents have since changed.

```yaml
Type: SwitchParameter
Parameter Sets: SpecializedDiskParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to the template disk (.VHDX) to be prepared.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PopulateFrom
Specifies the path of a template disk that contains a previously published volume signature catalog.
The disk name, version, and certificate will be used as defaults for the new template disk.

```yaml
Type: String
Parameter Sets: PopulateFrom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectedTemplateTargetDiskType
Specifies the type of OS installed on the VHDX.

```yaml
Type: ProtectedTemplateTargetDiskType
Parameter Sets: SpecifyVolumeNameAndVersion, PopulateFrom
Aliases:
Accepted values: MicrosoftWindows, PreprocessedLinux

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateName
Specifies the name of the template.

```yaml
Type: String
Parameter Sets: SpecifyVolumeNameAndVersion
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: PopulateFrom
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies a value that uniquely identifies this version of the template.
The version value uses the form a.b.c.d, where each value is an integer less than 65536.

```yaml
Type: Version
Parameter Sets: SpecifyVolumeNameAndVersion
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Version
Parameter Sets: PopulateFrom
Aliases:

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Initialize-VMShieldingHelperVHD](./Initialize-VMShieldingHelperVHD.md)

