---
title: Vevő felosztása számlázási ütemezések alapján
description: Ez a témakör azt ismerteti, hogyan lehet felosztást alkalmazni a vevők között az előfizetési számlázás használata esetén.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746331"
---
# <a name="customer-split-on-billing-schedules"></a>Vevő felosztása számlázási ütemezések alapján

A számlázási ütemezésben a számlaszám *az a vevő,* aki megkapja az értékesítési rendelés számláját, hogy ki tudja fizetni a számlát. Bizonyos helyzetekben egynél több vevő is fizethet egy számlát. A **Vevő felosztása** funkcióval több vevőt is hozzáadhat, amelyek ugyanabba a számlázási ütemezésbe még számlázhatóak. A funkció engedélyezéséhez válassza **\>\>\>** az Ismétlődő szerződés számlázása beállítás ismétlődő szerződés számlázási paramétereit, **·** **és állítsa a Vevői felosztás lehetőséget Igen beállításra.**

## <a name="customer-split-on-the-billing-schedule-header"></a>A vevő felosztása a számlázási ütemezés fejlécében

A számlázási ütemezés létrehozása után további vevőket lehet hozzáadni a számlázási ütemezés fejlécéhez.

Vevő hozzáadásához kövesse ezeket a lépéseket.

1. Válassza a Számlázás **ütemezése** lapon a Vevő felosztása **lehetőséget**. A **felső mezőben** **a** Vevő számla és vevő neve mező határozza meg azt a vevőt, aki a Számlázási **ütemezés** vevője.

    > [!NOTE]
    > A hozzáadt vevőszámla nem lehet ugyanaz, mint a számlaszám.

2. Válassza a Sor **hozzáadása lehetőséget a Vevői** felosztási sorok **lapon**.
3. Válasszon ki egy vevőt, majd adja meg az adott vevőhöz tartozó számlák százalékos arányát.
4. Alapértelmezés szerint a számlázási ütemezés kezdő és záró dátumát használja a rendszer kezdő és záró dátumként. Adjon meg más kezdő és záró dátumokat, ha az új vevő a megadott százalékot csak a számlázási ütemezés egy részére fizeti ki. Ha például a számlázási ütemezés kezdő dátuma január 1., záró dátuma pedig december 31., és az új vevőnek az első kilenc hónapra 40 százalékot számláz, adja meg január 1-jét kezdő dátumként, szeptember 30-át pedig záró dátumként, **és adja meg a 40,00-as** százalékot.

Egynél több vevőt is hozzáadhat a vevői felosztási sorokhoz. Ebben az esetben a megadott százalékérték nem haladhatja meg a 100 százalékot. Adja meg a vevői hivatkozást és a vevői igénylést információs mezőként, amelyek megjelennek az értékesítésirendelés-sorban a Számla **létrehozása folyamat** során.

A sor adatai a hozzáadott vevők kapcsolattartási adatait, szállítási címét, számlázási címét és fizetési adatait mutatják. Ez az információ a vevők értékesítési rendelésében is megjelenik.

Amikor vevői felosztási adatokat ad hozzá a számlázási ütemezés fejlécéhez, ha a számlázási ütemezésben nem számlázandó számlázási ütemezési sorok vannak, akkor a következő üzenet jelenik meg, amely arra kéri, hogy lefelé haladjon a módosításokon: "Szeretné a fejlécről a sorokra lecsukni a módosítást? A módosítások csak a nem számlázható számlázási ütemezéssorokat frissítik." Az **Igen beállítással** frissítheti a számlázási ütemezés sorában található vevői felosztási adatokat. Ha a számlázási ütemezés sorát már számlázták, a módosítások nem frissülnek.

Ha a Számlázási ütemezés létrehozása az **Ütemezés** másolása beállítással történik, az alapértelmezett adatok a vevői felosztási fejlécsorokbe lesznek beállítva. Nem lehet ugyanaz, mint a vevői számla.

Ha a **Számla létrehozása** folyamat befejeződött, több értékesítési rendelés jön létre. (Automatikus feladás használata esetén több értékesítési számla is létrejön.) Ezek az értékesítési rendelések **és** **·** **értékesítési számlák megtekinthetők a Számlázási adatok megtekintése lap Sor részletei gyorslapján.** **A** számlázási részletsoron több értékesítési rendelés és értékesítési számla is megjelenik.

## <a name="customer-split-on-billing-schedule-lines"></a>Vevő felosztása számlázási ütemezés sorai alapján

A vevői felosztás hozzáadható az egyes számlázási ütemezési sorokhoz, ha csak bizonyos számlázási ütemezéssorokat szeretne felosztani. Jelölje be **a sor Vevői** felosztás jelölőnégyzetét, **majd** a számlázási ütemezés sorához válassza a Vevő felosztása menüpontot a vevői felosztási adatok frissítéséhez vagy beírához.

A könyvvizsgálati adatok frissülnek, ha a számlázási ütemezés már ki van számlázva, de a százalékos érték módosult a számlázási ütemezés sorában. Bármely sor, amely a módosítás után számlázva lesz, az új százalékot használja.

> [!NOTE]
> - A vevői felosztási beállítás nem használható raktárkészletű termékekkel.
> - Ha a **Nemszámlázatlan bevétel** jelölőnégyzet be van jelölve, **a** Vevő felosztása jelölőnégyzet nem választható.
> - Ha csak a Bevétel felosztása **lehetőséget használja**, **a** szülősor vevői felosztási beállítással rendelkezik, de a gyermeksorok cikkei nem.
