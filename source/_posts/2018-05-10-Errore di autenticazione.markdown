---
title: Errore di autenticazione
date: 2018-05-10 12:07:24 Z
categories:
- CredSSP
- Oracle
- autenticazione
layout: post
---

Se provate a connettervi in remoto su una macchina  e ricevete "errore di autenticazione". 

{% highlight shell_session %}
La causa potrebbe essere la Correzione crittografia Oracle per CredSSP.
{% endhighlight %}

Potete provare a risolvere aggiungendo una chiave sul registro e riavviare il pc. Nella fattispecie:

{% highlight shell_session %}
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\CredSSP\Parameters] 
"AllowEncryptionOracle"=dword:00000002
{% endhighlight %}


