---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/get-uevtemplateprogram?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UevTemplateProgram
---

# Get-UevTemplateProgram

## SYNOPSIS
Gets the information about programs defined by a settings location template.

## SYNTAX

```
Get-UevTemplateProgram [-ID] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-UevTemplateProgram** cmdlet gets the information about programs defined by a settings location template.
Microsoft User Experience Virtualization (UE-V) monitors each program that is defined in the template for changes to the settings.

## EXAMPLES

### Example 1: Get all defined programs
```
PS C:\> Get-UevTemplate | Get-UevTemplateProgram | Format-Table -AutoSize


TemplateId                          ProgramName      ProductVersionRange FileVersionRange
----------                          -----------      ------------------- ----------------
MicrosoftCalculator6                CALC.EXE         6-6
MicrosoftNotepad6                   NOTEPAD.EXE      6-6
MicrosoftOffice2010.OneNote         ONENOTE.EXE      14.0-14.0           14.0-14.0
MicrosoftOffice2010.Word            WINWORD.EXE      14.0-14.0           14.0-14.0
MicrosoftOffice2010.Excel           EXCEL.EXE        14.0-14.0           14.0-14.0
MicrosoftOffice2010.PowerPoint      POWERPNT.EXE     14.0-14.0           14.0-14.0
MicrosoftOffice2010.Outlook         OUTLOOK.EXE      14.0-14.0           14.0-14.0
MicrosoftOffice2010.InfoPath        INFOPATH.EXE     14.0-14.0           14.0-14.0
MicrosoftOffice2010.Visio           VISIO.EXE        14.0-14.0           14.0-14.0
MicrosoftOffice2010.Groove          Groove.exe       14.0-14.0           14.0-14.0
MicrosoftOffice2010.Access          MSACCESS.EXE     14.0-14.0           14.0-14.0
MicrosoftOffice2010.Project         WINPROJ.EXE      14.0-14.0           14.0-14.0
MicrosoftOffice2010.Publisher       MSPUB.EXE        14.0-14.0           14.0-14.0
MicrosoftWordpad6                   WORDPAD.EXE      6-6
MicrosoftInternetExplorer.Version8  iexplore.exe     8.0-8.0             8.0-8.0
MicrosoftInternetExplorer.Version9  iexplore.exe     9.0-9.0             9.0-9.0
MicrosoftInternetExplorer.Version10 iexplore.exe     10.0-10.0           10.0-10.0
MicrosoftLync2010                   communicator.exe 4.0-4.0             4.0-4.0
```

This command gets the defined programs for all of the registered settings location templates.
The command uses the **Get-UevTemplate** cmdlet to get the template that is stored on the computer, and passes the output to the **Get-UevTemplateProgram** cmdlet by using the pipeline operator.
The command then passes the results to the **Format-Table** cmdlet by using the pipeline operator.
For more information, type `Get-Help Format-Table`.

### Example 2: Get all defined programs for Office applications
```
PS C:\> Get-UevTemplate -Application "office" | Get-UevTemplateProgram | Format-Table -AutoSize


TemplateId                     ProgramName  ProductVersionRange FileVersionRange
----------                     -----------  ------------------- ----------------
MicrosoftOffice2010.OneNote    ONENOTE.EXE  14.0-14.0           14.0-14.0
MicrosoftOffice2010.Word       WINWORD.EXE  14.0-14.0           14.0-14.0
MicrosoftOffice2010.Excel      EXCEL.EXE    14.0-14.0           14.0-14.0
MicrosoftOffice2010.PowerPoint POWERPNT.EXE 14.0-14.0           14.0-14.0
MicrosoftOffice2010.Outlook    OUTLOOK.EXE  14.0-14.0           14.0-14.0
MicrosoftOffice2010.InfoPath   INFOPATH.EXE 14.0-14.0           14.0-14.0
MicrosoftOffice2010.Visio      VISIO.EXE    14.0-14.0           14.0-14.0
MicrosoftOffice2010.Groove     Groove.exe   14.0-14.0           14.0-14.0
MicrosoftOffice2010.Access     MSACCESS.EXE 14.0-14.0           14.0-14.0
MicrosoftOffice2010.Project    WINPROJ.EXE  14.0-14.0           14.0-14.0
MicrosoftOffice2010.Publisher  MSPUB.EXE    14.0-14.0           14.0-14.0
```

This command gets the defined programs for the registered settings location templates of Office applications.
The command uses the **Get-UevTemplate** cmdlet to get the Office applications that are defined on the computer, and passes the output to the **Get-UevTemplateProgram** cmdlet by using the pipeline operator.
The command then passes the results to the **Format-Table** cmdlet by using the pipeline operator.
For more information, type `Get-Help Format-Table`.

### Example 3: Get all defined programs by template ID
```
PS C:\> Get-UevTemplateProgram -TemplateId "MicrosoftCalculator6" | Format-Table -AutoSize
TemplateId           ExecutableName VersionRangeList
----------           -------------- ----------------
MicrosoftCalculator6 CALC.EXE       6-6
```

This command gets the defined programs for the settings location template whose ID is MicrosoftCalculator6.
The command uses the **Get-UevTemplateProgram** cmdlet to get the application that is identified by the ID MicrosoftCalculator6.
The command then passes the results to the **Format-Table** cmdlet by using the pipeline operator.
For more information, type `Get-Help Format-Table`.

## PARAMETERS

### -ID
Specifies the ID of a settings location template.
A settings location template stores the location of files and registry keys that contain application settings.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TemplateID

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
The settings location template ID.

## OUTPUTS

### Microsoft.UEV.Commands.Process
This cmdlet generates an object that contains general information about a program defined in a settings location template, such as the program name and the range of the versions to monitor.

## NOTES
* UE-V can define multiple programs for a single application in the settings location template.

## RELATED LINKS

[Get-UevTemplate](./Get-UevTemplate.md)

