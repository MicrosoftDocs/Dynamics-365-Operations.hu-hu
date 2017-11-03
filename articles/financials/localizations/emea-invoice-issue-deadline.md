---
title: "Számlakibocsátás határideje"
description: "Ez a cikk bemutatja, hogy hogyan állíthatja be az Európai Unió (EU) területén belüli vevői és szállítói számlák kibocsátási határidejének kiszámításához használt paramétereket."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10923
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 93eaaad55c64ca6a0f3c4008149cf6ecc622d2a3
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="invoice-issue-deadline"></a>Számlakibocsátás határideje

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja, hogy hogyan állíthatja be az Európai Unió (EU) területén belüli vevői és szállítói számlák kibocsátási határidejének kiszámításához használt paramétereket.

Az Európai Unió (EU) 45/2010-es irányelve és más irányelvek kimondják, hogy az EU-n belüli szállítmányok szálázásának legkésőbb a szállítást követő hónap tizenötödik napján meg kell történnie. Ugyanakkor az egyes EU-országban különböző lehet a belföldi szállítások számlázási határideje. A Számlakibocsátási határidő funkció segítségével a dátumintervallumot az ország/régió típusához tudja igazítani. Ezután minden, adott típusú országból/régióból vagy országba/régióba irányuló szállítmány számlakiadási határidejét a rendszer a megadott dátumintervallumban beállított szabályok alapján számítja. Ezenkívül megjelenítheti az összes, adott számlakibocsátási határidejű szállítólevelet, számlakibocsátási határidő szerint szűrhet az időszakos értékesítési számlázás során, továbbá beállíthatja az értékesítési számla kibocsátásának idejét számlafeladáskor. Beállíthat egy dátumintervallum-kódot, majd beállíthatja a számlakibocsátás határidejének számítási szabályát úgy, hogy az intervallumkódot hozzárendeli egy ország-/régiótípushoz. A számítási szabály a következő tranzakciók számlák kibocsátási határidejének kiszámításához használható:

-   EU-n belüli szállítások
-   Egy EU-tagállamon belüli belföldi szállítások

Dátumvezérlőket is beállíthat, amelyek segítségével biztosítható, hogy a rendszer a vevői tranzakciókhoz tartozó vevői számlákat és jóváírásokat a szállítás teljesítését követő megadott időszakon belül generálja.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázat azokat az előfeltételeket mutatja, amelyek fennállása szükséges a számlakibocsátási határidő funkció használatához.

| Kategória            | Előfeltételek                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ország/régió      | A jogi személy elsődleges címének egy EU tagállamban kell lennie.                                                                                                                                                                                                                                                                                                                    |
| Kapcsolódó beállítási feladatok | A **Dátumintervallumok** lapon állítsa be a számlakibocsátási határidő számításához használni kívánt dátumintervallumot. (Kattintson a következőkre: **Főkönyv** &gt; **Főkönyv beállításai** &gt; **Dátumintervallumok**.) A **Külkereskedelmi paraméterek** lapon állítsa be a különböző országokhoz/régiókhoz tartozó külkereskedelmi tulajdonságokat. (Kattintson a következőre: **Adó** &gt; **Beállítás** &gt; **Külkereskedelem** &gt; **Külkereskedelmi paraméterek**.) |

## <a name="invoice-issue-due-date-calculation-rule"></a>Számlakibocsátási határidő számítási szabálya
A **Számlakibocsátási határidő kiszámításának beállítása** lapon állíthatja be a számlakibocsátás határidejének számítási szabályát úgy, hogy az intervallumkódot hozzárendeli egy ország-/régiótípushoz.

## <a name="date-control-parameters-for-customer-invoices-and-credit-notes"></a>Dátumvezérlési paraméterek vevői számlákhoz és jóváírásokhoz
Lehetősége van dátumvezérlési paraméterek beállítására, amelyek segítségével biztosítható, hogy a rendszer a vevői tranzakciókhoz tartozó vevői számlákat és jóváírásokat a szállítás teljesítését követő megadott időszakon belül generálja. Ezeket a paramétereket a **Kinnlevőségek paraméterei** oldal **Számladátumok ellenőrzése** területén találhatja meg.

## <a name="example"></a>Példa
A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszert beállíthatja úgy, hogy a számlakibocsátási határidőt EU-n belüli szállításoknál mindig a szállítás végrehajtását követő hónap 15-én számítsa ki – ehhez hozzon létre egy dátumintervallum-kódot és egy számítási szabályt az alábbi beállításokkal.

### <a name="date-interval-code"></a>Dátumtartomány kódja

| Mező                                                           | Érték                           |
|-----------------------------------------------------------------|---------------------------------|
| Dátumtartomány kódja                                              | 15-NM                           |
| Leírás                                                     | A következő hónap 15. napja |
| A következő előtt (A **Záró dátum** mezőcsoportban)                         | Hónap                           |
| Kezdés/befejezés (A **Záró dátum** mezőcsoportban)                      | Záró                             |
| +/- (A **Záró dátum** mezőcsoportban)                            | 15.                              |
| Napok, hónapok, évek vagy időszakok (A **Záró dátum** mezőcsoportban) | Napok                            |

### <a name="invoice-issue-due-date-calculation-rule"></a>Számlakibocsátási határidő számítási szabálya

| Mező               | Érték                                                     |
|---------------------|-----------------------------------------------------------|
| Ország/régió típusa | **EU**                                                    |
| Kezdő dátum          | Adja meg az aktuális beállítási sor érvénybe lépési dátumát. |
| Dátumtartomány kódja  | **15-NM**                                                 |

## <a name="next-steps"></a>További lépések
Miután befejezte a számlakibocsátási határidő kiszámításához használt paraméterek beállítását, létrehozhatja és feladhatja az alábbi tranzakciókat, amelyekkel automatikusan kiszámíthatja és aktualizálhatja a számlák kibocsátására vonatkozó határidőket:

-   **Értékesítési rendelések** – Amikor értékesítési rendelést hoz létre és szállítólevelet ad fel, a rendszer kiszámítja a számla kibocsátásának határidejét és aktualizálja azt a szállítólevélen. A határidő kiszámításának alapja az értékesítési rendelés címországához/régiójához meghatározott dátumintervallum. A szállítólevél feladása után a számlakibocsátási határidőt a **Termékbevételezési napló** oldal **Szállítólevél naplója** mezőjében ellenőrizheti. (Kattintson a következőre: **Értékesítés és marketing** &gt; **Értékesítési rendelés** &gt; **Rendelés szállítása** &gt; **Szállítólevél**.) A **Nem számlázott szállítólevelek** oldalon megtekintheti az összes, nem számlázott szállítólevelet és az azokhoz tartozó számlakibocsátási határidőket. (Kattintson a következőre: **Értékesítés és marketing** &gt; **Értékesítési rendelés** &gt; **Rendelés szállítása** &gt; **Nem számlázott szállítólevelek.**)
-   **Beszerzési rendelések** – Amikor beszerzési rendelést hoz létre és termékbevételezést ad fel, a rendszer kiszámítja a számla kibocsátásának határidejét és aktualizálja azt a termékbevételezésen. A határidő számítása a szállító elsődleges címében megadott országhoz/régióhoz társított dátumintervallum alapján történik. A termékbevételezés feladása után a számlakibocsátási határidőt a **Termékbevételezési napló** oldal **Számlakibocsátási határidő** mezőjében ellenőrizheti. (Kattintson a következőre: **Beszerzés és forrás** &gt; **Beszerzési rendelések** &gt; **Termékek bevételezése** &gt; **Termékbevételezés**.) A **Nem számlázott termékbevételezések** oldalon megtekintheti az összes, nem számlázott termékbevételezést és az azokhoz tartozó számlakibocsátási határidőket. (Kattintson a következőre: **Beszerzés és forrás** &gt; **Beszerzési rendelések** &gt; **Termékek bevételezése** &gt; **Nem számlázott termékbevételezések**.)

## <a name="technical-information-for-system-administrators"></a>Technikai információk rendszergazdáknak.
Amennyiben nincs hozzáférése a jelen cikkben szereplő feladatok végrehajtásához használt oldalakhoz, forduljon a rendszergazdához és adja meg azokat az információkat, amelyek a következő táblázatban szerepelnek.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategória</th>
<th>Előfeltételek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfigurációs kulcsok (Configuration Keys)</td>
<td>Kattintson a következőre: <strong>Rendszerfelügyelet</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Licenckezelés</strong> &gt; <strong>Licenckonfiguráció</strong>. Kattintson a <strong>Főkönyv</strong> konfigurációs kulcsra.</td>
</tr>
<tr class="even">
<td>Biztonsági szerepkörök és feladatok</td>
<td>A feladat végrehajtásához az alábbi feladatokat is tartalmazó biztonsági szerepkör tagjának kell lennie:
<ul>
<li><strong>CustInvoiceInvoiceAndCashProcessEnable</strong> (számlázási és készpénzforgalmi folyamat engedélyezése)</li>
<li><strong>VendInvoiceInvoicePaymentProcessEnable</strong> (számlázási és fizetési folyamat engedélyezése)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Biztonsági szerepkörök és jogosultságok</td>
<td>A feladat végrehajtásához az alábbi jogosultságokat is tartalmazó biztonsági szerepkör tagjának kell lennie:
<ul>
<li><strong>CustPackingSlipJournalView</strong> (értékesítési szállítólevelek megtekintése)</li>
<li><strong>VendPackingSlipJournalView</strong> (termékbevételezési napló megjelenítése beszerzési rendelésből)</li>
<li><strong>LedgerInvoiceIssueDueDateSetupMaintain_W</strong> (számlakiadási határidők kiszámítása)</li>
</ul></td>
</tr>
</tbody>
</table>






