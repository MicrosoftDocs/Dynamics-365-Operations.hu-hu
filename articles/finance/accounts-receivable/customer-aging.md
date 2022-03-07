---
title: Vevők korosítási jelentése
description: A vevők korosítási jelentése a vevőktől esedékes egyenlegeket jeleníti meg időintervallum vagy korosítási időszak alapján rendezve.
author: JodiChristiansen
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33bee60a3807c92cc97f0f5e6d660a67cdd7f297
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595089"
---
# <a name="customer-aging-report"></a>Vevők korosítási jelentése 

A **vevők korosítási** jelentése a vevőktől esedékes egyenlegeket jeleníti meg időintervallum vagy korosítási időszak alapján rendezve.

Ennek a jelentésnek a létrehozásakor a következő alapértelmezett paraméterek jelennek meg. Ezekkel a paraméterekkel szűrheti a jelentésben megjelenített adatokat. További tudnivalókért lásd: [Gyűjtemények beállítása](set-up-collections.md).

<table>
<colgroup>
<col>
<col>
</colgroup>
<thead>
<tr class="header">
<th><p>Mező</p></th>
<th><p>Leírás</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Számlázási osztály</strong></p></td>
<td><p>Válasszon ki egy vagy több számlázási osztályt, amelyeket a jelentésben kíván szerepeltetni.</p>
<div class="alert">

**Megjegyzés:** ez a vezérlő csak akkor érhető el, ha az <STRONG>állami szektor</STRONG> konfigurációs kulcs be van állítva.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Számlázási osztály nélküli tranzakciók belefoglalása</strong></p></td>
<td><p>Ha ez a jelölőnégyzet be van jelölve, akkor minden olyan tranzakció megjelenik a jelentésben, amely nem rendelkezik számlázási osztállyal.</p>
<div class="alert">

**Megjegyzés:** ez a vezérlő csak akkor érhető el, ha az <STRONG>állami szektor</STRONG> konfigurációs kulcs be van állítva.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Korosítás kezdete</strong></p></td>
<td><p>Adja meg az aktuális korosítási időszakhoz használt dátumot.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Egyenleg ezen a dátumon:</strong></p></td>
<td><p>Adja meg azt a dátumot, amelyhez a vevői egyenlegeket látni szeretné. Ezt a tranzakciók esetén fordulónapként is nevezik.</p></td>
</tr>
<tr class="even">
<td><p><strong>Kezdés dátuma</strong></p></td>
<td><p>A jelentésen megjelenő, az első időszakban vagy korosítási időszakban lévő dátum megadása.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Feltételek</strong></p></td>
<td><p>Válassza ki a jelentés alapjául szolgáló dátumtípust.</p>
<ul>
<li><p><strong>Tranzakció dátuma</strong> – A kiválasztott tranzakció feladási dátuma. Ez lehet például egy számlázási dátum, amely az esedékességi dátum kiszámításának alapját képezi.</p></li>
<li><p><strong>Esedékességi dátum</strong> –  A tranzakcióknak a fizetési feltételeken alapuló esedékességi dátuma.</p></li>
<li><p><strong>Dokumentumdátum</strong>  – A felhasználó által megadott dokumentumdátum, amely az esedékességi dátum kiszámításának alapjául szolgál.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Korosítási időszak definíciója</strong></p></td>
<td><p>Válassza ki a korosítási időszak definícióját. Az <strong>Intervallum</strong> mező korosítási időszak választásakor nem használható.</p>
<p>A kinyomtatott jelentésben nem használhatók a 6 korosítási időszaknál hosszabb korosítási időszakdefiníciók.</p>
<div class="alert">

**Megjegyzés:** Az elévülési időszakokat a <STRONG>Korosítási időszakdefiníció</STRONG> oldalon állíthatók be.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Korosítási időszak leírásának nyomtatása</strong></p></td>
<td><p>Válassza az <strong>Igen</strong> lehetőséget, ha azt szeretné, hogy a jelentés minden korosítási időszak oszlopának tetején megjelenjen a korosítási időszak leírása. Válassza a <strong>Nem</strong> lehetőséget, ha a jelentést oszlopfejlécek nélkül szeretné kinyomtatni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intervallum</strong></p></td>
<td><p>Határozza meg a használni kívánt időszakot a napok vagy hónapok számának megadásával minden egyes időszakhoz. Például a korosítási adatok hét alapján történő megtekintéséhez írja a 7 értéket ebbe a mezőbe, és válassza a <strong>Nap</strong> lehetőséget a <strong>Nap/hónap</strong> mezőben.</p>
<div class="alert">

**Megjegyzés:** A mezőben megadott információkat csak akkor veszi figyelembe a program, ha nem választott korosítási időszakdefiníciót. Ellenkező esetben a program a korosítási időszakdefiníción határozza meg a nyomtatási irányt.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Nap/hó</strong></p></td>
<td><p>Annak az egységnek (<strong>Nap</strong> vagy <strong>Hónap</strong>) a kiválasztása, amelyet az <strong>Intervallum</strong> mező periódusának meghatározásakor használ.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nyomtatás iránya</strong></p></td>
<td><p>Válassza ki, hogy ki szeretné-e számítani az egyenlegeket, és ki szeretné-e nyomtatni a korosítási jelentéseket a múltbeli vagy a jövőbeli időszakok vonatkozásában. A dátumok kiértékelése az <strong>Egyenleg úgy mint...</strong> mezőben megadott dátumhoz viszonyítással történik. Válassza a <strong>Vissza</strong> lehetőséget az elmúlt időszakokra vonatkozó adatok megjelenítéséhez. A jövőbeni adatok megjelenítéséhez válassza a <strong>Tovább</strong> lehetőséget.</p>
<div class="alert">
  
<STRONG>Megjegyzés:</STRONG> A mezőben megadott információkat csak akkor veszi figyelembe a program, ha nem választott korosítási időszakdefiníciót.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Részletek</strong></p></td>
<td><p>Ezzel a jelölőnégyzettel beállíthatja, hogy a jelentésen a megjelenő egyenlegekhez tartozó tranzakciók is listázva legyenek-e rajta.</p></td>
</tr>
<tr class="even">
<td><p><strong>Összegek feltüntetése a tranzakció pénznemében</strong></p></td>
<td><p>Jelölje ki ahhoz, hogy az összegek a tranzakció pénznemében megjelenjenek a könyvelési pénznemben megadott összegek mellett. Ha ez a jelölőnégyzet nincs bejelölve, a jelentésben szereplő összegek csak a könyvelési pénznemben jelennek meg.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Negatív egyenleg</strong></p></td>
<td><p>Akkor jelölje be, ha a negatív egyenleggel rendelkező vevői számlákat is figyelembe szeretné venni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nulla egyenlegű számlák kizárása</strong></p></td>
<td><p>Akkor jelölje be, ha a nullás egyenleggel rendelkező vevői számlákat is figyelembe szeretné venni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Kifizetés pozicionálása</strong></p></td>
<td><p>Akkor jelölje be, ha meg szeretné jeleníteni a kiegyenlítetlen kifizetéseket. Ezek a jelentés első oszlopában láthatók.</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]