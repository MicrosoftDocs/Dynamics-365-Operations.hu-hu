---
title: "Rendelési ígéretek"
description: "A cikk a rendelési ígéretekről nyújt információkat. A rendelési ígéret segít abban, hogy megbízható ígéretet tegyen a szállítási dátumról a vevőknek és rugalmasságot biztosít, hogy ezek a dátumok megfeleljenek."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8aa0a58b03ee18e42ca7770ea3e22311c1ddba67
ms.lasthandoff: 03/31/2017


---

# <a name="order-promising"></a>Rendelési ígéretek

A cikk a rendelési ígéretekről nyújt információkat. A rendelési ígéret segít abban, hogy megbízható ígéretet tegyen a szállítási dátumról a vevőknek és rugalmasságot biztosít, hogy ezek a dátumok megfeleljenek.

Rendelés ígéret számítja ki a lehető legkorábbi szállítási és kézhezvételi dátumok, és a szállítási dátum vezérlő módot és szállítási napok szállítási alapul. Négy szállítási dátum ellenőrzési módszer közül választhat:

-   **Értékesítés átfutási idő** – az értékesítés átfutási ideje az az idő, a értékesítési rendelés létrehozása és a cikkek szállítása közötti. A szállítási dátum kiszámítása egy napok alapértelmezett száma alapján, és nem veszi figyelembe a készlet rendelkezésre állását, ismert igény vagy tervezett ellátás.
-   **ATP (rendelkezésre álló Ígérethez)** – Ígérethez rendelkezésre áll az a mennyiség, az egyik elem áll rendelkezésre, és a vevőnek egy adott napon is ígért. Az Ígérethez rendelkezésre álló mennyiség kiszámítása tartalmazza a nem véglegesített készletet, az átfutási időket a tervezett bevételezéseket és kiadásokat.
-   **ígérethez rendelkezésre áll + Kiadási időtartalék**– A szállítás dátuma megegyezik az ígérethez rendelkezésre áll (ATP) dátummal, plusz a cikkre vonatkozó kiadási időtartalékkal. A kiadási időtartalék a szállítandó cikkek előkészítéséhez szükséges idő.
-   **Ígérhető **– Az elérhetőség az alábontás alapján számítható.

## <a name="atp-calculations"></a>Ígérethez rendelkezésre áll számítások
Az Ígérethez rendelkezésre álló mennyiség "a keresési összesített ATP" módszerrel számítják ki. Az ATP számítási módszer fő előnye a hogy is képes kezelni az esetekben, amikor problémák között bevételek összege több, mint a legújabb (például, ha egy korábbi kézhezvételétől számított mennyiség megfeleljen egy követelménynek kell használni). Számítási módszer: a "a keresési összesített ATP" magában foglalja valamennyi kérdést mindaddig, amíg az összesített mennyiség meghaladja az összesített mennyiség kibocsátására. Ezért az ígérethez rendelkezésre állás számítás módszer kiértékeli, hogy a mennyiség egy része a korábbi időszakból használható-e a későbbi időszakban.  

Az Ígérethez rendelkezésre álló mennyiség készletegyenlege nem véglegesített az első időszakban. Általában az egyes időszakokra kerül kiszámításra, amelyekben a bevételezés ütemezve van. A program kiszámítja az ígérethez rendelkezésre álló mennyiség időszakának napjait, és a mennyiség első napjaként az aktuális dátumot határozza meg. Az első időszakban az ígérethez rendelkezésre álló mennyiség az aktuális készlet esedékes és lejárt vevői rendelésekkel csökkentett mennyisége.  

A rendszer a következő képlettel számítja ki az ígérethez rendelkezésre álló mennyiséget:  

Ígérethez rendelkezésre álló mennyiség = ATP az előző időszak + bevételek a tárgyidőszakban – az aktuális időszak problémák – nettó kiadási mennyiség csak az időszakban, amikor minden jövőbeni időszakokra, az elkövetkező időszakra bezárólag bevételek összege meghaladja a problémák összege legfeljebb minden jövőbeli időszakra és többek között az elkövetkező időszakra.  

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

Mivel a szállítási dátum ellenőrzésének módja az ígérethez rendelkezésre áll, az ígérethez rendelkezésre áll adatokat ki kell számítani a legkorábbi szállítási dátumhoz. A beállítások alapján, a késleltetett beszerzési rendelés és eladási rendelés tekintendők, és az aktuális dátumot a létrejövő Ígérethez rendelkezésre álló mennyiség: 0. Holnap, ha a késleltetett beszerzési rendelés várhatóan befolyó, az Ígérethez rendelkezésre álló mennyiség számítása több mint 0 (ebben az esetben kiszámítása a következőképpen történik 125). Azonban 10 nap, amikor a 100 darabot újabb beszerzési rendelés várható kapott, az Ígérethez rendelkezésre álló mennyiség lesz több mint 150.  

Ezért a szállítási dátum értéke 10 nap múlva, az ígérethez alapján. Ennek megfelelően tájékoztassa az ügyfelet, hogy az igényelt mennyiség 10 nap múlva szállítható.


