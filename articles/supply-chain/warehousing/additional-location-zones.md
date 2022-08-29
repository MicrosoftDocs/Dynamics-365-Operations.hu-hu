---
title: További helyzónák
description: Ez a témakör áttekintést nyújt a Microsofthoz hozzáadott új helyzónákról Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 819330e0f6e6cd419da441f919d68ff996b6475c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336515"
---
# <a name="additional-location-zones"></a>További helyzónák

[!include [banner](../includes/banner.md)]

Három új zónamező érhető el a Microsoft Dynamics 365 Supply Chain Management modulban. A raktárkezelők segítségével további raktári szervezeteket és elrendezéseket lehet definiálni. Az új zónamezőket manuálisan vagy a **Hely beállítása** varázsló használatával lehet beállítani. Ezek Helyek táblát használó lekérdezésekben vagy szűrésekben használhatók.

Nincs szükség további beállításra a zónamezők használatához.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>A További helyzóna funkció be- és kikapcsolása

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.29-esnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatja ezt a funkciót, ha a Szolgáltatáskezelés munkaterületÉnek További helyzóna szolgáltatását keresi.

## <a name="use-location-zones"></a>Helyzónák használata

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Hely beállítása varázslóra**.
2. Adja meg az alábbi értékeket:

    - A **Raktár** mezőben válassza ki az _62_ értéket.
    - A **Zóna azonosítója** mezőben válassza ki a _EMELET_ elemet.
    - Az **1. további helyzóna** mezőben válassza ki a _PICKZONE1_ elemet.
    - Az **2. további helyzóna** mezőben válassza ki a _WEBSHOP1_ elemet.
    - A **Helyprofil azonosítója** mezőben válassza ki az _EMELET_ elemet.

3. Válassza ki az **Emelet** sort.
4. A **Kezdő szám** mezőben adja meg az _1_-es számot. A **Befejező szám** mezőben adja meg az _3_-es számot.
5. Válassza ki a **Folyosó** sort.
6. A **Kezdő szám** mezőben adja meg az _1_-es számot. A **Befejező szám** mezőben adja meg az _5_-ös számot.
7. Válassza a **Létrehozása** lehetőséget.
8. Olyan üzeneteket kap, amelyek tájékoztatnak az új helyek hozzáadásáról. Válassza ki az **Üzenetek megjelenítése** gombot az üzenetek megtekintéséhez.
9. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**. Az új helyek megjelennek a listán, és az összes zónamező elérhető (azaz a meglévő zónamezőn kívül az új zónamezők is).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]