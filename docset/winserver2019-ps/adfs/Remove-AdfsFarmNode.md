---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Deployment.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsfarmnode?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsFarmNode
---

# Remove-AdfsFarmNode

## SYNOPSIS
The Remove-AdfsFarmNode cmdlet is deprecated.
Instead, use the Uninstall-WindowsFeature cmdlet.

## SYNTAX

### ADFSRemoveFarmNodeDefault (Default)
```
Remove-AdfsFarmNode -ServiceAccountCredential <PSCredential> [<CommonParameters>]
```

### AdfsRemoveFarmNodeGmsa
```
Remove-AdfsFarmNode -GroupServiceAccountIdentifier <String> [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsFarmNode** cmdlet is deprecated in this release.
Instead, use the [Uninstall-WindowsFeature](https://go.microsoft.com/fwlink/?LinkID=287572) cmdlet.
For more information on the **Uninstall-WindowsFeature** cmdlet, type `Get-Help Uninstall-WindowsFeature`. Note that the **Uninstall-WindowsFeature** cmdlet removes only the server role but doesn't remove the node from the ADFS farm. For proper cleanup, use the **Set-AdfsFarmInformation** cmdlet with the `-RemoveNode` parameter.

## EXAMPLES

## PARAMETERS

### -Credential
```yaml
Type: PSCredential
Parameter Sets: AdfsRemoveFarmNodeGmsa
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupServiceAccountIdentifier
```yaml
Type: String
Parameter Sets: AdfsRemoveFarmNodeGmsa
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountCredential
```yaml
Type: PSCredential
Parameter Sets: ADFSRemoveFarmNodeDefault
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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Uninstall-WindowsFeature](/powershell/module/servermanager/uninstall-windowsfeature)

