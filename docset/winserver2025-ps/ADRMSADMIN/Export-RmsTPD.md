---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/export-rmstpd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-RmsTPD
---

# Export-RmsTPD

## SYNOPSIS
Exports a TPD in AD RMS.

## SYNTAX

```
Export-RmsTPD [-SavedFile] <String[]> [-Password] <SecureString> [-V1Compatible] [-Force] [-Path] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-RmsTPD** cmdlet exports a trusted publishing domain (TPD) in Active Directory Rights Management Services (AD RMS) to a file.

To perform the export, set the *SavedFilePath* parameter to the export file path, and then set the *Path* parameter to the AD RMS provider path `<PSDrive>:\TrustPolicy\TrustedPublishingDomain\<TPD_ID>` where `<PSDrive>` is the provider drive ID and `<TPD_ID>` is the ID of the TPD that you want to export.

## EXAMPLES

### Example 1: Export a TPD by ID
```
PS C:\> Export-RmsTPD -Path ".\100" -SavedFile "c:\temp\test.xml"
```

This command exports the TPD with the ID of 100 to the file C:\temp\test.xml.
Because the *Password* parameter is not specified, the command prompts for the password.

### Example 2: Read a password and use it to export a TPD
```
PS C:\> $pswd = Read-Host -AsSecureString
PS C:\> Export-RmsTPD -Path "100" -SavedFile "c:\temp\test.xml" -Password $pswd
```

The first command prompts for a password and saves it in the variable $pswd.
The variable is then passed to the **Export-RmsTPD** command as the *Password* parameter.
Note that the **Export-RmsTPD** command prompts for a confirmation password that must match the password stored in the $pswd variable.

### Example 3: Export a TPD without prompting for the password
```
PS C:\> $pswd=Read-Host -AsSecureString
PS C:\> Export-RmsTPD -Path "100" -SavedFile "c:\temp\test.xml" -Password $pswd -Force
```

The first command prompts for a password and saves it in the variable $pswd.
The variable is then passed to the **Export-RmsTPD** command as the *Password* parameter.
Because the *Force* parameter is specified, the **Export-RmsTPD** command does not prompt for a confirmation password.

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

### -Force
Overrides restrictions that prevent the command from succeeding if the restrictions do not compromise security.
For example, *Force* overrides the read-only attribute or creates directories to complete a file path, but it does not attempt to change file permissions.

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

### -Password
Specifies a password as a **SecureString** object.
To create a **SecureString** object that contains a password, use the Read-Host cmdlet and specify the *AsSecureString* parameter.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
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

### -SavedFile
Specifies the full path and filename of the file that receives the exported content.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -V1Compatible
Allows the trusted publishing domain to be imported to Windows Rights Management Services (RMS) 1.0.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Export-RmsTUD](./Export-RmsTUD.md)

[Import-RmsTPD](./Import-RmsTPD.md)

[Import-RmsTUD](./Import-RmsTUD.md)

