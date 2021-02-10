---
external help file: MSFT_DAClientExperienceConfiguration.cdxml-help.xml
Module Name: DirectAccessClientComponents
online version: 
schema: 2.0.0
title: Get-DAClientExperienceConfiguration
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8AD66898-56D9-4CDB-B2CC-AC0B8B8CFD8B
---

# Get-DAClientExperienceConfiguration

## SYNOPSIS
Returns the configuration for the DirectAccess client user experience.

## SYNTAX

```
Get-DAClientExperienceConfiguration [-PolicyStore <String>] [-GPOSession <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
**Get-DAClientExperienceConfiguration** returns the configuration for the DirectAccess client user experience.
The configuration returned controls the user interface behavior, as well as what configuration options are available to the user.

All **DAClientExperienceConfiguration** cmdlets have an ADMX file that can also be used to configure the client experience settings.

## EXAMPLES

### Example: Retrieve the DirectAccess client experience configuration from the active store
```
PS C:\> Get-DAClientExperienceConfiguration -PolicyStore ActiveStore
```

This cmdlet retrieves the DirectAccess client experience configuration from the active policy store.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -GPOSession
Specifies the Group Policy session from which to read client experience configuration information.
You can use **GPOSession** with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object.

**GPOSession** cannot be used in conjunction with **PolicyStore**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which the cmdlet reads the client experience configuration information.

To read the client experience configuration information from a Group Policy Object, specify the GPO name using the following format: "Domain\GPOName"

To read the client experience configuration information from a computer's local GPO, specify the computer's local GPO name in the following format: "GPO:\<computername\>"

**PolicyStore** cannot be used in conjunction with **GPOSession**.

The default value for **PolicyStore** is ActiveStore.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DAClientExperienceConfiguration
This cmdlet returns a CIM object that contains the DA client experience configuration.

## NOTES

## RELATED LINKS

[Reset-DAClientExperienceConfiguration](./Reset-DAClientExperienceConfiguration.md)

[Set-DAClientExperienceConfiguration](./Set-DAClientExperienceConfiguration.md)

