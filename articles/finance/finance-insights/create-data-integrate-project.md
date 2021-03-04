---
title: Adatintegrációs projekt létrehozása (előzetes verzió)
description: Ez a témakör bemutatja, hogyan hozhat létre adatintegrációs projektet.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: fb17d5e82709a34ff088774d9e9034adb714b58c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646253"
---
# <a name="create-a-data-integrator-project-preview"></a>Adatintegrációs projekt létrehozása (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör bemutatja, hogyan hozhat létre adatintegrációs projektet.

1. Jelentkezzen be a Microsoft Dynamics 365 Finance szolgáltatásba.
2. Menjen a **Munkaterületek \> Adatkezelés** pontra, és válassza az **Adatentitások** lehetőséget. Várja meg, amíg az összes adatentitás frissül, mielőtt továbblépne a következő lépésre.
3. Nyissa meg a [Power Apps-portált](https://make.powerapps.com/), és kövesse az alábbi lépéseket:

    1. Válassza ki a megfelelő környezetet.
    2. A bal oldali navigációs ablakban válassza ki az **Adat \> kapcsolatok** lehetőséget.
    3. Csatlakozzon a következő elemek megfelelő példányaihoz:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Nyissa meg a [Power Apps környezetet](https://admin.powerapps.com/environments), és kövesse az alábbi lépéseket:

    1. Válassza az **Adatintegrátor** lehetőséget.
    2. Válassza ki a **Csatlakozókészletek** lehetőséget.
    3. Válassza ki az **Új csatlakozókészlet** lehetőséget.
    4. Adja meg a csatlakozás nevét.
    5. Válassza ki a megfelelő kapcsolatokat a következő elemekhez:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Válassza ki a megfelelő szervezeti leképezést.
    7. Válassza a **Létrehozása** lehetőséget.

5. Nyissa meg a [Power Apps környezetet](https://admin.powerapps.com/environments), és kövesse az alábbi lépéseket:  

    1. Az imént létrehozott kapcsolatkészlet használatával adatintegrációs projekteket hozhat létre a következő sablonokhoz:

        - Az ügyfelek fizetési információinak eredményei (CDS to Fin and Ops)
        - Készpénzáramlási idősorozatok eredményei (CDS to Fin and Ops)
        - Költség idősorozatok eredményei (CDS to Fin and Ops)

    2. Állítsa be a megfelelő ütemezést az egyes projektekhez.

> [!NOTE]
> Ha nem látja a szükséges entitásokat a CDS-ben, válassza a **Követelések és beszedések > Beállítás > Pénzügyi információk > Pénzügyi információk paraméterei** lehetőséget, engedélyezze az Ügyfélfizetési előrejelzések funkciót, és kattintson az **Előrejelzési modell létrehozása** gombra. Ha az AI-modell telepítése befejeződött (sikeres vagy sikertelen), az integráció létrehozásához szükséges CDS-entitások a CDS-ben lesznek telepítve.

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]