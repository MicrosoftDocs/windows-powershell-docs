---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMultichannelConnection.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbmultichannelconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbMultichannelConnection
---

# Get-SmbMultichannelConnection

## SYNOPSIS
Retrieves the SMB connections made between the SMB client network interfaces and the SMB server network interfaces.

## SYNTAX

```
Get-SmbMultichannelConnection [[-ServerName] <String[]>] [-IncludeNotSelected] [-SmbInstance <SmbInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbMultichannelConnection** cmdlet retrieves the Server Message Block (SMB) connections made between the SMB client network interfaces and the SMB server network interfaces.
This cmdlet provides information about how the SMB multi-channel pairs the client and the server network interfaces and which pairs are selected to use for the SMB connections.

## EXAMPLES

### Example 1: Get connections
```
PS C:\>Get-SmbMultichannelConnection
Server Name    Selected       Client IP      Server IP      Client         Server         Client RSS     Client RDMA
                                                            Interface      Interface      Capable        Capable
                                                            Index          Index
-----------    --------       ---------      ---------      -------------- -------------- -------------- --------------
Contoso-SO     True           192.168.102.13 192.168.102.11 15             15             False          True
Contoso-SO     True           192.168.101.13 192.168.101.11 12             12             False          True
Contoso-FS     True           192.168.101.13 192.168.101.22 12             12             False          True
Contoso-FS     True           192.168.102.13 192.168.102.22 15             15             False          True
Contoso-FS1    True           192.168.102.13 192.168.102.22 15             15             False          True
Contoso-FS1    True           192.168.101.13 192.168.101.22 12             12             False          True
```

This command retrieves the SMB connections made between the SMB client network interfaces and the SMB server network interfaces.

### Example 2: Get connections for a specific server
```
PS C:\>Get-SmbMultichannelConnection -ServerName "Contoso-SO"
Server Name    Selected       Client IP      Server IP      Client         Server         Client RSS     Client RDMA
                                                            Interface      Interface      Capable        Capable
                                                            Index          Index
-----------    --------       ---------      ---------      -------------- -------------- -------------- --------------
Contoso-SO     True           192.168.102.13 192.168.102.11 15             15             False          True
Contoso-SO     True           192.168.101.13 192.168.101.11 12             12             False          True
```

This command retrieves the SMB connections made between the SMB client network interfaces and the SMB server network interfaces for the SMB server named Contoso-SO.

### Example 3: Get properties for connections for a specific server
```
PS C:\>Get-SmbMultichannelConnection -ServerName "Contoso-SO" | Select -Property *
ClientInterfaceFriendlyName : RDMA2
ClientInterfaceIndex        : 15
ClientIpAddress             : 192.168.102.13
ClientLinkSpeed             : 32000000000
ClientRdmaCapable           : True
ClientRSSCapable            : False
CurrentChannels             : 2
Failed                      : False
FailureCount                : 0
MaxChannels                 : 2
Selected                    : True
ServerInterfaceIndex        : 15
ServerIpAddress             : 192.168.102.11
ServerLinkSpeed             : 32000000000
ServerName                  : Contoso-SO
ServerRdmaCapable           : True
ServerRSSCapable            : False
PSComputerName              :
CimClass                    : ROOT/Microsoft/Windows/SMB:MSFT_SmbMultichannelConnection
CimInstanceProperties       : {ClientInterfaceFriendlyName, ClientInterfaceIndex, ClientIpAddress, ClientLinkSpeed...}
CimSystemProperties         : Microsoft.Management.Infrastructure.CimSystemProperties

ClientInterfaceFriendlyName : RDMA1
ClientInterfaceIndex        : 12
ClientIpAddress             : 192.168.101.13
ClientLinkSpeed             : 32000000000
ClientRdmaCapable           : True
ClientRSSCapable            : False
CurrentChannels             : 2
Failed                      : False
FailureCount                : 0
MaxChannels                 : 2
Selected                    : True
ServerInterfaceIndex        : 12
ServerIpAddress             : 192.168.101.11
ServerLinkSpeed             : 32000000000
ServerName                  : Contoso-SO
ServerRdmaCapable           : True
ServerRSSCapable            : False
PSComputerName              :
CimClass                    : ROOT/Microsoft/Windows/SMB:MSFT_SmbMultichannelConnection
CimInstanceProperties       : {ClientInterfaceFriendlyName, ClientInterfaceIndex, ClientIpAddress, ClientLinkSpeed...}
CimSystemProperties         : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command retrieves all of the information about the SMB connections made between the SMB client network interfaces and the SMB server network interfaces for the SMB server named Contoso-SO.

### Example 4: Get all connections for a specific server
```
PS C:\>Get-SmbMultichannelConnection -ServerName "Contoso-SO" -IncludeNotSelected
Server Name    Selected       Client IP      Server IP      Client         Server         Client RSS     Client RDMA
                                                            Interface      Interface      Capable        Capable
                                                            Index          Index
-----------    --------       ---------      ---------      -------------- -------------- -------------- --------------
Contoso-SO     True           192.168.102.13 192.168.102.11 15             15             False          True
Contoso-SO     False          192.168.102.13 192.168.102.11 15             15             True           False
Contoso-SO     True           192.168.101.13 192.168.101.11 12             12             False          True
Contoso-SO     False          192.168.101.13 192.168.101.11 12             12             True           False
Contoso-SO     False          192.168.100.13 192.168.100.11 14             14             False          False
Contoso-SO     False          172.30.182.10  192.168.102.11 32             15             False          False
Contoso-SO     False          172.30.182.10  192.168.102.11 32             15             False          False
Contoso-SO     False          172.30.182.10  192.168.100.11 32             14             False          False
Contoso-SO     False          172.30.182.10  192.168.101.11 32             12             False          False
Contoso-SO     False          172.30.182.10  192.168.101.11 32             12             False          False
```

This command retrieves the all of the connections made between the SMB client network interfaces and the SMB server network interfaces for the SMB server named Contoso-SO.

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

### -IncludeNotSelected
Indicates the client and server network interface combinations which are not selected are used by SMB are also enumerated.

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

### -ServerName
Specifies that the multi-channel connections made to the given server are enumerated.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: (All)
Aliases:
Accepted values: Default, CSV, SBL, SR

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbMultiChannelConnection
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
The **MSFT_SmbMultiChannelConnection** object represents a pair of a client and a server network interface.

## NOTES

## RELATED LINKS

[Update-SmbMultichannelConnection](./Update-SmbMultichannelConnection.md)

