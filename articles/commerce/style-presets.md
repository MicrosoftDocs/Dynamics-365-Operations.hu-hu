---
title: Előre beállított stílusok használata
description: Ez a témakör az előre beállított oldalstílus-elrendezésekkel végzett munkát mutatja be a Microsoft Dynamics 365 Commerce oldalépítőben.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 63e11b718a2b5221c722a11de3a8df6d9d0e3d6b
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964853"
---
# <a name="work-with-style-presets"></a>Előre beállított stílusok használata

[!include [banner](includes/banner.md)]

Ez a témakör az előre beállított oldalstílus-elrendezésekkel végzett munkát mutatja be a Microsoft Dynamics 365 Commerce oldalépítőben.

A stílus-előbeállítás az összes szerzői stílusérték tárolt készlete, amelyek lefedik a webhely témáját. Felhasználható arra, hogy azonnal módosítsa a webhely megjelenését a webhelyépítőből. A stílus előre beállításával a Commerce webhelyépítő szerzői gyorsan módosíthatják, előnézhetik és aktiválhatják a stílus értékeit a saját webhelyükön anélkül, hogy az egymásra épülő stílusalapokat (CSS) kellene használni, vagy a témákat kellene telepíteni. A betűstílusok, a gombstílusok és a webhely színei a stílus-előbeállításokon keresztül kezelhető stílusváltozók tipikus példái.

A webhelyen elérhető stílusváltozók készletét a webhely bérlője számára telepített téma- és modulkönyvtár határozza meg. Az Dynamics 365 Commerce online szoftverfejlesztési készlet (SDK) lehetővé teszi a fejlesztők számára, hogy tetszőlegesen sok (vagy kevés) szerzői stílusváltozót építsenek be egy adott téma esetében. Ha engedélyezi a minél több stílusváltozót, egy téma fejlesztője a webhelyépítő szerzők kezébe helyezheti a webhely stílusával kapcsolatos végleges döntéseket. Ennélfogva a nem fejlesztők a webhelystílusokat az eszközkészlet segítségével frissíthetik és előnézhetik. A funkció olyan esetekre is hasznos, amikor a közvetlen módosítások a témákban vagy CSS-ben felesleges költségeket okoznak.

Azoknál a témáknál, amelyekhez a szerzői stílusváltozók engedélyezve vannak, alapértelmezett előzetes beállítású stílust kell megadni. A telepíthető témacsomagok részeként lehetőség van további előbeállításos lehetőségek hozzáadására is. Például egy téma telepíthető egyetlen alapértelmezett „modern fény” stílus-előbeállítással. Azt is megteheti, hogy az alapértelmezett előbeállításon kívül további stílus-előbeállítási lehetőségeket is tartalmaz, például „modern sötét”, „vintage világos” vagy „vintage sötét”. Ezeket a beépített téma-előbeállításokat a fejlesztők hozzák létre, és kiindulópontként használhatók az új webhely tervezéséhez.

A webhely-szerkesztőben a szerzők választhatnak a téma beépített előbeállításai közül, vagy saját stílus-előbeállításokat és -testreszabásokat hozhatnak létre az engedélyezett stílusváltozók segítségével. A stílus-előbeállítások a webhelyépítőben megtekinthető, mielőtt aktiválná őket az élő webhelyen. Ha egy szerző stílusmódosításait felülvizsgálták, a stílus-előbeállítás „aktív” értékre állítható az élő webhelyen.

## <a name="preview-a-style-preset"></a>Stílus-előbeállítás előnézete

Ha meg szeretné tekinteni a webhely egy stílus-előbeállítását a webhely-építőben, hajtsa végre az alábbi lépéseket.

1. A webhely bal oldali navigációs ablakában nyissa meg a **Webhely beállításai \> Design** elemet.
1. A **Stílus-előbeállítások** lapon, a designszerkesztő felső részén, a **Rendelkezésre álló előbeállítások** listában válasszon ki egy előbeállítást, majd válassza a **Nézet** parancsot az előbeállítás-szerkesztőhöz való ugráshoz.

    Ha a **Rendelkezésre álló előbeállítások** listájában jelenleg nincsenek készletek, lásd: [Egyedi stílus-előbeállítás létrehozása](#create-a-custom-style-preset) az egyedi stílus-előbeállítás létrehozásáról.

    > [!NOTE]
    > A téma által tartalmazott előbeállítások a **Beépített** jelvény jelzi. Ez a beépített előbeállítások írásvédettek. Ha a beépített előbeállítást új, testreszabható előbeállításként szeretné átmásolni, válassza a három pont lehetőséget (**...**) az előbeállítás kiválasztásához, majd válassza a **Mentés másként** lehetőséget.

1. Válassza a parancssáv **Előnézet** elemét.
1. Válassza ki a webhely URL-címét a beállított stílus-előbeállítás előnézetéhez, majd kattintson az **OK** gombra.
1. Válassza ki a csatornára jellemző és a területi beállításhoz megadott URL-cím változatot a változat nevének kiválasztásával. Megnyílik egy új előnézeti böngészőablak, amelyen a kiválasztott stílus-előbeállítás a megadott lapra van alkalmazva.

> [!NOTE]
> Az előnézeti URL-cím állandó és hitelesített. Éppen ezért a webhely „aktív” értékre állítása előtt másolhatja, beillesztheti és elküldheti a többi hitelesített munkatárs számára. Az előnézeti URL-cím a különböző eszközökön, különböző böngészőkben és különböző képernyőkön a stílusok ellenőrzésére is használható.

> [!TIP]
> Ha szerkeszt egy stílus-előbeállítást, akkor hasznos lehet, ha egy külön böngészőablakban hagyja nyitva a böngészőablak-előnézeti ablakát, így gyorsan érvényesítheti a változtatásokat. Miután mentette a változtatásokat egy előbeállításhoz, frissítse a nyitott előnézeti böngészőablakot a felhasználói élmény ellenőrzéséhez.

## <a name="create-a-custom-style-preset"></a>Egyéni stílus-előbeállítás létrehozása

Ha egyedi stílus-előbeállítást szeretne létrehozni a webhely-építőben, hajtsa végre az alábbi lépéseket.

1. A webhely bal oldali navigációs ablakában nyissa meg a **Webhely beállításai \> Design** elemet.
1. A **Stílus-előbeállítások** lapon, a designszerkesztő felső részén, a parancssorban, válassza az **Új előbeállítás** parancsot.
1. Adja meg az új előbeállítás nevét és leírását, majd válassza a **Mentés** lehetőséget. Létrejön egy új testreszabható előbeállítás, amely a téma alapértelmezett értékeit használja kiindulási pontként.

> [!NOTE]
> A meglévő előbeállításból új egyéni stílus-előbeállítást is létrehozhat, ha bejelöli a beállításhoz a három pont lehetőséget (**...**), majd a **Mentés másként** parancsra kattint. Azt is megteheti, hogy az előbeállítás-szerkesztőben a parancssoron a **Mentés másként** parancsra kattint.

## <a name="modify-global-and-module-type-style-values"></a>A globális és a modul típusú stílusok módosítása

A témák stílusváltozóinak egy része több modultípus között osztozik. Ezeket a stílusváltozókat *globális* stílusváltozónak nevezzük. Ilyenek például az elsődleges hely színei, az alapértelmezett betűstílusok és a gombstílusok. A globális változók beállításával megváltoztathatja a különböző típusú modulokra a megjelenést.

Egyes stílusértékek egy modultípusra egyediek lehetnek, vagy az alapértelmezett globális érték felülbírálását kötelezővé tehetik. Ha egy webhelyhez tartozó téma modul típusú stílusváltozókat tartalmaz, akkor a webhelyépítő szerzők a globális beállításoktól függetlenül testreszabhatják a modultípus stílusát. A modul típusú változók kiegészítik vagy felülbírálják egy téma globális stílusának változóit.

> [!NOTE]
> Egy webhelyen a stílusértékek hierarchiája a következő módon viselkedik: A jobb oldalon megjelenő stílusértékek felülbírálják a tőlük balra levő stílusértékeket.
>
> A téma alapértelmezett értékei \< Globális stílus értékei \< Modul típusú stílusok értékei \< CSS felülbírálása

Ha módosítani kívánja egy stílus-előbeállítás globális vagy modul típusú értékeit a webhelyépítőben, hajtsa végre az alábbi lépéseket.

1. A webhely bal oldali navigációs ablakában nyissa meg a **Webhely beállításai \> Design** elemet.
1. A **Stílus-előbeállítások** lapon, a designszerkesztő felső részén, válassza ki a **Nézet** elemet bármely stílus-előbeállításhoz a belépéshez az előbeállítás-szerkesztőbe.
1. Válassza az **Előnézet** lehetőséget, majd az URL-cím kiválasztása lépéseivel nyissa meg az előbeállítás teljes böngészőablakos előnézetét. Hagyja nyitva ezt az előnézeti böngészőablakot.
1. Az előbeállítás-szerkesztőben válassza a jobb felső sarokban levő **Szerkesztés** elemet.
1. A szerkesztőben a stílusváltozó vezérlőelemeinek használatával módosíthatja a globális stílus bizonyos értékeit.
1. A szerkesztő felső részén, a **Modulok** lapon, a **Globális** lap jobb oldalán, válasszon ki egy olyan modultípust, amelyet stílusnak kell megadnia.
1. A stílus vezérlőelemekkel módosíthatók a modul típusának egyes értékei.
1. Ha készen áll a módosítások előnézetének megtekintésére, válassza a **Mentés** parancsot a parancssorból.
1. Térjen vissza a nyitott előnézeti böngészőablakhoz, és frissítse. A teljes böngészőablak-előnézet hasznos a különböző nézetekben, különböző böngészőprogramokban és különböző eszközökön a stílus változásainak ellenőrzésére.
1. Ha minden módosítást befejeztek és ellenőriztek, akkor a szerkesztő jobb felső részén válassza a **Szerkesztés befejezése** elemet.

> [!NOTE]
> Ha a webhelyén éppen aktív stílust szerkeszti, akkor a szerkesztőben egy kék **Aktív** jelvény jelenik meg. Ez a jelvény azt jelzi, hogy az előbeállítás jelenleg élő a webhelyén. Ha módosítja az aktív előbeállítást, akkor a **Közzététel** gomb megnyomásával továbbíthatja ezeket a változtatásokat az élő webhelyre.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Új stílus-előbeállítás aktiválása az élő webhelyen

A webhelyén egy stílus-előbeállítás új aktív előbeállításként történő beállításához hajtsa végre az alábbi lépéseket.

- Jelölje be a **Beállítás aktívként választógombot** az egyik helyen:

    - A stílus-előbeállítás szerkesztőben található parancssáv
    - A három pont menü (**...**) bármelyik rendelkezésre álló előbeállításnál a fő nézetben a **Stílus-előbeállítások** lapon itt: **Webhelybeállítások \> Design**

Az előbeállítás stílusértékei a nyilvános webhely egészére vonatkozóan aktívvá válnak.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[A CSS felülíró fájljainak használata](css-override-files.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
