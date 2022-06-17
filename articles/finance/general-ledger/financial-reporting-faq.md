---
title: Pénzügyi jelentéskészítés – GYIK
description: Ez a cikk a pénzügyi jelentéskészítéssel kapcsolatos néhány gyakran ismételt kérdésre ad választ.
author: jinniew
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5981946a4bba2c58402f4cf566bfa008de67363b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901370"
---
# <a name="financial-reporting-faq"></a>Pénzügyi jelentéskészítés – GYIK

Ez a cikk a pénzügyi jelentéskészítéssel kapcsolatos gyakran ismételt kérdésekre ad választ.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítás használatával?

A következő példák bemutatják, hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítás használatával.

Az USMF bemutatóvállalat **mérlegkimutatást** készít, amelyhez a pénzügyi jelentéskészítési funkció nem minden felhasználójának kellene hozzáférnie. A fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el.

1. Bejelentkezés a Financial Reporter Report Designer alkalmazásba.
2. Válassza a **Fájl \> Új \> Fadefiníció** lehetőséget egy új fadefiníció létrehozásához.
3. Koppintson duplán (vagy kattintson duplán) az **Összegzés** sorra az **Egység biztonsága** oszlopban.
4. Válassza ki a **Felhasználók és csoportok** lehetőséget.
5. Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek hozzá kell férnie a jelentéshez.
6. Válassza a **Mentés** lehetőséget.
7. A jelentésdefinícióban adja meg az új fadefiníciót.
8. A fadefinícióban válassza ki a **Beállítások** lehetőséget. Majd a **Jelentési egység kiválasztása** pont alatt válassza az **Összes egységgel együtt** lehetőséget.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel?

Ha a jelentés egyenlegei nem egyeznek meg, az alábbi eljárásokkal azonosíthatja a számlát és az eltérést.

### <a name="in-financial-reporter-report-designer"></a>Itt: Financial Reporter Report Designer

1. Hozzon létre egy új sordefiníciót.
2. Válassza ki a **Szerkesztés \> Sorok beszúrása dimenziókból** lehetőséget.
3. Válassza ki a **Főszámla** lehetőséget.
4. Válassza ki az **OK** lehetőséget.
5. Mentse a sordefiníciót.
6. Hozzon létre egy új oszlopdefiníciót.
7. Hozzon létre új jelentésdefiníciót.
8. Válassza ki a **Beállítások** lehetőséget és törölje az opció kijelölését.
9. Hozza létre a jelentést. 
10. Exportálja a jelentést a Microsoft Excel szoftverbe.

### <a name="in-dynamics-365-finance"></a>A Dynamics 365 Finance-ban

1. Lépjen a **Főkönyv \> Lekérdezések és jelentések \> Főkönyvi kivonat** lehetőségre.
2. Állítsa be a következő mezőket:

    - **Kezdő dátum** – Adja meg a pénzügyi év kezdő dátumát.
    - **Záró dátum** – Adja meg a dátumot, amelyhez létrehozza a jelentést.
    - **Pénzügyi dimenzió** – Állítsa ezt a mezőt a **Fő számlakészlet** lehetőségre.

3. Válassza ki a **Számítás** lehetőséget.
4. Exportálja a jelentést Excelbe.

Most már a **főkönyvi kivonati** jelentésbe másolhatja az Excelben létrehozott pénzügyi jelentést, hogy összehasonlítsa a **Záró egyenleg** oszlopokat.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Amikor jelentést tervezek a Report Designerben, vagy amikor pénzügyi jelentést készítek, a következő üzenet jelenik meg: „A műveletet nem lehet végrehajtani az adatszolgáltató keretrendszerében fellépő probléma miatt.” Hogyan reagáljak rá?

Az üzenet azt jelzi, hogy hiba történt, amikor a rendszer megpróbálta lekérni a pénzügyi metaadatokat a data martból a Pénzügyi jelentéskészítés használata közben. Erre a problémára kétféleképpen tud reagálni:

- Tekintse át az adatok integrációs állapotát a Report Designerben lévő **Eszközök \> Integráció állapota** segítségével. Ha az integráció még nem fejeződött be, várjon, amíg befejeződik. Ezután próbálja meg újra elvégezni azt, amit az üzenet megjelenésekor szeretett volna.
- Forduljon az ügyfélszolgálathoz a probléma azonosítása és megoldása érdekében. Inkonzisztens adatok lehetnek a rendszerben. A támogatási szakemberek segítséget tudnak nyújtani a kiszolgálón lévő probléma azonosításában, és a konkrét adatok megkeresésében, melyeket lehet, hogy frissíteni kell.

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>Hogyan befolyásolja a korábbi árfolyamok átszámításának kiválasztása a jelentés teljesítményét?

Ezt a historikus árfolyamot jellemzően az elhatárolt nyereség, az ingatlanok, gépek és berendezések, valamint a tőkeszámlák esetében használják. A historikus árfolyam a FASB (Pénzügyi Számviteli Normák Testülete) vagy az általánosan elfogadott könyvelési elvek (GAAP) irányelvei alapján írható elő. A további tudnivalókért lásd: [Pénznemekkel kapcsolatos képességek a pénzügyi jelentésben](financial-reporting-currency-capability.md).

## <a name="how-many-types-of-currency-rate-are-there"></a>Hányfajta pénznem árfolyamtípus létezik?

Három típus van:

- **Aktuális árfolyam** – ez a típus jellemzően mérlegszámlákhoz használatos. Ez általában *azonnali árfolyam* néven ismert, és lehet a hónap utolsó napján vagy más előre meghatározott időpontban érvényes árfolyam.
- **Átlagárfolyam** – ez a típus jellemzően a eredménykimutatási (nyereség/veszteség) számlák esetében használatos. Az átlagárfolyam beállítható egyszerű vagy súlyozott átlag alkalmazására.
- **Historikus árfolyam** – Ezt a típust jellemzően az elhatárolt nyereség, az ingatlanok, gépek és berendezések, valamint a tőkeszámlák esetében használják. Ezek a számlák a FASB vagy a GAAP irányelvei alapján lehetnek szükségesek.

## <a name="how-does-historical-currency-translation-work"></a>Hogyan működik a historikus devizaátváltás?

Az árfolyamok a tranzakció időpontjára vonatkoznak. Ezért minden tranzakciót egyénileg kell váltani, a legközelebbi árfolyam alapján.

A historikus pénznem átváltásához az előre kiszámított időszaki egyenlegek használhatók az egyes tranzakciók részletei helyett. Ez a működés eltér az aktuális árfolyamon történő váltástól.

## <a name="how-does-historical-currency-translation-affect-performance"></a>Hogyan befolyásolja a teljesítményt a historikus devizaátváltás?

Amikor a jelentésekben megjelenő adatokat frissítik, előfordulhat késés, mivel az összegeket újra kell kalkulálni a tranzakció részleteinek ellenőrzésével. Ez a késleltetés minden alkalommal bekövetkezik, amikor az árfolyamokat frissítik vagy több tranzakciót könyvelnek. Ha például naponta több alkalommal több ezernyi számla van beállítva historikus átszámításra, a jelentésben található adatok frissítése akár egy órányit is késhet. Ha viszont kisebb számú konkrét számla van, akkor a jelentésadatok feldolgozási ideje percekre vagy még kevesebb időre csökkenthető.

Hasonlóképpen, amikor a jelentések a historikus típusú számlák devizaátváltásának használatával készülnek, extra tranzakciónkénti számításokat kell végezni. A számlák számától függően a jelentés elkészítésének ideje több mint kétszeresére nőhet.

## <a name="what-are-the-estimated-data-mart-integration-intervals"></a>Melyek a adattérkép becsült integrációs intervallumai?

A Financial Reporter 16 feladat segítségével másolja az adatokat a Dynamics 365 Finance szolgáltatásból a Financial Reporter adatbázisába. Az alábbi táblázat felsorolja ezt a 16 feladatot, és ismerteti az intervallumot, amely meghatározza, hogy milyen gyakran futnak az egyes feladatok. Az intervallumok nem módosíthatók.

| Név                                                       | Intervallum | Intervallum időmérése |
|------------------------------------------------------------|----------|-----------------|
| AX 2012 Számlakategóriák számlakategóriához            | 41       | perc         |
| AX 2012 Számlák számlához                                | 7        | perc         |
| AX 2012 Vállalatok vállalathoz                               | 300      | másodperc         |
| AX 2012 Vállalatok szervezethez                          | 23       | perc         |
| AX 2012 Dimenziókombinációk dimenziókombinációhoz    | 1        | perc         |
| AX 2012 Dimenzióértékek dimenzióértékhez                | 11       | perc         |
| AX 2012 Dimenziók dimenzióhoz                            | 31       | perc         |
| AX 2012 Árfolyamok árfolyamhoz                    | 17       | perc         |
| AX 2012 Pénzügyi évek pénzügyi évhez                        | 13       | perc         |
| AX 2012 Főkönyvi tranzakciók információkhoz                | 1        | perc         |
| AX 2012 Szervezeti hierarchiák fához                   | 3600    | másodperc         |
| AX 2012 Esetek esethez                              | 29       | perc         |
| AX 2012 Tranzakciótípus minősítői információtípus minősítőjéhez | 19       | perc         |
| Karbantartási feladat                                           | 1        | perc         |
| MR Jelentésdefiníciók AX7 Pénzügyi jelentésekhez             | 45       | másodperc         |
| MR Jelentésverziók AX Pénzügyi jelentésverziókhoz         | 45       | másodperc         |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
