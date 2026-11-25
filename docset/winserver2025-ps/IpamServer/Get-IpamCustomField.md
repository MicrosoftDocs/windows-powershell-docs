---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCustomField.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamcustomfield?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamCustomField
---

# Get-IpamCustomField

## SYNOPSIS
Gets custom fields in IPAM.

## SYNTAX

```
Get-IpamCustomField [[-Name] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamCustomField** gets information about custom fields in IP Address Management (IPAM).
If you do not specify the *Name* parameter, this cmdlet retrieves all the custom fields in IPAM.
For multivalued custom fields, the cmdlet retrieves the custom field objects and the associated custom values.

## EXAMPLES

### Example 1: Get all custom fields
```
PS C:\> Get-IpamCustomField
Name                 Category               Multivalue          CustomValue
----------------------------------------------------------------------------------------------------------------------------
AdSite                BuiltIn               False
CountryOrRegion       BuiltIn               True                {Afghanistan, Alfand Islands,...}
.....
.....
```

This command retrieves all the built-in and user defined custom fields in the IPAM server.
For multivalued fields, the command retrieves the custom field objects and the associated custom value objects.

### Example 2: Get a custom field
```
PS C:\> Get-IpamCustomField -Name "ManagedByService"
Name                 Category               Multivalue          CustomValue
----------------------------------------------------------------------------------------------------------------------------
ManagedByService      BuiltIn                True               {IPAM,MS DHCP,Non-MS DHCP...}
```

This command retrieves the custom field named ManagedByService and then gets the corresponding custom value.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Name
Specifies the name of a custom field.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamCustomField
This cmdlet returns an object that contains an IPAM custom field.

## NOTES

## RELATED LINKS

[Add-IpamCustomField](./Add-IpamCustomField.md)

[Add-IpamCustomValue](./Add-IpamCustomValue.md)

