---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/merge-cipolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Merge-CIPolicy
---

# Merge-CIPolicy

## SYNOPSIS
Combines the rules in several Code Integrity policy files.

## SYNTAX

```
Merge-CIPolicy [-OutputFilePath] <String> [-PolicyPaths] <String[]> [-Rules <Rule[]>] [-AppIdTaggingPolicy]
 [<CommonParameters>]
```

## DESCRIPTION
The **Merge-CIPolicy** cmdlet combines the rules in several Code Integrity policy files.
This cmdlet creates a single policy .xml file.
You can specify rules to add to the merged list.
This cmdlet does not save redundant rules.
The cmdlet appends a digit to the IDs of the rules to make the IDs of the rules unique.

## EXAMPLES

### Example 1: Merge policies
```
PS C:\> Merge-CIPolicy -PolicyPaths '.\Policy.xml','.\Policy02.xml' -OutputFilePath '.\MergedPolicy.xml'

Name           : MSIT Test CodeSign CA 3
Id             : ID_SIGNER_S_17_0
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
Id             : ID_SIGNER_S_1D_0
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
Id             : ID_SIGNER_S_1E_0
TypeId         : Allow
Root           : CEC1AFD0E310C55C1DCC601AB8E172917706AA32FB5EAF826813547FDF02DD46
FileVersionRef :
Wellknown      : False
Ekus           :
Exceptions     :
FileAttributes :
FileException  : False
UserMode       : False

Name           : \\?\E:\cmdlets\temp\Microsoft.ConfigCI.Commands.dll Hash Sha1
Id             : ID_ALLOW_A_49_1
TypeId         : Allow
Root           :
FileVersionRef :
Wellknown      : False
Ekus           :
Exceptions     :
FileAttributes :
FileException  : False
UserMode       : False
```

This command merges policies defined in the two .xml files into a third file, MergedPolicy.xml.
The cmdlet appends _0 to ID of the rules from the first policy, such as ID_SIGNER_S_17_0.
It appends _1 to rules from the second policy, such as ID_ALLOW_A_49_1.
The command does not include duplicates.
For this example, we present only the first few rules.

## PARAMETERS

### -AppIdTaggingPolicy
This parameter is reserved for future use.

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

### -OutputFilePath
Specifies the path of the merged .xml policy file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: o

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyPaths
Specifies an array of paths of the policy .xml files that this cmdlet merges.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: p

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rules
Specifies an array of **Rule** objects that this cmdlet adds to the merged policy.
To obtain a rule object, use the **Get-CIPolicy** or **New-CIPolicyRule** cmdlets.

```yaml
Type: Rule[]
Parameter Sets: (All)
Aliases: r

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Rule
This cmdlet returns the rules in the policy that it creates.

## NOTES

## RELATED LINKS

[Get-CIPolicy](./Get-CIPolicy.md)

[New-CIPolicy](./New-CIPolicy.md)

