---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SyncServerSetting.cdxml-help.xml
Module Name: SyncShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/syncshare/set-syncserversetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SyncServerSetting
---

# Set-SyncServerSetting

## SYNOPSIS
Modifies settings of the Sync Share.

## SYNTAX

```
Set-SyncServerSetting [-InputObject <CimInstance[]>] [-Description <String>] [-AdministratorEmail <String>]
 [-ADFSUrl <String>] [-SuspendedUser <String[]>] [-MinimumChangeDetectionMins <UInt32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SyncServerSetting** cmdlet modifies settings of the Sync Share.

## EXAMPLES

### Example 1: Set the administrator email for the Sync Share server
```
PS C:\> Set-SyncServerSetting -AdministratorEmail "admin@contoso.com"
```

This command sets the administrator email address for the Sync Share server.
The administrator email address is propagated to the client devices so users can send email to the administrator and request help with troubleshooting Work Folders.

## PARAMETERS

### -ADFSUrl
Specifies the link, as a URL, of the Active Directory Federation Services (ADFS) for authentication .
If you do not specify this parameter, the cmdlet uses the default Windows authentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ADFSAuthenticationUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdministratorEmail
Specifies a semicolon-separated list of email addresses of the administrators of the Sync Share server.
Sync Server sends the email addressed to the client so the client can contact the administrator to report issues and to receive help troubleshooting the issues.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the Sync Share server.
The description appears in Server Manager and in Windows PowerShell.
The description does not appear to users.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MinimumChangeDetectionMins
Specifies the time, in minutes, before the Sync Share server detects changes on devices and syncs the client and server.
The default value is 5 minutes.
The minimum value that you can set is 1 minute.

The Sync Share server synchronizes with multiple devices for potentially many users.
Increasing the frequency that Sync Share detects changes on devices and syncs the client and server results in fresher data on the devices of users.
However, this increases the load on the Sync Share server and can affect the performance of the synchronization, particularly for users who make frequent changes to the files directly on the server and who have many devices.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -SuspendedUser
Specifies a list of users who are not permitted to synchronize on this server.
Needs to be valid user or security-enabled group.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DeniedAccount, BlockedUser

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SyncServerSetting
This cmdlet returns an object that changes the synchronization configuration on the local server.

## NOTES

## RELATED LINKS

[Get-SyncServerSetting](./Get-SyncServerSetting.md)
