---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 7B50DA56-FCFF-458D-9509-27001D232E00
manager: dansimp
---

# Set-WssMediaServerEnabled

## SYNOPSIS
Enables or disables media streaming on a server.

## SYNTAX

```
Set-WssMediaServerEnabled [-Enable] <Boolean>
```

## DESCRIPTION
The **Set-WssMediaServerEnabled** cmdlet enables or disables media streaming for the current server.
You can use the Get-WssMediaServerEnabled cmdlet to see the status of media streaming.

## EXAMPLES

### Example 1: Disable media streaming
```
PS C:\> Set-WssMediaServerEnabled -Enable $False
```

This command disables media streaming for the current server.

## PARAMETERS

### -Enable
Indicates whether the cmdlet enables or disables media streaming.
Use a value of $True to enable media streaming, or a value of $False to disable it.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaServerEnabled](./Get-WssMediaServerEnabled.md)

