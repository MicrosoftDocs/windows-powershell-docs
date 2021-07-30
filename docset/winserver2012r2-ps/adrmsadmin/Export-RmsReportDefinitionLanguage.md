---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSAdmin
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adrmsadmin/export-rmsreportdefinitionlanguage?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-RmsReportDefinitionLanguage
---

# Export-RmsReportDefinitionLanguage

## SYNOPSIS
Exports all report definition (.rdl) files for this version of Active Directory Rights Management Services (AD RMS).

## SYNTAX

```
Export-RmsReportDefinitionLanguage [-ExportLocation] <String> [-Force] [-Path] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
HelpLongDescription This cmdlet exports the following report definition (.rdl) files for this version of Active Directory Rights Management Services (AD RMS).

Report_Health_MultiReport.rdl

Report_TroubleShooting_UserRequestSummary.rdl

Report_TroubleShooting_UserRequestTypeList.rdl

Report_TroubleShooting_UserRequestDetail.rdl

Report_TroubleShooting_UserRequestCertificateInfo.rdl

Report_TroubleShooting_AllILsFromCLC.rdl.rdl

Report_TroubleShooting_AllEULsFromIssuanceLicense.rdl

The file Report_TroubleShooting_DecryptILRightsLabel.rdl is not exported because it cannot be used by the SQL Server report service because it would require a private key.

To export the report definition files, specify the ExportLocation where you want the files to be saved and then set the Path parameter to the AD RMS provider drive subpath "\<PSDrive\>:\Report" where \<PSDrive\> is the provider drive ID.
You can also specify a relative path.
For example, "." specifies the current location.

## EXAMPLES

### --------------  EXAMPLE1 --------------
```
C:\PS>Export-RmsReportDefinitionLanguage path . -ExportLocation c:\temp\
```

This command exports the .rdl files to the directory c:\temp\.

## PARAMETERS

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

### -ExportLocation
Specifies the path of the exported file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.
For example, Force will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Get-RmsSystemHealthReport](./Get-RmsSystemHealthReport.md)

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

