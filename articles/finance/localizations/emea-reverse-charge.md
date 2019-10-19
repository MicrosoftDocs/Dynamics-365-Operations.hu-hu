---
title: Fordított áfa
description: A cikk azt tekinti át, hogyan állítható be fordított áfa az európai országokhoz, Szaúd-Arábiához és Szingapúrhoz.
author: epodkolz
manager: AnnBe
ms.date: 07/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 530ff52abb1dd36c473ae436d61ea925c5696a30
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183689"
---
# <a name="reverse-charge-vat"></a>Fordított áfa


[!include [banner](../includes/banner.md)]


A cikk a fordított áfa európai országokhoz, Szaúd-Arábiához és Szingapúrhoz való beállításának általános leírását adja.

A fordított áfaszámítás egy olyan adózási rendszer, amely az áfa könyvelésének és jelentésének felelősségét a termék vagy szolgáltatás eladójáról a vevőre ruházza. Ezért az áruk és/vagy szolgáltatások fogadói vallják be mind a kimeneti áfát (az eladó szerepében), mind a bemeneti áfát (a beszerző szerepében).

Egyes országokban vagy régiókban a fordított áfafizetés rendszere csak bizonyos termékekre és/vagy szolgáltatásokra érvényes, és további feltételek vagy küszöbök érvényesek az értékesítési összegek függvényében. Más országokban vagy régiókban az áfafizetés felelőssége a beszállító és a vevő állapotától függ. Ha a vevő köteles megfizetni az áfát, akkor ezt egyértelműen jelezni kell a beszállító által kiadott számlán. Például a számlán szerepelnie kell a „Fordított áfa” megjelölésnek, valamint annak, hogy mely pozíciókra érvényes a fordított áfafizetési rendszer. 

A következő beállításokat kell elvégeznie a fordított áfa alkalmazásához.

## <a name="set-up-sales-tax-codes"></a>Áfakódok beállítása
Javasoljuk, hogy külön áfakódokat használjon az értékesítési és beszerzési műveleteknél.

<table>
<body>
<tr>
<td><strong>Áfakód az értékesítésekre vonatkozóan</strong></td>
<td>Hozzon létre áfakódot a fordított áfa fizetésének műveleteihez (<strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Áfakódok</strong>).
</td>
</tr>
<tr>
<td><strong>Áfakód a vásárlásoknál</strong></td>
<td><p>Hozzon létre pozitív és negatív áfakódot a fordított áfa számára a beszerzéseknél (<strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Áfakódok</strong>).</p>
<ol>
<li>Olyan áfakódot létrehozása, amelynek értéke pozitív.</li>
<li>Olyan áfakódot létrehozása, amelynek értéke negatív. Állítsa a <strong>Negatív áfaszázalék engedélyezése</strong> opciót <strong>Igen</strong> értékre.
Ezt a negatív áfakódot egy cikkáfacsoporthoz rendelje hozzá, majd ebbe a cikkáfacsoportba sorolja be azokat a cikkeket, melyeknél a fordított áfafizetés érvényes.</li>
</ol>
<p>További információért lásd a következő szakaszt: &quot;Áfacsoportok és cikkáfacsoportok beállítása&quot;.</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a>Adócsoportok és cikkáfacsoportok beállítása
Javasoljuk, hogy külön áfacsoportokat használjon az értékesítési és beszerzési műveleteknél.

<table>
<tr>
<td><strong>Áfacsoportok az értékesítésekre vonatkozóan</strong></td>
<td>Hozzon létre áfacsoportot a fordított áfát tartalmazó értékesítési műveleteihez (<strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Áfacsoportok</strong>). A <strong>Beállítás</strong> lapon szerepeltesse a csoport költségéhez tartozó áfakódot. Jelölje be az <strong>Adómentes</strong> és a <strong>Fordított adó</strong> négyzetet az áfakódnál.</td>
</tr>
<tr>
<td><strong>Áfacsoportok a beszerzéshez</strong></td>
<td>Hozzon létre áfacsoportot a fordított áfát tartalmazó beszerzési műveleteihez (<strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Áfacsoportok</strong>). A <strong>Beállítás</strong> lapon egyaránt szerepeltesse a csoporthoz tartozó pozitív és negatív áfakódokat. Jelölje be a <strong>Fordított adó</strong> jelölőnégyzetet annál az áfakódnál, amelyiknek negatív az értéke.</td>
</tr>
<tr>
<td><strong>Cikkáfacsoportok</strong></td>
<td>Hozza létre vagy frissítse a cikkáfacsoportot a negatív értékű áfakóddal (<strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Cikkáfacsoportok</strong>). Az alapértelmezett cikkáfacsoportot hozzá kell rendelnie azokhoz a termékekhez és kategóriákhoz, amelyek a fordított fizetés hatálya alá tartoznak.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a>Fordított adózású csoportok beállítása
A **Fordított fizetésű cikkcsoportok** oldalon (**Adó** &gt; **Beállítás** &gt; **Áfa** &gt; **Fordított fizetésű cikkcsoportok**) oldalon termékek vagy szolgáltatások csoportjait határozhatja meg, illetve olyan egyedi termékeket vagy szolgáltatásokat, amelyeknél alkalmazható a fordított adózás. Adja meg mindegyik fordított adózású cikkcsoportnál a cikkek, cikkcsoportok és kategóriák listáját az értékesítéseknél és/vagy vásárlásoknál.

## <a name="set-up-reverse-charge-rules"></a>Adja meg a fordított fizetésekkel kapcsolatos szabályokat.
A **Fordított fizetés szabályai** oldalon (**Adó** &gt; **Beállítás** &gt; **Áfa** &gt; **Fordított fizetés szabályai**) megadhatja az alkalmazhatósági szabályokat a beszerzési és értékesítési célokhoz. Fordított költség-alkalmazhatósági szabályokat is beállíthat. Állítsa be a következő mezőket minden egyes szabálynál:

- **Dokumentumtípus** – Válassza ki: **Beszerzési rendelés**, **Szállítói számla naplója**, **Értékesítési rendelés**, **Szabadszöveges számla**, **Vevői számlanapló**, illetve **Szállítói számla**.
- **Partner országának/régiójának típusa** – Válasszon a **Belföldi**, **EU** és **Külföldi** lehetőségek közül. Emellett ha a szabály minden kereskedelmi partnernél – a címük országától vagy régiójától függetlenül – alkalmazható a szabály, válassza a **Mindegyik** lehetőséget.
- **Belföldi szállítási cím** – Jelölje be ezt a jelölőnégyzetet, ha a szabály az azonos országban vagy régióban lévő szállításokra érvényes. Ez a jelölőnégyzet nem jelölhető be a **Szállítói számla naplója** és a **Vevői számlanapló** dokumentumtípusoknál.
- **Fordított fizetésű cikkcsoport** – Válassza ki a csoportot, amelyiknél alkalmazható a szabály.
- **Küszöbösszeg** – A fordított adózás sémáját csak akkor kell a számlára alkalmazni, ha a fordított adótételek csoportjában szereplő tételek és/vagy szolgáltatások értéke meghaladja az itt megadott értéket.

Az **Érvényesség dátuma** és **Lejárat dátuma** mezőkkel is meghatározhatja a szabály érvényességének időtartamát.

Ezenkívül megadhatja, hogy megjelenjen-e egy értesítés, és a dokumentumsor frissüljön-e az alapértelmezett fordított áfacsoporttal, ha teljesül a dokumentumsor feltétele. Az alábbi lehetőségek közül választhat:

- **Nincs** – A dokumentum nem frissül.
- **Kérdés** – Megjelenik egy értesítés annak megerősítésére, hogy alkalmazható-e a fordított áfa.
- **Beállítás** – A dokumentumsor külön értesítés nélkül frissül.

## <a name="set-up-default-parameters"></a>Alapértelmezett paraméterek beállítása
A fordított áfa funkció engedélyezéséhez a **Főkönyvi paraméterek** oldal **Fordított áfa** lapján állítsa a **Fordított fizetés engedélyezése** opciót **Igen** értékre. A **Beszerzési rendelés áfacsoportja** és az **Értékesítési rendelés áfacsoportja** mezőknél válassza ki az alapértelmezett áfacsoportokat. Ha a fordított adózási alkalmazhatósági feltétel teljesül, akkor az értékesítési vagy beszerzési sor frissül ezekkel az áfacsoportokkal.

## <a name="reverse-charge-on-a-sales-invoice"></a>Fordított áfa értékesítési számlánál
A fordított áfa hatályába tartozó értékesítéseknél az eladó nem számítja fel az áfát Ehelyett a számlán megjelennek mind a fordított áfa hatálya alá tartozó cikkek, mint a fordított áfa teljes összege.

Amikor olyan értékesítési számlát adnak fel, melyen fordított áfa szerepel, akkor az áfatranzakcióknál az **fizetendő áfa** áfairány és nulla áfa szerepel, és pipa kerül a **Fordított áfa** jelölőnégyzetbe.

## <a name="reverse-charge-on-a-purchase-invoice"></a>Fordított áfa beszerzési számlánál
A fordított áfaszámítás alá eső beszerzéseknél a fordított áfás számlát fogadó beszerző számít vevőnek és eladónak is az áfa könyvelésének szempontjából.

Ha fordított áfát tartalmazó beszerzési számlát ad fel, akkor két áfatranzakció jön létre. Az egyik tranzakció a **Visszaigényelhető áfa** áfairánnyal rendelkezik. A másik tranzakció a **Fizetendő áfa** áfairánnyal rendelkezik, és pipa kerül a **Fordított áfa** jelölőnégyzetbe.

A következő képernyőképen egy tranzakciónál a **Visszaigényelhető áfa** irány, a másik tranzakciónál pedig a **Fizetendő áfa** irány szerepel. 

![Feladott áfa](media/apac-sau-posted-sales-tax.png)
