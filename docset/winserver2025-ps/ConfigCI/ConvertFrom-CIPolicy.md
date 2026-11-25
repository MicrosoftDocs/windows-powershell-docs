---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ConfigCI.Commands.dll-Help.xml
Module Name: ConfigCI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/configci/convertfrom-cipolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-CIPolicy
---

# ConvertFrom-CIPolicy

## SYNOPSIS
Converts an .xml file that contains a Code Integrity policy into binary format.

## SYNTAX

```
ConvertFrom-CIPolicy [-XmlFilePath] <String> [-BinaryFilePath] <String> [<CommonParameters>]
```

## DESCRIPTION
The **ConvertFrom-CIPolicy** cmdlet converts an .xml file that contains a Code Integrity policy into binary format.
You can install the binary version of a policy on a computer.

## EXAMPLES

### Example 1: Converts a policy
```
PS C:\> ConvertFrom-CIPolicy -XmlFilePath ".\Policy03.xml" -BinaryFilePath "Policy03.bin"
C:\Policies\Policy03.bin
```

This command converts the policy in Policy03.xml into a binary named Policy03.bin.
The console displays the full path of the binary file.

## PARAMETERS

### -BinaryFilePath
Specifies the path for the output converted policy binary file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: bin

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -XmlFilePath
Specifies the path of the .xml policy file that this cmdlet converts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: xml

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-CIPolicy](./Get-CIPolicy.md)

[Merge-CIPolicy](./Merge-CIPolicy.md)

[New-CIPolicy](./New-CIPolicy.md)

