---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 4484E174-9C4B-40AF-AA2B-134B0E2D0B80
---

# Set-OBMachineSetting

## SYNOPSIS
Sets a OBMachineSetting object for the server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-OBMachineSetting [-EncryptionPassphrase] <SecureString> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-OBMachineSetting
 [-WorkDay] <DayOfWeek[] {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}>
 [-StartWorkHour] <TimeSpan> [-EndWorkHour] <TimeSpan> [-WorkHourBandwidth] <UInt32>
 [-NonWorkHourBandwidth] <UInt32> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-OBMachineSetting [-NoProxy] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Set-OBMachineSetting [-NoThrottle] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Set-OBMachineSetting [-ProxyServer] <String> [-ProxyPort] <Int32> [[-ProxyUsername] <String>]
 [[-ProxyPassword] <SecureString>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-OBMachineSetting** cmdlet sets a OBMachineSetting object for the server that includes proxy server settings for accessing the internet, network bandwidth throttling settings, and the encryption passphrase that is required to decrypt the files during recovery to another server.

This cmdlet supports WhatIf and Confirm parameters with a medium impact.
The medium impact signifies that the cmdlet will not prompt the user for confirmation by default.
The WhatIf parameter gives a verbose description of what the cmdlet does without performing any operation.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using -Confirm:$FALSE will override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>ConvertTo-SecureString -String Notag00pa55word -AsPlainText -Force | Set-OBMachineSetting
```

This example sets encryption passphrase for a computer.

### EXAMPLE 2
```
PS C:\>$spwd = ConvertTo-SecureString -String Notag00pa55word -AsPlainText -Force



PS C:\>Set-OBMachineSetting -ProxyServer http://proxycontoso.com -ProxyPort <your proxy port> -ProxyUsername contoso\johnj99 -ProxyPassword $spwd
```

This example sets proxy settings for a server.

### EXAMPLE 3
```
PS C:\>$mon = [System.DayOfWeek]::Monday



PS C:\>$tue = [System.DayOfWeek]::Tuesday



PS C:\>Set-OBMachineSetting -WorkDay $mon, $tue -StartWorkHour "9:00:00" -EndWorkHour "18:00:00" -WorkHourBandwidth (512*1024) -NonWorkHourBandwidth (2048*1024)
```

This example sets throttling settings.

### EXAMPLE 4
```
PS C:\>Set-OBMachineSetting -NoThrottle
```

This example specifies that network bandwidth throttling will not be used by this server.

### EXAMPLE 5
```
PS C:\>Set-OBMachineSetting -NoProxy
```

This example specifies that this server does not use a unique proxy server configuration.

## PARAMETERS

### -EncryptionPassphrase
Sets the encryption passphrase to be used to encrypt the backed up data.

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EndWorkHour
Specifies the hour that ends the work hours range.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoProxy
Specifies that unique proxy server settings are not to be used for online backups.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoThrottle
Specifies that network throttling is not used with online backups.
Data transfers of backed up items from the local server to the mob_name_1 server will use bandwidth as needed.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonWorkHourBandwidth
Specifies the bandwidth throttling setting to be used to limit the network bandwidth consumed by data transfers during non-work hours.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyPassword
Specifies authentication password to be used for proxy setting.

```yaml
Type: SecureString
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyPort
Specifies the port number to be used on the proxy server.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyServer
Specifies the proxy server to be used when connecting to the mob_name_1 server.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProxyUsername
Specifies the username to be used for proxy server authentication.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartWorkHour
Specifies the hour that starts the range of work hours.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkDay
Specifies the array of work days using the using **\[DayOfWeek\]** system variables.

```yaml
Type: DayOfWeek[] {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkHourBandwidth
Specifies the bandwidth throttling setting to be used to limit the network bandwidth consumed by data transfers during work hours.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Internal.CloudBackup.Commands.OBMachineSetting

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBMachineSetting

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](http://go.microsoft.com/fwlink/?LinkID=113291)

