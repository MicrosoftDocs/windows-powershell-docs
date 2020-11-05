---
external help file: MSFT_NetIpHTTPsConfiguration.cdxml-help.xml
Module Name: NetworkTransition
online version: 
schema: 2.0.0
title: Get-NetIPHttpsConfiguration
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E3DB6861-8AC4-43D7-96A7-E832280B9A10
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetIPHttpsConfiguration

## SYNOPSIS
Gets the IP-HTTPS configuration from a computer or a Group Policy Object (GPO).

## SYNTAX

### ByPolicyStore (Default)
```
Get-NetIPHttpsConfiguration [-Profile <String[]>] [-ProfileActivated <Boolean[]>] [-PolicyStore <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByGpoSession
```
Get-NetIPHttpsConfiguration [-Profile <String[]>] [-ProfileActivated <Boolean[]>] [-GPOSession <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetIPHttpsConfiguration** cmdlet gets the IP-HTTPS configuration from a computer or a Group Policy Object (GPO).

You can also use **Get-NetIPHttpsConfiguration** to retrieve the IP-HTTPS configuration, and then use the configuration information as input into other cmdlets.

## EXAMPLES

### Example 1: Get the IP-HTTPS configuration
```
PS C:\>Get-NetIPHttpsConfiguration
```

This command gets the IP-HTTPS configuration from a computer or a GPO.

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
Specifies the Group Policy session from which to get the configuration information. 
                         
You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO. 
                         
You cannot use this parameter with the **PolicyStore** parameter.

```yaml
Type: String
Parameter Sets: ByGpoSession
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which to get the configuration.
The default store is ActiveStore. 
                         
Valid values for this parameter are: 
                         
 -- ActiveStore 
                         
 -- PersistentStore 
                         
 -- GPO 
                         
To get the configuration of a GPO, specify the GPO name using the following format: `Domain\GPOName`
                         
You cannot use this parameter with the **GPOSession** parameter.

```yaml
Type: String
Parameter Sets: ByPolicyStore
Aliases: 

Required: False
Position: Named
Default value: ActiveStore
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Filters the objects retrieved by the profile name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: IPHttpsProfile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProfileActivated
Filters the objects retrieved by profile status.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIpHTTPsConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
This cmdlet returns one or more IP-HTTPS configuration objects.

## NOTES

## RELATED LINKS

[New-NetIPHttpsConfiguration](./New-NetIPHttpsConfiguration.md)

[Remove-NetIPHttpsConfiguration](./Remove-NetIPHttpsConfiguration.md)

[Rename-NetIPHttpsConfiguration](./Rename-NetIPHttpsConfiguration.md)

[Reset-NetIPHttpsConfiguration](./Reset-NetIPHttpsConfiguration.md)

[Set-NetIPHttpsConfiguration](./Set-NetIPHttpsConfiguration.md)

