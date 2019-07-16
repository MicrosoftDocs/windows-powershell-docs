---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
ms.assetid: 40463418-5B82-42E6-86E0-396B31E01EA8
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Import-RmsTPD

## SYNOPSIS
Imports a trusted publishing domain (TPD) from a file in Active Directory Rights Management Services (AD RMS).

## SYNTAX

```
Import-RmsTPD [-DisplayName] <String> [-SourceFile] <String> [-Password] <SecureString> [-Force] [-PassThru]
 [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Import-RmsTPD cmdlet imports a trusted publishing domain from a file in Active Directory Rights Management Services (AD RMS).

To perform the import, specify the DisplayName, SourceFile and Password parameters, and then set the Path parameter to the AD RMS provider drive subpath "\<PSDrive\>:\TrustPolicy\TrustedPublishingDomain" where \<PSDrive\> is the provider drive ID.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
C:\PS>Import-TPD -Path . -DisplayName Fabrikam -SourceFile c:\transfer\fabrikam.xml
```

This command imports the TPD information stored in the specified file and assigns the name Fabrikam to the TPD.
Note that because the Password parameter was not used, the Import-TPD cmdlet prompts for the domain password.

### --------------  EXAMPLE 2 --------------
```
C:\PS>$pswd = Read-Host -Prompt "Password:" -AsSecureString
Import-RmsTPD -Path . -DisplayName Fabrikam -SourceFile c:\transfer\fabrikam.xml -Password $pswd
```

This command uses the Read-Host cmdlet to prompt the user for a password and then stores the password in a variable that is passed to the Import-RmsTPD cmdlet.

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

### -DisplayName
Specifies the name that will be used to identify the domain being imported.

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

### -PassThru
Passes the object created by this cmdlet through the pipeline.
By default, this cmdlet does not pass any objects through the pipeline.

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
Specifies a password as a SecureString object.
To create a SecureString object that contains a password, use the Read-Host cmdlet and specify the AsSecureString parameter.

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

### -SourceFile
Specifies the path to the file that contains the domain information to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RightsManagementServices.PowerShell.TrustedPublishingDomainImportedItem

## NOTES

## RELATED LINKS

[Export-RmsTPD](./Export-RmsTPD.md)

[com/fwlink/?LinkId=136806](00000000-0000-0000-0000-000000000000)

