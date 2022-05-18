---
title: Affordable Care Act (ACA) jelentések létrehozása
description: Az Affordable Care Act (ACA) jelentéskészítés létrehoz egy 1095-B és egy 1095-C űrlapot, támogatva az ACA **munkáltatói felhatalmazás** részét.
author: twheeloc
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 9ef67fba97282d1fc641f0281cd51c8ff08c65e5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690834"
---
# <a name="generate-aca-reports"></a>ACA-jelentések generálása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Az Affordable Care Act (ACA) jelentéskészítés létrehoz egy 1095-B és egy 1095-C űrlapot, támogatva az ACA **munkáltatói felhatalmazás** részét.

> [!NOTE]
> Az ACA-jelentéskészítés csak az Egyesült Államokban engedélyezett jogi személyek esetén.

## <a name="getting-started"></a>Első lépések

Az adatoknak az 1095-B és 1095-C űrlapok esetében történő nyomon követéséhez először létre kell hozni egy vagy több Affordable Care fedezeti csoportot. Az Affordable Care fedezeti csoportok a következő állapotra utalnak:

- Az alkalmazott fedezeti ajánlata
- Az alkalmazott részesedése a legkisebb költségalapú havi díjból, ha költség magasabb a szövetségi szegénységi küszöbnél
- A munkáltató által használt Safe Harbor, ha van ilyen

Az Affordable Care fedezeti csoportok használata lehetővé teszi az adatok kezelését ezeknek a mezőknek az esetében anélkül, hogy minden alkalmazotti rekordot módosítani kellene abban az esetben, amikor a feltételek ugyanazok. Az Affordable Care fedezeti csoportokat egyszerűen hozzárendelheti egy vagy több alkalmazotthoz az oldal **Tömeges hozzárendelés** funkciójával.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Fedezeti csoportok több változatának karbantartása

A fedezeti csoportok több változatának karbantartása lehetséges. Ez a funkció anélkül teszi lehetővé a módosításokat, hogy új csoportot kelljen létrehozni és alkalmazottakat kelljen hozzárendelni a csoporthoz. 

Miután létrehozta az ACA fedezeti csoportokat, tömegesen hozzárendelheti a csoportokat az alkalmazottakhoz a **Tömeges hozzárendelés** lehetőséggel. Azt is jelezheti külön-külön, hogy kell-e követni és jelenteni az ACA-adatokat, és hozzárendelhet egy alkalmazottat egy Afordable Care fedezeti csoporthoz.

Nem kell nyomon követni az ACA bizonyos fedezeti adatait, például a részmunkaidős alkalmazottak esetében. Ebben az esetben állítsa a **Jogosultság bejelentése** mezőt **Nem** értékre. Annak ellenére, hogy minden, nyomon követhető ACA-információval rendelkező alkalmazottat hozzá kell rendelnie egy Affordable Care fedezeti csoporthoz, az alábbi értékeket továbbra is módosíthatja a különböző értékekkel rendelkező hónapokra vonatkozóan:

- **Jogosultságra vonatkozó ajánlat**
- **Alkalmazott költségmegosztása**
- **Safe Harbor**

Kivételek megadásához bármely Affordable Care fedezeti csoport értékének esetében kattintson a **Dolgozó részletes adatai** oldalon található **Affordable Care fedezet** lehetőségre, amely a **További információk** szakaszban található a **Foglalkoztatás** lapon.

## <a name="reporting-health-care-coverage"></a>Egészségügyi fedezeti jelentés

Annak a nyomon követése mellett, hogy egészségbiztosítást ajánlottak fel teljes munkaidős alkalmazottak számára, ha a munkáltató a munkáltató által támogatott, a munkavállaló által fizetett egészségügyi biztosítást kínál, amelyre az alkalmazott fel van iratkozva (függetlenül attól, hogy a foglalkoztatottsági állapota teljes munkaidős vagy részmunkaidős), további információt kell jelenteni a 1095-C űrlapon. A munkáltató által támogatott juttatási csomagban részesülő összes alkalmazottat (és eltartottjaikat) meg kell adni annak a hónapnak a jelentésében, amelyben a csomag vonatkozik rájuk. 

Azt, hogy minden juttatácsomagot jelenteni kell-e, az **ACA szerint bejelentendő** négyzet bejelölésével adhatja meg.

Ezenkívül, ha az alkalmazott úgy döntött, hogy a juttatás kiterjedjen eltartottjai bármelyikére, minden egyes alkalmazott esetében megadhatja azokat a dátumokat, amikor a juttatás kiterjedt az eltartottra a **Juttatások kezelése** lapon. Ha jelezni szeretné, hogy az eltartott jogosult a juttatásra, kattintson a **Szerkesztés** gombra az **Eltartottak** gyorslap műveleti ablaktáblájában.

A **Függő fél jogosultsági dátumának kezelése** lapon adhatja meg a dátumokat, amikor a juttatás vonatkozott az eltartottra. Ha ezen a lapon dátumokat ad meg, ezzel automatikusan bejelöli a **Fedezve** jelölőnégyzetet a **Juttatások karbantartása** oldalon.

## <a name="generate-1095-b-and-1095-c-forms"></a>1095-B és 1095-C űrlapok létrehozása

Lehetőség van a 1095-B és 1095-C űrlapok létrehozására a terméken belül, és a továbbításukra az összes alkalmazottnak. A rendszer elektronikusan is generálhat 1095-C űrlapokat és az 1094-C IRS benyújtandó fájlokat.  

A 1095-C űrlap létrehozásakor adja meg a megfelelő adóévet, és jelölje, hogy szükséges-e társadalombiztosítási számok maszkolása. Ha több mint 500 alkalmazottnak nyomtat 1095-C űrlapot, egynél több PDF-fájlt fog kapni. Azt ajánljuk, hogy növelje meg a **Maximális fájlméret** értékét a **Dokumentumkezelés paraméterei** ablakban 150 MB-ra.

## <a name="viewing-information"></a>Információk megtekintése

A **Dolgozói Affordable Care jogosultság** oldalon tekintheti meg, hogy mely alkalmazottak vannak hozzárendelve az egyes fedezeti csoportokhoz, mely alkalmazottakat nem kell feltüntetni a jelentésekben, és mely alkalmazottak nincsenek hozzárendelve.

Ha az Affordable Care fedezeti csoport bármely alapértelmezett értékét felülírták, csillag jelenik meg a módosított érték mellett. Ha az értékek a tizenkét hónap mindegyikében megegyeznek, és nem lettek felülbírálva, az értéket a rendszer a **Mind a 12 hónap** oszlopba nyomtatja.

A lekérdezés ablak segítségével megtekintheti, hogy mely alkalmazottaknál található meg az a jelölés, hogy nem kell jelenteni őket az ACA vonatkozásában. Nem kell követni, hogy felkínáltak-e nekik fedezetet, és nem szükséges kiadni számukra az 1095-C űrlapot az év végén. **Az ACA szerint nem bejelentendő** lehetőség kiválasztásával a **Szűrés alapja:** mezőben létre lehet hozni azoknak az alkalmazottaknak a listáját, akik nem kapnak 1095-C űrlapot.

Ezenkívül megtekinthető az összes hozzárendelés nélküli alkalmazott (az **ACA-jogosultság bejelentése** mező üres), valamint azok az alkalmazottak, akik olyan Affordable Care fedezeti csoporthoz vannak hozzárendelve, amely az **Év** mezőben kiválasztott évre nézve lejárt.

A bármely szűrési beállítás segítségével létrehozott alkalmazottlisták az Excel programba exportálhatók.

Ha jelentenie kell az eltartott személyeket, mert munkáltatóként a munkavállaló által fizetett egészségügyi biztosítást nyújt, lehetőség van a juttatási csomagok által lefedett, **ACA szerint bejelentendő** megjelölésű eltartottak megtekintésére. Válassza **A függő fél jogosultságának megtekintése** lehetőséget a műveleti ablaktáblán.

> [!NOTE]
> A lekérdezési ablakban csak az **ACA szerint bejelentendő** megjelölésű juttatáscsomagok jelennek meg.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
