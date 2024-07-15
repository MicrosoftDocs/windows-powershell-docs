---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbGlobalMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbglobalmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmbGlobalMapping
---

# New-SmbGlobalMapping

## SYNOPSIS
Creates an SMB global mapping.

## SYNTAX

```
New-SmbGlobalMapping [[-LocalPath] <String>] [-RemotePath] <String> -Credential <PSCredential>
 [-Persistent <Boolean>] [-RequireIntegrity <Boolean>] [-RequirePrivacy <Boolean>]
 [-UseWriteThrough <Boolean>] [-FullAccess <String[]>] [-DenyAccess <String[]>]
 [-TransportType <TransportType>] [-SkipCertificateCheck] [-CompressNetworkTraffic <Boolean>]
 [-BlockNTLM <Boolean>] [-TcpPort <UInt16>] [-QuicPort <UInt16>] [-RdmaPort <UInt16>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `New-SmbGlobalMapping` cmdlet creates an SMB global mapping on the SMB client to an SMB share.
Global mappings allow all users to use the same mapping. Its primary use is for Windows Containers.
Global mappings support standalone and failover cluster SMB shares, they don't support DFS
Namespace folder shares.

## EXAMPLES

### Example 1

```powershell
$creds = Get-Credential
New-SmbGlobalMapping -RemotePath "\\fs1.contoso.com\public" -Credential $creds -LocalPath "G:"
```

```output
Status Local Path Remote Path
------ ---------- -----------
OK     G:         \\fs1.contoso.com\public
```

This command will gather the credentials for the global mapping. It then maps the remote share path
`\\fs1.contoso.com\public` to the indicated drive letter. Any users, applications, or containers
can now access data on that drive.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

### -BlockNTLM

Specifies whether to block NT LAN Manager (NTLM) authentication. If this parameter is set to $true,
NTLM authentication will be blocked forcing the connection to use another negotiated authentication
method, such as Kerberos. If set to $false (default), NTLM authentication will be allowed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or
[Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

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

### -CompressNetworkTraffic

Specifies whether to compress network traffic. If this parameter is set to `$true`, network traffic
will be compressed. If set to `$false` (default), network traffic won't be compressed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies a credential gathered with Get-Credential.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyAccess

Specifies which accounts are denied access to the SMB mapping. Multiple accounts can be specified
by supplying a comma-separated list. For example: -NoAccess "NT AUTHORITY\SYSTEM", "contoso\ned".

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullAccess

Specifies which accounts are granted full permission to access the SMB mapping. Use a
comma-separated list to specify multiple accounts. For example: -FullAccess "NT AUTHORITY\SYSTEM",
"contoso\ned".

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPath

Specifies the local driver letter to which the remote path is mapped.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistent

Indicates that this connection is recreated after reboot.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuicPort

Specifies the port number to be used for QUIC protocol connections.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RdmaPort

Specifies the port number to be used for Remote Direct Memory Access (RDMA) protocol connections.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePath

Specifies the remote path that's accessed from this computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireIntegrity

Indicates that SMB signing is required for the mapped drive.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequirePrivacy

Indicates that SMB encryption is required for the mapped drive.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipCertificateCheck

Specifies whether to skip certificate validation when establishing a connection.

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

### -TcpPort

Specifies the port number to be used for Transmission Control Protocol (TCP) connections.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum
throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -TransportType

Specifies the transport protocol to be used for the connection. The accepted values for this
parameter are:

- `None`
- `TCP`
- `QUIC`

```yaml
Type: TransportType
Parameter Sets: (All)
Aliases:
Accepted values: None, TCP, QUIC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseWriteThrough

Indicates that forced unit access (write through) is required and bypasses all OS caches, forcing
IO to disk.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-SmbGlobalMapping](Get-SmbGlobalMapping.md)

[Remove-SmbGlobalMapping](Remove-SmbGlobalMapping.md)
