---
external help file: SMISConfig_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 82D7C783-EE46-46A1-AC2C-A6FD93FD1184
manager: dansimp
---

# Unregister-SmisProvider

## SYNOPSIS
Removes a registered SMI-S provider.

## SYNTAX

```
Unregister-SmisProvider [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -ConnectionUri <Uri>
```

## DESCRIPTION
The **Unregister-SmisProvider** removes a registered Storage Management Initiative - Specification (SMI-S) provider so that it cannot be used.
When you remove a provider, you also delete any stored credentials and clear the credential cache for that provider.
If a certificate was accepted from the provider, it will remain in the certificate store.
It can be manually removed using the Certificates snap-in.

If the URI does not identify a registered provider, the cmdlet returns an error.

To obtain a list of SMI-S providers on the same subnet as a server, use the **Search-SmisProvider** cmdlet.
This cmdlet returns a list of providers.

## EXAMPLES

### Example 1: Remove an SMI-S provider
```
PS C:\> Unregister-SmisProvider -ConnectionUri https://smis.contoso.com:5989
```

This command removes a registered SMI-S provider by using the URI of the provider.

### Example 2: Remove an SMI-S provider by its object instance
```
PS C:\>Get-StorageProvider smis.contoso.com | Unregister-SmisProvider
```

This command removes a registered SMI-S provider by using an existing storage provider instance and passing it to the Unregister-SmisProvider cmdlet, by using the pipe operator.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of a registered provider.
You must use the same URI as was used during the Register-SmisProvider cmdlet.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Register-SmisProvider](./Register-SmisProvider.md)

[Search-SmisProvider](./Search-SmisProvider.md)

[Get-StorageProvider](../Storage2_Cmdlets/Get-StorageProvider.md)

