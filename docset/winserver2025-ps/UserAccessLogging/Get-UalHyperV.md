---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_HyperV.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualhyperv?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalHyperV
---

# Get-UalHyperV

## SYNOPSIS
Gets UAL information about virtual machines.

## SYNTAX

```
Get-UalHyperV [-ProductName <String[]>] [-RoleName <String[]>] [-RoleGuid <String[]>] [-UUID <String[]>]
 [-ChassisSerialNumber <String[]>] [-FirstSeen <DateTime[]>] [-LastSeen <DateTime[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalHyperV** cmdlet gets User Access Logging (UAL) information about virtual machines hosted on Microsoft® Hyper-V® Server 2016.
Use the *CimSession* parameter to run the cmdlet on a remote server.
Use this cmdlet only for servers that host virtual machines.
UAL polls Hyper-V Server 2016 for data every 24 hours.

This cmdlet gets the virtual machine Universally Unique Identifier (UUID) for virtual machines hosted on a server, the name of the server product, and chassis serial number of the host server.
This cmdlet also gets the creation time for a virtual machine and the most recent time the virtual machine ran on the Hyper-V Server 2016 server.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get information about virtual machines
```
PS C:\>Get-UalHyperV
```

This command gets UAL virtual machine records for the current server.

## PARAMETERS

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

### -ChassisSerialNumber
Specifies an array of strings.
Each member contains the chassis serial number of a server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -FirstSeen
Specifies an array of dates, as **DateTime** objects.
A time represents when the virtual machine first existed.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LastSeen
Specifies an array of dates, as **DateTime** objects.
A time represents the most recent time when UAL logged a virtual machine.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductName
Specifies an array of names of products.
The installed role or specific product in the request is a component of this product.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleGuid
Specifies an array of GUIDs for roles that client's access.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleName
Specifies an array of names for roles that client's access.

```yaml
Type: String[]
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

### -UUID
Specifies an array of UUIDs for servers.
Each UUID refers to the virtual machine.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UalOverview](./Get-UalOverview.md)

[Get-UalServerDevice](./Get-UalServerDevice.md)

[Get-UalServerUser](./Get-UalServerUser.md)

[Get-UalDns](./Get-UalDns.md)

[Get-Ual](./Get-Ual.md)

