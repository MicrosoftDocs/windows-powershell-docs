---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_SmisProvider_v1.0.cdxml-help.xml
Module Name: SMISConfig
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/smisconfig/unregister-smisprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-SmisProvider
---

# Unregister-SmisProvider

## SYNOPSIS
Removes a registered SMI-S provider.

## SYNTAX

```
Unregister-SmisProvider -ConnectionUri <Uri> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-SmisProvider** removes a registered Storage Management Initiative - Specification (SMI-S) provider so that it cannot be used.
If you remove a provider, you also delete any stored credentials and clear the credential cache for that provider.
If a certificate was accepted from the provider, it remains in the certificate store.
It can be manually removed using the Certificates snap-in.

If the URI does not identify a registered provider, this cmdlet returns an error.

To obtain the SMI-S providers on the same subnet as a server, use the Search-SmisProvider cmdlet.
This cmdlet returns a list of providers.

## EXAMPLES

### Example 1: Remove an SMI-S provider
```
PS C:\> Unregister-SmisProvider -ConnectionUri https://smis.contoso.com:5989
```

This command removes a registered SMI-S provider by using the URI of the provider.

### Example 2: Remove an SMI-S provider by its object instance
```
PS C:\>Get-StorageProvider -Name "smis.contoso.com" | Unregister-SmisProvider
```

This command removes a registered SMI-S provider by using an existing storage provider instance and passing it to the Unregister-SmisProvider cmdlet, by using the pipeline operator.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of a registered provider.
You must use the same URI as was used for the Register-SmisProvider cmdlet.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: URI

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
The Force switch specifies whether to suppress warning and confirmation messages. It can be useful in scripting to suppress interactive prompts. If the Force switch isn't provided in the command, you're prompted for administrative input if required.

```yaml
Type: SwitchParameter
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Uri

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Register-SmisProvider](./Register-SmisProvider.md)

[Search-SmisProvider](./Search-SmisProvider.md)

[Get-StorageProvider](../storage/Get-StorageProvider.md)

