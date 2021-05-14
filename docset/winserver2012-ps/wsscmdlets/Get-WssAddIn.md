---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssaddin?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssAddIn

## SYNOPSIS
Gets installed add-ins.

## SYNTAX

```
Get-WssAddIn [[-Id] <Guid>]
```

## DESCRIPTION
The **Get-WssAddIn** cmdlet gets the add-ins for an installed package.
If you do not specify the **Id** parameter, the cmdlet gets all installed add-ins on the local computer.

## EXAMPLES

### Example 1: Get all installed add-ins
```
PS C:\> Get-WssAddIn
```

This command gets all add-ins installed on the local computer.

## PARAMETERS

### -Id
Specifies the GUID for an installed package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### PackageInfo

## NOTES

## RELATED LINKS

[Install-WssAddIn](./Install-WssAddIn.md)

[Uninstall-WssAddIn](./Uninstall-WssAddIn.md)

