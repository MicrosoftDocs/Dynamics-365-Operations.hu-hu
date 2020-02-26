---
title: Affordable Care Act (ACA) jelentések létrehozása
description: 'Olyan funkció érhető el, amely azokat a munkáltatókat segítik, amelyeknek az 1095-B és 1095-C űrlapokon jelentett adatokat kell támogatniuk az Affordable Care Act munkáltatói felhatalmazásra vonatkozó részének támogatása érdekében. Megjegyzés: Ez a funkció csak az Egyesült Államokbeli jogi személyek számára aktív.'
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 47532861203fedbffc49aa92d25fc99de9d25376
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009297"
---
# <a name="generate-affordable-care-act-aca-reports"></a>Affordable Care Act (ACA) jelentések létrehozása

Olyan funkció érhető el, amely azokat a munkáltatókat segítik, amelyeknek az 1095-B és 1095-C űrlapokon jelentett adatokat kell támogatniuk az Affordable Care Act **munkáltatói felhatalmazásra** vonatkozó részének támogatása érdekében. Megjegyzés: Ez a funkció csak az Egyesült Államokbeli jogi személyek számára aktív.

## <a name="getting-started"></a>Első lépések
Az adatok nyomon követésének megkezdésekor az 1095-B és 1095-C űrlapokon történő jelentéstételhez, először létre kell hozni egy vagy több Affordable Care fedezeti csoportot. Az Affordable Care fedezeti csoportok használatosak az alkalmazottaknak nyújtott fedezeti ajánlat jelzésére, az alkalmazott részesedésének jelzésére a legkisebb költség alapú havi díjból (ha költség magasabb a szövetségi szegénységi küszöbnél), valamint a munkáltató esetében használt Safe Harbor jelzésére, amennyiben ez alkalmazható. Az Affordable Care Act csoportok használata lehetővé teszi az adatok kezelését ezeknek a mezőknek az esetében anélkül, hogy minden alkalmazotti rekordhoz hozzá kellene nyúlni abban az esetben, amikor a feltételek ugyanazok. Ezenkívül az Affordable Care fedezeti csoportokat egyszerűen lehet hozzárendelni egy vagy több alkalmazotthoz az oldal tömeges hozzárendelés funkciójával.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Fedezeti csoportok több változatának karbantartása
Minden fedezeti csoportból több verzió kezelhető, így változtatásokat lehet végrehajtani, hogy naprakészek legyenek a csoportadatok, anélkül, hogy új csoportot kellene létrehozni, és hozzá kellene rendelni az alkalmazottakat, amikor változik valami a szervezetben vagy a kínált kedvezményekben. 

A szükséges Affordable Care fedezeti csoportok létrehozása után lehetőség van a csoportok tömeges hozzárendelésére az alkalmazottakhoz a **Tömeges hozzárendelés** funkcióval az oldalon; másik megoldásként minden egyes alkalmazott esetében megadhatja, hogy szükséges-e az ACA-információkat nyomon követés és jelentése, valamint hozzárendelheti az alkalmazottat egy Affordable Care fedezeti csoporthoz.

Ha az Affordable Care fedezeti adatokat nem kell nyomon követni vagy jelenteni egy alkalmazott esetében, például azért, mert az alkalmazott részmunkaidős, a **Jogosultság bejelentése** mező Nem értékre állítható. Annak ellenére, hogy az összes olyan alkalmazottat, akinek az esetében nyomon kell követni az ACA-információkat, hozzá kell rendelni egy Affordable Care fedezeti csoporthoz, továbbra is lehetőség van a **Jogosultságra vonatkozó ajánlat**, az **Alkalmazott költségmegosztása** és a **Safe Harbor** beállítások módosítására bármely hónapban – vagy hónapokban –, amelyben az Affordable Care fedezeti csoportokban megadottól különböző értékekre van szükség.

Kivételek megadásához bármely Affordable Care fedezeti csoport értékének esetében kattintson a Dolgozó részletes adatai oldalon található Affordable Care fedezet lehetőségre, amely a További információk szakaszban található a Foglalkoztatás lapon.

## <a name="reporting-health-care-coverage"></a>Egészségügyi fedezeti jelentés
Annak a nyomon követése mellett, hogy mi történne, ha egészségbiztosítás felajánlása történne egy teljes munkaidős alkalmazott számára, ha a munkáltató a munkáltató által támogatott, a munkavállaló által fizetett egészségügyi biztosítást kínál, amelyre az alkalmazott fel van iratkozva (függetlenül attól, hogy a foglalkoztatottsági állapota teljes munkaidős vagy részmunkaidős), további információt kell jelenteni a 1095-C űrlapon. A munkáltató által támogatott juttatási csomagban részesülő összes alkalmazottat (és eltartottjaikat) meg kell adni annak a hónapnak a jelentésében, amelyben a csomag vonatkozik rájuk. 

Azt, hogy minden juttatácsomagot jelenteni kell-e, az **ACA szerint bejelentendő** négyzet bejelölésével adhatja meg.

Ezenkívül, ha az alkalmazott úgy döntött, hogy a juttatás kiterjedjen eltartottjai bármelyikére, minden egyes alkalmazott esetében megadhatja azokat a dátumokat, amikor a juttatás kiterjedt az eltartottra, a Juttatások kezelése lapon. Ha jelezni szeretné, hogy az eltartott jogosult a juttatásra, kattintson a Szerkesztés gombra az Eltartottak gyorslap műveleti ablakában.

A **Függő fél jogosultsági dátumának kezelése** lapon adhatja meg a dátumokat, amikor a juttatás vonatkozott az eltartottra. Ha ezen a lapon dátumokat ad meg, ezzel automatikusan bejelöli a **Fedezve** jelölőnégyzetet a **Juttatások karbantartása** oldalon.

## <a name="generate-1095b-and-1095c-forms"></a>1095B és 1095C űrlap létrehozása
Lehetőség van a 109-B és 1095-C űrlapok létrehozására a terméken belül, és a továbbításukra az összes alkalmazottnak. Az adóhatósághoz elküldhető, 1095-C és a megfelelő benyújtandó 1094-C fájlok elektronikus úton történő generálása szintén megoldható a rendszerből.  

A 1095-C űrlap létrehozásakor adja meg a megfelelő adóévet, és jelölje, hogy szükséges-e társadalombiztosítási számok maszkolása. Ha több mint 500 alkalmazottnak nyomtat 1095-C űrlapot, egynél több PDF-fájl fog kapni. Azt ajánljuk, hogy növelje meg a **Maximális fájlméret** értékét a **Dokumentumkezelés paraméterei** ablakban 150 MB-ra.

## <a name="viewing-information"></a>Információk megtekintése
A **Dolgozói Affordable Care jogosultság** oldalon tekintheti meg, hogy mely alkalmazottak vannak hozzárendelve az egyes fedezeti csoportokhoz, mely alkalmazottakat nem kell feltüntetni a jelentésekben, és mely alkalmazottak nincsenek hozzárendelve.

Ha az Affordable Care fedezeti csoport bármely alapértelmezett értékét felülírták, csillag jelenik meg a módosított érték mellett. Ha az értékek a tizenkét hónap mindegyikében megegyeznek, és nem lettek felülbírálva, az értéket a rendszer a **Mind a 12 hónap** oszlopba nyomtatja.

A lekérdezés ablak segítségével megtekintheti, hogy mely alkalmazottaknál található meg az a jelölés, hogy nem kell jelenteni őket az ACA vonatkozásában, ami azt jelenti, hogy nem kell követni, hogy felkínáltak-e nekik fedezetet, és nem szükséges kiadni számukra az 1095-C űrlapot az év végén. **Az ACA szerint nem bejelentendő** lehetőség kiválasztásával a **Szűrés alapja:** mezőben, létre lehet hozni azoknak az alkalmazottaknak a listáját, akik azt a megjelölés kapták, hogy nem kell 1095-C űrlapot kapniuk.

Az ACA szempontjából nem jelentendő alkalmazottak listájának megtekintése mellett megtekinthető az összes hozzárendelés nélküli alkalmazott (az **ACA jogosultság bejelentése** mező üres), valamint azok az alkalmazottak, akik olyan Affordable Care fedezeti csoporthoz vannak hozzárendelve, amely az **Év** mezőben kiválasztott évre nézve lejárt.

A bármely szűrési beállítás segítségével létrehozott alkalmazottlisták az Excel programba exportálhatók.

Ha jelentenie kell az eltartott személyeket, mert munkáltatóként a munkavállaló által fizetett egészségügyi biztosítást nyújt, lehetőség van a juttatási csomagok által lefedett, **ACA szerint bejelentendő** megjelölésű eltartottak megtekintésére A függő fél jogosultságának megtekintése művelet kiválasztásával a műveleti ablaktáblán.

**Megjegyzés:** A lekérdezési ablakban csak az **ACA szerint bejelentendő** megjelölésű juttatáscsomagok jelennek meg.
