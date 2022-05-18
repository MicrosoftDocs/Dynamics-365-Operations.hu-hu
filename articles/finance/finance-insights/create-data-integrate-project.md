---
title: Adatintegrációs projekt létrehozása
description: Ez a témakör bemutatja az adatintegrációs projektek létrehozásához szükséges témaköröket.
author: ShivamPandey-msft
ms.date: 05/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4d69ffcb6ccfcc7bae2891f2539941f7b6bbf86e
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722883"
---
# <a name="create-a-data-integration-project"></a>Adatintegrációs projekt létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja az adatintegrációs projektek létrehozásához szükséges témaköröket.

1. Jelentkezzen be a Microsoft Dynamics 365 Pénzügy 365-be.
2. Menjen a **Munkaterületek \> Adatkezelés** pontra, és válassza az **Adatentitások** lehetőséget. Várja meg, amíg az összes adatentitás frissül, mielőtt továbblépne a következő lépésre.
3. Nyissa meg a [Power Apps-portált](https://make.powerapps.com/), és kövesse az alábbi lépéseket:

    1. Válassza ki a megfelelő környezetet.
    2. A bal oldali navigációs ablakban válassza a Kapcsolatok **Dataverse\> lehetőséget**.
    3. Csatlakozzon a következő elemek megfelelő példányaihoz:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Nyissa meg a [Power Apps környezetet](https://admin.powerapps.com/environments), és kövesse az alábbi lépéseket:

    1. Adatintegráció **kiválasztása**.
    2. Válassza ki a **Csatlakozókészletek** lehetőséget.
    3. Válassza ki az **Új csatlakozókészlet** lehetőséget.
    4. Adja meg a csatlakozás nevét.
    5. Válassza ki a megfelelő kapcsolatokat a következő elemekhez:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Válassza ki a megfelelő szervezeti leképezést.
    7. Válassza a **Létrehozása** lehetőséget.

5. Nyissa meg a [Power Apps környezetet](https://admin.powerapps.com/environments), és kövesse az alábbi lépéseket:  

    1. Hozzon létre egyetlen adatintegrációs projektet a következő sablonokhoz a most létrehozott kapcsolatkészlet használatával:

        - Vevői kifizetések eredményének (CDS – Fin and Ops 10.0.17+)
        - Készpénzáramlási idősorozatok eredményei (CDS to Fin and Ops)
        - Költség idősorozatok eredményei (CDS to Fin and Ops)

      > [!NOTE]
      > Ha több adatintegrációs projektet hoz létre mindegyik sablonhoz, akkor hibák okozhatják a frissítéseket.

    2. Állítsa be a megfelelő ütemezést az egyes projektekhez.

> [!NOTE]
> Ha nem látja a Dataverse szükséges entitásokat a mezőben, **akkor kattintson a Jóváírás és collectionsSetupFinance** > **·** > **Az előrejelzés** > **paraméterei** között, engedélyezze a funkciót, **a** vevői kifizetések előrejelzéseit, **majd válassza az Előrejelzési modell létrehozása** lehetőséget. Amikor befejeződött az AI-modell telepítése, Dataverse az integráció létrehozásához szükséges entitások telepítve lesznek.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
