---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
ms.assetid: A49F23B5-487F-43D3-9375-1B04F038E495
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-RmsSvcAccount

## SYNOPSIS
Gets service account credentials for an Active Directory Rights Management Services (AD RMS) cluster.

## SYNTAX

```
Get-RmsSvcAccount [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
HelpLongDescription The Get-RmsSvcAccount cmdlet gets service account credentials for an Active Directory Rights Management Services (AD RMS) cluster.



To get the service account credentials, set the Path parameter to "\<PSDrive\>:\" where \<PSDrive\> is the drive ID of the provider drive associated with AD RMS cluster.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
C:\PS>Get-RmsSvcAccount -Path .
```

This command displays the AD RMS service account.

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
Default value: String.empty
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

### System.Management.Automation.PSCredential

## NOTES

## RELATED LINKS

[Set-RmsSvcAccount](./Set-RmsSvcAccount.md)

[ADRMSAdmin Module](./ADRMSAdmin.md)

