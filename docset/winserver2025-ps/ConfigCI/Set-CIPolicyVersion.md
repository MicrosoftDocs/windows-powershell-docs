---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/set-cipolicyversion?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CIPolicyVersion
---

# Set-CIPolicyVersion

## SYNOPSIS
Updates the version number of the policy.

## SYNTAX

```
Set-CIPolicyVersion -FilePath <String> -Version <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-CIPolicyVersion** cmdlet updates the version number of the policy for a signed policy scenario.
When you update a signed policy, the policy must be replaced by a policy that has a signer specified in the **UpdatePolicySigners** property of the policy.
The policy must also be an equal or greater version that the previous policy.

## EXAMPLES

### Example 1: Update the version number of a policy
```
PS C:\> Set-CIPolicyVersion -FilePath '.\Policy.xml' -Version '11.1.0.2'
PS C:\> Get-Content -Path '.Policy.xml'
<?xml version="1.0" encoding="utf-8"?>
<SiPolicy xmlns="urn:schemas-microsoft-com:sipolicy">
  <VersionEx>11.1.0.2</VersionEx>
  <PolicyTypeID>{A244370E-44C9-4C06-B551-F6016E563076}</PolicyTypeID>
```

The first command modifies the version of Policy.xml to be 11.1.0.2.

The second command displays the contents of the policy.
This example shows the first few lines of the policy, which include the **VersionEx** property.
It now has a value of 11.1.0.2.

## PARAMETERS

### -FilePath
Specifies the path of a policy .xml file that this cmdlet updates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: f

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version string with which this cmdlet replaces the current version of the policy.
Specify the version in the following format: integer.integer.integer.integer.
The **New-CIPolicy** and **Merge-CIPolicy** cmdlets create policies with the default version of 10.0.0.0.

```yaml
Type: String
Parameter Sets: (All)
Aliases: v

Required: True
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

[Merge-CIPolicy](./Merge-CIPolicy.md)

[New-CIPolicy](./New-CIPolicy.md)

