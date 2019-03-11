---
title: Dolgozó konfigurálása mobil feladatvégző eszközzel
description: Ez az eljárás bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bb4d806810660e55ef13a9ff21c07e0ce194496
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "327389"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Dolgozó konfigurálása mobil feladatvégző eszközzel

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.


## <a name="assign-roles-to-user-account"></a>Szerepkörök hozzárendelése a felhasználói fiókhoz
1. Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.
2. A gyorsszűrő segítségével szűrheti a dolgozó nevét, amikor a felhasználói fiók társítva van a gépkezelő szerepkörrel. A mintaadatok esetében a név Shannon lenne.
3. Jelölje ki a Felhasználói fiók rekordot.
4. A listában kattintson a „Név” hivatkozásra a kijelölt sorban a felhasználói fiók adatainak megtekintéséhez.
5. A fán jelölje be a „Szerepkörök\gépkezelő" lehetőséget.
6. Zárja be a Felhasználói fiók részletei lapot.
7. Zárja be a lapot.

## <a name="configure-worker-account"></a>Dolgozói fiók konfigurálása
1. Ugrás az Emberi erőforrások > Dolgozók > Dolgozók elemre.
2. A gyorsszűrő segítségével szűrheti a dolgozó nevét, amikor a felhasználói fiók társítva van a gépkezelő szerepkörrel. A mintaadatok esetében a név Shannon lenne.
3. Jelölje ki a Felhasználói fiók rekordot.
4. A listában kattintson a „Név” hivatkozásra a kijelölt sorban a felhasználói fiók adatainak megtekintéséhez.
5. Kattintson a Foglalkoztatás lapra.
6. Bontsa ki a munkaidő-nyilvántartás gyorslapot, és kattintson az Aktiválás a regisztrációs terminálokon elemre.
7. Kattintson az Aktiválás a regisztrációs terminálokon elemre.
8. A Számításcsoport mezőben adjon meg vagy válasszon ki egy értéket.
9. Az Alapértelmezett számítási csoport mezőben adjon meg vagy válasszon ki egy értéket.
10. A Jóváhagyáscsoport mezőben adjon meg, vagy válasszon ki egy értéket.
11. A Normál profil mezőben adjon meg vagy válasszon ki egy értéket.
12. Az Profilcsoport mezőben adjon meg, vagy válasszon ki egy értéket.
13. Kattintson az OK gombra.
14. Kattintson a Szerkesztés gombra az új munkaidő-nyilvántartásos munkavállaló belépőkártyaszámának megadásához.
15. Írjon be egy értéket a Belépőkártya-azonosító mezőbe.
16. Kattintson a Mentés gombra.
17. Használja a SaveRecord parancsikont.
18. Zárja be a Dolgozók részletei lapot.
19. Zárja be a lapot.

## <a name="assign-worker-to-device-group"></a>Társítsa a dolgozót az eszközcsoporthoz.
1. Ugrás a Gyártásvezérlés > Beállítás > Gyártásvégrehajtás > Feladatkártya konfigurálása az eszközökhöz elemre.
2. Kattintson a Hozzáadás gombra.
3. A listában jelölje meg a kiválasztott sort.
4. Kattintson az OK gombra.
5. Kattintson a Szerkesztés lehetőségre.
6. A Termelési egység mezőben megadhatja az alapértelmezett szűrőt a dolgozóhoz. Ez biztosítja, hogy csak a kijelölt termelési egység termelési feladatai jelenjenek meg, amikor a dolgozó bejelentkezik az eszközön.
7. Zárja be a lapot.

