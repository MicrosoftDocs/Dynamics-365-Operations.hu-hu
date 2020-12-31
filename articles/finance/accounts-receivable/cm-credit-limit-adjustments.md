---
title: Hitelkeret-kiigazítások
description: Ez a témakör azt mutatja be, hogyan lehet beállítani és hozzáadni a hitelkorlát-korrekciókat.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: d55a7c5e24213f70a1b71f89691f0e5be8c36f10
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443945"
---
# <a name="credit-limit-adjustments"></a>Hitelkeret-kiigazítások 

[!include [banner](../includes/banner.md)]

A hitelkeret-korrekciók segítségével a hitelvezetők frissíthetik egyetlen ügyfél, egy ügyfélécsoport vagy az összes ügyfél hitelkereteit és lejárati dátumait egy feladási folyamat során. A hitelkeret-korrekciós bejegyzések hozzáadhatók a vevők és a vevői hitelcsoportok frissítéséhez, illetve az automatikus hitelkeretek kiszámítására is használhatók. A bejegyzések ezt követően áttekinthetők, elküldhetők jóváhagyásra egy munkafolyamaton keresztül, és feladhatók vevői számlákhoz.

## <a name="set-up-credit-limit-adjustments"></a>Hitelkeret-korrekció beállítása

Bejegyzéseket hozhat létre a Hitelkeret-korrekciós naplóban **Hitelkeret-korrekció** oldalon (**Hitelkezelés \> Hitelkeret-korrekciók \> Hitelkeret-korrekciók**).

1. Válassza az **Új** lehetőséget. A bejegyzések egy új csoportja jön létre, amelynek van hitelkeret-korrekciós száma.
2. A hitelkeret-módosítás típusának kiválasztása:

    - Válassza ki a **Hitelkeretet** a vevő hitelkeretének módosításához.
    - Ideiglenes hitelkeret létrehozásához válassza az **Ideiglenes hitelkeret** lehetőséget a vevő aktuális hitelkeretének módosítása helyett. Az ideiglenes hitelkeretek felülírják az ügyfél hitelkeretét egy megadott időszakra. Az időszakot követően a vevő hitelkerete újra fel lesz használva.
3. Adjon meg leírást. 

Ha a **Feladott** jelölőnégyzet be van jelölve, akkor a hitelkereteket alkalmazták. A **Jóváhagyási állapot** mező jelzi a napló munkafolyamat-állapotát. A munkafolyamat opcionális.

### <a name="add-credit-limit-adjustments"></a>Hitelkeret-korrekciók hozzáadása

A hitelkeret-korrekciók kézi hozzáadásához jelöljeki a **Sorok** lehetőséget, majd kövesse az alábbi lépéseket.

1. Ha egy vevőhöz hitelkeret-korrekciót szeretne hozzáadni, használja **Vevői** kiigazítások menüt. Ha hitelkeretet szeretne hozzáadni egy vevőcsoporthoz válassza **Vevői jócsoport hitelkorrekciói** lehetőséget.
2. Adjon meg egy vevői számlát a számla-ügyfélfiókhoz, amelyet az új hitelkerettel kell frissíteni. Ha az 1 . lépésben kiválasztotta a **Vevői hitelcsoportok helyesbítéseit**, akkor adja meg a vevői hitelcsoportot. Ugyanazon a naplósorban nem adhat meg vevői számlát és vevői hitelcsoport azonosítót is.

    Megjelenik az aktuális hitelkeret, és a név automatikusan megjelenik.

3. Adja meg az új hitelkeretet, amelynek a hitelkeret-bejegyzés feladásakor ki kell cserélnie az aktuális hitelkeretet.
4. Adjon meg egy dátumot a vevői hitelkeret új lejárati dátumának meghatározásához. A hitelkeret-módosítás létrehozásakor meg kell adni a hitelkeret lejárati dátumát.

A **Jóváhagyási állapot** mező jelzi a naplósor munkafolyamat-állapotát.

Ha azt szeretné, hogy a hitelkeret-módosítások automatikusan jöjjenek létre, akkor a Művelet ablaktáblán a **Létrehozás** menü használható.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Ideiglenes hitelkeret-korrekciók hozzáadása

A ideiglenes hitelkeret-korrekciók kézi hozzáadásához kövesse az alábbi lépéseket.

1. Ha egy vevőhöz hitelkeret-korrekciót szeretne hozzáadni, használja **Vevői** kiigazítások menüt. Ha hitelkeretet szeretne hozzáadni egy vevőcsoporthoz válassza **Vevői jócsoport hitelkorrekciói** lehetőséget.
2. Adjon meg egy vevői számlát a számla-ügyfélfiókhoz, amelyet az új hitelkerettel kell frissíteni. Ha az 1 . lépésben kiválasztotta a **Vevői hitelcsoportok helyesbítéseit**, akkor adja meg a vevői hitelcsoportot. Ugyanazon a naplósorban nem adhat meg vevői számlát és vevői hitelcsoport azonosítót is.

    Ha már létezik aktív vagy jövőbeli ideiglenes hitelkeret, akkor minden egyes ideiglenes hitelkeretnél megjelenik az aktuális ideiglenes hitelkeret és a dátumtartományok. A név automatikusan megjelenik.

3. Adja meg az új hitelkeretet, amely az aktuális hitelkeretet felülírja.
4. Az **Új kezdő dátum** és az **Új záró dátum** mezőkben adja meg azt az időszakot, amikor a speciális hitelkeret érvényes. A hitelkeretmódosítási napló létrehozásakor meg kell adni a hitelkeret lejárati dátumait.

A **Jóváhagyási állapot** mező jelzi a naplósor munkafolyamat-állapotát.

## <a name="generate-credit-limit-adjustments"></a>Hitelkeret-korrekciók generálása

A hitelkeret-módosítást automatikusan is el lehet végezni. Kattintson a műveleti ablaktáblán a **Létrehozás** elemre, majd válasszon a következő beállítások közül:

- Létező ügyfélből
- Létező vevői hitelcsoportból
- Automatikus hitelkeretek

### <a name="from-existing-customer"></a>Létező ügyfélből

Létre lehet hozni a meglévő vevőkből naplósorokat. Ha a **Létrehozás \> Meglévő vevőből** lehetőséget választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vevők kiválasztásának, valamint az új határértékek számításának kritériumait.

1. Adjon meg egy helyesbítő értéket, amely hozzá lesz adva vagy ki lesz vonva a hitelkeret összegéből. Adjon meg negatív értéket az aktuális hitelkeret csökkentéséhez vagy pozitív értéket a növeléséhez.
2. Az **Érték típusa** mezőben válassza ki, hogyan kell használni az 1. lépésben megadott értéket az új hitelkeret számításához:

    - A **Rögzített érték** választása esetén egy összeggel lesz módosítva a hitelkeret.
    - A **Százalék** választása esetén a egy százalékértékkel lesz módosítva a hitelkeret.

3. A számított hitelkeret kerekítésére használt érték megadása. Például írja be **10,00** a hitelkeret kerekítését a legközelebbi 10,00 helyiértékű pénzegységre.
4. A **Kerekítési képernyő** beállításával megadhatja, hogy a maradékot fel vagy le kell-e kerekíteni.
5. Válassza ki a dátumok módosításához használt módszert.

    - Ha az **Abszolút** értéketválasztja, akkor megadhatja azokat a dátumokat, amelyek meghatározzák a hitelkeretekhez a dátumtartományt.
    - Ha a **Relatív** akkor a tartományhoz eltolási dátumokat adhat meg. A hitelkeret aktuális dátumtartományát a program az eltolással korrigálja.

6. A szerepeltetni kívánt vevők listájának szűréséhez használja a **Befoglalandó rekordok** gyorslapot. Ha nem ad meg szűrőket, akkor a rendszer minden vevőhöz létrehoz hitelkeret-bejegyzést.
7. A hitelkeret -korrekció bejegyzéseinek létrehozásához kattintson az **OK** gombra.

### <a name="from-existing-customer-credit-group"></a>Létező vevői hitelcsoportból

Létre lehet hozni a meglévő vevői hitelcsoportokból is naplósorokat. Ha a **Létrehozás \> Meglévő vevői hitelcsoportból** lehetőséget választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vevői hitelcsoportok kiválasztásának, valamint az új határértékek számításának kritériumait. A feltételek ugyanazok a feltételek, amelyek a meglévő vevőkből származtatott naplósorok létrehozására használatosak. Lásd az előző szakasz lépéseit.

### <a name="automatic-credit-limits"></a>Automatikus hitelkeretek

A vevői hitelkeretek definiálásához és frissítéséhez automatikus hitelkereteket hozhat létre. Az automatikus hitelkeretek egy kockázati csoporthoz jönnek létre, és a pontozási csoportokban használt meghatározott értékeken alapulnak. Ezek az automatikus hitelkeretek a hitelkeret-bejegyzések előállítására használhatók. Ha egy vevő egy meghatározott kockázati csoporthoz van hozzárendelve, és a vevő hitelezési adatai megfelelnek az automatikus hitelkeret feltételeinek, akkor létrejön egy hitelkeret-módosítási bejegyzés.

#### <a name="create-automatic-credit-limits"></a>Automatikus hitelkeretek létrehozása

Automatikus hitelkereteket hitelkeret-kiigazítások használatával adhat meg. Amikor kiválasztja a **Létrehozás \> Automatikus hitelkeretek** lehetőséget, megjelenik egy párbeszédpanel, amelyen megadhatja az új hitelkeretek lejárati dátumát, amelyek a vevőkhöz rendelt kockázati csoportok alapján jönnek létre. Ha befejezte a beállítást, válassza az **OK** lehetőséget a hitelkeret-korrekciós sorok létrehozásához.

### <a name="post-adjustments"></a>Helyesbítések feladása

Miután létrehozta a hitelkeretkorrekciós sorokat, a művelet ablaktáblán a **Feladás** gombra kattintva feladhatja a tételeket, és frissítheti a vevői hitelkereteket. Ha azonban beállított egy munkafolyamatot, be kell jelölnie a **Munkafolyamat \> Beküldés** lehetőséget a Műveleti ablaktáblán, hogy beküldje a naplót jóváhagyásra.

### <a name="credit-limit-adjustments-workflows"></a>Hitelkeret-korrekciós munkafolyamatok

A **Hitelkeret-korrekciós** munkafolyamatok a munkafolyamat-jóváhagyási folyamaton keresztüli hitelkeret-korrekciók elküldésére használhatók. Két munkafolyamatot is létre lehet hozni a **Hitelkezelési munkafolyamart** oldalon **(Hitelkezelés \> Beállítások \> Hitelkezelési munkafolyamat**):

- **Hitelkeret-korrekciók** – Ez a munkafolyamat használható a fejléc szintjén történő bejegyzésjóváhagyásra.
- **Hitelkeret-helyesbítési sor** – Ez a munkafolyamat használható a korrekciós bejegyzések jóváhagyására, így a munkafolyamatban szereplő feltételek alapján különböző személyek is jóváhagyhatják a bejegyzéseket.

> [!NOTE]
> A **Hitelkeret-korrekció** munkafolyamat létrehozásakor beállíthatja, hogy a program automatikusan feladja a korrekciókat a sorok jóváhagyása után. Egyszerűen szerepeltesse a **Napló automatikus feladása** feladatot a munkafolyamatban.
