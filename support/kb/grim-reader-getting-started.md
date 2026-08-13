---
layout: kb
title_nl: Grim Reader — complete handleiding
title_en: Grim Reader — complete setup guide
title: Grim Reader — handleiding / guide
description: Read from your own sources with Grim Reader — WebDAV (NAS/Nextcloud), an OPDS catalogue, a Grimmory server, or just your own files. Step-by-step for each.
---

<div lang="nl" markdown="1">

Grim Reader is een complete e-reader die leest uit **je eigen bronnen** — een
NAS of Nextcloud (WebDAV), een OPDS-catalogus, een Grimmory-server, of gewoon je
eigen bestanden. De app praat alleen met de server die jij instelt — er zit geen
account of cloud van ons tussen.

Je hebt alleen de **Grim Reader**-app op je iPhone of iPad nodig, plus één bron
naar keuze (of geen). Kies hieronder je bron en volg de stappen.

## Inhoud
{: #inhoud-nl}

- [Je eigen bestanden — geen server nodig](#bestanden-nl)
- [WebDAV — een NAS of Nextcloud](#webdav-nl)
- [OPDS — een eigen catalogus (zoals Calibre-Web)](#opds-nl)
- [Grimmory — een eigen boekenserver](#grimmory-nl)
- [De app instellen — toegankelijkheid en taal](#instellen-nl)
- [Werkt er iets niet?](#hulp-nl)

Welke bron past bij jou?

- **Heb je een NAS** (Synology, QNAP) of een **Nextcloud**? → WebDAV.
- **Heb je een boekserver met een OPDS-feed**, zoals Calibre-Web? → OPDS.
- **Draai je Grimmory**, of wil je dat opzetten? → Grimmory.
- **Wil je gewoon losse boeken lezen**, zonder server? → Je eigen bestanden.

Je kunt meerdere bronnen tegelijk gebruiken; ze staan samen onder
**Instellingen → Servers**.

---

## Je eigen bestanden — geen server nodig
{: #bestanden-nl}

Grim Reader werkt volledig zonder server. Boeken die je zelf toevoegt,
verschijnen onder **Mijn boeken**, en de Start- en Auteurs-schermen vullen zich
automatisch met je eigen collectie.

Er zijn twee manieren om een boek toe te voegen:

- **Vanuit de Bestanden-app** — tik op de **+**-knop in *Mijn boeken* en kies een
  EPUB of PDF ergens in de Bestanden-app (iCloud Drive, Op mijn iPhone/iPad, een
  USB-stick, …).
- **"Open met…"** — deel een EPUB of PDF vanuit een andere app (Mail, Safari, een
  chat-app) en kies **Grim Reader**.

Het boek wordt in de app gekopieerd, de omslag en details worden uit het bestand
zelf gelezen, en het blijft offline beschikbaar.

> **Even rondkijken?** Tik op **Offline demo bekijken** onder **Instellingen** om
> de app te bekijken met een paar voorbeeldboeken, zonder iets in te stellen.

---

## WebDAV — een NAS of Nextcloud
{: #webdav-nl}

Grim Reader leest EPUB's, PDF's, strips (CBZ) en audioboeken rechtstreeks van een
**WebDAV**-server — bijvoorbeeld een NAS (Synology, QNAP) of een Nextcloud-share.
Grote audioboeken speel je rechtstreeks van de server, zonder ze eerst helemaal
te downloaden.

### Een server toevoegen

1. Open **Instellingen → Servers**.
2. Tik op **Server toevoegen** en kies **WebDAV-server**.
3. Vul in:
   - **Naam** — wat je wilt, gewoon een label.
   - **Adres** — het WebDAV-adres van de map die je boeken bevat (zie de tip
     hieronder).
   - **Gebruikersnaam** en **wachtwoord** — je login voor die server.
4. Tik op **Verbinding testen** om het adres en de login te controleren, en dan
   **Bewaar**.

Je wachtwoord wordt veilig bewaard in de **sleutelhanger**, niet in de
instellingen van de app. Om een server later te bewerken of te verwijderen, veeg
je 'm naar links in de serverlijst. WebDAV-servers kun je er zo veel toevoegen als
je wilt.

> **Belangrijk — wijs het adres naar de map, niet naar de root.** Veel servers
> (QNAP in het bijzonder) tonen hun shares niet als je de WebDAV-*root* opent,
> waardoor de app een lege lijst zou tonen. Vul het adres **inclusief de share of
> map** in die je boeken bevat — bijvoorbeeld
> `https://mijn-nas.example.com:5006/Ebooks` in plaats van alleen
> `https://mijn-nas.example.com:5006`. Zorg op een QNAP dat de **WebDAV**-dienst
> aan staat en noteer de poort die het gebruikt.

### De statusiconen

Naast elke server in de **Servers**-lijst toont een klein icoon de status,
gecontroleerd elke keer dat je Instellingen opent:

- een groen **vinkje** — de server is bereikbaar en je login werkt;
- een oranje **waarschuwing** — de app kan er niet bij (server offline, verkeerd
  adres of wachtwoord);
- een draaitolletje — de verbinding wordt gecontroleerd.

Je ziet mogelijk ook een groen **potlood**: de app heeft schrijftoegang en kan een
eigen kleine privémap op de server bijhouden voor boek- en auteursgegevens. Een
**slotje** betekent dat de share alleen-lezen is — boeken werken nog, de app kan
er alleen geen extra metadata opslaan.

### Al je boeken zien, downloaden en lezen

Tik op een WebDAV-server om één overzicht te openen van **elk boek erop**,
verzameld uit al zijn mappen en getoond als een raster met omslagen, titels en
auteurs. De app leest elk boek één keer om de omslag en details uit het bestand te
halen. Dit overzicht wordt **op je toestel onthouden**, zodat het niet elke keer de
hele server hoeft te scannen:

- **Vernieuwen** (de ronde pijl) scant de server opnieuw op nieuwe of verwijderde
  boeken.
- **Per map bladeren** (het map-icoon) opent de klassieke map-voor-map-weergave als
  je liever zelf door de structuur navigeert.

Open een boek voor de details en **Download** het. Gedownloade boeken verschijnen
onder **Mijn boeken** en blijven offline beschikbaar.

---

## OPDS — een eigen catalogus
{: #opds-nl}

OPDS is een open standaard voor boekencatalogi. Veel boekservers bieden er een —
bijvoorbeeld **Calibre-Web** — en Grim Reader kan er rechtstreeks doorheen
bladeren. Grim Reader levert zelf geen boeken of catalogi mee: je wijst je eigen
bron aan.

1. Open **Instellingen → Servers**.
2. Tik op **Server toevoegen** en kies **OPDS-catalogus**.
3. Vul in:
   - **Naam** — een label naar keuze.
   - **Feed-URL** — het OPDS-adres van de catalogus, bijvoorbeeld
     `https://mijn-calibre.example.com/opds`. Gebruik `https://`; iOS blokkeert
     onbeveiligde `http://`-adressen, behalve op je eigen lokale netwerk.
   - **Gebruikersnaam** en **wachtwoord** — alleen als de catalogus een login
     vereist. Leeg laten mag.
4. Tik op **Bewaar**. Het wachtwoord gaat in de **sleutelhanger**, niet in de
   app-instellingen.

De catalogus verschijnt nu in de **Servers**-lijst. Tik erop om erdoorheen te
bladeren, en open een boek om het rechtstreeks in **Mijn boeken** te downloaden.

> **Zoeken.** Grim Reader vraagt de catalogus zelf om zijn zoekadres, dus meestal
> werkt zoeken vanzelf. Doet het dat niet, dan kun je bij het bewerken van de
> catalogus een **zoek-URL** invullen met `{searchTerms}` op de plek van de
> zoekterm.

> **Alleen jouw bronnen.** Voeg alleen catalogi toe die je vertrouwt en waarvan je
> de boeken mag downloaden — bijvoorbeeld je eigen Calibre-Web-server of een
> publiek-domeincatalogus. De app controleert de inhoud van een catalogus niet.

---

## Grimmory — een eigen boekenserver
{: #grimmory-nl}

[Grimmory](https://grimmory.org) is een zelf-gehoste server voor je
boekenverzameling, met bibliotheken, series, schrijvers en planken. Grim Reader
toont die structuur precies zoals je 'm op de server ordent.

### 1. Een Grimmory-server draaien

Heb je nog geen Grimmory-server, zet die dan eerst op. De eenvoudigste en
aanbevolen manier is met **Docker**. De officiële image is
**`grimmory/grimmory:latest`** op Docker Hub, en je draait 'm met een
`docker-compose.yml` die Grimmory op twee dingen op je machine wijst:

- een **data**-map, waar Grimmory zijn instellingen bewaart;
- een of meer **boeken**-mappen, waar je eigen bestanden staan.

Grimmory scant je boekenmap, leest de metadata (titel, auteur, serie, omslag) en
bouwt je bibliotheek.

> **Volg het officiële compose-bestand.** Grimmory heeft ook een
> database-container nodig, en exacte poorten, volumes en omgevingsvariabelen
> veranderen na verloop van tijd — zet het dus op met de actuele
> `docker-compose.yml` van de bron in plaats van een commando uit je hoofd te
> kopiëren. De installatiegids en een actueel voorbeeld staan op
> **[grimmory.org](https://grimmory.org)**; de image is
> [`grimmory/grimmory`](https://hub.docker.com/r/grimmory/grimmory) op Docker Hub.

Zodra Grimmory draait, open je het in een webbrowser (meestal op een poort als
`6060`), maak je je **eerste gebruiker** aan en voeg je minstens één bibliotheekmap
toe. Noteer het **adres** en je **gebruikersnaam** en **wachtwoord** — die heb je
zo nodig.

### 2. Inloggen

1. Open Grim Reader en ga naar **Instellingen → Server toevoegen → Grimmory-server**.
2. Vul het **adres** in — lokaal (`192.168.1.10:6060`) of extern
   (`https://books.example.com`).
3. Vul je **gebruikersnaam** en **wachtwoord** in en log in.

Je bibliotheken verschijnen automatisch. Je serveradres en login worden veilig
bewaard in je **iCloud-sleutelhanger**, zodat je andere Apple-toestellen je
bibliotheek automatisch oppikken. Grim Reader logt op één Grimmory-server tegelijk
in; om te wisselen log je uit en opnieuw in met het nieuwe adres.

### 3. Hoe het samenwerkt

- **Bibliotheken** — elke bibliotheekmap die je op de server maakt, verschijnt als
  een eigen item in de zijbalk (iPad) of bladerlijst (iPhone).
- **Series en auteurs** — Grimmory leest die uit de metadata; belandt een boek
  verkeerd, pas het dan op de server aan (of gebruik de beheertools hieronder) en
  het wordt overal bijgewerkt. Onder **Instellingen → Series** kun je series met
  maar een paar boeken verbergen.
- **Planken** — een **plank** is een met de hand samengestelde collectie op de
  server; een **slimme plank** (fonkel-icoon) vult zichzelf op basis van regels die
  je in Grimmory instelt. Beide verschijnen in hun eigen sectie.

### 4. Beheeropties (op eigen risico)

Log je in als **Grimmory-beheerder**, dan toont Grim Reader een extra sectie
**Onderhoud** in Instellingen met tools die rechtstreeks op de bibliotheek van je
server ingrijpen.

> **⚠️ Op eigen risico.** Deze acties wijzigen of verwijderen gegevens op je
> Grimmory-server en sommige zijn niet ongedaan te maken. Maak eerst een back-up
> van je Grimmory-datamap, en begin met een kleine, omkeerbare wijziging.

De onderhoudstools: dubbele boeken opruimen, auteurs samenvoegen, series
samenvoegen, taalcodes standaardiseren, auteur-metadata verrijken via Wikipedia,
ontbrekende auteurs of omslagen invullen, en auteurs zonder boeken verwijderen.
Omdat ze je hele bibliotheek in één keer raken: back-up maken, één tool draaien,
resultaat controleren, dan verder.

---

## De app instellen
{: #instellen-nl}

### Toegankelijkheid

De leeservaring is sterk instelbaar onder **Instellingen**.

- **Dynamic Type** — zet *Tekstgrootte volgt iOS* aan zodat de lezer de
  tekstgrootte gebruikt die je systeembreed in iOS hebt ingesteld. Liever per app?
  Zet dat uit en gebruik de tekstgrootte-regelaar in de app zelf.
- **OpenDyslexic-lettertype** — een lettertype dat makkelijker leesbaar is voor
  mensen met dyslexie. Andere keuzes zijn klassieke boek-schreefletters (Georgia,
  Palatino, Iowan, Charter) en een schreefloos systeemlettertype.
- **Leesthema's** — Systeem, Licht, Sepia, Donker of **Hoog contrast** (puur zwart
  op wit).
- **Regelafstand** — vergroot de ruimte tussen regels als dichte tekst lastig te
  volgen is.
- **Voorlezen** — Grim Reader kan boeken voorlezen met de iOS-stemmen, met een
  instelbare **leessnelheid**. Voorlezen gaat door met het **scherm vergrendeld**,
  met afspeelknoppen, titel en omslag op het vergrendelscherm. Op iPhone gaat het
  ook door als je naar het beginscherm of een andere app gaat; houd op iPad de app
  op de voorgrond of vergrendel het scherm. (Audioboeken spelen overal op beide.)
- **VoiceOver** — de app werkt met Apples ingebouwde schermlezer.

### Taal

Grim Reader is beschikbaar in het **Nederlands** en **Engels**.

- **App-taal** — de app volgt je iOS-taalinstellingen. Om alleen deze app te
  wijzigen, open je **Instellingen → Taal** in Grim Reader en tik je door naar de
  iOS-instellingen voor de app.
- **Snel taalfilter** — tijdens het bladeren filtert een kleine taalbalk je
  bibliotheek op de taal van de boeken zelf.

---

## Werkt er iets niet?
{: #hulp-nl}

Loop je ergens vast, ga dan naar **[Help &amp; support](/support/)** om een
probleem te melden, een verbetering voor te stellen of een vraag te stellen.

</div>

<div lang="en" markdown="1">

Grim Reader is a complete e-reader that reads from **your own sources** — a NAS
or Nextcloud (WebDAV), an OPDS catalogue, a Grimmory server, or simply your own
files. The app talks only to the server you set up — there is no account or cloud
of ours in between.

All you need is the **Grim Reader** app on your iPhone or iPad, plus one source of
your choice (or none). Pick your source below and follow the steps.

## Contents
{: #contents-en}

- [Your own files — no server needed](#files-en)
- [WebDAV — a NAS or Nextcloud](#webdav-en)
- [OPDS — your own catalogue (such as Calibre-Web)](#opds-en)
- [Grimmory — your own book server](#grimmory-en)
- [Setting up the app — accessibility and language](#settings-en)
- [Something not working?](#help-en)

Which source fits you?

- **Have a NAS** (Synology, QNAP) or **Nextcloud**? → WebDAV.
- **Have a book server with an OPDS feed**, like Calibre-Web? → OPDS.
- **Running Grimmory**, or want to set it up? → Grimmory.
- **Just want to read standalone books**, no server? → Your own files.

You can use several sources at once; they live together under
**Settings → Servers**.

---

## Your own files — no server needed
{: #files-en}

Grim Reader works entirely without a server. Books you add yourself appear under
**My books**, and the Start and Authors screens fill up with your own collection
automatically.

There are two ways to add a book:

- **From the Files app** — tap the **+** button in *My books* and pick an EPUB or
  PDF from anywhere in the Files app (iCloud Drive, On My iPhone/iPad, a USB
  stick, …).
- **"Open with…"** — share an EPUB or PDF from any other app (Mail, Safari, a
  messaging app) and choose **Grim Reader**.

The book is copied into the app, its cover and details are read from the file
itself, and it stays available offline.

> **Just looking around?** Tap **View offline demo** under **Settings** to explore
> the app with a few sample books, without setting anything up.

---

## WebDAV — a NAS or Nextcloud
{: #webdav-en}

Grim Reader reads EPUBs, PDFs, comics (CBZ) and audiobooks straight from a
**WebDAV** server — for example a NAS (Synology, QNAP) or a Nextcloud share. Large
audiobooks stream straight from the server, without downloading them in full
first.

### Add a server

1. Open **Settings → Servers**.
2. Tap **Add server** and choose **WebDAV server**.
3. Fill in:
   - **Name** — anything you like, just a label.
   - **Address** — the WebDAV address of the folder that contains your books
     (see the tip below).
   - **Username** and **password** — your login for that server.
4. Tap **Test connection** to check the address and login, then **Save**.

Your password is stored securely in the **Keychain**, not in the app's settings.
To edit or remove a server later, swipe left on it in the Servers list. You can add
as many WebDAV servers as you like.

> **Important — point the address at the folder, not the root.** Many servers
> (QNAP in particular) don't list their shares when you open the WebDAV *root*, so
> the app would show an empty list. Enter the address **including the share or
> folder** that holds your books — for example
> `https://my-nas.example.com:5006/Ebooks` rather than just
> `https://my-nas.example.com:5006`. On a QNAP, make sure the **WebDAV** service is
> enabled and note the port it uses.

### The status icons

Next to each server in the **Servers** list a small icon shows its status, checked
every time you open Settings:

- a green **check** — the server is reachable and your login works;
- an orange **warning** — the app can't reach it (server offline, wrong address or
  password);
- a spinner — the connection is being checked.

You may also see a green **pencil**: the app has write access and may keep a small
private folder of its own on the server for book and author details. A **lock**
means the share is read-only — books still work, the app just can't store extra
metadata there.

### See all your books, download and read

Tap a WebDAV server to open a single overview of **every book on it**, gathered
from across all its folders and shown as a grid with covers, titles and authors.
The app reads each book once to pull its cover and details out of the file. This
overview is **remembered on your device**, so it doesn't have to scan the whole
server every time:

- **Refresh** (the circular arrow) rescans the server for new or removed books.
- **Browse by folder** (the folder icon) opens the classic folder-by-folder view
  if you'd rather navigate the structure yourself.

Open any book to see its details, then **Download** it. Downloaded books appear
under **My books** and stay available offline.

---

## OPDS — your own catalogue
{: #opds-en}

OPDS is an open standard for book catalogues. Many book servers offer one — for
example **Calibre-Web** — and Grim Reader can browse it directly. Grim Reader ships
no books or catalogues of its own: you point it at your own source.

1. Open **Settings → Servers**.
2. Tap **Add server** and choose **OPDS catalogue**.
3. Fill in:
   - **Name** — a label of your choice.
   - **Feed URL** — the catalogue's OPDS address, for example
     `https://my-calibre.example.com/opds`. Use `https://`; iOS blocks insecure
     `http://` addresses, except on your own local network.
   - **Username** and **password** — only if the catalogue requires a login. Leave
     empty otherwise.
4. Tap **Save**. The password goes into the **Keychain**, not the app settings.

The catalogue now appears in the **Servers** list. Tap it to browse through it, and
open a book to download it straight into **My books**.

> **Search.** Grim Reader asks the catalogue for its own search address, so search
> usually works automatically. If it doesn't, you can enter a **search URL** when
> editing the catalogue, with `{searchTerms}` where the search term goes.

> **Your sources only.** Only add catalogues you trust and whose books you're
> allowed to download — for example your own Calibre-Web server or a public-domain
> catalogue. The app doesn't vet a catalogue's contents.

---

## Grimmory — your own book server
{: #grimmory-en}

[Grimmory](https://grimmory.org) is a self-hosted server for your book collection,
with libraries, series, authors and shelves. Grim Reader shows that structure
exactly as you organise it on the server.

### 1. Run a Grimmory server

If you don't have a Grimmory server yet, set that up first. The simplest and
recommended way is with **Docker**. The official image is
**`grimmory/grimmory:latest`** on Docker Hub, and you run it with a
`docker-compose.yml` that points Grimmory at two things on your machine:

- a **data** folder, where Grimmory keeps its settings;
- one or more **book** folders, where your actual files live.

Grimmory scans your book folder, reads the metadata (title, author, series, cover)
and builds your library.

> **Follow the official compose file.** Grimmory also needs a database container,
> and exact ports, volumes and environment variables change over time — so set it
> up with the current `docker-compose.yml` from the source rather than copying a
> command from memory. The install guide and an up-to-date example are on
> **[grimmory.org](https://grimmory.org)**; the image is
> [`grimmory/grimmory`](https://hub.docker.com/r/grimmory/grimmory) on Docker Hub.

Once Grimmory is running, open it in a web browser (usually on a port like
`6060`), create your **first user** and add at least one library folder. Make a
note of the **address** and your **username** and **password** — you'll need them
next.

### 2. Sign in

1. Open Grim Reader and go to **Settings → Add server → Grimmory server**.
2. Enter the **address** — local (`192.168.1.10:6060`) or remote
   (`https://books.example.com`).
3. Enter your **username** and **password** and sign in.

Your libraries appear automatically. Your server address and login are stored
securely in your **iCloud Keychain**, so your other Apple devices pick up your
library automatically. Grim Reader signs in to one Grimmory server at a time; to
switch, log out and sign in again with the new address.

### 3. How it works

- **Libraries** — each library folder you create on the server shows up as its own
  entry in the sidebar (iPad) or browse list (iPhone).
- **Series and authors** — Grimmory reads these from the metadata; if a book lands
  wrong, fix it on the server (or use the admin tools below) and it updates
  everywhere. Under **Settings → Series** you can hide series with only a few
  books.
- **Shelves** — a **shelf** is a hand-picked collection on the server; a **smart
  shelf** (sparkle icon) fills itself based on rules you set in Grimmory. Both
  appear in their own section.

### 4. Admin options (use at your own risk)

If you sign in as a **Grimmory administrator**, Grim Reader shows an extra
**Maintenance** section in Settings with tools that act directly on your server's
library.

> **⚠️ Use at your own risk.** These actions change or remove data on your
> Grimmory server and some cannot be undone. Back up your Grimmory data folder
> first, and start with a small, reversible change.

The maintenance tools: clean up duplicates, merge authors, merge series,
standardise language codes, enrich author metadata via Wikipedia, fill in missing
authors or covers, and remove authors without books. Because they touch your whole
library at once: back up, run one tool, check the result, then continue.

---

## Setting up the app
{: #settings-en}

### Accessibility

The reading experience is highly adjustable under **Settings**.

- **Dynamic Type** — turn on *Text size follows iOS* so the reader uses the text
  size you've set system-wide in iOS. Prefer per-app? Turn that off and use the
  in-app text-size control.
- **OpenDyslexic font** — a typeface designed to be easier to read for people with
  dyslexia. Other choices include classic book serifs (Georgia, Palatino, Iowan,
  Charter) and a sans-serif system font.
- **Reading themes** — System, Light, Sepia, Dark or **High contrast** (pure black
  on white).
- **Line spacing** — increase the space between lines if dense text is hard to
  track.
- **Read aloud** — Grim Reader can read books to you using the iOS voices, with an
  adjustable **reading speed**. Reading aloud keeps going with the **screen
  locked**, with playback controls, title and cover on the Lock Screen. On iPhone
  it also keeps going when you switch to the Home Screen or another app; on iPad,
  keep the app in the foreground or lock the screen. (Audiobooks play everywhere on
  both.)
- **VoiceOver** — the app works with Apple's built-in screen reader.

### Language

Grim Reader is available in **Dutch** and **English**.

- **App language** — the app follows your iOS language settings. To change just
  this app, open **Settings → Language** in Grim Reader and tap through to the iOS
  settings for the app.
- **Quick language filter** — when browsing, a small language bar filters your
  library by the language of the books themselves.

---

## Something not working?
{: #help-en}

If you get stuck at any step, head to **[Help &amp; support](/support/)** to report
a problem, suggest an improvement or ask a question.

</div>
