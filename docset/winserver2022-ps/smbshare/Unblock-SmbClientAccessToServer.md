---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbClientAccessToServer.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/unblock-smbclientaccesstoserver?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-SmbClientAccessToServer
---

# Unblock-SmbClientAccessToServer

## SYNOPSIS
Unblocks SMB client access to a previously blocked server.

## SYNTAX

### Query

```
Unblock-SmbClientAccessToServer [-Name] <String[]> -IdentifierType <IdentifierType>
 -Identifier <String> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Unblock-SmbClientAccessToServer -InputObject <CimInstance[]> -IdentifierType <IdentifierType>
 -Identifier <String> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Unblock-SmbClientAccessToServer` cmdlet is used to allow SMB clients to access a server that
was previously blocked using the `Block-SmbClientAccessToServer` cmdlet. When you run this cmdlet,
any existing block on SMB client connections to the specified server will be lifted, and new
connections will be allowed.

## EXAMPLES

### Example 1: Unblock SMB client access to a server

```powershell
$params = @{
    Name = "Server01"
    IdentifierType = "ISSUER"
    Identifier = "CN=MyCertificateIssuer"
    Force = $true
}
Unblock-SmbClientAccessToServer @params
```

This command unblocks SMB client access to a server named `Server01` for the based on the client's
certificate. This command runs without prompting for confirmation as the **Force** parameter is set
to `$true`.

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

### -Force

Forces the command to run without asking for user confirmation.

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

### -Identifier

Specifies the identity of the client that is being granted access to the SMB server. This parameter
takes a string value that represents the identity of the client. The format of the string value
will depend on the **IdentifierType** parameter that you're using.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentifierType

Specifies the type of identifier that you're using to identify a client. The valid values for the
**IdentifierType** parameter are:

- SHA256
- ISSUER

If you're using the `SHA256` identifier type, you're specifying a hash value that uniquely
identifies the client. If you're using the `ISSUER` identifier type, you're specifying the issuer
of the client's certificate.

```yaml
Type: IdentifierType
Parameter Sets: (All)
Aliases:
Accepted values: SHA256, ISSUER

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the input object that's used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies a fully-qualified DNS name or NetBIOS name that must match the certificate's subject name
or an entry in the certificate's subject alternative names.

```yaml
Type: String
Parameter Sets: Query
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

## NOTES

## RELATED LINKS

[Block-SmbClientAccessToServer](Block-SmbClientAccessToServer.md)

[Get-SmbClientAccessToServer](Get-SmbClientAccessToServer.md)

[Grant-SmbClientAccessToServer](Grant-SmbClientAccessToServer.md)

[Revoke-SmbClientAccessToServer](Revoke-SmbClientAccessToServer.md)
