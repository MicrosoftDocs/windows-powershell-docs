---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/set-cipolicyidinfo?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CIPolicyIdInfo
---

# Set-CIPolicyIdInfo

## SYNOPSIS
Modifies the name and ID of a Code Integrity policy.

## SYNTAX

```
Set-CIPolicyIdInfo [-FilePath] <String> [-PolicyName <String>] [-PolicyId <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-CIPolicyIdInfo** cmdlet modifies the policy name and policy ID of a Code Integrity policy.
Specify the .xml file of the policy to modify.
Event Tracing for Windows (ETW) events use the **PolicyID** and **Name** properties to identify which policy is currently running on a computer.

## EXAMPLES

### Example 1: Modify the ID and name of a policy
```
PS C:\> Set-CIPolicyIdInfo -FilePath ".\Policy03.xml" -PolicyId "CIP077" -PolicyName "CIPolicy03"
```

This command modifies the policy ID and the policy name for the policy stored in the Policy03.xml file.

### Example 2: Modify the name of a policy
```
PS C:\> Set-CIPolicyIdInfo -FilePath ".\Policy03.xml" -PolicyName "CIPolicy77"
```

This command modifies only the policy name for the policy stored in the Policy03.xml file.

## PARAMETERS

### -FilePath
Specifies the path of a Code Integrity policy .xml file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyId
Specifies the value for the **PolicyID** property.
This string is not required to be a GUID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pid

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyName
Specifies the value for the **Name** property.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-CIPolicyIdInfo](./Get-CIPolicyIdInfo.md)

