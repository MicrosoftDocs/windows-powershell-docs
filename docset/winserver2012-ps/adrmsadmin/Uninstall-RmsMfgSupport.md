---
author: Kateyanne
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
manager: dansimp
Module Name: ADRMSAdmin
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adrmsadmin/uninstall-rmsmfgsupport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Uninstall-RmsMfgSupport

## SYNOPSIS
Removes Microsoft Federation Gateway support from an AD RMS server.

## SYNTAX

```
Uninstall-RmsMfgSupport [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-RmsMfgSupport cmdlet removes Microsoft Federation Gateway support from an AD RMS server.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
PS C:\>Uninstall-RmsMfgSupport -Force
```

Forces removal of Microsoft Federation Gateway support for AD RMS.

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
Forces completion of the current operation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* Before uninstalling Service Pack 1 for nextref_server_7, you must remove Microsoft Federation Gateway Support from the AD RMS cluster. Failure to do this may cause an inconsistent configuration of your AD RMS cluster.

## RELATED LINKS

[Install-RmsMfgSupport](./Install-RmsMfgSupport.md)

