---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/get-uevtemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UevTemplate
---

# Get-UevTemplate

## SYNOPSIS
Gets settings location templates for UE-V.

## SYNTAX

### ParameterSetNoParameter (Default)
```
Get-UevTemplate [<CommonParameters>]
```

### ParameterSetApplication
```
Get-UevTemplate -Application <String> [<CommonParameters>]
```

### ParameterSetTemplateID
```
Get-UevTemplate -TemplateID <String> [<CommonParameters>]
```

### ParameterProfile
```
Get-UevTemplate -Profile <String> [<CommonParameters>]
```

### ParameterSetApplicationOrTemplateID
```
Get-UevTemplate [-ApplicationOrTemplateID] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-UevTemplate** cmdlet gets settings location templates that are registered with Microsoft User Experience Virtualization (UE-V).
Use this cmdlet to display information which includes the template ID, template name, template version, template description, template type, and the state settings of the template.
The template ID includes a primary ID and a secondary ID.
Applications in the same suite share the same primary ID.

## EXAMPLES

### Example 1: Get all registered templates
```
PS C:\> Get-UevTemplate | Format-Table -AutoSize
TemplateId                                  TemplateName                                TemplateVersion PackageVersion TemplateType Enabled EnableStateLocation TemplateDescription
----------                                  ------------                                --------------- -------------- ------------ ------- ------------------- -------------------
DesktopSettings                             Desktop Settings                                          1 N/A            OS             False LocalMachine
MicrosoftNotepad6                           Microsoft Notepad                                         0 N/A            Application     True NotSet
MicrosoftCalculator6                        Microsoft Calculator                                      0 N/A            Application     True NotSet
MicrosoftCommunicator2007                   Microsoft Communicator 2007                               7 N/A            Application     True NotSet
MicrosoftOffice2010Win64                    Microsoft Office 2010 (64-bit)                           18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.common             Common Settings                                          18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.Access             Microsoft Access 2010 (64-bit)                           18 N/A            Application     True NotSet
```

This command gets all the settings location templates that are registered with UE-V, and then passes them to the **Format-Table** cmdlet by using the pipeline operator.
For more information, type `Get-Help Format-Table`.

### Example 2: Get registered templates that contain a specified string
```
PS C:\> Get-UevTemplate -ApplicationOrTemplateID "office" | Format-Table -AutoSize
TemplateId                                  TemplateName                                TemplateVersion PackageVersion TemplateType Enabled EnableStateLocation TemplateDescription
----------                                  ------------                                --------------- -------------- ------------ ------- ------------------- -------------------
MicrosoftOffice2010Win64                    Microsoft Office 2010 (64-bit)                           18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.common             Common Settings                                          18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.Access             Microsoft Access 2010 (64-bit)                           18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.Excel              Microsoft Excel 2010 (64-bit)                            18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.Groove             Microsoft Groove 2010 (64-bit)                           18 N/A            Application     True NotSet
MicrosoftOffice2010Win64.InfoPath           Microsoft InfoPath 2010 (64-bit)                         18 N/A            Application     True NotSet
```

This command gets settings location templates that are registered with UE-V, and passes them to **Format-Table** by using the pipeline operator.
This command specifies a value for the *ApplicationOrTemplateID* parameter.
The cmdlet gets the templates that have a name or template ID that includes the specified string.

### Example 3: Get registered templates that contain a specified string that includes a wildcard
```
PS C:\> Get-UevTemplate -ApplicationOrTemplateID "office*word" | Format-Table -AutoSize
TemplateId                    TemplateName                 TemplateVersion PackageVersion TemplateType Enabled EnableStateLocation TemplateDescription
----------                    ------------                 --------------- -------------- ------------ ------- ------------------- -------------------
MicrosoftOffice2010Win64.Word Microsoft Word 2010 (64-bit)              18 N/A            Application     True NotSet
```

This command gets settings location templates that are registered with UE-V, and passes them to **Format-Table** by using the pipeline operator.
This command specifies a value for the *ApplicationOrTemplateID* parameter that contains a wildcard.
The cmdlet gets the templates that have a name or template ID that includes the string office followed by the string word.

### Example 4: Get registered templates associated with the Backup profile
```
PS C:\>Get-UevTemplate -Profile Backup
TemplateId          : MicrosoftCalculator6

TemplateName        : Microsoft Calculator
TemplateDescription :
TemplateVersion     : 0
TemplateType        : Application
Enabled             : True
EnableStateLocation : NotSet
TemplateProfile     : Backup

TemplateId          : MicrosoftWordpad6

TemplateName        : Microsoft Wordpad

TemplateDescription :

TemplateVersion     : 0

TemplateType        : Application

Enabled             : True

EnableStateLocation : LocalUser

TemplateProfile     : Backup
```

This command gets settings location templates that are registered with UE-V and are associated with the Backup profile.

## PARAMETERS

### -Application
Specifies the name of an application.
The cmdlet gets templates that include the applications that you specify.
Use wildcards to specify a partial name.

```yaml
Type: String
Parameter Sets: ParameterSetApplication
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationOrTemplateID
Specifies an application name or a template ID.
The cmdlet gets templates that include the applications or IDs that you specify.
Use wildcards to specify partial names or IDs.

```yaml
Type: String
Parameter Sets: ParameterSetApplicationOrTemplateID
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the name of a profile.
The cmdlet gets all templates associated with the specified profile.
Valid values are:

- Roaming
- Backup

```yaml
Type: String
Parameter Sets: ParameterProfile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateID
Specifies the ID of a template.
The cmdlet gets templates that include the applications that you specify.
Use wildcards to specify partial IDs.

```yaml
Type: String
Parameter Sets: ParameterSetTemplateID
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.UEV.Commands.Template
This cmdlet generates a **Template** object that contains the general information about a settings location template, such as template ID, template name, and template version.

## NOTES

## RELATED LINKS

[Disable-UevTemplate](./Disable-UevTemplate.md)

[Enable-UevTemplate](./Enable-UevTemplate.md)

[Register-UevTemplate](./Register-UevTemplate.md)

[Set-UevTemplateProfile](./Set-UevTemplateProfile.md)

[Test-UevTemplate](./Test-UevTemplate.md)

[Unregister-UevTemplate](./Unregister-UevTemplate.md)

[Update-UevTemplate](./Update-UevTemplate.md)

