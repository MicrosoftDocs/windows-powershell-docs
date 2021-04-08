---
author: Kateyanne
external help file: SmbShare_Cmdlets.xml
manager: dansimp
Module Name: SmbShare
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/smbshare/update-smbmultichannelconnection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Update-SmbMultichannelConnection

## SYNOPSIS
Forces the Server Message Block (SMB) client to update the multi-channel-related information.

## SYNTAX

```
Update-SmbMultichannelConnection [[-ServerName] <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Update-SmbMultichannelConnection** cmdlet forces the Server Message Block (SMB) client to update the multi-channel-related information.
To do this the SMB client will communicate with one or more servers to which it is connected, to get the latest information on the network interfaces that is shared.
If a server name is provided, then the SMB client will communicate with only that server to get the information.
If no parameter is provided, then the SMB client will communicate with all of the servers to which it is connected.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Update-SmbMultichannelConnection
```

This example forces the SMB client to update the multi-channel-related information.

### EXAMPLE 2
```
PS C:\>Update-SmbMultichannelConnection -ServerName Contoso-SO
```

This example forces the SMB client to update the multi-channel-related information for the SMB server named Contoso-SO.

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
Specifies the name of the server to which to connect from the SMB client to get the latest information on the network interfaces it has.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)

