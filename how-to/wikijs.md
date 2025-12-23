---
title: WikiJS
description: Kurzer Guide zu diesem Wiki
published: 1
date: 2025-12-23T20:22:17.687Z
tags: 
editor: markdown
dateCreated: 2025-12-23T20:21:01.462Z
---

## Ein Wiki nicht wie Wikipedia 

Unter einem Wiki stellt man sich normalerweise unendlich viele verknuepfte Textseiten vor. Aber ich seh das hier mehr als eine Plattform, auf der man seine Projekte oder auch nur kleine Experimente teilen und sich darueber dann in den Kommentaren austauschen kann. Die einzelnen Pages sind dabei der Container, in die man seine Praesentation einbettet. Dazu habe ich unter Playground einige Beispiele zusammengestellt, wie das aussehen koennte.

## Native Wiki Funktionen

Dieses Wiki hab ich gewaehlt, weil es sehr einfach aufgebaut ist, trotzdem von Haus aus viele Funktionen bietet und sich "guenstig" hosten laesst. Die ganzen Pages werden z.b. in einem [Github Repository](https://github.com/Golden-Apple-Researcher/wikijs)* gespeichert, das ganze Auth Zeugs wird von [Keycloak via OIDC] gehandelt und als DB haette ich eigentich auch direkt [SupaBase](https://supabase.com) statt SQlite nehmen koennen. 

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
Ich versteh zwar nicht, wieso da kein Wrapper eingebaut wurde, aber ist jetzt halt so. Dafuer lassen sich global im Header noch Script Tags platzlieren, dort hab ich einfach mal for teh lulz [AlpineJS](https://alpinejs.dev) und Mithrill gesourced. Die beiden Frameworks sollten sich also in den script Tags wie oben beschrieben, ohne weitere import oder sonstiges, direkt inline in Pages verwenden lassen. 

<div x-data="{ open: false }">
    <button @click="open = true">Expand</button>
 
    <span x-show="open">
        Content...
    </span>
</div>
## Playground




\* Leider laeuft das nach meinem Gefuehl nicht so wie ich das gerne haette. Github ist wohl eher darauf ausgelegt,  Repositories zu clonen, mergen, committen etc. Aber es gibt auch die Moeglichkeit einzelne Files aus einem Repository ueber das CDN [JSDeliver zu beziehen](https://terryjett.com/need-to-know/post/using-github-to-jsdelivr-cdn). Bzw. der Link muesste jeweils nur von [https://github.com](https://github.com/Golden-Apple-Researcher/wikijs) auf [https://cdn.jsdelivr.net/gh](https://cdn.jsdelivr.net/gh/Golden-Apple-Researcher/wikijs/) geaendert werden. Wie Storage Module funktionieren wird [hier erklaert](https://docs.requarks.io/dev/storage) und hier die [Module im Repository](https://github.com/requarks/wiki/tree/main/server/modules/storage). 

Aber ebenso bin ich auf der anderen Seite gerade noch damit beschaeftigt, den Caddy Revproxy mit Redis als Cache einzurichten, was aber auch wieder Zeit braucht, dafuer aber verspricht auch Latenzprobleme anderer Apps zu beheben. Und eigentlich wollte ich ja gerade hier ein paar Worte zu diesem Wiki verlieren.....