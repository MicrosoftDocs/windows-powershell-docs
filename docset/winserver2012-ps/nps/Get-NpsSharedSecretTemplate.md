---
external help file: NPS_Cmdlets.xml
Module Name: NPS
online version: https://docs.microsoft.com/powershell/module/nps/get-npssharedsecrettemplate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NpsSharedSecretTemplate

## SYNOPSIS
Returns a list of available shared secret templates.

## SYNTAX

```
Get-NpsSharedSecretTemplate [-Name <String>]
```

## DESCRIPTION
The **Get-NpsSharedSecretTemplate** cmdlet returns a list of available shared secret templates.
Network Policy Server (NPS) includes a template type that you can use to assign a shared secret when you configure a Remote Authentication Dial-In User Service (RADIUS) client or server.

A shared secret is a text string that serves as a password between a Remote Authentication Dial-In User Service (RADIUS) client and a RADIUS server, a RADIUS client and a RADIUS proxy, or a RADIUS proxy and a RADIUS server.
RADIUS clients, servers, and proxies use shared secrets to verify that the RADIUS messages they receive originate with a RADIUS-enabled device that is configured with the same shared secret.

## EXAMPLES

### Example 1: Get shared secrets templates from a Network Policy Server
```
PS C:\>$NPSSharedSecrets01 = Get-NPSSharedSecretTemplate
```

This command gets the shared secrets templates from an NPS and puts them in the variable named **$NPSSharedSecrets01**.

## PARAMETERS

### -Name
Specifies the name of the shared secret template to return.
If you do not specify this parameter, the cmdlet returns all shared secret templates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### NpsSharedSecretTemplate[]

## NOTES

## RELATED LINKS



