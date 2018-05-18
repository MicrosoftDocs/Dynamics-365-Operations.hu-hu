---
title: "Rendelési ígéretek"
description: "A cikk a rendelési ígéretekről nyújt információkat. A rendelési ígéret segít abban, hogy megbízható ígéretet tegyen a szállítási dátumról a vevőknek és rugalmasságot biztosít, hogy ezek a dátumok megfeleljenek."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 039bc5c572d204d9fa3e10a9f33cb4f4eb00b31c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="order-promising"></a>Rendelési ígéretek

[!include [banner](../includes/banner.md)]

A cikk a rendelési ígéretekről nyújt információkat. A rendelési ígéret segít abban, hogy megbízható ígéretet tegyen a szállítási dátumról a vevőknek és rugalmasságot biztosít, hogy ezek a dátumok megfeleljenek.

Rendelés ígéret számítja ki a lehető legkorábbi szállítási és kézhezvételi dátumok, és a szállítási dátum vezérlő módot és szállítási napok szállítási alapul. Négy szállítási dátum ellenőrzési módszer közül választhat:

-   **Értékesítés átfutási ideje** – Az értékesítés átfutási ideje az értékesítés rendelés létrehozása és a szállítás közti idő. A kézbesítési dátum számítása a napok egy alapértelmezett száma alapján történik, és nem veszi figyelembe a készlet rendelkezésre állását, az ismert igényt vagy a tervezett ellátást.
-   **Ígérethez rendelkezésre áll (elérhető Ígérethez)** – Az Ígérethez rendelkezésre áll a cikk azon mennyiségét jelenti, amely elérhető és szállítható a vevőnek adott időre. Az Ígérethez rendelkezésre álló mennyiség kiszámítása tartalmazza a nem véglegesített készletet, az átfutási időket a tervezett bevételezéseket és kiadásokat.
-   **ígérethez rendelkezésre áll + Kiadási időtartalék**– A szállítás dátuma megegyezik az ígérethez rendelkezésre áll (ATP) dátummal, plusz a cikkre vonatkozó kiadási időtartalékkal. A kiadási időtartalék a szállítandó cikkek előkészítéséhez szükséges idő.
-   **Ígérhető**– Az elérhetőség az alábontás alapján számítható.

## <a name="atp-calculations"></a>Ígérethez rendelkezésre áll számítások
Az ígérethez rendelkezésre álló mennyiséget a rendszer a „kumulatív és előretekintéssel meghatározott, ígérethez rendelkezésre álló mennyiség” módszerrel számítja ki. Ennek az ígérethez rendelkezésre áll számítási módszernek a fő előnye, hogy kezelhetők olyan esetek, ahol a kiadások összeg a bevételek között nagyobb, mint a legfrissebb bevétel (például amikor egy korábbi bevételezési mennyiséget fel kell használni a követelmények miatt). A „kumulatív ígérethez rendelkezésre állás és előretekintés” számítási módszer minden kiadást magába foglal, amíg a bevételezendő kumulatív mennyiség meghaladja a kumulatív kiadandó mennyiséget. Ezért az ígérethez rendelkezésre állás számítás módszer kiértékeli, hogy a mennyiség egy része a korábbi időszakból használható-e a későbbi időszakban.  

Az Ígérethez rendelkezésre álló mennyiség készletegyenlege nem véglegesített az első időszakban. Általában az egyes időszakokra kerül kiszámításra, amelyekben a bevételezés ütemezve van. A program kiszámítja az ígérethez rendelkezésre álló mennyiség időszakának napjait, és a mennyiség első napjaként az aktuális dátumot határozza meg. Az első időszakban az ígérethez rendelkezésre álló mennyiség az aktuális készlet esedékes és lejárt vevői rendelésekkel csökkentett mennyisége.  

A rendszer a következő képlettel számítja ki az ígérethez rendelkezésre álló mennyiséget:  

Ígérethez rendelkezésre áll = Az előző időszakban ígérethez rendelkezésre álló készlet + Az aktuális időszak bevételezései - Az aktuális időszak kiadásai – Az összes jövőbeni időszak bevételezéseinek összegének időszakáig, minden egyes jövőbeni időszak nettó kiadási mennyisége, a jövőbeni időszakot beleértve és azzal bezárólag nagyobb, mint a kiadások összege a jövőbeni időszakkal bezárólag.  

Ha nincs több figyelembe vehető kiadás vagy bevételezés, akkor az ígérethez rendelkezésre álló mennyiség a további dátumokon ugyanaz lesz, mint az ígérethez rendelkezésre álló utolsó számított mennyiség.  

Ha az ígérethez rendelkezésre álló mennyiség ellenőrzésekor egy cikknek nincs minden dimenziója megadva, a hiányzó dimenziók később is megadhatók a bevételezésekben és kiadásokban. Ebben az esetben az ígérethez rendelkezésre álló mennyiség számításakor a bevételezéseket és kiadásokat összesíteni kell a meglévő dimenziókban, hogy a mennyiség számításában résztvevő bevételezési és kiadási sorok száma csökkenjen.  

A megjelenített ígérethez rendelkezésre állási mennyiség mindig 0 (nulla) vagy nagyobb. Ha az ígérethez rendelkezésre állási mennyiség számítás eredménye negatív (pl. ha az előzetesen ígért mennyiség túllépi az elérhető mennyiséget), akkor a program automatikusan **0** értékre állítja.

### <a name="example"></a>Példa

Az **Ígérethez rendelkezésre áll – igény visszamenőleges időkorlátja** mező szabályozza, hogy milyen messzire lehet visszamenni időben késett igényrendelések vagy készletkiadások keresésekor. Az **Ígérethez rendelkezésre áll – készlet visszamenőleges időkorlátja** mező szabályozza, hogy milyen messzire lehet visszamenni időben késett készletrendelések vagy készlet bevételezések keresésekor. Például ha a csak hét napot késett rendeléseket figyelembe kívánja venni az ígérethez rendelkezésre állási számításban, mindkét mező értéke **7** kell legyen.  

Az **Ígérethez rendelkezésre áll – késleltetett igény várakozási ideje** és **Ígérethez rendelkezésre áll - késleltetett ellátás várakozási ideje** mezők szabályozzák, hogy a késleltetett igényt vagy ellátást figyelembe kell-e venni az ígérethez rendelkezésre állási számításban. Például ha a késleltetett szállításokat és igényeket is figyelembe kell venni az ígérethez rendelkezésre állási számításban holnapután, akkor mindkét mező értéke **2** kell hogy legyen. A **2** értéke azt jelenti, hogy a cikk mennyisége a késleltetett beszerzési rendelésen, amelyet figyelembe kell venni a ígérethez rendelkezésre állási számításban, két nap múlva is elérhető lesz.  

Az alábbi példánál **7** van megadva az **Ígérethez rendelkezésre áll – igény visszamenőleges időkorlátja** és **Ígérethez rendelkezésre áll – ellátás visszamenőleges időkorlátja** mezőkben, és **1** az **Ígérethez rendelkezésre áll - késleltetett igény várakozási ideje** és **Ígérethez rendelkezésre áll – késleltetett ellátás várakozási ideje** mezőkben.  

Egy 200 darabos beszerzési rendelés, amelyet három nappal korábban kellett volna megkapni még nem érkezett meg. Emiatt egy termék értékesítési rendelésének 75 sora, amelyet tegnap kellett volna szállítani nem került szállításra.  

A vevő telefonál, és 150 egységet venne egy termékből. Ha megerősíti a termék elérhetőségét, akkor egy másik, a termékre szóló 100 darabos beszerzési rendelés 10 napon belül kerül szállításra.  

Létrehozhat egy értékesítési rendeléssort a termékhez és megadhat **150** mennyiséget.  

Mivel a szállítási dátum ellenőrzésének módja az ígérethez rendelkezésre áll, az ígérethez rendelkezésre áll adatokat ki kell számítani a legkorábbi szállítási dátumhoz. A beállítások alapján a késleltetett beszerzési rendelés és értékesítési rendelés feldolgozásra kerül és kapott ígérethez rendelkezésre állási mennyiség a jelenlegi dátumhoz 0. Holnap, amikor a késleltetett beszerzési rendelés beérkezése várható, az ígérethez rendelkezésre állási mennyiségre kapott érték nagyobb, mint 0 (ebben az esetben 125 az értéke). Ugyanakkor mostantól 10 nap múlva, amikor a 100 darabra szóló kiegészítő beszerzési rendelés érkezése várható, az ígérethez rendelkezésre állási mennyiség több, mint 150.  

Ezért a szállítási dátum az ígérethez rendelkezésre állás számításának alapján a mai naptól számított 10 nap. Ennek megfelelően tájékoztassa az ügyfelet, hogy az igényelt mennyiség 10 nap múlva szállítható.




