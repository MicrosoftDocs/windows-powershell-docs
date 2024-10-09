---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMultichannelConstraint.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbmultichannelconstraint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbMultichannelConstraint
---

# Get-SmbMultichannelConstraint

## SYNOPSIS
Retrieves the constraints that define how the SMB client uses network interfaces to connect to the servers.

## SYNTAX

```
Get-SmbMultichannelConstraint [[-ServerName] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbMultichannelConstraint** cmdlet retrieves the constraints that define how the Server Message Block (SMB) client uses network interfaces to connect to the servers. This constraint applies to the Default instance of SMB used for normal sharing. It does not apply to SMB-using application instances like Storage Replica, Storage Spaces Direct SBL, or CSV.

## EXAMPLES

### Example 1: Get multichannel constraints
```
PS C:\>Get-SmbMultichannelConstraint
InterfaceAlias : RDMA1
InterfaceGuid  : {597b0a73-2b66-4be0-9e6d-f42eae8a35d6}
InterfaceIndex : 12
ServerName     : Contoso-SO
PSComputerName :

InterfaceAlias : RDMA2
InterfaceGuid  : {bd3c4a04-64cf-4205-88f5-38c4c35dfc38}
InterfaceIndex : 15
ServerName     : Contoso-SO
PSComputerName :
```

This command retrieves the constraints that define how the SMB client uses network interfaces to connect to the servers.

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

### -ServerName
Specifies the constraints for the specified server being returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbMultichannelConstraint
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The MSFT_SmbMultichannelConstraint object represents the constraints that define how the SMB client uses the network interfaces to connect to servers.

## NOTES

## RELATED LINKS

[New-SmbMultichannelConstraint](./New-SmbMultichannelConstraint.md)

[Remove-SmbMultichannelConstraint](./Remove-SmbMultichannelConstraint.md)

