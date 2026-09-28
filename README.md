# SymyOnBot

SymyOnBot is the web reader of **SymyOn**, an experimental AI research system run by one person for personal,
non-commercial research. It is not a service, a search engine or a crawler that builds an index: it reads a few pages
to learn about a subject, and cites them.

Every request it makes carries the user agent `SymyOnBot/1.0` with a link to this page.

## How it behaves

* **robots.txt**: it reads a page only when the rules for `SymyOnBot` and for `\*` both allow it. A disallow aimed at
a known AI crawler (GPTBot, ClaudeBot, CCBot, Google-Extended and others) is honoured too.
* **Text and data mining reservations**: `/.well-known/tdmrep.json`, the `tdm-reservation` header, and `noai` or
`noimageai` in a robots meta tag or an `X-Robots-Tag` header. A reserved page is not read.
* **A slow pace**: one page of a site at a time, at least 3 seconds apart (longer when robots.txt asks for a
`Crawl-delay`), at most 50 pages of a site in any 24 hours, and at most 20 pages of a site for one subject.
* **It backs off**: after a 401, 403 or 429, or a block page, it leaves the site alone (a 429's `Retry-After` is
honoured) and never changes its identity to get around a limit.
* **Never**: logging in, creating accounts, accepting terms, filling in forms, buying anything, solving a CAPTCHA,
going around a paywall or a login, or downloading programs or code.
* **What it keeps**: notes, facts, citations and short quotes with their source. Never a copy of a page, never
republished.
* It never reads LinkedIn, Facebook, Instagram, WhatsApp, Messenger, Threads, X or TikTok.

## How to block it

Add this to your site's `robots.txt`:

```
User-agent: SymyOnBot
Disallow: /
```

Or reserve your pages for text and data mining (TDMRep, or `<meta name="robots" content="noai">`).

## Contact

Write to **supportinprenotation.info@gmail.com** about anything SymyOnBot did on your site, or to ask what SymyOn keeps about you, to object to it, or to have it deleted.

\---

## SymyOnBot (italiano)

SymyOnBot è il lettore web di **SymyOn**, un sistema di ricerca sperimentale di intelligenza artificiale gestito da
una persona per ricerca personale, senza scopi commerciali. Legge poche pagine per imparare un argomento e le cita.
Rispetta robots.txt (per `SymyOnBot`, per `\*` e per i crawler IA noti), le riserve di text and data mining (TDMRep,
`noai`), un ritmo lento (una pagina alla volta per sito, almeno 3 secondi tra una e l'altra, al massimo 50 pagine di
un sito in 24 ore) e si ferma dopo un 401, 403 o 429. Non accede mai con un account, non compila moduli, non risolve
CAPTCHA, non aggira paywall e non scarica programmi. Conserva appunti e brevi citazioni con la fonte, mai copie delle
pagine.

Per bloccarlo: `User-agent: SymyOnBot` e `Disallow: /` nel tuo `robots.txt`. Per qualsiasi richiesta (anche per
sapere cosa SymyOn conserva su di te, opporti o farlo cancellare): **supportinprenotation.info@gmail.com** 

