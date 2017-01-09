---
author: brianlic
description: 
external help file: MSFT_MpSignature.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Update-MpSignature
ms.assetid: 755740EB-1B6C-48C2-BE9C-16CD893EE064
---

# Update-MpSignature

## SYNOPSIS
Updates the antimalware definitions on a computer.

## SYNTAX

```
Update-MpSignature [-UpdateSource <UpdateSource>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Update-MpSignature** cmdlet updates the antimalware definitions with the latest definitions available on an update server.

## EXAMPLES

### Example 1: Update signatures
```
PS C:\> Update-MpSignature
```

This command updates the antimalware definitions.
By default, the cmdlet uses the default update source.

### Example 2: Update signatures from a specific source
```
PS C:\> Update-MpSignature -UpdateSource MicrosoftUpdateServer
```

This command updates the antimalware definitions from the Microsoft Update Server.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateSource
Specifies an update source.
This cmdlet downloads updated definitions from the server you specify.
If you do not specify this parameter, the cmdlet uses the Microsoft Update Server, then Microsoft Malware Protection Center (MMPC), as an update source.
The acceptable values for this parameter are:

- InternalDefinitionUpdateServer
- MicrosoftUpdateServer
- MMPC 
- FileShares

If you specify the InternalDefinitionUpdateServer setting, the service checks for updates on the Windows Software Update Services (WSUS) server.

```yaml
Type: UpdateSource
Parameter Sets: (All)
Aliases: 
Accepted values: InternalDefinitionUpdateServer, MicrosoftUpdateServer, MMPC, FileShares

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

