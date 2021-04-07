---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/install-wssaddin?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-WssAddIn
---

# Install-WssAddIn

## SYNOPSIS
Installs or redeploys an add-in package.

## SYNTAX

### InstallParamSet (Default)
```
Install-WssAddIn [-Force] [-InstallOnClients] [-PackagePath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RedeployParamSet
```
Install-WssAddIn [-Force] [-Id] <Guid> [-Redeploy] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-WssAddIn** cmdlet installs a new add-in or redeploys an installed add-in.
To install an add-in, specify the path of a package file.
To redeploy an add-in, specify the Id of the alert.

## EXAMPLES

### Example 1: Install an add-in package
```
PS C:\> Install-WssAddIn -PackagePath "c:\TSQAaddin.wssx"
```

This command installs the add-in from the add-in package named TSQAaddin.wssx.

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
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the GUID for an installed package.
The cmdlet redeploys the add-ins for this package.

```yaml
Type: Guid
Parameter Sets: RedeployParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstallOnClients
Indicates that cmdlet deploys the add-in to clients.

```yaml
Type: SwitchParameter
Parameter Sets: InstallParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackagePath
Specifies the absolute path of the add-in package file (.wssx).

```yaml
Type: String
Parameter Sets: InstallParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Redeploy
Indicates that the cmdlet redeploys an add-in.
If you specify this parameter, specify the **PackagePath** parameter.

```yaml
Type: SwitchParameter
Parameter Sets: RedeployParamSet
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.AddinInfrastructure.PackageInfo
This cmdlet generates package information about the installed add-in.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssAddIn](./Get-WssAddIn.md)

[Uninstall-WssAddIn](./Uninstall-WssAddIn.md)

