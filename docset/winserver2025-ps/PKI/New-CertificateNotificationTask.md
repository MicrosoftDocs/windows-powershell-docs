---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
Module Name: PKI
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pki/new-certificatenotificationtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-CertificateNotificationTask
---

# New-CertificateNotificationTask

## SYNOPSIS
Creates a new task in the Task Scheduler that will be triggered when a certificate is replaced,
expired, or about to expired.

## SYNTAX

```
New-CertificateNotificationTask -Type <CertificateNotificationType>
 [-RunTaskForExistingCertificates] -PSScript <String> -Name <String>
 -Channel <NotificationChannel> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `New-CertificateNotificationTask` cmdlet creates a new task in the Task Scheduler that will be
triggered when a certificate is replaced or expires. The task will launch the script specified by
the **PSScript** parameter.

If the **RunTaskForExistingCertificates** parameter is specified, then after this cmdlet is
registered, the cmdlet will go through all certificates (including archived certificates) in the My
store and initiate `Replace` events for all certificates with a Renewal property. The `NewCertHash`
value will always be the one at the end of the renewal chain. For example; if certificate A was
renewed to certificate B, which was then renewed to certificate C, then the cmdlet fires two events:
certificate A to certificate C and certificate B to certificate C. This will ensure that
applications that are still using old certificates are properly updated to the newest certificates.
If any certificate has a renewal chain longer than 20, then the certificate is not logged.

## EXAMPLES

### EXAMPLE 1

```powershell
$params = @{
    PSScript = 'C:\myscript.ps1'
    Channel = 'System'
    Type = 'Replace'
    Name = 'My System Certificate Task'
}
New-CertificateNotificationTask @params
```

This example creates a system notification task for certificate replacement events with the name
`My System Certificate Task` that will launch the `C:\myscript.ps1` script. The cmdlet will run on
the local system.

### EXAMPLE 2

```powershell
$params = @{
    PSScript = 'C:\myscript.ps1'
    Channel = 'User'
    Type = 'Expire'
    Name = 'My User Certificate Task'
}
New-CertificateNotificationTask @params
```

This example creates a system notification task for the expiration and close-to-expiration
certificate events with the name `My User Certificate Task` that will launch the `C:\myscript.ps1`.
The cmdlet will run for all currently logged on users in the user contexts.

## PARAMETERS

### -Channel

Sets the channel of the **CertificateServicesClient-Notifications** log that will be monitored for
certificate lifecycle events. The acceptable values for this parameter are:

- `System`: The **Operation-System** channel will be used. This channel should be used to modify
  system certificate bindings that use computer certificates.

- `User`: The **Operational-User** channel will be used. This channel should be used to modify user
  certificate bindings.

```yaml
Type: Microsoft.CertificateServices.Commands.NotificationChannel
Parameter Sets: (All)
Aliases:
Accepted values: System, User

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the unique name for the certificate notification task. If a certificate notification task
with the same name already exists, then an error is generated.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSScript

Identifies the Windows PowerShell script that will be triggered by the certificate notification
task. The script will be launched with the **NonInteractive** parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunTaskForExistingCertificates

Generates a replacement notification for any certificate in the My store that has been replaced in
the past. For the notification to be generated both certificates must be present in the store. This
parameter can only be used with the `Replace` type.

> [!NOTE]
> The following warning is displayed when this parameter set to `False` and there are some
> certificates in MY store that would have resulted in a notification.
>
> ```Output
> There are certificates in My store that have been replaced in the past. You can use the
> New-CertificateNotification cmdlet with the RunTaskForExistingCerts parameter to generate
> notifications for those certificates to correct any configuration problems that you may already
> have on this machine.
> ```

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Specifies the type of events that will trigger certificate notifications. The acceptable values for
this parameter are:

- `Replace`: Certificate replacement events will trigger this notification, including certificates
  that are renewed by auto-enrollment, using the Certificates snap-in, or by using the
  `Switch-Certificate` cmdlet.

- `Expire`: Certificate expiration and close-to-expire events will trigger this notification.

```yaml
Type: Microsoft.CertificateServices.Commands.CertificateNotificationType
Parameter Sets: (All)
Aliases:
Accepted values: Replace, Expire

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Command.CertificateNotificationTask

A **CertificateNotificationTask** object that contains details about a newly created task.

## NOTES

## RELATED LINKS

[Get-CertificateNotificationTask](./Get-CertificateNotificationTask.md)

[Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)

[Switch-Certificate](./Switch-Certificate.md)
