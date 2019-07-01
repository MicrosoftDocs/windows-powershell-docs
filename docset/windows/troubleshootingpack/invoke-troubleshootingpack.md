---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Diagnosis.TroubleshootingPack.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Invoke-TroubleshootingPack
ms.reviewer:
ms.assetid: 25FC6F1B-B88E-457B-8AC2-95A35E63FF63
---

# Invoke-TroubleshootingPack

## SYNOPSIS
Runs a troubleshooting pack.

## SYNTAX

```
Invoke-TroubleshootingPack [-Pack] <DiagPack> [-AnswerFile <String>] [-Result <String>] [-Unattended]
 [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-TroubleshootingPack** cmdlet runs a troubleshooting pack in either interactive or unattended mode.
A troubleshooting pack determines the root causes of issues, resolves the issues, and verifies that the issues were resolved.
The cmdlet can save reports that detail issues and resolutions.

In interactive mode, you can select the resolutions to use and provide input to interactions with the troubleshooting pack.
In unattended mode, the troubleshooting pack determines which resolutions to use at run time.
While in unattended mode, if the troubleshooting pack requires input, you need to provide answers or specify an answer file.
To create an answer file, use the Get-TroubleshootingPack cmdlet.

You can save the result report and the debug report, along with XSL and any linked files.
Both reports contain the issues and resolutions.
The debug report contains additional information.

## EXAMPLES

### Example 1: Run a troubleshooting pack
```
PS C:\> Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio" | Invoke-TroubleshootingPack
```

This example runs the Audio pack in interactive mode.
This example does not save reports.

The command uses the **Get-TroubleshootingPack** cmdlet to get a **DiagPack** object and pipes it to the **Invoke-TroubleshootingPack** cmdlet.

### Example 2: Save troubleshooting reports
```
PS C:\> $Audio = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio"
PS C:\> Invoke-TroubleshootingPack -Pack $Audio -Result "C:\DiagResult"
```

This example runs the Areo pack in interactive mode and saves the results to a folder.

The first command uses the **Get-TroubleshootingPack** cmdlet to get a DiagPack object and stores it in the $Audio variable.

The second command invokes the troubleshooting pack stored in $Audio.
The pack saves reports in the specified folder.

### Example 3: Run a troubleshooting pack in unattended mode
```
PS C:\> $Audio = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio"
PS C:\> Invoke-TroubleshootingPack -Pack $Audio -AnswerFile "AudioAnswerFile.xml" -Unattended
```

This example runs the Audio pack in unattended mode with a specified answer file.

The first command uses the **Get-TroubleshootingPack** cmdlet to get a DiagPack object and stores it in the $Audio variable.

The second command invokes the troubleshooting pack stored in $Audio in unattended mode.
The command specifies an answer file, previously created by using the **Get-TroubleshootingPack** cmdlet.

### Troubleshooting commands for all the components or devices and save all reports in C:\Diagresult
make a folder "DiagResult" in C:\
then open powershell application with administrator right, type the following 

01. Apps
**$Apps = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Apps"**
**Invoke-TroubleshootingPack -Pack $Apps -Result "C:\DiagResult"**

02. Audio
**$Audio = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Audio"**
**Invoke-TroubleshootingPack -Pack $Audio -Result "C:\DiagResult"**

03. BITS
**$BITS = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\BITS"**
**Invoke-TroubleshootingPack -Pack $BITS -Result "C:\DiagResult"**

04. Bluetooth
**$Bluetooth = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Bluetooth"**
**Invoke-TroubleshootingPack -Pack $Bluetooth -Result "C:\DiagResult"**

05. Device
**$Device = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Device"**
Invoke-TroubleshootingPack -Pack $Device -Result "C:\DiagResult"**

06. DeviceCenter
**$DeviceCenter = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\DeviceCenter"**
**Invoke-TroubleshootingPack -Pack $DeviceCenter -Result "C:\DiagResult"**

07. Internet Explorer WebBrowser
**$IEBrowseWeb = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\IEBrowseWeb"**
**Invoke-TroubleshootingPack -Pack $IEBrowseWeb -Result "C:\DiagResult"**

08. Internet Explorer Security
**$IESecurity = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\IESecurity"**
**Invoke-TroubleshootingPack -Pack $IESecurity -Result "C:\DiagResult"**

09. Keyboard
**$Keyboard = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Keyboard"**
**Invoke-TroubleshootingPack -Pack $Keyboard -Result "C:\DiagResult"**

10. Networking 
**$Networking = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Networking"**
**Invoke-TroubleshootingPack -Pack $Networking -Result "C:\DiagResult"**

11. PCW
**$PCW = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\PCW"**
**Invoke-TroubleshootingPack -Pack $PCW -Result "C:\DiagResult"**

12. Power
**$Power = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Power"**
**Invoke-TroubleshootingPack -Pack $Power -Result "C:\DiagResult"**

13. Printer
**$Printer = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Printer"**
**Invoke-TroubleshootingPack -Pack $Printer -Result "C:\DiagResult"**

14. Search
**$Search = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Search**
**Invoke-TroubleshootingPack -Pack $Search -Result "C:\DiagResult"**

15. Speech
**$Speech = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Speech"**
**$SpeInvoke-TroubleshootingPack -Pack $Speech -Result "C:\DiagResult"**

16. Video
**$Video = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\Video"**
**Invoke-TroubleshootingPack -Pack $Video -Result "C:\DiagResult"**

17. WindowsmediaPlayerConfiguartion
**$WindowsMediaPlayerConfiguration = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\WindowsMediaPlayerConfiguration"**
**Invoke-TroubleshootingPack -Pack $WindowsMediaPlayerConfiguration -Result "C:\DiagResult"**

18. WindowsMediaPlayerMediaLibrary
**$WindowsMediaPlayerMediaLibrary = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\WindowsMediaPlayerMediaLibrary"**
**Invoke-TroubleshootingPack -Pack $WindowsMediaPlayerMediaLibrary -Result "C:\DiagResult"**

19. WindowsMediaPlayerPlayDVD
**$WindowsMediaPlayerPlayDVD = Get-TroubleshootingPack -Path "C:\Windows\Diagnostics\System\WindowsMediaPlayerPlayDVD"**
**Invoke-TroubleshootingPack -Pack $WindowsMediaPlayerPlayDVD -Result "C:\DiagResult"**


> [!NOTE]
>  All Troubleshooting reports will be  stored in the folder  **C:\DiagResult\**

## PARAMETERS

### -AnswerFile
Specifies a path for an answer file.
You can use an absolute path, a relative path, or a Universal Naming Convention (UNC) path.
To generate an answer file, use the **Get-TroubleshootingPack** cmdlet.

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

### -Pack
Specifies a **DiagPack** object.
The **DiagPack** object defines a troubleshooting pack.
To obtain a **DiagPack** object, use the **Get-TroubleshootingPack** cmdlet.

```yaml
Type: DiagPack
Parameter Sets: (All)
Aliases: P

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Result
Specifies a path for the result report and the debug report.
You can use an absolute path, a relative path, or a Universal Naming Convention (UNC) path.

If you do not use this parameter, the cmdlet does not save reports.

```yaml
Type: String
Parameter Sets: (All)
Aliases: R

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unattended
Indicates that the troubleshooting pack runs in unattended mode.
If you specify this parameter and the troubleshooting pack requires input, specify an answer file in the *AnswerFile* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: U

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.Diagnosis.DiagPack
The troubleshooting pack to run.
To obtain a **DiagPack** object, use the **Get-TroubleshootingPack** cmdlet.

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-TroubleshootingPack](./Get-TroubleshootingPack.md)

