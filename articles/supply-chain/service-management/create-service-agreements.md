---
title: Szolgáltatási szerződések létrehozása
description: Ez a témakör leírja, hogyan lehet szolgáltatási szerződéseket létrehozni a Szolgáltatáskezelés és a Projektkezelés és könyvelés modul szolgáltatásaival.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d18d279cd437e98cad6495def953978cb78e723e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901763"
---
# <a name="create-service-agreements"></a>Szolgáltatási szerződések létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet szolgáltatási szerződéseket létrehozni a Szolgáltatáskezelés és a Projektkezelés és könyvelés modul szolgáltatásaival.

## <a name="create-a-service-agreement-from-service-management"></a>Szolgáltatási szerződés létrehozása a Szolgáltatáskezelésből

1. Lépjen a **Szolgáltatáskezelés** ponthoz.
2. Válassza a **Szolgáltatási szerződések** lehetőséget egy új szolgáltatásiszerződés-sor létrehozásához a lap fejlécében. 
3. Válassza az **Új** lehetőséget. Adjon meg egy leírást, válasszon egy hivatkozást a projekthez a **Projektazonosító** mezőben, és töltse ki a szolgáltatási szerződés többi mezőjét és sorát. Válassza a **Mentés** lehetőséget.
4. A **Kapcsolatok** lapon válassza **A szolgáltatás tárgyai** vagy a **Szervizfeladatok** elemet a szolgáltatásiobjektum-kapcsolatok vagy a szervizfeladat-kapcsolatok létrehozásához. A szolgáltatások kapcsol tárgyai és a kapcsolt szervizfeladatok hozzárendelhetők a szolgáltatási szerződés soraihoz.
5. Alap alsó részén a sablonból, másik szolgáltatási szerződésből történő másolással vagy a sorok kézi megadásával hozzon létre szolgáltatásiszerződés-sorokat.

> [!NOTE]
> Ha másik szolgáltatási szerződésből másol át sorokat, akkor jelezheti, hogy a szolgáltatás tárgyainak és a szervizfeladatoknak a kapcsolatait át szeretné-e másolni. Ha átmásolja ezeket a kapcsolatokat, akkor megjelennek a szolgáltatási szerződés meglévő kapcsolatai mellett. Ha szolgáltatási sablonból másol szerződéssorokat, akkor a kapcsolatok automatikusan az új szolgáltatásiszerződés-sorok megfelelő kapcsolati mezőibe kerülnek.

## <a name="create-service-agreement-lines-manually"></a>Szolgáltatási szerződés sorainak létrehozása kézzel

1. A **Szolgáltatási szerződések** lapon adjon meg egy szolgáltatásiszerződés-sort a sorrácsban. 
2. Írja be a megfelelő adatokat a szolgáltatásiszerződés-sorba. 
3. Válassza a **Mentés** lehetőséget a sor mentéséhez, és zárja be a lapot.

## <a name="create-a-service-agreement-from-project"></a>Szolgáltatási szerződések létrehozása a Projekt modulból

1. Válassza a **Projektvezetés és könyvelés** elemet.
2. Az **Összes projekt** elemet válassza.
3. Válassza ki a projektet a listából.
4. A **Műveleti ablaktáblán** válassza a **Kezelés** lehetőséget. Az **Új** műveletcsoportban válassza a **Szolgáltatás** lehetőséget, és válassza ki a **Szolgáltatási szerződés** pontot.
5. A projekthivatkozás létrehozásához **kövesse a** Szolgáltatási szerződés létrehozása című szakaszban ismertetett lépéseket.


## <a name="related-articles"></a>Kapcsolódó cikkek

[Szolgáltatási szerződések kialakítása és megkötése – áttekintés](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]