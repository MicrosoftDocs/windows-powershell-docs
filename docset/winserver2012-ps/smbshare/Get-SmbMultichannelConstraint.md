---
author: Kateyanne
external help file: SmbShare_Cmdlets.xml
manager: dansimp
Module Name: SmbShare
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/smbshare/get-smbmultichannelconstraint?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SmbMultichannelConstraint

## SYNOPSIS
Retrieves the constraints that define how the Server Message Block (SMB) client uses network interfaces to connect to the servers.

## SYNTAX

```
Get-SmbMultichannelConstraint [[-ServerName] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-SmbMultichannelConstraint** cmdlet retrieves the constraints that define how the Server Message Block (SMB) client uses network interfaces to connect to the servers.

## EXAMPLES

### EXAMPLE 1
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

This example retrieves the constraints that define how the SMB client uses network interfaces to connect to the servers.

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
Aliases: 

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
Position: 2
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

