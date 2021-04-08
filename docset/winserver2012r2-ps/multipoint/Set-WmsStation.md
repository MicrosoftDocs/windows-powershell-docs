---
author: Kateyanne
description: 
external help file: WmsCmdlets.dll-Help.xml
manager: jasgro
Module Name: MultiPoint
ms.author: v-kaunu
ms.date: 12/06/2017
ms.prod: powershell
ms.reviewer: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/multipoint/set-wmsstation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmsStation
---

# Set-WmsStation

## SYNOPSIS
Sets station information.

## SYNTAX

```
Set-WmsStation [-StationId <Int32>] [-StationFriendlyName <String>] [-AutoLogonUserName <String>]
 [-AutoLogonPassword <String>] [-OverrideAdminWarning] [-EnableAutoLogon] [-DisableAutoLogon]
 [-SetFriendlyName] [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-WmsStation cmdlet sets station information.
It also sets the auto-logon and the friendly name for the station based on the specified parameters.
If you want to enable a user in the administrator group to auto-logon, specify -OverrideAdminWarning.

## EXAMPLES

### Example
```
PS C:\> Set-WmsStation -StationId 1 -SetFriendlyName -StationFriendlyName UwB0AGEAdABpAG8AbgAxAA== -EnableAutoLogon -AutoLogonUserName "UwB0AHUAZABlAG4AdAAxAA=="  -AutoLogonPassword "UABAAHMAcwB3ADAAcgBkAA=="
No output.
```

Station friendly name of station 1 will be set. 
Station #1 is now configured to autologon as "Student1" with password "P@ssw0rd". 
Note: -StationFriendlyName parameter value is expected to Base64 encoded.
To convert a string to Base64 encoded string, refer to the following example: 

PS C:\\\> $Name="Station1"

PS C:\\\> \[System.Convert\]::ToBase64String(\[System.Text.Encoding\]::UNICODE.GetBytes($Name))UwB0AGEAdABpAG8AbgAxAA==

### 1:
```
PS C:\>
```

## PARAMETERS

### -AutoLogonPassword
The password for the user account that is configured for autologon.

This parameter is BASE64 encoded.

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

### -AutoLogonUserName
The user name for the autologon account. 

This parameter is BASE64 encoded.

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

### -DisableAutoLogon
Disables autologon for the specified station.

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

### -EnableAutoLogon
Enables autologon for the specified station.

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

### -OverrideAdminWarning
Specify this option if the autologon account is a member of the administrators group.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SetFriendlyName
Sets the friendly name for the specified station.

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

### -StationFriendlyName
The friendly name for the station. 

This parameter is BASE64 encoded.

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

### -StationId
The station to be configured.

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

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### None
Throws SecurityException if the specified autologon user is an administrative user.
This exception is not thrown if the OverrideAdminWarning option is specified for administrative users.

## NOTES

## RELATED LINKS

