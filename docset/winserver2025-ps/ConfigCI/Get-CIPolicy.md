---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/get-cipolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CIPolicy
---

# Get-CIPolicy

## SYNOPSIS
Gets the rules in a Code Integrity policy.

## SYNTAX

```
Get-CIPolicy [-FilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-CIPolicy** cmdlet returns the rules in a Code Integrity policy.
Specify a policy .xml file.
This cmdlet does not currently support policies in Public-Key Cryptography Standards #7 format (.p7b files).

## EXAMPLES

### Example 1: Get rules from a policy
```
PS C:\> Get-CIPolicy -FilePath '.\Policy.xml'
Name           : MSIT Test CodeSign CA 3
Id             : ID_SIGNER_S_17
TypeId         : Allow
Root           : FA6B9A2230CE08BCA81D096B28CF495672401D3A43A0D285CF352464A6C9C7FD
FileVersionRef :
Wellknown      : False
Ekus           :
Exceptions     :
FileAttributes :
FileException  : False
UserMode       : False

Name           : VeriSign Class 3 Code Signing 2010 CA
Id             : ID_SIGNER_S_1D
TypeId         : Allow
Root           : 4843A82ED3B1F2BFBEE9671960E1940C942F688D
FileVersionRef :
Wellknown      : False
Ekus           :
Exceptions     :
FileAttributes :
FileException  : False
UserMode       : False

Name           : Microsoft Windows Third Party Component CA 2012
Id             : ID_SIGNER_S_1E
TypeId         : Allow
Root           : CEC1AFD0E310C55C1DCC601AB8E172917706AA32FB5EAF826813547FDF02DD46
FileVersionRef :
Wellknown      : False
Ekus           :
Exceptions     :
FileAttributes :
FileException  : False
UserMode       : False
```

This command returns the rule objects from Policy.xml.
For this example, we present only the first few rules.

## PARAMETERS

### -FilePath
Specifies the path of the policy .xml file for which this cmdlet gets rules.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Rule
This cmdlet returns rules from the policy.

## NOTES

## RELATED LINKS

[Merge-CIPolicy](./Merge-CIPolicy.md)

[New-CIPolicy](./New-CIPolicy.md)

