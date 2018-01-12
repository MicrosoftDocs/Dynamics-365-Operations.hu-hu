---
title: "Hitelkártya-tranzakciók importálása és karbantartása"
description: "Ez a témakör bemutatja, hogyan importálhatja és tarthatja karban a költséggel kapcsolatos hitelkártya-tranzakciókat. Ezeket a tranzakciókat be lehet állítani úgy, hogy importálásuk ütemezés alapján automatikusan ismétlődjön, vagy importálhatók manuálisan, szükség szerint."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e640c9e44add5599be4a2e381b4ffd81f212889c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="import-and-maintain-credit-card-transactions"></a>Hitelkártya-tranzakciók importálása és karbantartása

[!include[banner](../includes/banner.md)]

A költségjellegű hitelkártya-tranzakciókat be lehet úgy állítani, hogy importálásuk ismétlődő ütemezés szerint automatikusan megtörténjen. Másik lehetőségként a tranzakciók manuálisan is importálhatók szükség szerint. A hitelkártya-tranzakciók importálása a Hitelkártya-tranzakciók adatentitáson keresztül történik.

Az adatentitásokkal kapcsolatos további tudnivalókért lásd: [Adatentitások](../../dev-itpro/data-entities/data-entities.md).

## <a name="import-credit-card-transactions"></a>Hitelkártya-tranzakciók importálása

1. A **Hitelkártyás tranzakciók** oldalon válassza a **Tranzakciók importálása** elemet. Az adatkezelés első megnyitásakor a folytatás előtt a rendszernek frissítenie kell az entitások listáját.
2. A **Név** mezőben adja meg az importálási feladat egyedi leírását.
3. A **Forrásadatok formátuma** mezőben válassza ki az importálandó hitelkártya-tranzakciókat tartalmazó fájl formátumát.
4. Válassza a **Feltöltés** elemet, majd keresse meg és válassza ki az importálandó fájlt.
5. A fájl feltöltését követően ellenőrizze a hitelkártya-tranzakciók fájljának hozzárendelését és a Hitelkártyás tranzakciók adatentitás oszlopait; ehhez válassza a csempén látható **Leképezés megtekintése** elemet. Ha leképezési hibák vannak jelen, vagy ha módosítania kell a leképezést, a leképezés módosításait a **Megfeleltetés megjelenítése** lapon vagy a **Hozzárendelés adatai** lapon végezheti el.
6. A hitelkártya-tranzakciók automatizálásához jelölje be az **Ismétlődő adatkezelési feladat létrehozása** elemet. Ezután beállíthatja az ismétlődést, amely meghatározza, hogy milyen gyakran kell importálni a hitelkártya-tranzakciókat. Amikor elkészült, válassza az **OK** elemet.
7. A kiválasztott fájl azonnali importálásához válassza az **Importálás** elemet.
8. Ha az importálás során hibák lépnek fel, megtekintheti a végrehajtási naplót vagy az előkészítési adatokat, és megkeresheti a hibákat, amelyeket ki kell javítani a sikeres importálás biztosítása érdekében.

> [!NOTE]
> Ha egynél több fájlformátumot kell importálni, külön importálási feladatot kell létrehoznia minden formátumtípushoz.

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>Kilépett alkalmazottak hitelkártyás tranzakcióinak ismételt hozzárendelése

Alkalmazotti rekord lezárását követően az alkalmazott Active Directory Domain Services (AD DS) fiókja letiltásra kerül. Lehet viszont, hogy még mindig vannak aktív hitelkártya-tranzakciók, amelyeket kiadásként könyvelni kell és vissza kell téríteni. A **Hitelkártyás tranzakciók** oldalon minden olyan alkalmazotti hitelkártya-tranzakciót ismételten hozzárendelhet, ahol a társított alkalmazott kilépett.

Válasszon ki egy vagy több hitelkártyás tranzakciót, majd ezután válassza a **Tranzakciók ismételt hozzárendelése** elemet. Ezután kiválaszthat egy másik alkalmazottat, akihez hozzárendelheti a hitelkártyás tranzakciókat. A hitelkártyás tranzakciók ismételt hozzárendelése után a tranzakciók kiválaszthatók egy költségjelentéshez, és a költségjelentések szokásos visszaigénylési folyamatával fizethető ki a visszatérítés.

