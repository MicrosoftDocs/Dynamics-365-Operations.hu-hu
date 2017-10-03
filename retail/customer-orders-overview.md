---
title: "Vevői rendelések – áttekintés"
description: "Ez a témakör a vevői rendelések a Retail Modern POS (MPOS) modulban történő kezelését ismerteti. A vevői rendelések speciális rendelések néven is ismertek. A témakör a kapcsolódó paramétereket és tranzakciófolyamatokat is tárgyalja."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 89e79c7227e05eec539d9bb142b8f41de092f01b
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017



---

# <a name="customer-orders-overview"></a>Vevői rendelések – áttekintés

[!include[banner](includes/banner.md)]


Ez a témakör a vevői rendelések a Retail Modern POS (MPOS) modulban történő kezelését ismerteti. A vevői rendelések speciális rendelések néven is ismertek. A témakör a kapcsolódó paramétereket és tranzakciófolyamatokat is tárgyalja.

A sokcsatornás kiskereskedelmi világ számos kiskereskedő biztosít lehetőséget vevői rendelésekre vagy speciális rendelésekre, hogy így elégítsen ki termékkel és teljesítéssel kapcsolatos különböző igényeket. Íme néhány tipikus forgatókönyv:

-   Egy vevő azt szeretné, ha a termékeket egy adott napon egy adott címre szállítanák ki.
-   Egy vevő egy olyan üzetben vagy helyen szeretné átvenni a termékeket, amely eltér attól az üzlettől vagy helytől, ahol az ügyfél megvásárolta az adott termékeket.
-   Egy vevő szeretné, ha valaki más venné át a vevő által vásárolt termékeket.

A kiskereskedők a készlethiány által okozott elmaradt értékesítések minimálisra csökkentése érdekében is használják a vevői rendeléseket, mivel így az áru más időben vagy helyen is kiszállítható vagy átvehető.

## <a name="set-up-customer-orders"></a>Vevői rendelések beállítása
Íme néhány, a **Kiskereskedelmi paraméterek** oldalon beállítható paraméter, amely megszabja, hogyan teljesülnek a vevői rendelések:

-   **Letét alapértelmezett százalékos értéke** – annak az összegnek a megadása, amelyet a vevőnek ki kell fizetnie letétként, mielőtt a megrendelést meg lehet erősíteni. Az alapértelmezett letét kiszámítása a rendelés százalékának függvényeként történik. Jogosultságoktól függően előfordulhat, hogy egy bolti dolgozó felülbírálhatja az összeget a **Letét felülbírálása** funkcióval.
-   **Érvénytelenítési díj százalékos értéke** – ha vevői rendelés visszavonásakor díjfizetés szükséges, úgy adja meg ezen díj összegét.
-   **Érvénytelenítési díj kódja** – ha vevői rendelés visszavonásakor díjfizetés szükséges, ezt a díjat egy díjkód tükrözi az értékesítési rendelésben. E paraméter segítségével határozza meg a lemondási díj kódját.
-   **Szállítási költség kódjának** – a kiskereskedők külön díjat számolhatnak fel az áru szállításáért a vevőnek. E szállítási költség összege költségkód alatt megjelenik az értékesítési rendelésen. Használja ezt a paramétert a szállítási költségkód hozzárendeléséhez a szállítási költségekhez a vevői rendelésen.
-   **Szállítási költségek visszatérítése** – adja meg, hogy a vevői rendeléshez kapcsolódó szállítási költségek visszatéríthetők-e.
-   **Maximális összeg jóváhagyás nélkül** – ha a szállítási költségek visszatéríthetők, adja meg a visszárurendeléseken keresztül biztosítható maximális szállításiköltség-visszatérítés összegét. Ha ezt az összeget túllépik, a vezető részéről felülbírálás szükséges a visszatérítés folytatásához. Az alábbi esetek kezeléséhez a szállítási költségek visszatérítése túllépheti az eredetileg kifizetett összeget:
    -   A költségek alkalmazására az értékesítési rendelés fejlécének szintjén kerül sor, és amikor egy termékkör bizonyos mennyiségét visszaküldik, a szállítási költségek a termékekhez engedélyezett maximális visszatérítése és a mennyiség nem határozható meg úgy, hogy az minden kiskereskedelmi vevő számára megfelelő legyen.
    -   Minden szállítási példánynál felmerülnek szállítási költségek. Ha egy vevő többször küld vissza termékeket, és a kiskereskedő irányelve kimondja, hogy a visszatérítési szállítási költségek költségét a kiskereskedő viseli, a visszatérítési szállítási költségek összege magasabb lesz a tényleges szállítási költségeknél.

## <a name="transaction-flow-for-customer-orders"></a>Tranzakció folyamata vevői rendeléseknél
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Vevői rendelés létrehozása Retail Modern POS-ben

1.  Vevő hozzáadása a tranzakcióhoz
2.  Adjon hozzá termékeket a kosárhoz.
3.  Kattintson a **Vevői rendelés létrehozása** elemre, majd válassza ki a rendelés típusát. A rendelés típusa lehet **Vevői rendelés** vagy **Ajánlat**.
4.  Kattintson a **Kijelölt szállítása** vagy az **Összes szállítása** elemre a termékek a vevői fiókban szereplő egyik címre történő kiszállításához, adja meg a kért szállítási dátumot, és adja meg a szállítási költségeket.
5.  Kattintson a **Kijelölt felvétele** vagy az **Összes felvétele** elemre a jelenlegi vagy egy másik boltból adott napon átvételre kerülő termékek kiválasztásához.
6.  Szedje be a letét összegét, ha letétre szükség van.

### <a name="edit-an-existing-customer-order"></a>Meglévő vevői rendelés szerkesztése

1.  A kezdőlapon kattintson a **Rendelés keresése** elemre.
2.  Keresse meg és válassza ki a szerkesztendő rendelést. A lap alján kattintson a **Szerkesztés** elemre.

### <a name="pick-up-an-order"></a>Rendelés felvétele

1.  A kezdőlapon kattintson a **Rendelés keresése** elemre.
2.  Válassza ki a felveendő rendelést. A lap alján kattintson a **Kitárolás és csomagolás** elemre.
3.  Kattintson a **Felvétel** elemre.

### <a name="cancel-an-order"></a>Rendelés visszavonása

1.  A kezdőlapon kattintson a **Rendelés keresése** elemre.
2.  Válassza ki a visszavonni kívánt megrendelést. A lap alján kattintson az **Érvénytelenítés** elemre.

#### <a name="create-a-return-order"></a>Visszárurendelés létrehozása

1.  A kezdőlapon kattintson a **Rendelés keresése** elemre.
2.  Válassza ki a visszaküldeni kívánt rendelést, válassza a rendeléshez tartozó számlát, és válassza ki a visszaküldendő áruhoz tartozó terméksort .
3.  A lap alján kattintson a **Visszárurendelés** elemre.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Tranzakció aszinkron folyamata vevői rendeléseknél
Vevői rendelések pénztári (POS) kliensből szinkron vagy aszinkron üzemmódban hozhatók létre.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Vevői rendelések aszinkron módban történő létrehozásának engedélyezése

1.  Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztárbeállítás** &gt; **Pénztárprofil** &gt; **Funkcióprofilok** elemre.
2.  Az **Általános** gyorslapon állítsa a **Vevői rendelés létrehozása aszinkron módban** lehetőséget **Igen** értékre.

Ha a **Vevői rendelés létrehozása aszinkron módban** beállítása **Igen**, a vevői rendelések mindig aszinkron módban jönnek létre, akkor is, ha a Retail Transaction Service (RTS) elérhető. Ha ennél a beállításnál **Nem** értéket ad meg, a vevői rendelések mindig szinkron módban jönnek létre az RTS segítségével. Vevői rendelések aszinkron módban történő létrehozásakor ezeket a rendszer lekéri és kiskereskedelmi lekérési (P) feladatként beilleszti. A megfelelő vevői rendelések a **Rendelések szinkronizálása** manuális futtatásakor vagy kötegelt feldolgozás révén jönnek létre a Kiskereskedelem modulban.

<a name="see-also"></a>Lásd még
--------

[Hibrid vevői rendelések](hybrid-customer-orders.md)




