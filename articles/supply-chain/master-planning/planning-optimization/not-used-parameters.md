---
title: A tervezésoptimalizálás által nem használt paraméterek
description: Ez a témakör felsorolja azokat a paramétereket, amelyeket a tervezésoptimalizálás a működése során jelenleg nem vesz figyelembe.
author: ChristianRytt
ms.date: 09/02/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 55b174b426b02e59f75d58e9a6cf32991089ca22
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728955"
---
# <a name="parameters-not-used-by-planning-optimization"></a>A tervezésoptimalizálás által nem használt paraméterek

[!include [banner](../../includes/banner.md)]

Ez a témakör felsorolja azokat a paramétereket, amelyeket a tervezésoptimalizálás a működése során jelenleg nem vesz figyelembe. Előfordulhat, hogy a tervezési szolgáltatás kihagy egy paramétert, mert például a kapcsolódó funkció még nem támogatott. A paraméter a funkcionális változások miatt elavulttá is válhatott.

Az alábbi szakaszok felsorolják azokat a paramétereket, amelyeknél a tervezési optimalizálás nem használható az egyes lapokon. Arra is magyarázatot ad, hogy miért nem használják az egyes paramétereket.

## <a name="master-planning-parameters-page"></a>Alaptervezés paraméterei oldal

A tervezésoptimalizálás nem használja a következő paramétereket és beállításokat az **Alaptervezés paraméterei** lapon:

- **Általános** fül:

  - **Aktuális előrejelzési terv** – függőben van az *Előrejelzés* támogatása.
  - **Aktuális statikus alapterv** – függőben van a *Statikus másolás a dinamikus tervbe* támogatásba.
  - **Aktuális dinamikus alapterv** – függőben van a *Statikus másolás a dinamikus tervbe* támogatása.
  - **A teljes és frissített statikus alapterv másolása a dinamikus alaptervbe** – függőben van a *Statikus másolás a dinamikus tervbe* támogatása.
  - **A számított késések kezdési ideje** – függőben van a *Számított késések* támogatása.
  - **Dinamikus negatív napok használata** – a tervezésoptimalizálás mindig a *Dinamikus negatív napok* megközelítést használja.
  - **Mai dátumnaptár** – függőben van az *Ütemezés* támogatása.
  - **Gyorsítótár használata** – az Microsoft Azure előfizetés konfigurációja kezeli a teljesítménypontokat.
  - **A segítő feladatcsomagban található feladatok száma** – az Azure-előfizetési konfiguráció kezeli a teljesítménypontokat.
  - **Előfeldolgozás: cikkek szerinti automatikus szűrés közvetlen igény esetén** – az Azure-előfizetés konfigurációja kezeli a teljesítménypontokat.
  - **Utófeldolgozás: cikkek szerinti automatikus szűrés közvetlen igény esetén** – az Azure-előfizetés konfigurációja kezeli a teljesítménypontokat.
  - **A megerősítési kötegben lévő rendelések száma** – az Azure-előfizetési konfiguráció kezeli a teljesítménypontokat.
  - **Szálak száma** – az Azure-előfizetési konfiguráció kezeli a teljesítménypontokat.
  - **Tervezési folyamat időtúllépése percekben** – az Azure-előfizetési konfiguráció kezeli a teljesítménypontokat.
  - **Ütemezés kezdési ideje** – az *Ütemezés* támogatása függőben van.

- **Tervezett rendelések** lap:

  - **Bevételezési idő** – az *Ütemezés* támogatása függőben van.
  - **Termelés** – az *Ütemezés* támogatása függőben van.
  - A **Projekt** szakasz mezői – az *Ütemezés* támogatása függőben van.

## <a name="coverage-groups-page"></a>Fedezeti csoportok oldal

A tervezésoptimalizálás nem használja a következő paramétereket és beállításokat a **Fedezeti csoportok** lapon:

- **Általános** Gyorslap:

  - **Pozitív napok – a** pozitív napok értéke nincs *·* használva. A tervezési optimalizálás során a pozitív napok végtelennek számítanak.
  - **Aktuális készletfelhasználás** – az *Aktuális készletfelhasználás* támogatása függőben van.
  - **A megadott anyagjegyzék- vagy receptúraverzió használata** – a *Képletverziók társ- vagy melléktermékekkel* támogatása függőben van.
  - **A megadott útvonalverzió használata** – az *Igény megadott darajegyzék- vagy meghatározott útvonal-követelményekkel* támogatása függőben van.

- **Műveletek** gyorslap:

  - **Műveletküzenet** – a *Műveletek* támogatása függőben van.
  - **Műveleti időkorlát** – a *Műveletek* támogatása függőben van.
  - **Árrés halasztás** – a *Műveletek* támogatása függőben van.
  - **Előleg árrés** – a *Műveletek* támogatása függőben van.
  - **Alapdátum** – a *Műveletek* támogatása függőben van.
  - **Előleg** – a *Műveletek* támogatása függőben van.
  - **Halasztás** – a *Műveletek* támogatása függőben van.
  - **Csökkentés** – a *Műveletek* támogatása függőben van.
  - **Növelés** – a *Műveletek* támogatása függőben van.
  - **Származtatott műveletek** – a *Műveletek* támogatása függőben van.

- **Egyéb** gyorslap:

  - **Befagyasztási időkorlát (nap)** – a tervezésoptimalizálásban nincs megtervezve a *Befagyasztási időkorlát* támogatása.
  - **Anyagjegyzék-aláütemezés időkorlátja (nap)** – az *Ütemezés* támogatása függőben van.
  - **apacitásütemezési időkorlát (napok)** – az *Ütemezés* támogatása függőben van.
  - **Jóváhagyott igénylési időkorlát (nap)** – az *Igénylés* támogatása függőben van.
  - **Előrejelzési terv időkorlátja** – függőben van az *Előrejelzés* támogatása.

- **Késések** gyorslap:

  - **Számított késések** – a *Számított késések* támogatása függőben van.
  - **Kiszámított késések időkorlátja (napok)** – függőben van a *Számított késések* támogatása.

## <a name="item-coverage-page"></a>Cikk fedezete oldal

A tervezésoptimalizálás nem használja a következő paramétereket és beállításokat a **Cikk fedezete** lapon:

- **Általános** fül:

  - **Tervezett rendelés típusa** – a tervezésoptimalizálás nem támogatja a *Kanban* lehetőséget, mivel függőben van a *Kanban* támogatása.
  - **Befagyasztási időkorlát (nap)** – a tervezésoptimalizálásban nincs megtervezve a *Befagyasztási időkorlát* támogatása.
  - **Anyagjegyzék-aláütemezés időkorlátja (nap)** – az *Ütemezés* támogatása függőben van.
  - **apacitásütemezési időkorlát (napok)** – az *Ütemezés* támogatása függőben van.
  - **Jóváhagyott igénylési időkorlát (nap)** – az *Igénylés* támogatása függőben van.
  - **Minimum teljesítése** – a tervezésoptimalizálás nem támogatja a *mai dátumot*, az *első kiadást* és a *fedezet időkorlátját*. Mindig a *Mai dátum + beszerzési idő* lehetőséget használja.
  - **Minimumidőszakok** – függőben van a *Minimumkészlet szintje* támogatása.
  - **Tervezési receptúra** – függőben van a *Képletverziók társ- vagy melléktermékekkel* támogatása.
  - **Alapértelmezett prioritás** – függőben van a *Képletverziók társ- vagy melléktermékekkel* támogatása.
  - **Jelenlegi prioritás** – függőben van a *Képletverziók társ- vagy melléktermékekkel* támogatása.
  - **Dátum módosult** – függőben van a *Képletverziók társ- vagy melléktermékekkel* támogatása.
  - **Aktuális készletfelhasználás** – az *Aktuális készletfelhasználás* támogatása függőben van.

- **Átfutási idő** lap:

  - **Beszerzési idő** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.
  - **Termelési idő** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.
  - **Átviteli idő** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.
  - **Munkanapok** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.

## <a name="master-plans-page"></a>Alaptervek oldal

A tervezésoptimalizálás nem használja a következő paramétereket és beállításokat az **Alaptervek** lapon:

- **Általános** Gyorslap:

  - **Aktuális készlettel együtt** – az *Aktuális készletfelhasználás* támogatása függőben van.
  - **Kézi felülbírálás** – az *Aktuális készletfelhasználás* támogatása függőben van.
  - **Aktuális készletfelhasználás** – az *Aktuális készletfelhasználás* támogatása függőben van.
  - **Aktuális készlettranzakciók** – az *Aktuális készletfelhasználás* támogatása függőben van.
  - **Értékesítési ajánlatok bekérése** – függőben van az *Értékesítési ajánlatok* támogatása.
  - **Ajánlatkérések bekérése** – az *Ajánlatkérés támogatása* függőben van.
  - **Eltarthatósági dátumok használata** – függőben van az *Eltarthatósági idő* támogatása.
  - **Folytonossági terv befoglalása** – a *Folytonosság ütemezésének* támogatása függőben van.
  - **Ütemezés módszere** – az *Ütemezés* támogatása függőben van.
  - **Véges tulajdonság** – az *Ütemezés* támogatása függőben van.
  - **Visszafelé ütemezési kapacitási időkorlát** – az *Ütemezés* támogatása függőben van.
  - **Véges kapacitás** – az *Ütemezés* támogatása függőben van.
  - **Véges kapacitás időkorlátja** – az *Ütemezés* támogatása függőben van.
  - **Szűk keresztmetszetű erőforrások véges kapacitása** – az *Ütemezés* támogatása függőben van.
  - **Szűk keresztmetszetű erőforrások kapacitási időkorlátja** – az *Ütemezés* támogatása függőben van.
  - **Tervezett rendelések** – a tervezésoptimalizálás rögzített számsorozatokat használ.
  - **Munkamenet** – a tervezésoptimalizálás rögzített számsorozatokat használ.
  - **Folytonossági terv** – a tervezésoptimalizálás rögzített számsorozatokat használ.

- **Időkorlát napokban** gyorslap:

  - **Befagyasztás** – a tervezésoptimalizálásban nincs megtervezve a *Befagyasztási időkorlát* támogatása.
  - **Alábontás** – az *Ütemezés* támogatása függőben van.
  - **Előrejelzési terv** – függőben van a további *Előrejelzés* támogatása.
  - **Kapacitás** – az *Ütemezés* támogatása függőben van.
  - **Folytonossági terv** – a *Folytonosság ütemezésének* támogatása függőben van.
  - **Műveletküzenet** – a *Műveletek* támogatása függőben van.
  - **Számított késések** – a *Számított késések* további támogatása függőben van.
  - **Sorrendbe állítás** – a *Termelés* támogatása függőben van.

- **Számított késések** gyorslap:

  - **Győződjön meg arról, hogy a tervezett rendelések létrehozása nem történik meg az alaptervezés futtatásának dátuma előtt** – a *Számított késések* támogatása függőben van.
  - **A számított késés hozzáadása a szükségletdátumhoz** (a **Tervezett beszerzési rendelések** szakaszban) – a *Számított késések* támogatása függőben van.
  - **A számított késés hozzáadása a szükségletdátumhoz** (a **Tervezett termelési rendelések** szakaszban) – a *Számított késések* támogatása függőben van.
  - **A számított késés hozzáadása a szükségletdátumhoz** (a **Tervezett átvitel** szakaszban) – a *Számított késések* támogatása függőben van.
  - **A számított késés hozzáadása a szükségletdátumhoz** (a **Tervezett kanban** szakaszban) – a *Számított késések* támogatása függőben van.

- **Sorrendbe állítás** gyorslap:

  - **Tervezett rendelések sorrendje az alaptervezés után** – a *Sorrendbe állítás* támogatása függőben van.
  - **Gyűjtőtípus** – a *Sorrendbe állítás* támogatása függőben van.
  - **Időszaktípus** – a *Sorrendbe állítás* támogatása függőben van.
  - **A kampányciklusban lévő gyűjtők száma** – a *Sorrendbe állítás* támogatása függőben van.

## <a name="released-product-details-page"></a>Megjelent termék részletei oldal

A tervezésoptimalizálás nem használja a következő paraméterbeállításokat a **Megjelent termék részletei** lapon:

- **Mérnöki** gyorslap:

  - **Termeléstípus** – a tervezésoptimalizálás nem támogatja a *Tervezési cikk* lehetőséget, mert a *Tervezési cikkek* támogatása függőben van.

## <a name="default-order-settings-page"></a>Alapértelmezett rendelésbeállítások lap

A tervezésoptimalizálás nem használja a következő paraméterbeállításokat az **Alapértelmezett rendelésbeállítások** lapon:

- **Beszerzési rendelések** gyorslap:

  - **Beszerzés átfutási ideje** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.
  - **Munkanapok** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.

- **Készlet** gyorslap:

  - **Szállítási dátum ellenőrzése** – a tervezésoptimalizálás nem támogatja a *CTP* beállítást, mert a *CTP* támogatása függőben van.
  - **Készlet átfutási ideje** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.
  - **Munkanapok** – A 2021. augusztus 6-ai kiadásnál régebbi tervezésoptimalizálási szolgáltatásverziókban a tervezési optimalizálás ezt a paramétert használja a helyes rendelési és szállítási dátum kiszámításához, de a kiszámított átfutási időt nem menti a tervezett rendelésbe. A későbbi verziókban a szolgáltatás a számított átfutási időt is használja az **Átfutási idő** mező és a **Munkanapok** beállítások kötelezőként történő beállításához a relevánt tervezési rendeléshez.

## <a name="working-time-calendars-page"></a>Munkaidőnaptárak oldal

A tervezésoptimalizálás nem használja a következő paramétereket a **Munkaidőnaptárak** lapon:

- **Alapnaptár** – függőben van az *Alapnaptárak* támogatása.

## <a name="batch-disposition-master-page"></a>Köteg alapintézkedése oldal

A tervezésoptimalizálás nem használja a következő paramétereket a **Köteg alapintézkedése** lapon:

- **Beállítás** gyorslap:

  - **Nettósítható** – a *Kötegrendelkezési kódok* támogatása függőben van.
