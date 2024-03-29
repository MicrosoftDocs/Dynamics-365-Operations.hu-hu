---
title: Értékesítési szerződések áttekintése
description: Ez a cikk az értékesítési szerződésekkel kapcsolatos információkról nyújt tájékoztatást. Az értékesítési szerződés olyan szerződés, amelyben egy vevő vállalja, hogy az adott termékből bizonyos összegért vagy egy bizonyos mennyiséget vásárol az idő tekintetében, különleges árak és engedmények ellenében.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage, SalesAgreementInvoiceJournal, SalesAgreementInvoicePart
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "9554"
- intro-internal
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e84b8be597870deea3beaf1bdc4a98021b7f135
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903840"
---
# <a name="sales-agreements-overview"></a>Értékesítési szerződések áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk az értékesítési szerződésekkel kapcsolatos információkról nyújt tájékoztatást. Az értékesítési szerződés olyan szerződés, amelyben egy vevő vállalja, hogy az adott termékből bizonyos összegért vagy egy bizonyos mennyiséget vásárol az idő tekintetében, különleges árak és engedmények ellenében.

Az értékesítési szerződés olyan szerződés, amely kötelez egy vevőt, hogy termékeket vásároljon egy adott mennyiségben, vagy adott összegben adott idő alatt, különleges árakért, engedményekért és egyéb különleges feltételekért cserébe, mint például fizetési vagy szállítási feltételek. Az értékesítési szerződésben foglalt árak és engedmények felülírják a többi létező kereskedelmi megállapodásban beállított árak és engedmények értékét.  

Az értékesítési szerződés érvényességi időszakát a szerződés **Érvénybe lépési dátum** és **Lejárat dátuma** mezői határozzák meg. A vevő értékesítési rendelése akkor felel meg a szerződés feltételeinek, ha a rendelés kért szállítási dátuma az érvényességi időszakban van. Minden értékesítésirendelés-sor, amely egy értékesítési szerződéshez van kötve hozzájárul az adott értékesítési szerződés teljesítéséhez.  

Értékesítési rendelést közvetlenül létrehozhat az értékesítési szerződésből a **Kiadási rendelés** művelet felhasználásával. Másik lehetőségként kiválaszthatja az érvényes értékesítési szerződést, amikor megteszi a rendelést (lásd az „Értékesítési szerződések alkalmazása a rendelési folyamatban” bekezdést ebben a cikkben).  

> [!NOTE] 
> A korábbi verziókban az értékesítési szerződéseket keretrendelésnek nevezik.

## <a name="commitment-types"></a>Kötelezettségtípusok
Az értékesítési szerződés minden sora egy-egy kötelezettségvállalás bizonyos eladásra. A kötelezettségek alapvetően két csoportra oszlanak:

-   **Érték-kötelezettség**– a vevő elfogadja, hogy termékeket vásárol egy meghatározott összegért.
-   **Mennyiség-kötelezettség**– A vevő elfogadja, hogy meghatározott mennyiségű terméket fog vásárolni.

Továbbá a szerződés kötelezheti a vevőt, hogy meghatározott terméket vagy termékeket vásároljon egy termék kategóriában. E két tényező (érték–mennyiség és meghatározott termékek–termékkategóriák), kombinálásával a kötelezettségvállalás négy típusát kapjuk meg:

-   **Termékmennyiségi kötelezettség** – a vevő elfogadja, hogy meghatározott mennyiségű terméket vásárol. Azok a sorok, amelyek ezt a kötelezettség-típust használják egy elfogadott cikkszám és mennyiség által vannak meghatározva. Az **Összeg** mező nem érhető el.
-   **Termék értékére vonatkozó kötelezettség**– a vevő elfogadja, hogy meghatározott termékeket vásárol meghatározott összegért. Azok a sorok, amelyek ezt a kötelezettség-típust használják egy elfogadott cikkszám és összeg által vannak meghatározva. A **Mennyiség** és az **Egység** mezők nem érhetők el.
-   **Termékkategória értékére vonatkozó kötelezettség**– a vevő elfogadja, hogy egy meghatározott értékesítési kategóriából vásárol termékeket egy meghatározott összegért. Azok a sorok, amelyek ezt a kötelezettség-típust használják egy az értékesítési kategóriák hierarchiájában szereplő értékesítési kategória és egy összeg által vannak meghatározva. A **Mennyiség** és az **Egység** mezők nem érhetők el.
-   **Érték-kötelezettség**– a vevő elfogadja, hogy bármely terméket, vagy termékeket vásárol bármely beszerzési kategóriában egy meghatározott összegért. A **Mennyiség** és az **Egység** mezők nem érhetők el.

Ugyanazon értékesítési szerződés sorainak lehetnek különböző típusú kötelezettségvállalásai.

## <a name="pricing-terms-for-sales-agreements"></a>Értékesítési szerződések árképzési feltételei
Az árképzési feltételek a kötelezettségvállalás típusától függően többfélék lehetnek. Egy értékesítési rendelésben, amely egy értékesítési szerződéshez van csatolva az értékesítési szerződés árképzési feltételei fölülírnak minden más árképzési feltételt amelyek kereskedelmi megállapodásokban alkalmazandók. A következő táblázat leírja az egyes kötelezettségtípusoktól függő árspecifikus mezőket. „Igen” jelöli, hogy a mező frissíthető egy rendeléssoron.

| Kötelezettség típusa                   | Egységár | Áregység | Engedményszázalék | Készpénzfizetési engedmény összege |
|-----------------------------------|------------|------------|------------------|----------------------|
| Termékmennyiségi kötelezettség       | Igen        | Igen        | Igen              | Igen                  |
| Termék értékére vonatkozó kötelezettség          |            |            | Igen              |                      |
| Termékkategória értékére vonatkozó kötelezettség |            |            | Igen              |                      |
| Értékre vonatkozó kötelezettség                  |            |            | Igen              |                      |

## <a name="policies-for-sales-agreements"></a>Értékesítési szerződések irányelvei
A következő irányelvek befolyásolják a módot, ahogy az értékesítési szerződés kötelezettségvállalása és a megfelelő értékesítési rendelés kapcsolata működik.

-   **Maximum betartása** – Az összes rendelési sor összes mennyisége vagy összege nem haladhatja meg azt a mennyiséget vagy összeget, amely a kapcsolódó kötelezettségben van megadva.
-   **Az ár és az engedmény rögzített** – A rendeléssorban található ár és a hozzá kapcsolódó kötelezettségvállalásban megadott ár nem lehet eltérő. Ha a rendelési sorban módosítja az árat, akkor a kapcsolat a kötelezettségvállaláshoz megszakad. Ha a kapcsolat megszakad, akkor a rendeléssor nem számít bele a kötelezettségvállalás teljesítésébe.
-   **Kiadás minimális összege** és **Kiadás maximális összege** – Ha itt szerepel összeg, akkor egy üzenet jelenik meg, valahányszor úgy próbálja módosítani a rendeléssort, hogy az eltér a hozzá kapcsolódó kötelezettségvállalástól.

## <a name="fulfillment-calculations-for-sales-agreements"></a>Értékesítési szerződések teljesítésének kiszámítása
A **Teljesítés** lapról **Soradatok** gyorslapon az **Értékesítési szerződések** lap megmutatja a teljesítési mennyiségeket és összegeket.  

A **Teljesítés** területen láthatja a kérdéses értékesítési szerződéshez kapcsolt rendelési sorokhoz meghatározott mennyiségeket és összegeket. Megtekintheti a fennmaradó összeget és mennyiséget is, amely a kötelezettségvállalás teljesítéséhez szükséges.  

A **Szerződés** területen megtekintheti az adott értékesítési szerződésből származó mennyiségeket és összegeket. Összesen ezekre a összegekre és mennyiségekre vállalt kötelezettséget a szervezet.

## <a name="confirmations-and-version-history-for-sales-agreements"></a>Értékesítési szerződés visszaigazolásai és verzióelőzményei
Miután az értékesítési szerződést megerősítették, aktuális verziója bekerül az előzményeket tároló táblába. Ha módosítja az értékesítési szerződést, akkor újra megerősítheti, hogy egy másik verzióját tárolja el az előzményekben.  

Ha nem erősíti meg az értékesítési szerződést, akkor is használhatja azt értékesítési rendelések létrehozásához. Ilyenkor azonban az értékesítési szerződés előzményadatai nem kerülnek tárolásra.  

A visszaigazolások valamennyi revízióját megtekintheti és ki is nyomtathatja. Ezután megoszthatja a módosításokat a vevőjével, hogy jóváhagyását kérje rájuk.

## <a name="applying-sales-agreements-during-the-ordering-process"></a>Értékesítési szerződések használata a rendelési folyamatban
Ha nem ad ki értékesítési rendeléseket közvetlenül az értékesítési szerződésekhez, attól még hozzákapcsolhat egy értékesítési szerződés egy rendeléshez a rendelésbeviteli folyamat során. Amikor egy új értékesítési rendelést hoz létre és kiválasztja az értékesítési szerződést, akkor annak a szerződésnek a feltételei, úgy mint fizetési feltételek, szállítási feltételek és szállítási cím bekerülnek a rendelés fejlécébe és a szerződés és rendelés közötti kapcsolat létrejön. Ezután a rendelési sorokba másolódnak az árak és engedmények a szerződésből, amikor termékeket és termékkategóriákat jelölhet ki a meghatározott értékesítési rendelésben. Ugyanazon értékesítési rendelés tartalmazhat olyan sorokat, amelyek nincsenek kapcsolatban állnak az értékesítési szerződéssel és olyanokat is, amelyek kötelezettséggel rendelkeznek az értékesítési szerződés felé.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Értékesítési szerződésekhez kapcsolat értékesítési rendelések módosítása
Ha létrehozott (kiadott) egy értékesítési rendelést egy értékesítési szerződés szerint, akkor az értékesítési rendelés soraiban szereplő néhány mező csak akkor módosítható, ha eltávolítja a kapcsolatot a társított értékesítési szerződés sorokkal. A következő táblázat felsorol ezen mezők közül néhányat.

| Mező                                                             | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kért szállítási dátum                                               | Ha módosítja a kért szállítási dátumot egy korábbi dátumra, mint az **Érvénybe lépési dátum** érték az értékesítési szerződés sorában, akkor el kell távolítania a kapcsolatot az értékesítési szerződéshez, mielőtt el tudja menteni a módosított szállítási dátumot. Ha módosítja a kért szállítási dátumot egy későbbi dátumra, mint az **Lejárat dátuma** érték az értékesítési szerződés sorában, akkor el kell távolítania a kapcsolatot az értékesítési szerződéshez, mielőtt el tudja menteni a módosított szállítási dátumot. |
| CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet összege | Ha ezen mezők értékének bármelyikét módosítja és ha a **Rögzített ár és engedmény** jelölőnégyzet be van jelölve, a kapcsolódó értékesítési szerződés sorában, akkor egy üzenetpanel kéri a módosítás mentését. Kattintson az **Igen** gombra, hogy eltávolítsa a az értékesítési szerződéssel való kapcsolatot és újraszámítsa az árat. Kattintson a **Nem** gombra, hogy eltávolítsa a az értékesítési szerződéssel való kapcsolatot az ár újraszámítása nélkül.                                                                   |
| Nettó összeg                                                        | Ha megad egy összeget amely meghaladja az értékesítési szerződés sorában meghatározott összeget, ahol a **Maximum betartatása** jelölőnégyzet be van jelölve, akkor egy üzenetpanelen kéri a módosított összeg mentését. Kattintson az **Igen** gombra, hogy eltávolítsa a az értékesítési szerződéssel való kapcsolatot és újraszámítsa az árat. Kattintson a **Nem** gombra, hogy eltávolítsa a az értékesítési szerződéssel való kapcsolatot az ár újraszámítása nélkül.                                                                 |
| Mennyiség                                                          | Ha megad egy mennyiséget amely meghaladja az értékesítési szerződés sorában meghatározott mennyiséget, ahol a **Maximum betartatása** jelölőnégyzet be van jelölve, akkor egy üzenetpanelen kéri a módosított mennyiség mentését. Kattintson az **Igen** gombra, hogy eltávolítsa a az értékesítési szerződéssel való kapcsolatot és újraszámítsa az árat. Kattintson a **Nem** gombra, hogy eltávolítsa a az értékesítési szerződéssel való kapcsolatot az ár újraszámítása nélkül.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Értékesítési szerződéssel rendelt cikk visszaküldése
Amikor egy vevő visszaküld egy értékesítési szerződéssel megrendelt terméket, a Supply Chain Management megtalálja és automatikusan frissíti a vonatkozó értékesítési szerződés kötelezettségvállalását, hogy tükrözze a változást a mennyiségben vagy összegben. Olyan visszáru rendelés létrehozásával, amely egy értékesítési szerződéshez kötött értékesítési rendelésen alapul Ön kialakít egy kapcsolatot az értékesítési szerződés kötelezettségvállalása az értékesítésirendelés-sor és a visszárurendelés-számla között.  

Ha nem szeretné az értékesítési szerződés kötelezettségvállalásából levonni a visszaküldött cikkek mennyiségét, használhatja a **Kapcsolat eltávolítása** vezérlőt a **Visszáru rendelés** oldalon, hogy eltávolítsa a visszáru rendelés és az értékesítési szerződés kötelezettségvállalása közötti kapcsolatot. Ha később újra ki kell alakítania a kapcsolatot kattintson a **Kapcsolat létrehozása** gombra.  

**Megjegyzés:** A visszáru rendelés csak egy értékesítési szerződéshez kapcsolható. Ha a vevő több terméket küld vissza, mint amennyi több értékesítési szerződésben rendelve lett, akkor létre kell hoznia egy új visszáru rendelést minden termékhez, és össze kell kapcsolnia a hozzá tartozó értékesítési szerződéssel.

## <a name="automatic-search-for-sales-agreements"></a>Értékesítési szerződések automatikus keresése
Bizonyos esetekben, ha értékesítési rendelések közvetetten jönnek létre, például mikor jóváírást vagy vállalatközi értékesítési rendeléseket készít eldöntheti, hogy a rendszer automatikusan keressen-e alkalmazható értékesítési szerződéseket.

## <a name="financial-dimensions-on-sales-agreements"></a>Értékesítési szerződések pénzügyi dimenziói
Pénzügyi dimenziókat másolhat a dokumentum fejlécébe vagy az értékesítési szerződés egyedi soraiba. Bármikor módosíthatja egy szerződés fejlécének vagy sorainak dimenzióit. Ebben az esetben a dimenziók automatikusan átmásolódnak a kiadási rendelések kiadás fejlécébe vagy kiadás sorába.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]