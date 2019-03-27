---
external help file: SMISConfig_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 48F983FE-A8EA-4A2E-9CAF-A6B41B990EB9
manager: dansimp
---

# Search-SmisProvider

## SYNOPSIS
Searches for a list of SMI-S providers.

## SYNTAX

```
Search-SmisProvider [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Search-SmisProvider** cmdlet searches for Storage Management Initiative - Specification (SMI-S) providers available on the same subnet as your server as long as they are advertised through the Service Location Protocol v2 (SLPv2).
The cmdlet returns a list of Uniform Resource Identifiers (URIs) that you can use with other cmdlets to register or remove a provider.
If the cmdlet finds no SMI-S providers, it returns nothing.

To register a provider, use the **Register-SmisProvider** cmdlet.
To remove a registered provider so that it can no longer be used, use the **Unregister-SmisProvider** cmdlet.
Both cmdlets take a URI as input.

## EXAMPLES

### Example 1: Search for an SMI-S provider
```
PS C:\>Search-SmisProvider
```

This command searches for all SMI-S providers on the same subnet as the server.

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

### System.Uri[]
The URI represents the list of devices that the cmdlet discovered.

## NOTES

## RELATED LINKS

[Register-SmisProvider](./Register-SmisProvider.md)

[Unregister-SmisProvider](./Unregister-SmisProvider.md)

[Get-StorageProvider](../Storage2_Cmdlets/Get-StorageProvider.md)

