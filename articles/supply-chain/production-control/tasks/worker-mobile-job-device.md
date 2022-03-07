---
title: Dolgozó konfigurálása mobil feladatvégző eszközzel
description: Ez a témakör bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.
author: johanhoffmann
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d9745995752c06385acc31e529de52eefaa6f96
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573561"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Dolgozó konfigurálása mobil feladatvégző eszközzel

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet a megfelelő szerepköröket hozzárendelni egy dolgozó felhasználói fiókjához, és ezt követően engedélyezni a dolgozónak az üzemi regisztrációk végrehajtását.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Annak ellenőrzése, hogy a dolgozó hozzá van-e rendelve egy adott szerephez

Ebben a példában a dolgozó fiókjának konfigurálása előtt ellenőrizze, hogy a „SHANNON” nevű felhasználó hozzá van-e rendelve a gépkezelői szerepkörhöz.

1. Ugorjon a **Navigációs ablaktábla > Modulok > Rendszerfelügyelet > Felhasználók > Felhasználók** lehetőségre.
2. Keressen felhasználót a gyorsszűrőben. Ennél a példánál adja meg a `shannon` nevet.
3. Válassza ki a hivatkozást a felhasználói fiók **Felhasználóazonosító** oszlopában.
4. A **Felhasználói szerepkörök** fán, válassza ki a **Szerepkörök > Gépkezelő** lehetőséget.
5. A kezdőlapra való visszatéréshez zárja be a **felhasználói adatok** és **felhasználók** oldalakat.

## <a name="configure-worker-account"></a>Konfigurálja a dolgozó fiókját
1. Ugorjon a **Navigációs ablaktábla > Modulok > Emberi erőforrások > Dolgozók > Dolgozók >** lehetőségre.
2. Keressen felhasználót a gyorsszűrőben. Ennél a példánál adja meg a `shannon` nevet.
3. Válassza ki a hivatkozást a felhasználói fiók **Név** oszlopában.
4. Válassza ki az **Időnyilvántartás** fület.
5. Válassza ki az **Aktiválás a regisztrációs terminálokon** lehetőséget.
6. Adja meg vagy válassza ki a következő mezőkben szereplő értékeket:  

    - **Számítási csoport**  
    - **Alapértelmezett számítási csoport**  
    - **Jóváhagyási csoport**  
    - **Szokásos profil**  
    - **Profilcsoport**  

7. Válassza ki az **OK** lehetőséget.
8. Válassza ki a **Szerkesztés** lehetőséget az új munkaidő-nyilvántartásos dolgozó belépőkártyaszámának megadásához. Adjon meg egy értéket a **Belépőkártya azonosítója** mezőben.
9. Válassza a **Mentés** lehetőséget.
10. Zárja be a **Dolgozó részletes adatai** és **Dolgozók** oldalt.

## <a name="assign-worker-to-device-group"></a>Dolgozó társítása eszközcsoporthoz
1. Ugorjon a **Gyártásvezérlés > Beállítás > Gyártásvégrehajtás > Feladatkártya konfigurálása az eszközökhöz** elemre.
2. Válassza a **Hozzáadás** lehetőséget.
3. Válassza ki a listából a kívánt dolgozót. Ebben a példában válassza ki **SHANNON-t**.
4. Válassza ki az **OK** lehetőséget.
5. Válassza ki a **Szerkesztés** opciót.
6. A **Termelési egység** mezőben megadhatja az alapértelmezett szűrőt a dolgozóhoz. Ez biztosítja, hogy csak a kijelölt termelési egység termelési feladatai jelenjenek meg, amikor a dolgozó bejelentkezik az eszközön. Adja meg a kívánt értéket.
7. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]