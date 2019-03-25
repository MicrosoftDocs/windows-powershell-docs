---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 2D03CC4A-89CB-47B1-ABDE-7AB4E2DA0232
manager: dansimp
---

# Enable-NetIPHttpsProfile

## SYNOPSIS
Enables an IP-HTTPS configuration profile.

## SYNTAX

```
Enable-NetIPHttpsProfile [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -Profile <String>
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Enable-NetIPHttpsProfile** cmdlet enables an IP-HTTPS configuration profile.
Only one configuration can be active at a time.

An active configuration does not mean that IP-HTTPS is active.
The active configuration may disable IP-HTTPS.

## EXAMPLES

### Example 1: Enable IP-HTTPS configuration profile
```
PS C:\>Enable-NetIPHttpsProfile -Profile "Redmond"
```

This command enables the IP-HTTPS configuration profile named Redmond.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the name of the profile to enable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### System.Object
This cmdlet returns an object.

## NOTES

## RELATED LINKS

[Disable-NetIPHttpsProfile](./Disable-NetIPHttpsProfile.md)

