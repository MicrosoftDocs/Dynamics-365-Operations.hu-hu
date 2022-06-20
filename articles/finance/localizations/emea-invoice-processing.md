---
title: Számlák feldolgozása
description: Ez a cikk a kelet-európai számlák feldolgozásával kapcsolatban tartalmaz tájékoztatást.
author: EvgenyPopovMBS
ms.date: 02/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia, Italy
ms.author: epopov
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: edb50ddebeca18653a318596e9c291a3f3df6d9c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848445"
---
# <a name="invoice-processing"></a>Számlák feldolgozása

[!include [banner](../includes/banner.md)]

Ez a témakör röviden leír néhány országspecifikus helyzetet, például a közösségen belüli forgalmi adót (áfa) és a halasztott adót. Egyes európai országok számára a jogi követelmények befolyásolják a számlázási folyamatot. Ez a cikk arról is tájékoztatást ad, hogyan kell feldolgozni a vevői és szállítói számlákat ezekben az országokban. 
<table>
<thead>
<tr>
<th>Eset</th>
<th>Országok</th>
<th>A funkciómódosítások leírása</th>
</tr>
</thead>
<tbody>
<tr>
<td> Kinnlevőségek és kötelezettségek áfadátumai</td>
<td>Cseh Köztársaság, Lengyelország</td>
<td>
<p>Az Európai Unió (EU) országaiból beszerzett áruk esetében áfa-önértékelési kötelezettség áll fenn:</p>
<ul>
<li>A kimeneti áfát abban az áfaidőszakban kell megfizetni, amelyben a számlát kiállították (bizonylatdátum).</li>
<li>A bejövő áfa nem vonható le a bizonylat bevételezése előtt (áfaregisztráció dátuma).</li>
</ul>
<p>Ebben az esetben a következő beállításokat kell megadni a forgatókönyv támogatására:</p>
<ul>
<li>A <strong>Kötelezettségek paraméterei</strong> oldalon engedélyezze a <strong>Közösségi áfa</strong> és a <strong>Bizonylat dátuma közösségen belüli áfához</strong> paramétereket.</li>
<li>Állítson be két áfakódot, egyet, amelynek pozitív az százalékos áfaértéke, és egy másikat, amelynek negatív a százalékos áfaértéke.</li>
<li>Állítson be egy áfacsoportot, amely a pozitív és negatív áfakódokat is tartalmazza. A negatív áfakód esetében a <strong>Közösségen belüli áfa</strong> paraméter beállítása legyen <strong>Igen</strong>.</li>
</ul>
<p>A sikeres beállítás után a beszerzéseknek két feladott áfatranzakciója lesz:</p>
<ul>
<li>A pozitív tranzakció, amelynél az irány a <strong>visszaigényelhető áfa</strong>, és az áfajegyzék dátuma megegyezik a számla feladási dátuma lap dátumával.</li>
<li>A negatív tranzakció, amelynél az irány a <strong>befizetendő áfa</strong>, és az áfajegyzék dátuma megegyezik a bizonylat dátumával.</li>
</ul>
</td>
</tr>
<tr>
<td>Értékesítési bizonylat dátumának módosítása.</td>
<td>Az összes közép-kelet-európai ország</td>
<td><p>Módosíthatja a projektszámla <strong>Dokumentumdátum</strong> mezőjét. Ez a dátum megjelenik a nyomtatott számlán.</p>
<p><strong>Dokumentumdátum</strong> mező a <strong>Számla feladása</strong> és a <strong>Szabadszöveges számla</strong> oldalakon is van. Számlák feladása után a dokumentum dátuma megjelenik a számla fejlécében.</p>
</td>
</tr>
<tr>
<td>Dokumentum dátuma az árfolyamokhoz</td>
<td>Lengyelország, Magyarország, Cseh Köztársaság, Olaszország</td>
<td>
<p>A jogszabályok eltérő szabályokat adnak meg az érvényes árfolyamok kiválasztásához az üzleti tranzakciók számára. Az <strong>Árfolyam dátuma</strong> mezőben a <strong>Kinnlevőségek paraméterei</strong> és a <strong>Kötelezettségek paraméterei</strong> lapon, kiválaszthatja a dátumot, amely a könyvelési pénznemben szereplő összegekre használandó a beszerzési és értékesítési bizonylatok számításánál. Adatbevitel közben a rendszer beolvassa a tranzakció átváltási árfolyamát ennek a paraméternek az alapján.</p>
<blockquote>[!NOTE]<br>Olaszország esetében ez a funkció csak a kötelezettségek modulban használható. A kötelezettségek paraméterei között a felhasználó kiválaszthatja a <strong>feladási dátumot</strong> vagy a <strong>bizonylat dátumát</strong> az <strong>árfolyam dátuma</strong> mezőben.   </blockquote>
<blockquote><br>Az <strong>Árfolyam dátuma</strong> mező beállításakor a <strong>Bizonylat dátuma (csak EU-kereskedelemben)</strong> lehetőségre, a rendszer az áfacsoportot használja. Az áfacsoportra nézve van egy <strong>EU-kereskedelem</strong> paraméter az <strong>Általános</strong> lapon. Ha az <strong>EU-kereskedelem</strong> beállítás <strong>Igen</strong> az áfacsoport esetében, és a bizonylat fejlécében létezik ez az áfacsoport, a rendszer beolvassa az átváltási árfolyamot a bizonylat dátuma alapján. Ha az <strong>EU-kereskedelem</strong> beállítás <strong>Nem</strong> az áfacsoport esetében, a rendszer a bizonylat feladási dátuma alapján olvassa be az árfolyamot.</blockquote>
  <blockquote><br>Lengyelország esetében a Kinnlevőségek <strong></strong><strong>modulban további automatikus dátummeghatározási</strong> érték érhető el ehhez a paraméterhez. Ha be van jelölve, a rendszer automatikusan kiválasztja a legkorábbi dátumot a számla feladási dátumtól, értékesítési dátumtól és fizetési dátumtól.</blockquote>
</td>
</tr>
<tr>
<td>Ügyletek dátumai, áfaregisztrálási dátumok, valamint a bizonylatok és az áfa dátumellenőrzése</td>
<td>Lengyelország, Magyarország, Cseh Köztársaság</td>
<td>
<p>Az eladási dátum és a dokumentum kézhezvételi dátuma kötelező az áfabevalláshoz:</p>
<ul>
<li>Az eladási dátum a kinnlevőséget teljesítő tranzakció dátuma.</li>
<li>A bizonylat kézhezvételi dátuma feljogosít áfacsökkentési kérelemre a kötelezettségekből. Minden kapott bizonylathoz dátum tartozik ellenőrzési célokból.</li>
</ul>
<p>A magyar dátum határidők funkció, a cseh kitöltési dátumok és a lengyel áfatételjegyzék dátum funkció teljesíti azt a követelményt, amely az adóinformáció jelentésére vonatkozik a postázási dátumtól eltérő dátum esetében.</p>
<p>Az <strong>Áfatételjegyzék dátuma</strong> mező támogatja a követelményt, és több mint 20 oldalon jelenik meg. Az oldalak közé tartoznak többek között a következők: naplók, értékesítési rendelések, beszerzési rendelések, szabadszöveges számlák, szállítóiszámla-naplók és projektszámlák. A dokumentumok frissítése vagy feladása során minden adó feladásra kerül az áfatételjegyzék megfelelő dátumának használatával, és a dátum felkerül az olyan oldalakra, mint a vevői és a szállítói számlanaplók.</p>
<p>Kimondottan Csehország esetében a <strong>Áfatételjegyzék dátuma</strong> mező üresen hagyható a feladás közben, halasztott áfa esetén. Ellenkező esetben a mező kötelező, és meg kell adni.</p>
<p>Dátumellenőrzési paraméterek adhatók meg a <strong>Áfacsoportok</strong> lapon:</p>
<ul>
<li>Az <strong>Áfatételjegyzék kitöltésének dátuma</strong> és az <strong>Értékesítési dátum kitöltése</strong> paraméterek a megfelelő dátumok esetében az alapértelmezés szerint használt feltöltési módot jelentik. Manuális bevitel és több automatikus beviteli módszert is elérhető.</li>
<li>A <strong>Kötelező értékesítési dátum</strong> mező jelzi, hogy az értékesítési dátumot meg kell-e adni egy értékesítési számla feladása előtt.</li>
</ul>
<p>Az <strong>Áfatételjegyzék-tranzakciók</strong> lapon a feladott áfatranzakciókhoz kitöltheti az üres áfatételjegyzék-dátumokat.</p>
</td>
</tr>
<tr>
<td>Halasztott adót tartalmazó áfatételjegyzék-dátumok</td>
<td>Magyarország</td>
<td>
<p>A magyar adójogszabályok a számlák létrehozásakor megkövetelik, hogy a számla kiállítása vagy a teljesítés legyen, vagy legkésőbb a teljesítése utáni 15. nap.</p>
<p>A teljesítés dátuma az a dátum, amikor a megrendelt szolgáltatásokat teljesítették, vagy amikor leszállították a megrendelt cikkeket. A bizonylatok feladásakor vagy frissítésekor az összes adó feladása a megfelelő áfatételjegyzék-dátum használatával történik, és a dátum megjelenik a megfelelő oldalakon. Ezenkívül a vonatkozó előírások szerint meg kell felelni a következő feltételeknek a szolgáltatások folyamatos leszállításakor (például bérlet, lízing, tanácsadás vagy fűtés):</p>
<ul>
<li>Az áfát a számla dátumán erre a célra kijelölt főkönyvi számlára kell könyvelni.</li>
<li>Az áfát át kell adni a speciális számlák az áfa kinnlevőségek vagy a kötelezettségek számlára, és szerepelnie kell az áfabevallásban az esedékesség napján.</li>
</ul>
<p>Ezeknek a követelményeknek a támogatása érdekében a főkönyvi feladások átvihetők a halasztott bejövő adó számlára és a halasztott kimenő adó számlára. Azonban először meg kell felelni a következő előfeltételeknek:</p>
<ul>
<li>A halasztott áfa fizetendő és a halasztott áfa kinnlevőségek főkönyvi számlákat be kell állítani a főkönyvi feladási csoportokban.</li>
<li>Engedélyezni kell a <strong>Halasztott áfa</strong> cikkáfacsoportok paramétert.</li>
</ul>
</td>
</tr>
<tr>
<td> Kötelező ÁFA-dátum</td>
<td>Lengyelország</td>
<td>
<p>Előírhatja, hogy az áfatételjegyzék dátuma szerepeljen a beszerzési és értékesítési tranzakciórekordokban. Emiatt az áfatételjegyzék dátuma rögzíthető a tranzakció feladása előtt. A funkció segítségével elkerülheti, hogy több tranzakciót kelljen kezelni az időszak végén.</p>
<p>Az <strong>Áfatételjegyzék dátuma</strong> mezőt kötelezővé teheti a vevői vagy szállítói tranzakciók feladása alkalmával. A mező kötelezővé tételéhez engedélyezze az <strong>Áfadátum megadása kötelező</strong> beállítást a kapcsolódó vevői vagy szállítói számlára.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
