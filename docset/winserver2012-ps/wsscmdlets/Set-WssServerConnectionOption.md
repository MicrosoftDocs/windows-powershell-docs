---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssserverconnectionoption?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssServerConnectionOption

## SYNOPSIS
Modifies the server connection option.

## SYNTAX

```
Set-WssServerConnectionOption -Option <String>
```

## DESCRIPTION
The **Set-WssServerConnectionOption** cmdlet modifies the server connection option in sbs_sbs8_2.
WSS supports the use of a terminal session directly to the server (RemoteDesktop) or the use of the dashboard as a remote application (RemoteApp).

## EXAMPLES

### Example 1: Set the connection option
```
PS C:\> Set-WssServerConnectionOption -Option RemoteDesktop
```

This command sets the connection option for the WSS server to RemoteDesktop.

## PARAMETERS

### -Option
Specifies the server connection option.
Valid values for this parameter are: RemoteDesktop or RemoteApp.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssServerConnectionOption](./Get-WssServerConnectionOption.md)

