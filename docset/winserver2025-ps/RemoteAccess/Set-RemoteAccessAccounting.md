---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessAccounting_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-remoteaccessaccounting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-RemoteAccessAccounting
---

# Set-RemoteAccessAccounting

## SYNOPSIS
Sets the enabled state for inbox and RADIUS accounting for both external RADIUS and Windows accounting and configures the settings when enabled.

## SYNTAX

### EnableAccounting (Default)
```
Set-RemoteAccessAccounting [-ComputerName <String>] [-PassThru] [-RadiusServer <String>]
 [-SharedSecret <String>] [-RadiusPort <UInt16>] [-RadiusScore <Byte>] [-RadiusTimeout <UInt32>]
 [-AccountingOnOffMsg <String>] [-EnableAccountingType] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableAccounting
```
Set-RemoteAccessAccounting -DisableAccountingType <String> [-ComputerName <String>] [-PassThru]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RemoteAccessAccounting** cmdlet sets the enabled state for inbox and RADIUS accounting for both external RADIUS and Windows accounting and configures the settings when enabled.

The accounting configuration is globally applicable, such as if a particular kind of accounting is Enabled or Disabled, then that particular kind of accounting is Enabled or Disabled on all Remote Access (RA) servers in the corporate network.
The associated configuration is also applicable for all of the corporate network.

 -- All RA servers have the same configured accounting RADIUS servers.

 -- The default limit set for the inbox accounting store size is the same on all RA servers.

Therefore, this cmdlet is not impacted by a multi-site deployment.

Both inbox accounting and RADIUS accounting can be active at the same time.
RADIUS accounting includes Windows accounting, external RADIUS accounting and accounting on the local Network Policy Server (NPS), but only one type of accounting can be active at any time.
The **RadiusServer**, **SharedSecret**, **RadiusPort**, **RadiusScore**, **RadiusTimeout**, and **AccountingOnOffMsg** parameters are applicable only when RADIUS accounting is Enabled and cannot be specified when inbox accounting is Enabled.

The following is the behavior associated with enabling External RADIUS accounting.

 -- If there is a VPN deployment with accounting enabled and if DirectAccess (DA) is installed on the same RA server then accounting is automatically enabled for DA also and the configuration remains unchanged.
Note: If Windows Accounting is enabled for VPN, then it will not work for DA as this is not a supported configuration for DA.
For accounting to work for DA in this scenario either NPS needs to be installed locally or an external RADIUS server needs to be configured for accounting.
The external radius server can be added using the Add-RemoteAccessRadius cmdlet.

 -- If user does not specify a RADIUS server then this cmdlet automatically configures Windows accounting: Note: In this scenario, for accounting to work for DA, NPS needs to be installed on the RA server.

Switching from Windows Accounting to external RADIUS accounting and switching from external RADIUS accounting to Windows Accounting.

 -- If the current configuration is Windows accounting a user can switch to external RADIUS accounting by doing one of the following:

 ---- Run the same cmdlet to enable RADIUS accounting and specify an external RADIUS server

 ---- Add an external RADIUS server using the Add-RemoteAccessRadius cmdlet.
This enables RADIUS accounting without running this cmdlet.

 -- A user can switch back to Windows accounting by deleting all the configured external RADIUS servers.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-RemoteAccessAccounting -EnableAccountingType Inbox -ComputerName edge2 -PassThru
WARNING-GPO updates cannot be applied to edge2.corp.contoso.com. Changes will not take effect until the next policy refresh.
RadiusAccountingStatus          : Disabled
RemoteRadiusServerList          :
InboxAccountingStatus           : Enabled
InboxStoreLimit                 : 12m
InboxStoreUsedBytes             : 0
InboxStoreUsedBytesInPercentage : 0
InboxStoreFreeBytes             : 4282318848
InboxStoreFreeBytesInPercentage : 99.7055053710938
InboxStoreFirstRecordDate       : 12/17/2011 6:53:24 PM
InboxStoreLastRecordDate        : 12/17/2011 6:53:24 PM

The accounting store is configured to retain data for up to 2 years.
PS C:\>Set-RemoteAccessInboxAccountingStore -StoreLimit 2y
```

This example enables inbox accounting for this deployment.
The RA server on which this cmdlet is run is specified using the **ComputerName** parameter.

### EXAMPLE 2
```
PS C:\>Set-RemoteAccessAccounting -EnableAccountingType ExternalRadius -RadiusServer radius1.corp.contoso.com -RadiusTimeout 5 -SharedSecret s3cr3t -RadiusPort 1813 -RadiusScore 30
RadiusAccountingStatus          : ExternalRadius
RemoteRadiusServerList          : {radius1.corp.contoso.com}
InboxAccountingStatus           : Enabled
InboxStoreLimit                 : 12m
InboxStoreUsedBytes             : 0
InboxStoreUsedBytesInPercentage : 0
InboxStoreFreeBytes             : 4282318848
InboxStoreFreeBytesInPercentage : 99.7055053710938
InboxStoreFirstRecordDate       : 12/17/2011 6:53:24 PM
InboxStoreLastRecordDate        : 12/17/2011 6:53:24 PM
```

This example configures RA to use RADIUS accounting with configuration parameters.

### EXAMPLE 3
```
PS C:\>Set-RemoteAccessAccounting -DisableAccountingType ExternalRadius
RadiusAccountingStatus          : Disabled
RemoteRadiusServerList          :
InboxAccountingStatus           : Enabled
InboxStoreLimit                 : 12m
InboxStoreUsedBytes             : 0
InboxStoreUsedBytesInPercentage : 0
InboxStoreFreeBytes             : 4282318848
InboxStoreFreeBytesInPercentage : 99.7055053710938
InboxStoreFirstRecordDate       : 12/17/2011 6:53:24 PM
InboxStoreLastRecordDate        : 12/17/2011 6:53:24 PM
```

This example disables RADIUS accounting while still retaining inbox accounting.

## PARAMETERS

### -AccountingOnOffMsg
Specifies the enabled state for the sending of accounting on and off messages.
The acceptable values for this parameter are:

 -- Enabled.

 -- Disabled.

The default value is Disabled.

```yaml
Type: String
Parameter Sets: EnableAccounting
Aliases:
Accepted values: Enabled, Disabled

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the RA server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -DisableAccountingType
Indicates the accounting type that has to be disabled.
The acceptable values for this parameter are:

 -- Inbox.

 -- ExternalRadius.

```yaml
Type: String
Parameter Sets: DisableAccounting
Aliases:
Accepted values: Inbox, ExternalRadius

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableAccountingType
Indicates the accounting type that needs to be enabled.
The acceptable values for this parameter are:

 -- Inbox: The store size is set to 12 months automatically.
The Set-RemoteAccessInboxAccountingStore cmdlet is used to change the store size on individual RA servers.

 -- ExternalRadius: Can also be used to enable Windows Accounting or Accounting on the NPS installed locally on the same computer.

```yaml
Type: String
Parameter Sets: EnableAccounting
Aliases:
Accepted values: Inbox, ExternalRadius

Required: True
Position: 1
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

### -RadiusPort
Specifies the port number on which the RADIUS server is accepting authentication requests.

The default value is 1813.

This parameter can be configured only if the **EnableAccountingType** parameter is specified to be ExternalRadius.

```yaml
Type: UInt16
Parameter Sets: EnableAccounting
Aliases: Port

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusScore
Specifies the initial score.

The default value is 30.

This parameter can be configured only if the **EnableAccountingType** parameter is specified to be ExternalRadius.

```yaml
Type: Byte
Parameter Sets: EnableAccounting
Aliases: Score

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServer
Specifies the IPv4 or IPv6 address, or host name, of the external RADIUS server that is used for accounting.
This parameter can be configured only if the **EnableAccountingType** parameter is specified to be ExternalRadius.

```yaml
Type: String
Parameter Sets: EnableAccounting
Aliases: ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusTimeout
Specifies the time in seconds that the RA server waits for a response from the RADIUS server before the RA server tries to connect to the next RADIUS server.
The default value is 5.
Specify this parameter only if you specify ExternalRadius for the **EnableAccountingType** parameter.

```yaml
Type: UInt32
Parameter Sets: EnableAccounting
Aliases: Timeout

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret between the RA server and the specified external RADIUS server which is required for successful communication between the two servers.
Note: The secret is specified in clear text.
This parameter can be configured only if the **EnableAccountingType** parameter is specified to be ExternalRadius.

```yaml
Type: String
Parameter Sets: EnableAccounting
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

### System.String

### System.UInt16

### System.Byte

### System.UInt32

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessAccounting

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessAccounting object consists of the following properties:

 -- The status of RADIUS accounting (Disabled, Windows, or ExternalRadius) and the list of RADIUS servers in the case of ExternalRadius accounting.
If there is no external radius accounting enabled, then the list of Radius servers is empty.

 -- The status of inbox accounting (Enabled or Disabled) and the associated properties.

 -- Time span of the store.

 -- Number of used bytes.

 -- Percentage of used bytes.

 -- Number of free bytes.

 -- Percentage of free bytes.

 -- Time stamp of the first record in the database.

 -- Time stamp of the last record in the database.

## NOTES

## RELATED LINKS

[Add-RemoteAccessRadius](./Add-RemoteAccessRadius.md)

[Get-RemoteAccessAccounting](./Get-RemoteAccessAccounting.md)

[Set-RemoteAccessInboxAccountingStore](./Set-RemoteAccessInboxAccountingStore.md)

