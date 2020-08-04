---
title: További helyzónák
description: Ez a témakör áttekintést nyújt a Microsoft rendszerhez hozzáadott új helyzónákról Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 32114db4cf202870bae5ce307517170d3e618762
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597142"
---
# <a name="additional-location-zones"></a>További helyzónák

[!include [banner](../includes/banner.md)]

Három új zónamező érhető el a Microsoft Dynamics 365 Supply Chain Management modulban. A raktárkezelők segítségével további raktári szervezeteket és elrendezéseket lehet definiálni. Az új zónamezőket manuálisan vagy a **Hely beállítása** varázsló használatával lehet beállítani. Ezek Helyek táblát használó lekérdezésekben vagy szűrésekben használhatók.

Nincs szükség további beállításra a zónamezők használatához.

## <a name="turn-on-the-additional-location-zone-feature"></a>A További helyzóna funkció bekapcsolása

A *További helyzóna* funkciót használata előtt be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkciónév:** *További helyzóna*

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
