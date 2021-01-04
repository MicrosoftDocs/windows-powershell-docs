---
external help file: Microsoft.Windows.Diagnosis.TroubleshootingPack.dll-Help.xml
ms.assetid: 9ED46ACE-1590-4CCA-97A8-C494DD1162BE
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-TroubleshootingPack

## SYNOPSIS
Gets a troubleshooting pack or generates an answer file.

## SYNTAX

```
Get-TroubleshootingPack [-Path] <String> [-AnswerFile <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-TroubleshootingPack** cmdlet gets a **DiagPack** object that you can pass to the **Invoke-TroubleshootingPack** cmdlet.

The **Get-TroubleshootingPack** can also get information about a troubleshooting pack and generate an answer file.

## EXAMPLES

### Example 1: Get a troubleshooting pack
```
PS C:\> Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio"
```

The command gets the troubleshooting pack for Audio in the specified path.

### Example 2: Get a root cause
```
PS C:\> $Audio = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio" PS C:\>$Audio.Rootcauses[2]
```

This example shows how to discover a root cause from a troubleshooting pack.

The first command gets the troubleshooting pack for Audio in the specified path and saves that object in the $Audio variable.

The second command displays a root cause.
The $Audio object contains an array of root causes.
This command uses conventional array notation to access the third member of the array.

### Example 3: Get a resolution
```
PS C:\> $Audio = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio" PS C:\>$Audio.RootCauses[2].Resolutions[0]
```

This example shows how to discover a resolution for a root cause.

The first command gets the troubleshooting pack for Audio in the specified path and saves that object in the $Audio variable.

The second command displays a resolution for a root cause.
The $Audio object contains an array of root causes, each of which contains an array of resolutions.
This command uses conventional array notation to access the first resolution for the third root cause.

### Example 4: Generate an answer file
```
PS C:\> Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio" -AnswerFile "AudioAnswerFile.xml"
```

This command uses the **Get-TroubleshootingPack** cmdlet to generate an answer file.
The Audio troubleshooting pack provides a series of questions for the user to describe the troubleshooting situation and saves that information in the specified XML file.

## PARAMETERS

### -AnswerFile
Specifies a path where the cmdlet saves an answer file.
You can use an absolute path, a relative path, or a Universal Naming Convention (UNC) path.
If you specify this parameter, this cmdlet does not provide output.

You can use the **Get-TroubleshootingPack** cmdlet to generate an XML file that contains answers to troubleshooting questions.
You can use the answers stored in an answer file to automate question responses during package execution using **Invoke-TroubleshootingPack**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies a path to the folder that contains the troubleshooting pack.
You can use an absolute path, a relative path, or a Universal Naming Convention (UNC) path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: P

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.Diagnosis.DiagPack
The **DiagPack** object defines the troubleshooting pack.

## NOTES

## RELATED LINKS

[Invoke-TroubleshootingPack](./Invoke-TroubleshootingPack.md)

