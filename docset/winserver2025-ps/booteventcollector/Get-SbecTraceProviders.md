---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/get-sbectraceproviders?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SbecTraceProviders
---

# Get-SbecTraceProviders

## SYNOPSIS
Gets the ETW trace providers.

## SYNTAX

```
Get-SbecTraceProviders [-Uncached] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecTraceProviders** cmdlet gets the list of ETW trace providers, building the hash tables for translation from name to GUID and back.

**Get-SbecTraceProviders** returns a hash table with the following nested hash tables:

- `<ByName>`: Finds the provider object by name.
- `<ByGuid>`: Finds the provider object by GUID.
- `<NameToGuid>`: Translation of provider name (key) to GUID string (value).
- `<GuidToName>`: Translation of provider GUID (key) to name (value).

Curly braces are added to the GUIDs when they are converted to strings.

The returned hash table is also saved as a cache, and is returned on subsequent calls.
If any new providers are defined, they are added to the cache (and thus to the previously returned references to it) on subsequent calls.

## EXAMPLES


## PARAMETERS

### -Uncached
Indicates that this operation bypasses the cache.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### hash table

## NOTES

## RELATED LINKS

[Clear-SbecProviderCache](./Clear-SbecProviderCache.md)

