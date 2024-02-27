---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/import-rmstud?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-RmsTUD
---

# Import-RmsTUD

## SYNOPSIS
Imports a TUD from a file in AD RMS or specifies to trust Microsoft account IDs.

## SYNTAX

### EnterpriseTUD (Default)
```
Import-RmsTUD [-DisplayName] <String> [-SourceFile] <String> [-TrustADFederatedUser] [-PassThru]
 [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WindowsLiveID
```
Import-RmsTUD [-WindowsLiveId] [-PassThru] [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-RmsTUD** cmdlet imports an enterprise trusted user domain (TUD) from a file in Active Directory Rights Management Services (AD RMS) or it specifies to trust a Microsoft account ID.

To perform the import of enterprise TUDs, specify the *DisplayName* and *SourceFile* parameters and set the *Path* parameter to the AD RMS provider drive folder `<PSDrive>:\TrustPolicy\TrustedUserDomain` where `<PSDrive>` is the provider drive ID.

To trust a Microsoft account ID, specify the *WindowsLiveID* parameter, and set the *Path* parameter to the AD RMS provider drive folder `<PSDrive>:\TrustPolicy\TrustedUserDomain`.

## EXAMPLES

### Example 1: Import a TUD and assign it a name
```
PS C:\> Import-TUD -Path "." -DisplayName "Fabrikam" -SourceFile "c:\transfer\fabrikam.xml"
```

This command imports the TUD information stored in the specified file and assigns the name Fabrikam to the TUD.

### Example 2: Configure a TUD to trust Microsoft account IDs
```
PS C:\> Import-RmsTUD -Path "." -WindowsLiveId
```

This command configures the AD RMS cluster to trust Microsoft account IDs.

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
Parameter Sets: EnterpriseTUD
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -SourceFile
Specifies the path to the file that contains the domain information to import.

```yaml
Type: String
Parameter Sets: EnterpriseTUD
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TrustADFederatedUser
Specifies to trust Active Directory Federation Services (ADFS) users.

```yaml
Type: SwitchParameter
Parameter Sets: EnterpriseTUD
Aliases:

Required: False
Position: 3
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

### -WindowsLiveId
Indicates to trust Microsoft account IDs.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsLiveID
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.RightsManagementServices.PowerShell.TrustedUserDomainImportedItem

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Export-RmsTUD](./Export-RmsTUD.md)

