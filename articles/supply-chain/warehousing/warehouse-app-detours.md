---
title: Elterelések konfigurálása a mobileszközök menüelemeinek lépéseihez
description: Ez a cikk azt írja le, hogyan kell konfigurálni a menüelemeket, hogy a dolgozók információvesztés nélkül elvégezzék az aktuális feladatot, másik feladatot hajtsanak végre, majd térjenek vissza az eredeti feladathoz.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 50f899cd7f28a4b7fd23db5f049de02896e8d8e9
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336125"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Elterelések konfigurálása a mobileszközök menüelemeinek lépéseihez

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Az ebben a cikkben leírt funkciók csak az új Raktárkezelés mobilalkalmazásra vonatkoznak. Ezek nem érintik a régi raktár alkalmazást, amely már elavult.

Ez a témakör leírja, hogyan kell konfigurálni a menüelemek hibasorát, hogy a dolgozók "egyetlen" feladatot is végrehajt tudjanak, másik feladatot hajtsanak végre, majd adatok elvesztése nélkül térjenek vissza az eredeti feladathoz.

Az elterelés egy külön menüpont, amely egy fő tevékenység egyik lépéséből nyitható meg. Az elterelés végén a dolgozó visszakerül arra a helyre, ahol abbahagyta a fő feladatot. A konfiguráció során meg kell adnia azt a menüpontot, amely elterelésként működik. Azt is kiválaszthatja, hogy a fő tevékenység mely mezőértékeit kell automatikusan továbbítani (másolni) a az eltereléshez, és itt megadni. Ezért meg kell értenie, hogy a feladatfolyamatban hol szeretné, hogy az elterelés a munkavállalók számára elérhető legyen. Azt is biztosítania kell, hogy az eltereléshez másolandó információk rendelkezésre álljanak a feladatfolyamat adott lépéséhez.

## <a name="enable-detours-in-your-system"></a>Elterelések engedélyezése a rendszerben

Mielőtt eltereléseket állíthatna be a lépésekhez a mobileszköz menüelemeiben, az alábbi eljárást kell végrehajtania, hogy engedélyezze a szükséges funkciókat, és előállítsa a szükséges mezőneveket a Warehouse Management mobilalkalmazásban.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. Győződjön meg arról, hogy a *Raktár alkalmazás lépéséhez* funkció be van kapcsolva a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A *Raktári alkalmazás lépésutasítások* funkciójával kapcsolatos további információkért lásd: [Lépéscímek és utasítások testreszabása a Warehouse Management mobilalkalmazáshoz](mobile-app-titles-instructions.md). Ez a funkció előfeltétele a *Warehouse Management alkalmazás elterelései* funkciónak.
1. A Raktárkezelés *alkalmazás-hibakezelés funkció* bekapcsolása. Ez a funkció az ebben a cikkben ismertetett funkció. Az ellátásilánc-kezelés 10.0.29-es verziója alapértelmezés szerint be van kapcsolva.
1. Ha még nem bekapcsolta a Raktárkezelés alkalmazás-hibakezelési szolgáltatást, frissítse a mezőneveket a Raktárkezelés mobilalkalmazásban *úgy, hogy a Raktárkezelés* **\>\>\> beállítása mobileszköz-alkalmazás mezőnevére vált, és az Alapértelmezett beállítás létrehozása lehetőséget választja.** **·** Ismételje meg ezt a lépést minden olyan jogi személynél (vállalatnál), ahol a Raktárkezelés mobilalkalmazást használja. ovábbi információ: [A Raktárkezelés mobilalkalmazás mezőinek konfigurálása](configure-app-field-names-priorities-warehouse.md).

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Elterelés konfigurálása menüspecifikus felülbírálásból

Az alábbi eljárással beállíthatja a menüspecifikus felülbírálásból származó elterelést.

1. Menüspecifikus felülbírálás létrehozása a megfelelő menühöz és lépéshez a [A Warehouse Management mobilalkalmazás lépéscímeinek és utasításainak testreszabása](mobile-app-titles-instructions.md) című témakörben leírtak szerint.
1. Keresse meg a **Lépésazonosító** és a **Menüelem neve** értékek azon kombinációját, amelyet szerkeszteni szeretne, majd jelölje ki az értéket a **Lépésazonosító** oszlopban.
1. A megjelenő oldalon a **Elérhető elterelések (menüpontok)** gyorslapon megadhatja azt a menüpontot, amely elterelésként kell működjön. Azt is kiválaszthatja, hogy a fő tevékenység mely mezőértékeit kell automatikusan másolni az eltereléshez és az elterelésből. A beállítások használatát szemléltető példák a cikk későbbi, az esetekről tartalmaznak további példákat.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a>1. mintaforgatókönyv: Értékesítési kitárolás, ahol a helykeresés elterelésként működik

Ez a forgatókönyv azt mutatja be, hogyan konfigurálhat egy helykeresést elterelésként egy dolgozó által irányított értékesítési kitárolási tevékenységfolyamban. Ez az elterelés lehetővé teszi a dolgozók számára, hogy megkeressék az összes azonosítószámot azon a helyen, ahonnan kitárolnak, és kitárolják azt az azonosítószámot, amelyet a kitárolás befejezéséhez használni szeretnének. Ez a fajta elterelés akkor lehet hasznos, ha a vonalkód sérült, ezért az olvasóeszköz számára olvashatatlan. Mindemelett hasznos lehet, ha a dolgozónak meg kell tudnia, hogy mi érhető el valójában a rendszerben. Vegye figyelembe, hogy ez a forgatókönyv csak akkor működik, ha a azonosítótábla által vezérelt helyekről választ.

### <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ahhoz, hogy a megadott mintarekordokat és értékeket használni tudja az eseten, olyan rendszert kell használnia, ahol telepítve vannak a [szabványos bemutatóadatok](../../fin-ops-core/fin-ops/get-started/demo-data.md). Az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Menüspecifikus felülbírálás létrehozása és az 1. forgatókönyv elterelésének konfigurálása

Ebben az eljárásban az **Értékesítési kitárolási** menüelemhez állít be elterelést az azonosítótábla lépésében.

1. Menjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz lépések** pontra.
1. Keresse meg a *LicensePlateId* nevű lépésazonosítót, és jelölje ki.
1. A Műveletpanelen válassza a **Lépéskonfiguráció hozzáadása** lehetőséget.
1. A legördülő párbeszédpanelen a **Menüelem** mezővel keresse meg és válassza az *Értékesítési kitárolás* lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Megjelenik az imént létrehozott elterelés részletek lapja. A **Elérhető elterelése (menüpontok)** gyorslapon válassza az eszköztár **Hozzáadás** lehetőségét.
1. Az **Elterelés hozzáadása** párbeszédpanelen válassza a **Helykeresés** lehetőséget a Warehouse Management mobilalkalmazásban elérhetővé tenni kívánt kitérőhöz.
1. Válassza ki az **OK** lehetőséget.
1. Az **Elérhető kitérők (menüpontok)** gyorslapon jelölje ki az imént hozzáadott kitérőt, majd válassza az eszköztáron a **Mezők kiválasztása elküldéshez** lehetőséget.
1. A **Mezők kijelölése elküldésre** párbeszédpanelen adja meg az eltereléshez és elterelésből küldendő információkat. Ebben az esetben lehetővé teszi a dolgozók számára, hogy a helylekérdezés elterelés bemeneteként azt a helyet használják, ahonnan ki kellene tárolniuk. Ezért a **Küldés az értékesítési kitárolásból** szakaszban válassza az eszköztár **Hozzáadás** parancsát, ha sort szeretne hozzáadni a rácshoz. Ezután új sorhoz állítsa be a következő értékeket:

    - **Másolás az értékesítés kitárolásból:** *Hely*
    - **Beillesztés a hely lekérdezésbe:** *Hely*

1. Mivel az elterelés ebben a forgatókönyvben az azonosítótábla lépésben van konfigurálva, hasznos lesz, ha a munkavállalók vissza tudják hozni az azonosítótáblát a lekérdezésből a főfolyamatba. Ezért a **Visszahozás a hely lekérdezésből** szakaszban válassza az eszköztár **Hozzáadás** parancsát, ha sort szeretne hozzáadni a rácshoz. Ezután új sorhoz állítsa be a következő értékeket:

    - **Másolás a helymeghatározásból:** *Azonosítótábla*
    - **Beillesztés az Értékesítési kitárolásába:** *Azonosítótábla*

1. Válassza ki az **OK** lehetőséget.

Az elterelés most már teljesen be van állítva. A **Helykeresés** elterelés elindításához egy gomb jelenik meg az **Értékesítés kitárolás** menüpont azonosítótábla lépésében.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Végezzen el egy értékesítési kitárolást egy mobileszközön, és használja az elterelést

Ebben az eljárásban a Warehouse Management mobilalkalmazás használatával befejezheti az értékesítési kitárolást. Az imént konfigurált elterelést arra fogja használni, hogy megtalálja a kitárolási lépés befejezéséhez használt rendszámot.

1. A Microsoft Dynamics 365 Supply Chain Management alkalmazásban hozzon létre egy értékesítési rendelést, amelynél szüksége lesz a kitárolás egy olyan helyről, amely azonosítótáblával van nyomon követve. Majd adja ki az értékesítési rendelést a raktárnak. Jegyezze fel a létrehozott munkaazonosítót.
1. Nyissa meg a Warehouse Management mobilalkalmazást és jelentkezzen be a 24-es raktárba. (A normál demóadatokban *24*-es felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Válassza a **Kimenő** menüt, majd válassza ki az **Értékesítési kitárolás** menüpontot.
1. Az 1. lépésben létrehozott munkaazonosító megadásához kövesse a képernyőn megjelenő adatbeviteli utasításokat.
1. Az **Azonosítótábla beolvasása** szöveget tartalmazó lépésben Nyissa meg a műveletek menüt. A **Hely lekérdezés** címkével ellátott új gombnak kell megjelennie. A bal felső sarokban lévő nyíl azt jelzi, hogy a gomb elterelést indít. Válassza a **Helylekérdezés** lehetőséget.
1. Az elterelés elkezdődött. A következő oldalon erősítse meg a fő folyamatból másolt helyet.
1. A helyen elérhető azonosítótáblák listájában koppintson a főfolyamatba másolni kívánt azonosítótáblára. Ezután válassza a **Vissza** gombot.
1. Visszakerül az értékesítési kitárolási főfolyamatba, és az azonosítótáblát visszamásolták az elterelésből. Erősítse meg az értéket a következő lépésre lépéshez.
1. Most már befejezheti a standard folyamat többi részét a kért adatbeviteli utasítások megadásával.

A raktári munka befejeződött. A dolgozó sikeresen megnyitott egy elterelést egy másodlagos feladat (helylekérdezés) végrehajtásához anélkül, hogy elveszítette volna a pozícióját a fő feladatban, és visszahozta a fő feladat végrehajtásához szükséges információkat.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>2. mintaforgatókönyv: Cikklekérdezés mozgatási és helyesbítési elterelésekkel

Ez a forgatókönyv bemutatja, hogyan konfigurálhatja a mozgatás és a kiigazítást több elterelésként a helylekérdezés feladatfolyamatban. Ez a képesség hasznos lehet olyan helyzetekben, amikor a dolgozó megérkezik egy helyre, megállapítja, hogy a raktár készlete eltér a rendszerben regisztrálttól, ezért módosítania vagy mozgatnia kell az árukat.

A helylekérdezést szükség szerint azonosítótábla-lekérdezésre vagy cikklekérdezéssel helyettesítheti.

### <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ahhoz, hogy a megadott mintarekordokat és értékeket használni tudja az eseten, olyan rendszert kell használnia, ahol telepítve vannak a [szabványos bemutatóadatok](../../fin-ops-core/fin-ops/get-started/demo-data.md). Az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Menüspecifikus felülbírálás létrehozása és az 2. forgatókönyv elterelésének konfigurálása

Ebben az eljárásban az **Értékesítési kitárolási** menüelemhez állít be elterelést az azonosítótábla lépésében.

1. Menjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz lépések** pontra.
1. Keresse meg és jelölje ki a *LocationInquiryList* nevű lépésazonosítót, és jelölje ki.

    > [!NOTE]
    > Ha helylekérdezés helyett cikk-lekérdezést szeretne használni, jelöljön ki egy sort, ahol a lépésazonosító neve *ItemInquiryList*. Azonostótábla-lekérdezés használatához jelöljön ki egy sort, ahol a lépésazonosító neve *LPInquiryList*.

1. A Műveletpanelen válassza a **Lépéskonfiguráció hozzáadása** lehetőséget.
1. A legördülő párbeszédpanelen a **Menüelem** mezővel keresse meg és válassza a *Helylekérdezés* lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Megjelenik az imént létrehozott elterelés részletek lapja. A **Elérhető elterelése (menüpontok)** gyorslapon válassza az eszköztár **Hozzáadás** lehetőségét.
1. Az **Elterelés hozzáadása** párbeszédpanelen válassza a **Mozgás** lehetőséget a Warehouse Management mobilalkalmazásban elérhetővé tenni kívánt kitérőhöz.
1. Válassza ki az **OK** lehetőséget.
1. Az **Elérhető kitérők (menüpontok)** gyorslapon jelölje ki az imént hozzáadott kitérőt, majd válassza az eszköztáron a **Mezők kiválasztása elküldéshez** lehetőséget.
1. A **Mezők kijelölése elküldésre** párbeszédpanelen adja meg az eltereléshez és elterelésből küldendő információkat. Ebben a forgatókönyvben azt várja a dolgozóktól, hogy azonosítótábla által vezérelt helyeket keressenek. Ezért hasznos lesz átmásolni az azonosítótáblát a lekérdezésből **Mozgatás** elterelésbe. A **Küldés az értékesítési kitárolásból** szakaszban válassza az eszköztár **Hozzáadás** parancsát, ha sort szeretne hozzáadni a rácshoz. Ezután új sorhoz állítsa be a következő értékeket:

    - **Beillesztés a hely lekérdezésből:** *Hely*
    - **Beillesztés mozgatásba:** *Hely / Az. tábla*

    Ebben az elterelésben nem számít adatok visszamásolására, mivel a fő folyamat olyan lekérdezés volt, amelyben nincs szükség további lépésekre.

1. Válassza ki az **OK** lehetőséget.

Az elterelés most már teljesen be van állítva. A **Mozgatás** elterelés elindításához egy gomb jelenik meg az **Hely lekérdezése** menüpont azonosítótábla lépésében.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Végezzen helylekérdezést mobileszközön és használja az elterelést

Ebben az eljárásban a Warehouse Management mobilalkalmazás használatával helylekérdezést végez. Ezt követően az elterelést használja az árumozgatások befejezéséhez.

1. Nyissa meg a Warehouse Management mobilalkalmazást és jelentkezzen be a 24-es raktárba. (A normál demóadatokban *24*-es felhasználó azonosító és az *1* jelszó használatával jelentkezzen be.)
1. Válassza a **Készlet** menüt, majd válassza ki az **Helylekérdezés** menüpontot.
1. Adja meg azt a helyet, amelyről lekérdezést szeretne indítani, például *FL-001*.
1. Amikor megjelenik a lista, tartsa lenyomva az egyik benne található kártyát, hogy megjelenjenek a rendelkezésre álló elterelések.
1. Válassza a **Mozgatás** lehetőséget.
1. Figyelje meg, hogy az azonosítótábla a kiválasztott kártyáról másolva lett. Az érték megerősítése.
1. A mozgatás befejezéséhez követheti lehet a szokásos feladatfolyamatot. A munka befejezése után nyissa meg a Műveletek menüt, és válassza a **Mégse** lehetőséget.
1. Visszatér a **Helylekérdezés** lapra. Ne feledje, hogy az értékek frissítése nem történik meg automatikusan. Emiatt manuálisan kell frissítenie a lapot ahhoz, hogy látni tudja a mozgatás elterelés változtatásait.
