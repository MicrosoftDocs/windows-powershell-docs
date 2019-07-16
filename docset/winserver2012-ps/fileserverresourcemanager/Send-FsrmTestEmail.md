---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: BA2C3A10-736C-4328-B8CA-C8E74A950143
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Send-FsrmTestEmail

## SYNOPSIS
Sends a test email message.

## SYNTAX

```
Send-FsrmTestEmail [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -ToEmailAddress <String>
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Send-FsrmTestEmail** cmdlet sends an email message to test the email settings in File Server Resource Manager (FSRM).
This cmdlet tests the SMTP server that you specify in the Set-FsrmSetting cmdlet.
The subject and message body are predefined, localized text.

## EXAMPLES

### Example 1: Send a test email
```
PS C:\>Send-FsrmTestEmail -ToEmailAddress "admin@contoso.com"
```

This command sends a test email message to admin@contoso.com.

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

### -ToEmailAddress
Specifies a valid email address.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-FsrmSetting](./Get-FsrmSetting.md)

[Set-FsrmSetting](./Set-FsrmSetting.md)

