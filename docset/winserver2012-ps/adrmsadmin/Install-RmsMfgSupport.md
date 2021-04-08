---
author: Kateyanne
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
manager: dansimp
Module Name: ADRMSAdmin
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/adrmsadmin/install-rmsmfgsupport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Install-RmsMfgSupport

## SYNOPSIS
Adds Microsoft Federation Gateway support to an AD RMS server.

## SYNTAX

```
Install-RmsMfgSupport [-Force] [-FederationUrl <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-RmsMfgSupport cmdlet adds Microsoft Federation Gateway support to an AD RMS server.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
PS C:\>Install-RmsMfgSupport
```

Adds Microsoft Federation Gateway support to an AD RMS server.

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

### -FederationUrl
Specifies the uniform resource locator (URL) that the AD RMS server is to use when connecting to the Microsoft Federation Gateway.
If this parameter is not supplied, AD RMS will connect to the Microsoft Federation Gateway using default

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Forces the installation process to be completed, even if there are issues.

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
* Before adding Microsoft Federation Gateway Support, it is very important that you back up the AD RMS configuration database.

  Do not run this command if the AD RMS snap-in is open in the Microsoft Management Console (MMC).
If you do, the command will not respond until you close the AD RMS MMC snap-in.

  Before uninstalling Service Pack 1 for nextref_windows_7, you must remove Microsoft Federation Gateway Support from the AD RMS cluster by running the **Uninstall-RmsMfgSupport** cmdlet.
Failure to do this may cause an inconsistent configuration of your AD RMS cluster.

## RELATED LINKS

