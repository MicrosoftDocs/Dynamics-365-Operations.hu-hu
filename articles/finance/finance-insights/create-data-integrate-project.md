---
title: Adatintegrációs projekt létrehozása
description: Ez a témakör bemutatja, hogyan hozhat létre adatintegrációs projektet.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: b08af906c18f6c0790ca56c69a833733f48cd88c
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386362"
---
# <a name="create-a-data-integrator-project"></a>Adatintegrációs projekt létrehozása

[!include [banner](../includes/banner.md)]

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
            - Ha a 10.0.17-es vagy újabb verziót használja, akkor az ügyfélkifizetések eredményének megfelelő sablont (CDS to Fin and Ops 10.0.17+) kell használnia.
        - Készpénzáramlási idősorozatok eredményei (CDS to Fin and Ops)
        - Költség idősorozatok eredményei (CDS to Fin and Ops)

    2. Állítsa be a megfelelő ütemezést az egyes projektekhez.

> [!NOTE]
> Ha nem látja a szükséges entitásokat a CDS-ben, válassza a **Követelések és beszedések > Beállítás > Pénzügyi információk > Pénzügyi információk paraméterei** lehetőséget, engedélyezze az Ügyfélfizetési előrejelzések funkciót, és kattintson az **Előrejelzési modell létrehozása** gombra. Ha az AI-modell telepítése befejeződött (sikeres vagy sikertelen), az integráció létrehozásához szükséges CDS-entitások a CDS-ben lesznek telepítve.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
