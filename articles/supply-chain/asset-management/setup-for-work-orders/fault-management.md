---
title: Hibakezelés
description: Ez a témakör az Eszközkezelésben történő hibakezelést ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 43f996921ccac0b3c85ecea2460cb9e4614f8c04
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226809"
---
# <a name="fault-management"></a>Hibakezelés

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezelés modulban használhatja a hibatervezőt hibatünetek, a meghibásodási területeket és a hibatípusok beállításához az eszköztípusokhoz. Ily módon az eszközökön észlelt hibák kezelhetők lesznek. Ezenkívül a hibák oka és a hibák elhárításával kapcsolatos javaslatok a munkarendelésen regisztrálhatók.

A hibák regisztrálásának és kezelésének folyamata a következő lépésekből áll.

1. A tárgyieszköz-típusokon esetleg előforduló hibatünetek, hibás területek és hibatípusok listájának létrehozása.
2. A hibatervező modulban állítsa be a tüneteket, a hibaterületeket és a hibatípusokat.

A következőkben néhány példával seítünk megérteni a hibatünetek, hibaterületek és a hibatípusok közötti különbségét.

**Hibatünetek:**

- Feszültségingadozások
- Rövidzárlat
- Zaj
- Szivárgás
- Vibrációk

**Hibaterületek:**

- Elektromos
- Mechanikai
- Hidraulikus
- Pneumatikus

**Hibatípusok:**

- Hibás fő stator tekercselés
- Hibás dióda
- Szennyezett tekercselések
- Hibás generátor
- Hibás érzékelő

## <a name="create-fault-symptoms"></a>Hibatünetek létrehozása

Hajtsa végre a következő lépéseket a hibatervezőben használható tünetlista létrehozásához.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibatünetek** lehetőséget.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. A **Hibatünet** mezőbe írjon be egy nevet a hibatünethez.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. Válassza a **Mentés** lehetőséget.

## <a name="create-fault-areas"></a>Hibaterületek létrehozása

Hajtsa végre a következő lépéseket a hibatervezőben használható területek vagy helyek listájának létrehozásához.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibaterületek** lehetőséget.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. A **Hibaterület** mezőbe írjon be egy nevet a hibaterülethez.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. Válassza a **Mentés** lehetőséget.

## <a name="create-fault-types"></a>Hibatípusok létrehozása

Hajtsa végre a következő lépéseket a hibatervezőben használható hibatípusok listájának létrehozásához.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibatípusok** lehetőséget.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. A **Hibatípus** mezőben adja meg a hibatípus nevét.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. Válassza a **Mentés** lehetőséget.

## <a name="set-up-the-fault-designer"></a>A hibatervező beállítása

A hibatervezőben be lehet állítani a tárgyieszköz-típusokra vonatkozó hibaadatokat.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibatervező** lehetőséget.
2. A bal oldali ablakban válassza ki, hogy melyik eszköztípushoz szeretné beállítani a hibarekordot.
3. A **Hibatünet** gyorslapon válassza ki a **Sorhozzáadása** elemet, majd a **Hibatünet** mezőben válassza ki a hiba tünetét.
4. A **Hibaterület** gyorslapon válassza ki a **Sorhozzáadása** elemet, majd a **Hibaterület** mezőben válassza ki a hiba területét.
5. A **Hibatípus** gyorslapon válassza ki a **Sor hozzáadása** elemet, majd a **Hiba típusa** mezőben válassza ki a hiba típusát.
6. Ha gyorsan létre kívánja hozni az összes meglévő hibatünet, -területet és -típus kombinációit a kiválasztott eszköztípushoz, válassza a **Hibakombinációk létrehozása** lehetőséget. Ez a funkció akkor hasznos, ha sok hibatünetet, -területet és -típust adott hozzá. Könnyebb törölni azokat a sorokat azon kombinációkhoz, amelyek nem relevánsak az eszköztípushoz, mint az új sorokat manuálisan létrehozni.

    > [!NOTE]
    > Ha azt szeretné, hogy a rendszer egy eszköztípusról a hibás tünetek, területek és típusok beállításait a kiválasztott eszköztípusra másolja, válassza a **Másolás eszköztípusból** parancsot.

7. A változtatások mentéséhez válassza a **Mentés** elemet.

![Hibatervező oldal](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Hibaokok létrehozása

Hajtsa végre az alábbi lépéseket a munkarendeléshez vagy a karbantartási kérelemhez adható ismert hibaokok listájának létrehozásához.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibaokok** lehetőséget.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. A **Hibaok** mezőben adja meg a hibaok nevét.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. Válassza a **Mentés** lehetőséget.

## <a name="create-fault-remedies"></a>Hibajavítások létrehozása

Hajtsa végre az alábbi lépéseket a munkarendeléshez vagy a karbantartási kérelemhez adható megoldások vagy javítások listájának létrehozásához.

1. Válassza az **Eszközkezelés** \> **Beállítás** \> **Hiba** \> **Hibajavítások** lehetőséget.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. A **Hibajavítás** mezőbe írjon be egy nevet a hibajavításhoz.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. Válassza a **Mentés** lehetőséget.

> [!NOTE]
> Igény esetén a hibák, területek, típusok, okok és javítások nevei módosíthatók. A névmódosítások automatikusan tükröződnek kapcsolódó hibaregisztrációkban.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]