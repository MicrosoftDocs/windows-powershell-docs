---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 10/26/2021
online version: https://docs.microsoft.com/powershell/module/adfs/export-adfsdeploymentsqlscript?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-AdfsDeploymentSQLScript
---

# Export-AdfsDeploymentSQLScript

## SYNOPSIS
Generates SQL scripts to create the AD FS database and to grant permissions.

## SYNTAX

```
Export-AdfsDeploymentSQLScript -DestinationFolder <String> -ServiceAccountName <String>
 [-DatabaseType <DatabaseType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-AdfsDeploymentSQLScript** cmdlet generates the SQL scripts that you can use separately to create the Active Directory Federation Services (AD FS) database and to grant permissions.

## EXAMPLES

### Example 1: Export SQL deployment scripts
```
PS C:\> Export-AdfsDeploymentSQLScript -DestinationFolder ".\ScriptFolder" -ServiceAccountName "ContosoDomain\PattiFuller"
```

This command exports SQL deployment scripts for AD FS installation on behalf of the specified AD FS service account.

## PARAMETERS

### -DatabaseType
Specifies the AD FS database type.

The acceptable values for this parameter are: All, Artifact, or Configuration.

If no **DatabaseType** parameter is specified, **All** is the default and the script configures both
the Artifact and Configuration scripts.

```yaml
Type: DatabaseType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationFolder
Specifies the folder in which the cmdlet saves the generated SQL scripts.

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

### -ServiceAccountName
Specifies the name of the Active Directory&reg; Domain Services account under which the AD FS service runs. 
All nodes in the farm must use the same service account.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

