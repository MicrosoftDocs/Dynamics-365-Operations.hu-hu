---
title: Rendelési ígéretek
description: A cikk a rendelési ígéretekről nyújt információkat. A rendelési ígéret segít abban, hogy megbízható ígéretet tegyen a szállítási dátumról a vevőknek és rugalmasságot biztosít, hogy ezek a dátumok megfeleljenek.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c835e25348b937c1dd68d8fa45b0264bd6815c23
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228266"
---
# <a name="order-promising"></a>Rendelési ígéretek

[!include [banner](../includes/banner.md)]

A cikk a rendelési ígéretekről nyújt információkat. A rendelési ígéret segít abban, hogy megbízható ígéretet tegyen a szállítási dátumról a vevőknek és rugalmasságot biztosít, hogy ezek a dátumok megfeleljenek.

Rendelés ígéret számítja ki a lehető legkorábbi szállítási és kézhezvételi dátumok, és a szállítási dátum vezérlő módot és szállítási napok szállítási alapul. A következő szállításidátum-ellenőrzési módszerek közül választhat:

- **Értékesítés átfutási ideje** – Az értékesítés átfutási ideje az értékesítés rendelés létrehozása és a szállítás közti idő. A szállítási dátum számítása az alapértelmezett számú napon alapul, és nem veszi figyelembe a készlet rendelkezésre állását, az ismert igényt vagy a tervezett készletet.
- **Ígérethez rendelkezésre áll (elérhető Ígérethez)** – Az Ígérethez rendelkezésre áll a cikk azon mennyiségét jelenti, amely elérhető és szállítható a vevőnek adott időre. Az Ígérethez rendelkezésre álló mennyiség kiszámítása tartalmazza a nem véglegesített készletet, az átfutási időket a tervezett bevételezéseket és kiadásokat.
- **ATP + kiadási időrés** – a szállítási dátum megegyezik az "Tp" dátum és a cikk kiadási időrtéke alapján. A kiadási időtartalék a szállítandó cikkek előkészítéséhez szükséges idő.
- **Ígérhető**– Az elérhetőség az alábontás alapján számítható. Ha tervezés szerinti optimalizálást használ, *a "CTP* " szállításidátum-ellenőrzési módszer nem engedélyezett, és ha be van jelölve, hibát okoz a számítás futtatásakor. A CTP beállításával és használatával kapcsolatos további tudnivalókat lásd [: Értékesítési rendelés szállítási dátumának kiszámítása a CTP használatával](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).
- **CTP tervezési optimalizáláshoz** – a tervezési optimalizálás által biztosított CTP-számítás használható. Ennek a beállításnak nincs hatása, ha a beépített alaptervezési motort használja. A CTP beállításával és használatával kapcsolatos további tudnivalókat lásd [: Értékesítési rendelés szállítási dátumának kiszámítása a CTP használatával](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

> [!NOTE]
> Értékesítési rendelés frissítésekor a rendelési ígéret adatai csak akkor frissülnek, ha a meglévő rendelési ígéret dátuma nem teljesíthető, ahogy a következő példákban látható:
>
> - **1. példa**: Az aktuális rendelési ígéret dátuma július 20., de a megnövekedett mennyiség miatt nem tud majd július 25-ig teljesíteni. Mivel az aktuális dátum már nem teljesíthető, aktiválódik a rendelési ígéret.
> - **2. példa**: az aktuális rendelési dátum július 20., de a csökkentett mennyiség miatt most július 15-én lehet szállítani. Mivel azonban az aktuális dátum még teljesítható, a rendelési ígéretek nem indulnak el, így július 20-a marad a rendelés ígérő dátuma.

## <a name="atp-calculations"></a>Ígérethez rendelkezésre áll számítások

Az "halmozott, előretek számított" módszerrel kiszámított" az "összesítve rendelkezésre álló mennyiség" módszer. Ennek az ígérethez rendelkezésre áll számítási módszernek a fő előnye, hogy kezelhetők olyan esetek, ahol a kiadások összeg a bevételek között nagyobb, mint a legfrissebb bevétel (például amikor egy korábbi bevételezési mennyiséget fel kell használni a követelmények miatt). Az "kumulatív, előretektekével számolt" számítási módszer az összes kiadást tartalmazza addig, amíg a fogadandó kumulatív mennyiség meghaladja a kumulatív kiadási mennyiséget. Ezért az ígérethez rendelkezésre állás számítás módszer kiértékeli, hogy a mennyiség egy része a korábbi időszakból használható-e a későbbi időszakban.

Az Ígérethez rendelkezésre álló mennyiség készletegyenlege nem véglegesített az első időszakban. Általában az egyes időszakokra kerül kiszámításra, amelyekben a bevételezés ütemezve van. A program kiszámítja az ígérethez rendelkezésre álló mennyiség időszakának napjait, és a mennyiség első napjaként az aktuális dátumot határozza meg. Az első időszakban az ígérethez rendelkezésre álló mennyiség az aktuális készlet esedékes és lejárt vevői rendelésekkel csökkentett mennyisége.

A rendszer a következő képlettel számítja ki az ígérethez rendelkezésre álló mennyiséget:

Ígérethez rendelkezésre áll = Az előző időszakban ígérethez rendelkezésre álló készlet + Az aktuális időszak bevételezései - Az aktuális időszak kiadásai – Az összes jövőbeni időszak bevételezéseinek összegének időszakáig, minden egyes jövőbeni időszak nettó kiadási mennyisége, a jövőbeni időszakot beleértve és azzal bezárólag nagyobb, mint a kiadások összege a jövőbeni időszakkal bezárólag.

Figyelje meg, hogy az ATP-számítás nem tartalmazza a lejárati dátum körüli és az ATP időkorláton túli adatokat, amelyekre a rendszernek szüksége van az ígérhető mennyiség esetén.

Ha nincs több figyelembe vehető kiadás vagy bevételezés, akkor az ígérethez rendelkezésre álló mennyiség a további dátumokon ugyanaz lesz, mint az ígérethez rendelkezésre álló utolsó számított mennyiség.

Ha az ígérethez rendelkezésre álló mennyiség ellenőrzésekor egy cikknek nincs minden dimenziója megadva, a hiányzó dimenziók később is megadhatók a bevételezésekben és kiadásokban. Ebben az esetben az ígérethez rendelkezésre álló mennyiség számításakor a bevételezéseket és kiadásokat összesíteni kell a meglévő dimenziókban, hogy a mennyiség számításában résztvevő bevételezési és kiadási sorok száma csökkenjen.

A megjelenített ígérethez rendelkezésre állási mennyiség mindig 0 (nulla) vagy nagyobb. Ha az ígérethez rendelkezésre állási mennyiség számítás eredménye negatív (pl. ha az előzetesen ígért mennyiség túllépi az elérhető mennyiséget), akkor a program a mennyiséget automatikusan 0 értékre állítja.

### <a name="example"></a>Példa

Az **Ígérethez rendelkezésre áll – igény visszamenőleges időkorlátja** mező szabályozza, hogy milyen messzire lehet visszamenni időben késett igényrendelések vagy készletkiadások keresésekor. Az **Ígérethez rendelkezésre áll – készlet visszamenőleges időkorlátja** mező szabályozza, hogy milyen messzire lehet visszamenni időben késett készletrendelések vagy készlet bevételezések keresésekor. Például ha a csak hét napot késett rendeléseket figyelembe kívánja venni az ígérethez rendelkezésre állási számításban, mindkét mező értéke **7** kell legyen.

Az **Ígérethez rendelkezésre áll – késleltetett igény várakozási ideje** és **Ígérethez rendelkezésre áll - késleltetett ellátás várakozási ideje** mezők szabályozzák, hogy a késleltetett igényt vagy ellátást figyelembe kell-e venni az ígérethez rendelkezésre állási számításban. Például ha a késleltetett szállításokat és igényeket is figyelembe kell venni az ígérethez rendelkezésre állási számításban holnapután, akkor mindkét mező értéke **2** kell hogy legyen. A **2** értéke azt jelenti, hogy a cikk mennyisége a késleltetett beszerzési rendelésen, amelyet figyelembe kell venni a ígérethez rendelkezésre állási számításban, két nap múlva is elérhető lesz.

Az alábbi példánál **7** van megadva az **Ígérethez rendelkezésre áll – igény visszamenőleges időkorlátja** és **Ígérethez rendelkezésre áll – ellátás visszamenőleges időkorlátja** mezőkben, és **1** az **Ígérethez rendelkezésre áll - késleltetett igény várakozási ideje** és **Ígérethez rendelkezésre áll – késleltetett ellátás várakozási ideje** mezőkben.

Egy 200 darabos beszerzési rendelés, amelyet három nappal korábban kellett volna megkapni még nem érkezett meg. Emiatt egy termék értékesítési rendelésének 75 sora, amelyet tegnap kellett volna szállítani nem került szállításra.

A vevő telefonál, és 150 egységet venne egy termékből. Ha megerősíti a termék elérhetőségét, akkor egy másik, a termékre szóló 100 darabos beszerzési rendelés 10 napon belül kerül szállításra.

Létrehozhat egy értékesítési rendeléssort a termékhez és megadhat **150** mennyiséget.

Mivel a szállítási dátum ellenőrzési módja az "ATP", a program úgy számolja ki az "ATP" adatokat, hogy a lehető legkorábbi szállítási dátumot keresse meg. A beállítások alapján a késleltetett beszerzési rendelés és értékesítési rendelés feldolgozásra kerül és kapott ígérethez rendelkezésre állási mennyiség a jelenlegi dátumhoz 0. Holnap, amikor a késleltetett beszerzési rendelés beérkezése várható, az ígérethez rendelkezésre állási mennyiségre kapott érték nagyobb, mint 0 (ebben az esetben 125 az értéke). Ugyanakkor mostantól 10 nap múlva, amikor a 100 darabra szóló kiegészítő beszerzési rendelés érkezése várható, az ígérethez rendelkezésre állási mennyiség több, mint 150.

Ezért a szállítási dátum az ígérethez rendelkezésre állás számításának alapján a mai naptól számított 10 nap. Ennek megfelelően tájékoztassa az ügyfelet, hogy az igényelt mennyiség 10 nap múlva szállítható.

## <a name="ctp-calculations"></a>CTP-számítások

A ígért szolgáltatásokat lehetővé teszi a vevők számára, hogy valószerű dátumokat adjanak meg arra az időpontra, amikor adott árukat ígérhet. Minden értékesítési sorhoz meg lehet adni egy dátumot, amely figyelembe veszi a meglévő aktuális készletet, termelési kapacitást és szállítási időket.

A "CTP" a kapacitási adatok figyelembevekkel bővíti az "Egyen rendelkezésre álló mennyiség" funkciót. Míg az "ATP" figyelembe veszi, hogy csak az anyagok rendelkezésre állása áll rendelkezésre, és végtelen kapacitású erőforrásokat feltételez, a CTP figyelembe veszi mind az anyagok, mind a kapacitás elérhetőségét. Így pontosabb képet ad arról, hogy az igényt egy adott időkereten belül kielégítheti-e.

Az ön által használt alaptervezési motortól (tervezési optimalizálás vagy beépített motor) függően a CTP (CTP) egy kissé másképp működik. A tervezési optimalizáláshoz rendelkezésre álló mennyiség jelenleg csak a beépített motor által támogatott CTP esetek egy részkészletét támogatja.

A CTP [beállításával és az egyes kalkulátokhoz történő használatával kapcsolatos részletes tudnivalókat lásd: Értékesítési rendelés szállítási dátumának kiszámítása a CTP használatával.](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
