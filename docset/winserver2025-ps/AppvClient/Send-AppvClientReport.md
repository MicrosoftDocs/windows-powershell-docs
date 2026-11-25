---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/send-appvclientreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Send-AppvClientReport
---

# Send-AppvClientReport

## SYNOPSIS
Sends reporting data from the client.

## SYNTAX

```
Send-AppvClientReport [-NetworkCostAware] [-DeleteOnSuccess] [[-URL] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Send-AppVClientReport** cmdlet sends all the available reporting data to the specified location in XML format.
You can delete the data from the client.
Reporting must be enabled.
By default, the data is sent to the location that is listed in the **ReportingServer** registry value.
This value can be either an UNC Share or the name of the Microsoft Application Virtualization (App-V) Reporting Server.
To override this location, you can specify a location by using the *URL* parameter.
The location can be either an UNC share or the App-V Reporting Server location.

By default, after the data is sent, the data is not deleted from the client and is sent to the reporting server as part of the next scheduled sync, if applicable.
You can specify to delete the data from the client.
If the *DeleteOnSuccess* parameter is specified, the reporting data is deleted from the client.

If the data is successfully sent, this cmdlet displays a success message.

If reporting is not enabled, the cmdlet fails.

If there is no valid location specified, the cmdlet fails.

## EXAMPLES

### Example 1: Send data to previously configured location
```
PS C:\> Send-AppVClientReport
The Application Virtualization Client Report was sent successfully
```

This command sends the data to the location that is configured in the client and does not delete the data after it is sent.

### Example 2: Send data to previously configured location and delete data
```
PS C:\> Send-AppVClientReport -DeleteOnSuccess
Tee Application Virtualization Client Report was sent successfully
```

This command sends the data to the location that is configured in the client and deletes the data after it is sent.

### Example 3: Send data to specified location and delete data
```
PS C:\> Send-AppVClientReport -URL "http://myreportingserver:port" -DeleteOnSuccess
The Application Virtualization Client Report was sent successfully
```

This command sends the data to the location specified by the URL parameter and deletes the data after it is sent.

### Example 4: Send data to incorrect location
```
PS C:\> Send-AppVClientReport -URL "http://incorrectservername:port" -DeleteOnSuccess
The reporting server or share location has not been specified.  You must specify the reporting server or share location using the following format: -Url <location>
```

This command tries to send the data to the location specified by the URL parameter but because the server name is incorrect, the sending action fails and an error is returned.
The data is not deleted.

## PARAMETERS

### -DeleteOnSuccess
Indicates that this cmdlet delete the data after it has been sent.

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

### -NetworkCostAware
Indicates that this cmdlet is network cost aware.

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

### -URL
Specifies the location on the reporting server where client information is saved.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

