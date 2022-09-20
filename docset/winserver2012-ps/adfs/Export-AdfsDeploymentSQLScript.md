---
external help file: Microsoft.FederationServices.Deployment.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/export-adfsdeploymentsqlscript?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Export-AdfsDeploymentSQLScript

## SYNOPSIS
Generates the SQL scripts that can be used separately to create the AD FS database and to grant permissions.

## SYNTAX

```
Export-AdfsDeploymentSQLScript -DestinationFolder <String> -ServiceAccountName <String> [<CommonParameters>]
```

## DESCRIPTION
The Export-AdfsDeploymentSQLScript cmdlet generates the SQL scripts that can be used separately to create the AD FS database and to grant permissions.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Export-AdfsDeploymentSQLScript -DestinationFolder ".\scriptfolder" -ServiceAccountName DOMAIN\adfsUser
```

Description

-----------

Exports SQL deployment scripts for AD FS installation on behalf of the specified AD FS service account ("adfsUser").

## PARAMETERS

### -DestinationFolder
Specifies the folder in which the generated SQL scripts will be saved.

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
Specifies the name of the Active Directory account under which the AD FS service runs. 
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Result object

## NOTES

## RELATED LINKS

