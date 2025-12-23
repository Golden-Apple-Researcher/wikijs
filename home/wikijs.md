---
title: WikiJS
description: Kurzer Guide zu diesem Wiki
published: 1
date: 2025-12-23T23:24:04.024Z
tags: 
editor: markdown
dateCreated: 2025-12-23T20:21:01.462Z
---

## Ein Wiki zum experimentieren

Unter einem Wiki stellt man sich normalerweise unendlich viele verknuepfte Textseiten vor. Aber ich seh das hier mehr als eine Plattform, auf der man seine Projekte oder auch nur kleine Experimente teilen und sich darueber dann in den Kommentaren austauschen kann. Die einzelnen Pages sind dabei der Container, in die man seine Praesentation einbettet. Dazu habe ich unter Playground einige Beispiele zusammengestellt, wie das aussehen koennte.

Dieses Wiki hab ich gewaehlt, weil es sehr einfach aufgebaut ist, trotzdem von Haus aus viele Funktionen bietet und sich "guenstig" hosten laesst. Die ganzen Pages werden z.b. in einem [Github Repository](https://github.com/Golden-Apple-Researcher/wikijs)* gespeichert, das ganze Auth Zeugs wird von [Keycloak via OIDC] gehandelt. Dafuer hat es einige Macken, eine bescheidene Dokumentation und eine alte Codebase, die wohl nur noch im Maintenance Mode ist. Aber das ist bei anderen Wikis meist auch nicht besser und die basieren dann noch auf PHP. 

## Native Wiki Funktionen

Anyway, ein weiterer Vorteil ist die simple, aber flexible [Rendering Pipeline](https://docs.requarks.io/en/rendering). Artikel lassen sich so ganz einfach in Markdown verfassen und bei Bedarf lassen sich einfach HTML Tags verwenden, die auch mitgerendert werden. So reicht:
```
<iframe src="https://some.source.com/index.html" height="1000px" width="100%"></iframe>
```
Und in der gerenderten Page erscheint dann das gewuenschte Iframe. Mit Scripts ist es aehnlich, hier reicht:
```
<script> 
  window.boot.register('page-ready', () => {
      // code to execute
	})
</script>
```
Ich versteh zwar nicht, wieso da kein Wrapper eingebaut wurde, aber ist jetzt halt so.~~Dafuer lassen sich global im Header noch Script Tags platzlieren, dort hab ich einfach mal for teh lulz [AlpineJS](https://alpinejs.dev) und [Mithril](https://mithril.js.org) gesourced. Die beiden Frameworks sollten sich also in den script Tags wie oben beschrieben, ohne weitere import oder sonstiges, direkt inline in Pages verwenden lassen.~~ Oder halt eben auch nicht so einfach ¯\\\_(ツ)_/¯

## [Playground](/playground)

### [Color Mixer](/playground/color-mixer)

Ein plain JS Color Mixer, direkt in der Wikipage umgesetzt, ohne externe Depencies

### [Codesandbox](/playground/codesandbox)

Eine Online IDE die es einfach macht Code, sowohl Backend als auch Frontend ganz, zu teilen. 

### [GrapesJS](/playground/grapesjs)

Ein WYSIWYG Editor mit der Moeglichkeit React Componenten zu verwenden (aber auch VanillaJS oder andere Frameworks...)

### [Huggingface](/playground/huggingface)

Embedding von Huggingface Spaces, also im Prinzip sowas wie Docker Container

### [Jupyter](/playground/jupyter)

Ein Notebook, hier ausgefuehrt im Browser mit einem JavaScript Kernel. 

### [No-Sidebar-Template](/playground/template)

Kann man auswaehlen bei der Erstellung einer neuen Page, geeignet wenn da die eingebetette App ansonsten eingeengt wird. I.e. so wie es bei den anderen Pages im Playground aussieht.

## LLM - Charts

Da keine Woche vergeht, ohne dass das naechste Top Modell in irgendeiner Disziplin released wird, macht es imo wenig Sinn da ueberhaupt irgendwelche Einschaetzungen zu schreiben. Daher sind dort u.a. direkt die Ranglisten der OSS Modelle von Huggingface eingebettet. 

## Tools 

Unter Tools kommen einfach noch einige hilfreiche Online Tools, teils lokal gehostest, teils einfach eingebettet. 90% davon wird man ganz sicher nie brauchen, aber wenn man etwa mal einen JWT parsen, Mermaid zu PNG konvertieren, einen Barcode generieren oder einen QR Code ohne Smartphone lesen muss, oder irgend sonst was exotisches braucht, sind die Chancen gut da das passende Tool zu finden. 

## [N.A.T.I.](/general/nati)

Falls bisher uebersehen, der Punkt rechts unten oeffnet ein Chatfenster. Dort beantwortet N.A.T.I. (Neuronal Artificial Tensor Intelligence) gerne Fragen zum Wiki und dem Projekt insgesamt. 

\* Leider laeuft das nach meinem Gefuehl nicht so wie ich das gerne haette. Github ist wohl eher darauf ausgelegt,  Repositories zu clonen, mergen, committen etc. Aber es gibt auch die Moeglichkeit einzelne Files aus einem Repository ueber das CDN [JSDeliver zu beziehen](https://terryjett.com/need-to-know/post/using-github-to-jsdelivr-cdn). Bzw. der Link muesste jeweils nur von [https://github.com](https://github.com/Golden-Apple-Researcher/wikijs) auf [https://cdn.jsdelivr.net/gh](https://cdn.jsdelivr.net/gh/Golden-Apple-Researcher/wikijs/) geaendert werden. Wie Storage Module funktionieren wird [hier erklaert](https://docs.requarks.io/dev/storage) und hier die [Module im Repository](https://github.com/requarks/wiki/tree/main/server/modules/storage). 

Aber ebenso bin ich auf der anderen Seite gerade noch damit beschaeftigt, den Caddy Revproxy mit Redis als Cache einzurichten, was aber auch wieder Zeit braucht, dafuer aber verspricht auch Latenzprobleme anderer Apps zu beheben. Und eigentlich wollte ich ja gerade hier ein paar Worte zu diesem Wiki verlieren.....