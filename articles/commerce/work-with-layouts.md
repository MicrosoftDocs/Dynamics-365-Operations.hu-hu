---
title: Előre beállított elrendezések használata
description: Ez a témakör azt ismerteti, hogyan kell dolgozni az előre beállított elrendezésekkel a következőben:Microsoft Dynamics 365 Commerce
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b588df5702657f07e1e790ffba39d2e459901557
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286276"
---
# <a name="work-with-preset-layouts"></a>Előre beállított elrendezések használata

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell dolgozni az előre beállított elrendezésekkel a következőben:Microsoft Dynamics 365 Commerce

A cikk eljárásának befejezése előtt mindenképpen [olvassa el az előre beállított és az egyéni elrendezéseket](templates-layouts-overview.md#preset-and-custom-layouts). Általános áttekintés: [Sablonok és elrendezések áttekintése](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Új előre beállított elrendezés létrehozása

Kétféleképpen hozható létre kegyéni elrendezés. Egy meglévő egyéni elrendezést új előre beállított elrendezésként menthet, vagy létrehozhat egy előre beállított elrendezést a nulláról is.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Előre beállított elrendezés létrehozása meglévő egyéni elrendezésből

Egy előre beállított elrendezés létrehozása meglévő egyéni elrendezésből kövesse az alábbi lépéseket.

1. Nyisson meg egy olyan meglévő lapot, amely jelenleg nem használ előre beállított elrendezést, és rendelkezik egy modulstruktúrával, amelyet újra fel szeretne használni a webhely egyéb oldalain.
1. A lap kivételéhez válassza a **Szerkesztés** parancsot.
1. Válassza a **Mentés új elrendezésként** parancsot. Megjelenik a **Mentés új elrendezésként** párbeszédpanel.
1. Írja be az előre beállított elrendezés nevét és a leírását. A megadott értékek más szerkesztőknek is megjelennek meg, amikor új lapokat hoznak létre az elrendezéséből, vagy átváltanak arra. Ennek megfelelően a szerzők számára hasznos értékeket adjon meg.
1. Válassza ki az **OK** lehetőséget.

Az előre beállított elrendezés immár elérhető lesz, amikor új lapokat hoz létre, vagy más elrendezést választ ki egy laphoz ugyanazon sablonhierarchiában.

> [!TIP]
> Annak gyors megtekintéséhez, hogy egy adott lap egy előre beállított elrendezéshez van-e kapcsolva, jelölje ki a lapot a lapok listájának nézetében, és tekintse meg az elrendezés metaadatait a jobb oldali tulajdonságok ablaktáblán.

### <a name="create-a-new-preset-layout"></a>Új előre beállított elrendezés létrehozása

Egy előre beállított elrendezés létrehozásához a nulláról kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki az **Elrendezések** lehetőséget.
1. Válassza az **Új elrendezés** lehetőséget. Megjelenik a **Új elrendezés** párbeszédpanel.
1. Válassza ki az előre beállított elrendezéséhez használni kívánt sablont.
1. Írja be az előre beállított elrendezés nevét és a leírását. A megadott értékek más szerkesztőknek is megjelennek meg, amikor új lapokat hoznak létre az elrendezéséből, vagy átváltanak arra. Ennek megfelelően a szerzők számára hasznos értékeket adjon meg.
1. Kattintson az **OK** gombra az új előre beállított elrendezés létrehozásához és az elrendezésszerkesztő megnyitásához.
1. Az elrendezésszerkesztőben a bal oldali fastruktúrában, és a jobb oldali tulajdonságok ablaktáblában adhatja meg és konfigurálhatja a modulokat. (A folyamat hasonlít a modulok sablonokhoz történő hozzáadásának és konfigurálásának folyamatára a sablonszerkesztőben.) A modulok elrendezése és az összes zárolt alapértelmezett beállítás egy központi modulkonfigurációvá válik az összes laphoz, amely ezt az előre beállított elrendezést használja.

## <a name="modify-a-preset-layout"></a>Előre beállított elrendezés módosítása

Egy előre beállított elrendezés módosításához kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki az **Elrendezések** lehetőséget.
1. Válassza ki a módosítani kívánt modult az elrendezésszerkesztő bal oldali fastruktúrájában. Majd tegye a következők valamelyikét:

    - Ha a modult a szülőn belül fel-le szeretne mozgatni, akkor válassza ki a három pont gombot (**...**) a modulhoz, majd válassza a **Felfelé** vagy a **Lefelé** billentyűt.
    - A modul alapértelmezett beállításainak módosításához használja a tulajdonság ablaktáblát az alapértelmezett értékek megadásához, és tetszés szerint zárolja őket az összes alárendelt oldalhoz.
    - Új modulok vagy töredékek a tárolómodulokhoz történő hozzáadásához válassza a három pont gombot, majd válassza a **Modul hozzáadása** vagy a **Töredék hozzáadása** lehetőséget.
    - Ha el szeretne távolítani egy modult az elrendezésből, válassza ki a három pont gombot, majd válassza a **Törlés** elemet.

## <a name="change-a-preset-layout-theme"></a>Előre beállított elrendezési téma módosítása

Általános gyakorlat az, hogy megadnak egy alapértelmezett témát az összes olyan oldalhoz, amely ez előre beállított elrendezést használja.

Ha meg szeretné adni vagy módosítani szeretné a témát az összes olyan származtatott oldal esetében, amely az előre beállított elrendezést használja, hajtsa végre az alábbi lépéseket.

1. Válassza ki az oldaltároló modult az elrendezésszerkesztő bal oldali fastruktúrájában. (Ez a modul általában a második csomópont, és a neve **Alapértelmezett lap**.)
1. A jobb **oldalon**, a tulajdonságok ablakában, a Téma mezőben válasszon ki egy témamezőt.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Előre beállított elrendezés mentése, beadása, előnézete és közzététele

Egy előre beállított elrendezés mentéséhez és beadásához kövesse az alábbi lépéseket.

1. Az elrendezésszerkesztő felső részén válassza a **Mentés** parancsot. A mentett módosítások nem érintik az alsóbb szintű lapokat mindaddig, amíg nincsenek beadva.
1. Válassza a **Szerkesztés befejezése** lehetőséget. A módosítások most már felderíthetők az alsóbb szintű munkafolyamatok számára.

A módosítások előnézetéhez nyisson meg egy az előre beállított elrendezést használó meglévő lapot, vagy hozzon létre egy új lapot az elrendezésből.

Miután megtekintette az előre beállított elrendezés módosításainak előnézetét, kövesse az alábbi lépések egyikét, és tegye közzé az elrendezést az élő webhelyen:

1. Nyissa meg az **Elrendezések** elemet, válasszon ki egy elrendezést, majd válassza a **Közzététel** parancsot.
1. Az elrendezésszerkesztő megnyitásához válassza ki az elrendezés nevét, majd válassza a **Közzététel** lehetőséget.
1. Egy nem közzétett elrendezésre hivatkozó lap közzététele. A program automatikusan közzéteszi az elrendezést.

> [!WARNING]
> Az előre beállított elrendezések több oldalról is hivatkozhatók. Egy előre beállított elrendezés közzététele esetén ügyeljen arra, hogy ez több oldal elrendezését is érintheti.

## <a name="rename-a-preset-layout"></a>Előre beállított elrendezés átnevezése

A webhelyszerkesztő egy előre beállított elrendezésének átnevezéséhez hajtsa végre a következő lépéseket.

1. Válassza az Elrendezések lehetőséget a bal oldali **navigációs ablakban**.
1. Válassza ki az átnevezni kívánt elrendezés nevét.
1. Válassza a **Szerkesztés** lehetőséget az elrendezés szerkesztésének elkezdéséhez.
1. Az elrendezéstulajdonságok ablaktáblán válassza ki az elrendezés neve melletti toll szimbólumot.
1. Szükség szerint módosítsa az elrendezés nevét.
1. A névváltozás megerősítéséhez jelölje be ezt a jelölőnégyzetet.
1. Válassza a **Szerkesztés befejezése** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Sablonok használata](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
