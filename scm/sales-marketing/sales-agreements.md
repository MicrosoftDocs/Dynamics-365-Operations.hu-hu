---
title: "Értékesítési szerződések"
description: "Ez a cikk az értékesítési szerződésekkel kapcsolatos információkról nyújt tájékoztatást. Az értékesítési szerződés olyan szerződés, amelyben egy vevő vállalja, hogy az adott termékből bizonyos összegért vagy egy bizonyos mennyiséget vásárol az idő tekintetében, különleges árak és engedmények ellenében."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 9554
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4dd1eae27ae33837fbab16f764083168578d0a29
ms.lasthandoff: 03/31/2017


---

# <a name="sales-agreements"></a>Értékesítési szerződések

Ez a cikk az értékesítési szerződésekkel kapcsolatos információkról nyújt tájékoztatást. Az értékesítési szerződés olyan szerződés, amelyben egy vevő vállalja, hogy az adott termékből bizonyos összegért vagy egy bizonyos mennyiséget vásárol az idő tekintetében, különleges árak és engedmények ellenében.

Az értékesítési szerződés olyan szerződés, amely kötelez egy vevőt, hogy termékeket vásároljon egy adott mennyiségben, vagy adott összegben adott idő alatt, különleges árakért, engedményekért és egyéb különleges feltételekért cserébe, mint például fizetési vagy szállítási feltételek. Az értékesítési szerződésben foglalt árak és engedmények felülírják a többi létező kereskedelmi megállapodásban beállított árak és engedmények értékét.  

Az értékesítési szerződés érvényességi időszakát a szerződés **Érvénybe lépési dátum** és **Lejárat dátuma** mezői határozzák meg. A vevő értékesítési rendelése akkor felel meg a szerződés feltételeinek, ha a rendelés kért szállítási dátuma az érvényességi időszakban van. Minden értékesítésirendelés-sor, amely egy értékesítési szerződéshez van kötve hozzájárul az adott értékesítési szerződés teljesítéséhez.  

Értékesítési rendelést közvetlenül létrehozhat az értékesítési szerződésből a **Kiadási rendelés** művelet felhasználásával. Másik lehetőségként kiválaszthatja az érvényes értékesítési szerződést, amikor megteszi a rendelést (lásd az „Értékesítési szerződések alkalmazása a rendelési folyamatban” bekezdést ebben a cikkben).  

**Megjegyzés:** a korábbi verziókban értékesítési szerződések voltak a továbbiakban eladási keretszerződéseknél.

## <a name="commitment-types"></a>Kötelezettségtípusok
Az értékesítési szerződés minden sora egy-egy kötelezettségvállalás bizonyos eladásra. A kötelezettségek alapvetően két csoportra oszlanak:

-   **Érték-kötelezettség **– a vevő elfogadja, hogy termékeket vásárol egy meghatározott összegért.
-   **Mennyiség-kötelezettség **– A vevő elfogadja, hogy meghatározott mennyiségű terméket fog vásárolni.

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
Ha nem ad ki értékesítési rendeléseket közvetlenül az értékesítési szerződésekhez, attól még hozzákapcsolhat egy értékesítési szerződést egy rendeléshez a beviteli folyamat során. Amikor egy új értékesítési rendelést hoz létre és kiválasztja az értékesítési szerződést, akkor annak a szerződésnek a feltételei, úgy mint fizetési feltételek, szállítási feltételek és szállítási cím bekerülnek a rendelés fejlécébe és a szerződés és rendelés közötti kapcsolat létrejön. Ezután a rendelési sorokba másolódnak az árak és engedmények a szerződésből, amikor termékeket és termékkategóriákat jelölhet ki a meghatározott értékesítési rendelésben. Ugyanazon értékesítési rendelés tartalmazhat olyan sorokat, amelyek nincsenek kapcsolatban állnak az értékesítési szerződéssel és olyanokat is, amelyek kötelezettséggel rendelkeznek az értékesítési szerződés felé.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Értékesítési szerződésekhez kapcsolat értékesítési rendelések módosítása
Ha létrehozott (kiadott) egy értékesítési rendelést egy értékesítési szerződés szerint, akkor az értékesítési rendelés soraiban szereplő néhány mező csak akkor módosítható, ha eltávolítja a kapcsolatot a társított értékesítési szerződés sorokkal. A következő táblázat felsorol ezen mezők közül néhányat.

| Mező                                                             | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kért szállítási dátum                                               | Ha módosítja a kért szállítási dátumot egy korábbi dátumra, mint az **Érvénybe lépési dátum** érték az értékesítési szerződés sorában, akkor el kell távolítania a kapcsolatot az értékesítési szerződéshez, mielőtt el tudja menteni a módosított szállítási dátumot. Ha módosítja a kért szállítási dátumot egy későbbi dátumra, mint az **Lejárat dátuma** érték az értékesítési szerződés sorában, akkor el kell távolítania a kapcsolatot az értékesítési szerződéshez, mielőtt el tudja menteni a módosított szállítási dátumot. |
| CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet összege | Ha ezen mezők értékének bármelyikét módosítja és ha a **Rögzített ár és engedmény** jelölőnégyzet be van jelölve, a kapcsolódó értékesítési szerződés sorában, akkor egy üzenetpanel kéri a módosítás mentését. Kattintson a **Igen** az értékesítési szerződés sorára mutató hivatkozás eltávolítása, és az ár újraszámítása. Kattintson a **nem** az értékesítési szerződés sorára mutató hivatkozás eltávolítása nélkül az ár újraszámítása.                                                                   |
| Nettó összeg                                                        | Ha megad egy összeget amely meghaladja az értékesítési szerződés sorában meghatározott összeget, ahol a **Maximum betartatása** jelölőnégyzet be van jelölve, akkor egy üzenetpanelen kéri a módosított összeg mentését. Kattintson a **Igen** az értékesítési szerződés sorára mutató hivatkozás eltávolítása, és az ár újraszámítása. Kattintson a **nem** az értékesítési szerződés sorára mutató hivatkozás eltávolítása nélkül az ár újraszámítása.                                                                 |
| Mennyiség                                                          | Ha megad egy mennyiséget amely meghaladja az értékesítési szerződés sorában meghatározott mennyiséget, ahol a **Maximum betartatása** jelölőnégyzet be van jelölve, akkor egy üzenetpanelen kéri a módosított mennyiség mentését. Kattintson a **Igen** az értékesítési szerződés sorára mutató hivatkozás eltávolítása, és az ár újraszámítása. Kattintson a **nem** az értékesítési szerződés sorára mutató hivatkozás eltávolítása nélkül az ár újraszámítása.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Értékesítési szerződéssel rendelt cikk visszaküldése
A vevő a megrendelt termék értékesítési szerződés adja vissza, amikor Microsoft Dynamics 365 műveletek keresse meg, és automatikusan frissíti a kapcsolódó értékesítési szerződés kötelezettségvállalás a mennyiség vagy összeg módosításának megfelelően. Olyan visszáru rendelés létrehozásával, amely egy értékesítési szerződéshez kötött értékesítési rendelésen alapul Ön kialakít egy kapcsolatot az értékesítési szerződés kötelezettségvállalása az értékesítésirendelés-sor és a visszárurendelés-számla között.  

Ha nem szeretné az értékesítési szerződés kötelezettségvállalásából levonni a visszaküldött cikkek mennyiségét, használhatja a **Kapcsolat eltávolítása** vezérlőt a **Visszáru rendelés** oldalon, hogy eltávolítsa a visszáru rendelés és az értékesítési szerződés kötelezettségvállalása közötti kapcsolatot. Ha később újra ki kell alakítania a kapcsolatot kattintson a **Kapcsolat létrehozása** gombra.  

**Megjegyzés:** A visszáru rendelés csak egy értékesítési szerződéshez kapcsolható. Ha a vevő több terméket küld vissza, mint amennyi több értékesítési szerződésben rendelve lett, akkor létre kell hoznia egy új visszáru rendelést minden termékhez, és össze kell kapcsolnia a hozzá tartozó értékesítési szerződéssel.

## <a name="automatic-search-for-sales-agreements"></a>Értékesítési szerződések automatikus keresése
Bizonyos esetekben, amikor eladási rendeléseket készít közvetve például a jóváírás vagy a vállalatközi értékesítési rendelések létrehozásakor megadhatja, hogy Microsoft Dynamics 365 műveletek automatikusan megkeresi alkalmazandó értékesítési szerződések.

## <a name="financial-dimensions-on-sales-agreements"></a>Értékesítési szerződések pénzügyi dimenziói
Pénzügyi dimenziókat másolhat a dokumentum fejlécébe vagy az értékesítési szerződés egyedi soraiba. Bármikor módosíthatja egy szerződés fejlécének vagy sorainak dimenzióit. Ebben az esetben a dimenziók automatikusan átmásolódnak a kiadási rendelések kiadás fejlécébe vagy kiadás sorába.


