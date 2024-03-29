---
external help file: NPS_Cmdlets.xml
Module Name: NPS
online version: https://learn.microsoft.com/powershell/module/nps/remove-npsradiusclient?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NpsRadiusClient

## SYNOPSIS
Removes a RADIUS client.

## SYNTAX

```
Remove-NpsRadiusClient [-Name] <String>
```

## DESCRIPTION
The **Remove-NpsRadiusClient** cmdlet removes a Remote Authentication Dial-In User Service (RADIUS) client.
A RADIUS client uses a RADIUS server to manage authentication, authorization, and accounting requests that the client sends.
A RADIUS client can be an access server, such as a dial-up server or wireless access point, or a RADIUS proxy.

## EXAMPLES

### Example 1: Remove a RADIUS client
```
PS C:\>Remove-NpsRadiusClient -Name "RadiusClient01"
```

This command removes a RADIUS client named RadiusClient01.

## PARAMETERS

### -Name
Specifies the name of the RADIUS client to remove.

```yaml
Type: String
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

### None

## NOTES

## RELATED LINKS

[Get-NpsRadiusClient](./Get-NpsRadiusClient.md)

[New-NpsRadiusClient](./New-NpsRadiusClient.md)

[Set-NpsRadiusClient](./Set-NpsRadiusClient.md)



