---
title: Vevői tranzakciók listaoldala
description: Ez a témakör a Microsoft Dynamics 365 Finance Ügyféltranzakciós listaoldalával kapcsolatban nyújt tájékoztatást.
author: mikefalkner
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 9ee8b64375bcd73447206f552df61f9122d949a9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814224"
---
# <a name="customer-transactions-list-page"></a>Vevői tranzakciók listaoldala

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Kiegyenlítések megjelenítése

A műveleti panel **Kiegyenlítések megjelenítése** gombjával gyorsan hozzáférhet a kiegyenlítési előzményekhez és a kiegyenlítés tranzakció részletes adataihoz. További kapcsolódó tranzakciókat is megjeleníthet, amelyek kapcsolódna a kiválasztott tranzakcióhoz vagy azért, mert ugyanazon kiegyenlítés részei vagy azért, mert olyan fizetések, amelyeket ugyanazon fizetési naplóban hoztak létre.

1. Válassza a **Kinnlévőségek \> Minden vevő** lehetőséget.
2. Válasszon ki egy vevőt, amelyikhez tranzakció tartozik, és ezt követően a műveleti ablak **Vevő** lapján válassza a **Tranzakciók** elemet.
3. Válassza ki a kivizsgálni kívánt tranzakciót, majd a műveleti panelen válassza a **Kiegyenlítések megjelenítése** lehetőséget.

    A **Kiegyenlítések megjelenítése** párbeszédpanel mutatja a kijelölt tranzakciót és minden dokumentumot, amelyek ki lettek egyenlítve vele szemben. Ezen a párbeszédpanelen hasonlít a kiegyenlítési előzmények nézetre, de az összes kapcsolódó dokumentumot tartalmazza.

4. A párbeszédpanelen a különböző feladatok hajthatók végre. Válasszon ki egy vagy több bizonylatot majd, válassza ki az alábbi gombok egyikét:

    - **Kapcsolódók megtekintése** – Megjeleníti az összes kifizetési napló tranzakciót és a főkönyvi napló tranzakcióit a vevőhöz, akit abban a naplóban hoztak létre, amelyben a dokumentumok a létrehozott listában megjelennek. Például ha egy kifizetés megjelenik, akkor az összes olyan fizetés abban a fizetési naplóban, amelyben létrehozták, megjelenik. Ha egy számla vagy kifizetés megjelenik, és ezt egy általános naplóban hozták létre, akkor az adott általános naplóban levő összes dokumentum megjelenik. Ezenkívül az összes kiegyenlítés, amely a dokumentumlistához kapcsolódik, szintén megjelenik. Miközben megtekinti a kapcsolódó fizetéseket, a gombon a címke a **Kiegyenlítések megjelenítése** értékre vált. Válassza a **Kiegyenlítések megjelenítése** lehetőséget hogy csak azokat a tranzakciókat jelenítse meg, amelyek meg lettek jelenítve amikor először nyitotta meg a **Kiegyenlítések megjelenítése** párbeszédpanelt.
    - **Előzmények megtekintése** – A bizonylatok kiegyenlítési előzményeinek megtekintése. A **Bezárás** gombbal zárja be a párbeszédpanelt.
    - **Könyvelés megtekintése** – A kiválasztott dokumentumhoz kapcsolódó összes bizonylat megtekintése. A **Bezárás** gombbal zárja be a párbeszédpanelt.
    - **Exportálás** – A kijelölt bizonylatok exportálása a Microsoft Excel programba.
    - **Tranzakciók kiegyenlítése** – Ez a gomb csak akkor jelenik meg, ha a kiválasztott eredeti dokumentum nem lett teljesen kiegyenlítve. Ha kiválasztja ezt a gombot, a **Tranzakciók kiegyenlítése** párbeszédpanel jelenik meg, ahol kiválaszthatja a tranzakciókat a kiegyenlítéshez.
    - **Kiegyenlítések visszavonása** – Ez a gomb csak akkor jelenik meg, ha a kiválasztott eredeti dokumentum teljesen ki lett egyenlítve. Ha kiválasztja ezt a gombot, megjelenik a **Kiegyenlítések visszavonása** párbeszédpanel jelenik meg, ahol visszavonhatók a dokumentumhoz végrehajtott kiegyenlítések.

## <a name="global-transactions"></a>Globális tranzakciók

A **globális tranzakciók** gomb is látható a **Vevőtranzakciók** listaoldalán. Ez a gomb lehetővé teszi a vevő minden tranzakciójának megtekintéslt az összes jogi személy között. A **Vevői tranzakciók** listaoldal csak azon jogi személyek tranzakcióit jeleníti meg, amelyekhez a felhasználó a biztonsági beállításai alapján hozzáférhet.

A listalap jeleníti az összes tranzakciót azoknál a vevőknél, akiknek félazonosítója megegyezik az induló vevőkéval. Ha például az US-001 vevő egy jogi személy esetében azonos félazonosítóval rendelkezik, mint a DE-001 egy másik jogi személynél, akkor megjelenik minden tranzakció mindkét vevői azonosítóra vonatkozóan.

A **Vevői tranzakciók** listaoldal menüi eltérőek a tranzakció jogi személyétől függően. Ha például egy funkció csak a svájci jogi személyek esetében érhető el, az ilyen funkció menüpontjai csak akkor jelennek meg, ha svájci tranzakció van kijelölve.

A szolgáltatás eléréséhez kövesse az alábbi lépéseket.

1. Válassza a **Kinnlévőségek \> Minden vevő** lehetőséget.
2. Válasszon ki egy vevőt, és ezt követően a műveleti ablak **Vevő** lapján, a **Tranzakciók** csoportban válassza a **Globális tranzakciók** elemet.

## <a name="more-transaction-filters"></a>További tranzakciószűrők 

A nyitott tranzakciók megjelenítését lehetővé tevő szűrő helyére egy új szűrő került, melynek révén megtekintheti a több tranzakcióból álló kombinációkat. A **Megjelenítés** mezőben a következő beállítások közül választhat:

- **Mind** – Az összes tranzakció megtekintése a kiválasztott vevőnél (nyitott és lezárt).
- **Lezárt** – Csak a teljesen kiegyenlített és lezárt tranzakciók megjelenítése.
- **Nyitott** – Csak a még nem teljesen kiegyenlített tranzakciók megjelenítése.
- **Nyitott elemek, valamint a dátum napján vagy utána lezárt elemek** – Csak a megadott dátumon vagy az után még nem teljesen kiegyenlített tranzakciók megjelenítése. Ha ezt a lehetőséget választja, módosíthatja a szűrő mellett megjelenő dátumot. Az olyan tranzakciók, melyeknél az **Utolsó kiegyenlítés dátuma** érték az Ön által megadott dátumon vagy utána van, megjelennek a listában, még akkor is, ha az adott tranzakciók teljesen ki lettek egyenlítve az aktuális dátumig. Az egyenleg azonban az aktuális dátum szerinti, és nem a kijelölt dátumnak felel meg.

Válassza ki a **Pénznem-átértékelés elrejtése** jelölőnégyzetet a pénznem átszámítási tranzakciók elrejtéséhez.

## <a name="modify-due-dates-and-discount-dates"></a>Határidők és engedménydátumok módosítása

A határidők és az engedmények dátumait a nyitott vevői tranzakcióknál frissítheti. A 8.1-es kiadásban felveheti az esedékességi dátumokat a **Vevői tranzakciók** listaoldalra. Ha rákattint a határidőre a **Vevői tranzakciók** listaoldalon, akkor módosíthatja a határidőket, a kedvezménydátumokat, a fizetési feltételeket és a készpénzfizetési kedvezmény feltételeit **Az esedékességi dátum és készpénzfizetési engedmény dátumainak frissítése** párbeszédpanelen.

### <a name="activate-the-feature"></a>A funkció aktiválása

Ha határidőket szeretne hozzáadni a **Vevői tranzakciók** listaoldalhoz, és módosítani kívánja a fizetési beállításokat egy tranzakciónál **Az esedékességi dátum és készpénzfizetési engedmény dátumainak frissítése** párbeszédpanelen, kövesse ezeket a lépéseket.

1. Válassza a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontot.
2. A **Kiegyenlítések** lapon állítsa az **Esedékességi dátum megjelenítése és a szerkesztés engedélyezése** lehetőséget **Igen** értékre.
3. A funkció engedélyezéséhez új mezőket adtunk a vevői tranzakciókhoz. Ezek a mezők az új tranzakció befejezésekor tölthetők ki. Akkor is megtörténik a kitöltésük, ha megnyitja **Az esedékességi dátum és készpénzfizetési engedmény dátumainak frissítése** párbeszédpanelt. Ha az **Esedékességi dátum megjelenítése és a szerkesztés engedélyezése** beállítást **Igen** értékre állítja, akkor megjelenik a **Fizetési információk frissítése** párbeszédpanel.  A meglévő tranzakciók azonnali frissítéséhez válassza az **Összes létező tranzakció frissítése** lehetőséget. Ha csak az új tranzakcióknál szeretné kitölteni a mezőket, válassza a **Folytatás frissítés nélkül** lehetőséget.

A határidő most hozzáadódik a **Vevői tranzakciók** listaoldalhoz, és Ön könnyen módosíthatja a határidő és készpénzfizetési engedmény dátumait a tranzakcióknál.

### <a name="modify-the-payment-settings"></a>A fizetési beállításainak módosítása

A **Vevői tranzakciók** listaoldal megjeleníti a vevő minden tranzakcióját. Amikor kiválaszt egy határidőt egy tranzakcióhoz, megjelenik **Az esedékességi dátum és készpénzfizetési engedmény dátumainak frissítése** párbeszédpanel. Ezen a párbeszédpanelen látható az esedékességi dátum és az engedményszámítások alapdátuma, az esedékességi dátum, a fizetési feltételek, a készpénzengedmény feltételei, továbbá a készpénzfizetési engedmény dátumai.

Minden mező más hatással rendelkezik a tranzakcióra a szerkesztésekor:

- **Alapdátum szerkesztése** – A határidőnek és az engedmény dátumai módosulnak, ha a dokumentum dátuma az alapdátum.
- **Az esedékességi dátum szerkesztése** – Csak az esedékességi dátum módosul.
- **Az engedmények dátumainak módosítása** – Csak az engedmények dátumai módosulnak.
- **Fizetési feltételek szerkesztése** – Az esedékességi dátum módosul az alapdátum és a fizetési feltételek alapján.
- **Készpénzfizetési engedmény feltételeinek módosítása:** – A készpénzfizetési engedmények módosulnak az alapdátum és a készpénzfizetési engedmény feltételei alapján.

Amikor befejezte a fizetési beállítások módosítását, válassza a **Bezárás** elemet a módosítások mentéséhez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]