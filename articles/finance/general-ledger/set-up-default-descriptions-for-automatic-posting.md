---
title: Alapértelmezett leírások beállítása az automatikus feladáshoz
description: Beállíthat olyan alapértelmezett szöveget, amelyet a rendszer a  mező kitöltésére használ olyan könyvelési bejegyzések esetén, amelyek feladása automatikusan történik a főkönyvbe. Minden tranzakciótípus esetén beállíthat alapértelmezett leírásszöveget szabad formájú szöveget használva vagy rögzített változókat kijelölve.
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3963b4ed63021dd3c84a0d87b768486dcb0f386d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837081"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Alapértelmezett leírások beállítása az automatikus feladáshoz

[!include [banner](../includes/banner.md)]

Beállíthat olyan alapértelmezett szöveget, amelyet a rendszer a  mező kitöltésére használ olyan könyvelési bejegyzések esetén, amelyek feladása automatikusan történik a főkönyvbe. Minden tranzakciótípus esetén beállíthat alapértelmezett leírásszöveget szabad formájú szöveget használva vagy rögzített változókat kijelölve.

> [!NOTE]
> Bizonyos tranzakciótípusok esetén belefoglalhat az adott tranzakciótípusokkal kapcsolatos Microsoft Dynamics AX adatbázisban lévő mezőkből származó szöveget is. A tranzakciótípusok és az országok és régiók listája tekintetében lásd: [Választható: Szövegek más alapértelmezett leírások](#optional-add-other-text-to-default-descriptions) szakasz a témakör későbbi részében.

## <a name="set-up-default-descriptions"></a>Alapértelmezett leírások beállítása

1. Lépjen a **Szervezetadminisztráció** \> **Beállítás** \> **Alapértelmezett leírások** menüpontba.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Leírás** mezőben válassza ki a tranzakciótípust, amelyhez alapértelmezett leírást kíván létrehozni.
4. A **Nyelv** mezőben válassza ki azt a nyelvet, amelyre ez a leírás vonatkozik.
5. A **Szöveg** mezőbe írja be az alapértelmezett leírást. A szöveget beírhatja a mezőbe, vagy használhat egyet vagy többet a következő szabad szöveges változók közül:

    - **%1** – A tranzakció dátumának hozzáadása.
    - **%2** – A főkönyvbe feladásra kerülő dokumentumtípusnak megfelelő azonosító hozzáadása. Például számlákhoz kapcsolódó tranzakciótípusok esetén a **%2** változó a számlaszámot adja hozzá.
    - **%3** – A főkönyvbe feladásra kerülő dokumentumtípushoz kapcsolódó azonosító hozzáadása. Például számlákhoz kapcsolódó tranzakciótípusok esetén a **%3** változó a vevőkód számát adja hozzá.

## <a name="optional-add-other-text-to-default-descriptions"></a>Választható: Szöveget más alapértelmezett leírások

Bizonyos tranzakciótípusok esetén belefoglalhat egyes országokban vagy régiókban az alapértelmezett leírások adott tranzakciótípusokkal kapcsolatos adatbázisban lévő mezőkből származó szöveget is. A következő listák megjelenítése a tranzakciótípusok és országok és régiók amelyhez ez a beállítás akkor érhető el.

**Tranzakciótípusok**

Más szöveget adhat a tranzakciótípusokat, amelyeket a következő dokumentumtípusokat kapcsolódó alapértelmezett leírása:

- Vevői számlák
- Vevő jóváírások
- Vevő készpénzfizetések
- Szállítói kifizetések
- Értékesítési rendelés
- Beszerzési rendelések
- Készletnaplók
- Alaptervezés (MRP)
- Tárgyi eszközök

**Országok és régiók**

Ez a beállítás a következő országokra és régiókra érhető el:

- Brazília
- Kína
- Cseh Köztársaság
- Kelet-Európa
- Magyarország
- Indiai
- Japán
- Litvánia
- Lettország
- Lengyelország
- Oroszország

### <a name="add-text-to-default-descriptions"></a>Választható: Szöveget más alapértelmezett leírások

A lépések elvégzése után a korábbi [Alapértelmezett leírások beállítása](#set-up-default-descriptions) szakasz lépései végrehajtásával más szöveget adhat az alapértelmezett leírásokhoz.

1. Válassza a **Paraméterek** gyorslap **Hozzáadás** elemét.
2. A **Hivatkozási tábla** mezőben válassza ki azt a táblát, amelyből paraméteradatokat szeretne hozzáadni a leíráshoz.
3. A **Hivatkozási mező** mezőben válassza ki azt mezőt, amelyből paraméteradatokat szeretne hozzáadni a leíráshoz.
4. További mezők hozzáadásához ismételje meg a 1–3. lépéseket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]