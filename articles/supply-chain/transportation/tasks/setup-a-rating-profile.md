---
title: Díjazási profilok
description: Ez a témakör az adatok beállítását írja le a díjazási profilokhoz.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceb2b7a5edcee6e248798a6bee114c7da7ecb18a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973960"
---
# <a name="rating-profiles"></a>Díjazási profilok

A díjazási profil egy logisztikai szerződéshez hasonlít (de nem szerződéshez). Ez a rakományok szállítási vámtarifáinak meghatározására szolgál. 

Minden díjazási profil egyedi jellegű a szállítmányozóra vonatkozóan. A profilban a szállítmányozót egy díjnyilvántartáshoz társíthatja. A díjnyilvántartás meghatározza a díjalap-hozzárendelést és az alapdíjat. Az alapdíj határozza meg a szállítmányozó díját.

A díjazási profilt egy általános oldal, amely áttekintést nyújt az összes meglévő díjazási profilra vonatkozóan. Másik lehetőségként a díjazási profilt közvetlenül a szállítmányozóból is beállíthatja. Mindkét esetben a minősítési profilhoz megadott információ ugyanaz.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Díjazási profil létrehozása vagy szerkesztése a díjazási profilok oldalon lehetséges

A **Díjazási profilok** lapon tekintheti meg az összes elérhető díjazási profilt. Lehetőség van a meglévő profilok szerkesztésére és új profilok létrehozására is.

1. Lépjen a **Szállításkezelés \> Beállítás \> Díjazás \> Díjazási profil** lehetőségre.
1. A művelet ablakban válassza az **Új** lehetőséget új díjazási sablon rácshoz való hozzáadásához, vagy válassza a **Szerkesztés** lehetőséget egy meglévő profil szerkesztéséhez.
1. Az új vagy meglévő díjazási profil sorában állítsa be a következő mezőket:

    - **Díjazási profil** – Adja meg a díjazási profil egyedi azonosítóját (azonosító).
    - **Név** – Írja be a díjazási profil leíró nevét.
    - **Szállítmányozó** – Válasszon ki egy szállítmányozót. A beállított díjazási profil a kiválasztott szállítmányozó **Szállítmányozó** lapján is látható lesz .
    - **Telephely** és **Raktár** – Válasszon ki egy telephelyet és raktárat.
    - **Díjazási motor** – Válassza ki a díjazási profilhoz tartozó díjazási motort.
    - **Díjnyilvántartás** – Válassza ki a díjnyilvántartáshoz tartozó díjazási motort. A díjnyilvántartás segítségével meghatározhatja az alapdíj típusát és az alapdíjat. További információkért lásd: [Díjnyilvántartások beállítása](set-up-rate-masters.md).
    - **Szállításiidő-kalkulátor** – Válassza ki a díjazási profil szállításiidő-kalkulátorát.
    - **Szállítmányozói üzemanyag-mutató** – Válassza ki a díjazási profilhoz használt díjkalkulátort és szállítmányozói üzemanyag-mutatót.
    - A **Kezdő dátum és idő** és a **Tényleges befejezés dátuma és időpontja** – Adja meg azt az időszakot, amikor a díjazási profilnak aktívnak kell lennie.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Díjazási profil létrehozása közvetlenül a Szállítmányozók oldalon lehetséges

1. Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozók** lehetőségre.
1. A listában válasszon ki egy szállítót.
1. A **Díjazási profilok** gyorslapon válassza az **Új** lehetőséget a díjazási profil létrehozásához.
1. Adja meg az új díjazási profil mezőit. Ezek a mezők megegyeznek a **Díjazási profilok** lap mezőivel, a témakör előző szakaszának leírása szerint.

> [!NOTE]
> A **Szállítmányozók** lapon létrehozott profilok a **Díjazási profilok** oldalon is megjelennek.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]