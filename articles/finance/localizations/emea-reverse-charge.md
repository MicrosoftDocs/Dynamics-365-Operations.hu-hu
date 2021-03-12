---
title: Fordított költségmechanizmus az adó/GST sémához
description: A cikk azt tekinti át, hogyan állítható be fordított áfa az európai országokhoz, Szaúd-Arábiához és Szingapúrhoz.
author: epodkolz
manager: AnnBe
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore, Bahrain, Kuwait, Oman, Qatar
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 46b26fc1c0c45be894e226080a5aa9d5ae48b595
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005995"
---
# <a name="reverse-charge-mechanism-for-vatgst-scheme"></a>Fordított költségmechanizmus az adó/GST sémához

[!include [banner](../includes/banner.md)]

Ez a témakör az áfa- vagy GST sémákat alkalmazó országok/régiók fordított költségfunkció beállítására szolgáló általános megközelítést ismerteti.
                                                                                 
A funkció ország-/régióelérhetőségét a **Funkciókezelési** munkaterületen a következő funkciók kezelik.

| Funkció                                              | Ország/régió                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nincsenek specifikus funkciók                                | Ausztria </br>Belgium </br>Bulgária </br>Horvátország </br>Ciprus </br>Cseh Köztársaság </br>Dánia  </br>Észtország  </br>Finnország  </br>Franciaország  </br>Németország  </br>Magyarország  </br>Izland  </br>Írország  </br>Olaszország  </br>Lettország  </br>Liechtenstein  </br>Litvánia  </br>Luxemburg  </br>Hollandia  </br>Norvégia Lengyelország </br>Portugália </br>Románia  </br>Szaúd-Arábia </br>Szingapúr  </br>Szlovákia  </br>Szlovénia  </br>Spanyolország  </br>Svédország  </br>Svájc  </br>Egyesült Királyság  </br>Egyesült Arab Emírségek |
| Fordított áfa további országok esetében            | Bahrein  </br>Kuvait  </br>Omán  </br>Katar                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Fordított költségmechanizmus engedélyezése áfa/GST-sémához | Minden más ország/régió, kivéve:  </br>Brazília  </br>India  </br>Oroszország                                                                                                                                                                                                                                                                                                                                                                                         |
 
 További információt a témakör későbbi, [Fordított költségmechanizmus engedélyezése áfa/GST-séma funkcióhoz](#enable-reverse-charge) szakaszban talál.

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

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><a name="sales-tax-item-sales-tax-groups"></a>Adócsoportok és cikkáfacsoportok beállítása
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

## <a name="set-up-reverse-charge-item-groups"></a><a name="reverse-charge-item-group"></a>Fordított adózású cikkcsoportok beállítása
A **Fordított fizetésű cikkcsoportok** oldalon (**Adó** &gt; **Beállítás** &gt; **Áfa** &gt; **Fordított fizetésű cikkcsoportok**) oldalon termékek vagy szolgáltatások csoportjait határozhatja meg, illetve olyan egyedi termékeket vagy szolgáltatásokat, amelyeknél alkalmazható a fordított adózás. Adja meg mindegyik fordított adózású cikkcsoportnál a cikkek, cikkcsoportok és kategóriák listáját az értékesítéseknél és/vagy vásárlásoknál.

## <a name="set-up-reverse-charge-rules"></a><a name="reverse-charge-rules"></a>Adja meg a fordított fizetésekkel kapcsolatos szabályokat.
A **Fordított fizetés szabályai** oldalon (**Adó** &gt; **Beállítás** &gt; **Áfa** &gt; **Fordított fizetés szabályai**) megadhatja az alkalmazhatósági szabályokat a beszerzési és értékesítési célokhoz. Fordított költség-alkalmazhatósági szabályokat is beállíthat. Állítsa be a következő mezőket minden egyes szabálynál:

- **Dokumentumtípus** – Válassza ki: **Beszerzési rendelés**, **Szállítói számla naplója**, **Értékesítési rendelés**, **Szabadszöveges számla**, **Vevői számlanapló**, illetve **Szállítói számla**.
- **Partner országának/régiójának típusa** – Válasszon a **Belföldi**, **EU**, **GCC** vagy **Külföldi** lehetőségek közül. Emellett ha a szabály minden kereskedelmi partnernél – a címük országától vagy régiójától függetlenül – alkalmazható a szabály, válassza a **Mindegyik** lehetőséget.
- **Belföldi szállítási cím** – Jelölje be ezt a jelölőnégyzetet, ha a szabály az azonos országban vagy régióban lévő szállításokra érvényes. Ez a jelölőnégyzet nem jelölhető be a **Szállítói számla naplója** és a **Vevői számlanapló** dokumentumtípusoknál.
- **Fordított fizetésű cikkcsoport** – Válassza ki a csoportot, amelyiknél alkalmazható a szabály.
- **Küszöbösszeg** – A fordított adózás sémáját csak akkor kell a számlára alkalmazni, ha a fordított adótételek csoportjában szereplő tételek és/vagy szolgáltatások értéke meghaladja az itt megadott értéket.

Az **Érvényesség dátuma** és **Lejárat dátuma** mezőkkel is meghatározhatja a szabály érvényességének időtartamát.

Ezenkívül megadhatja, hogy megjelenjen-e egy értesítés, és a dokumentumsor frissüljön-e az alapértelmezett fordított áfacsoporttal, ha teljesül a dokumentumsor feltétele. Az alábbi lehetőségek közül választhat:

- **Nincs** – A dokumentum nem frissül.
- **Kérdés** – Megjelenik egy értesítés annak megerősítésére, hogy alkalmazható-e a fordított áfa.
- **Beállítás** – A dokumentumsor külön értesítés nélkül frissül.

## <a name="set-up-countryregion-properties"></a><a name="Set-up-Country/region-properties"></a>Ország- és régiótulajdonságok beállítása
A **Külkereskedelmi paraméterek** oldalon (**Sdó** &gt; **Beállítás** &gt; **Áfa** &gt; **Külkereskedelem** &gt; **Külkereskedelmi paraméterek**) az **Ország/régió tulajdonságai** lapon állítsa be az aktuális jogi személy országát/területét *Belföldi* értékre. Állítsa az EU kereskedelemben aktuális jogi személlyel résztvevő EU országok/régiók országok **Ország/régió típusa** menüjét *EU* értékre. Állítsa az GCC kereskedelemben aktuális jogi személlyel résztvevő GCC országok/régiók országok **Ország/régió típusa** menüjét *GCC* értékre.

## <a name="set-up-default-parameters"></a>Alapértelmezett paraméterek beállítása
A fordított áfa funkció engedélyezéséhez a **Főkönyvi paraméterek** oldal **Fordított áfa** lapján állítsa a **Fordított fizetés engedélyezése** opciót **Igen** értékre. A **Beszerzési rendelés áfacsoportja** és az **Értékesítési rendelés áfacsoportja** mezőknél válassza ki az alapértelmezett áfacsoportokat. Ha a fordított adózási alkalmazhatósági feltétel teljesül, akkor az értékesítési vagy beszerzési sor frissül ezekkel az áfacsoportokkal.

## <a name="reverse-charge-on-a-sales-invoice"></a><a name="reverse-charge-sale"></a>Fordított áfa értékesítési számlánál
A fordított áfa hatályába tartozó értékesítéseknél az eladó nem számítja fel az áfát Ehelyett a számlán megjelennek mind a fordított áfa hatálya alá tartozó cikkek, mint a fordított áfa teljes összege.

Amikor olyan értékesítési számlát adnak fel, melyen fordított áfa szerepel, akkor az áfatranzakcióknál az **Fizetendő áfa** áfairány és nulla áfa szerepel, és pipa kerül a **Fordított áfa** és **Mentes** jelölőnégyzetekbe.

## <a name="reverse-charge-on-a-purchase-invoice"></a><a name="reverse-charge-purchase"></a>Fordított áfa beszerzési számlánál
A fordított áfaszámítás alá eső beszerzéseknél a fordított áfás számlát fogadó beszerző számít vevőnek és eladónak is az áfa könyvelésének szempontjából.

Ha fordított áfát tartalmazó beszerzési számlát ad fel, akkor két áfatranzakció jön létre. Az egyik tranzakció a **Visszaigényelhető áfa** áfairánnyal rendelkezik. A másik tranzakció a **Fizetendő áfa** áfairánnyal rendelkezik, és pipa kerül a **Fordított áfa** jelölőnégyzetbe.

A következő képernyőképen egy tranzakciónál a **Visszaigényelhető áfa** irány, a másik tranzakciónál pedig a **Fizetendő áfa** irány szerepel. 

![Elszámolt áfa](media/apac-sau-posted-sales-tax.png)

## <a name="enable-reverse-charge-mechanism-for-vatgst-scheme-feature"></a><a name="enable-reverse-charge"></a>Fordított költségmechanizmus engedélyezése áfa/GST-sémához funkció
A **Funkciók kezelése** munkaterületre keresse meg a funkciót, és válassza az **Engedélyezés** lehetőséget.

Miután engedélyezte a funkciót, a **Fordított költség** fül minden jogi személynél elérhető lesz. A fordított költség visszavonásának engedélyezése a jogi személynél a **Fordított költség engedélyezése** lehetőség **Igen** érték beállításával.

A szolgáltatás beállításához kapcsolódó következő oldalak és menüelemek lesznek elérhetők:
 - **Fordított költség cikkcsoportok** (**Adó** > **Beállítás** > **Áfa** > **Fordított költség cikkcsoportok**). További információt a [Fordított költség cikkcsoportok](#reverse-charge-item-group) beállítása című szakaszban talál.
 - **Fordított költség szabályok** (**Adó** > **Beállítás** > **Áfa** > **Fordított költség szabályok**). Lásd: [Adja meg a fordított fizetésekkel kapcsolatos szabályokat](#reverse-charge-rules).
 - **Külkereskedelmi paraméterek** (**Adó** > **Beállítás** > **Áfa** > **Külkereskedelem** > **Külkereskedelmi paraméterek**). Lásd: [Ország- és régiótulajdonságok beállítása](#Set-up-Country/region-properties).

A **Fordított költség** jelölőnégyzet az **Áfacsoport** és a **Feladott áfa** oldalakon lesz elérhető. További információt a következő szakaszokban talál: [Áfacsoportok és cikkáfacsoportok beállítása](#sales-tax-item-sales-tax-groups), [Fordított áfa értékesítési számlánál](#reverse-charge-sale)és a [Fordított áfa beszerzési számlánál](#reverse-charge-purchase) című szakaszban.
