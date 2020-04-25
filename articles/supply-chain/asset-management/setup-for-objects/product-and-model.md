---
title: Eszközgyártók és modellek
description: Ez a témakör azt mutatja be, hogyan lehet eszközgyártókat és kapcsolódó modelleket beállítani az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2ef8a9afc007ce7e453f5e9cadfb912490545c0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205115"
---
# <a name="asset-manufacturers-and-models"></a>Eszközgyártók és modellek

[!include [banner](../../includes/banner.md)]

 

Ez a témakör azt mutatja be, hogyan lehet eszközgyártókat és kapcsolódó modelleket beállítani az Eszközkezelés modulban. A modellek az eszköztípusokhoz kapcsolhatók.

## <a name="set-up-product-model-relations"></a>Termék-modell kapcsolatok beállítása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Gyártó és modell** lehetőséget.
2. Válassza ki az **Új** lehetőséget egy új termék létrehozásához.
3. Az **Gyártó** mezőben adja meg az eszközgyártó nevét.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A **Modellek** gyorslap **Hozzáadás** elemét választva hozzon létre egy eszközmodellt, amely az eszköz gyártójához kapcsolódik.
6. A **Modell** mezőben adja meg az eszközmodell nevét.
7. Adjon meg egy leírást a **Leírás** mezőben.
8. Az **Eszköztípus** mezőben válassza ki az eszköztípust, amelyhez a gyártómodell kapcsolódjon.

    > [!NOTE]
    > Az **Eszköztípusok** keresésben beállíthat eszköztípusok, gyártók és modellek közti kapcsolatokat. További tudnivalókért lásd: [Eszköztípusok](../setup-for-objects/object-types.md).

    A **Részletek** gyorslapon a **Modellek** mezőben látható a kiválasztott eszközgyártónál beállított eszközmodellek száma. Az **Eszközök** mező a kiválasztott gyártó által használt eszközök számát jeleníti meg.
    
    Az **Eszközök** mező a kiválasztott gyártói modell által használt objektumok számát jeleníti meg.

> [!NOTE]
> Egy eszköztípus nem rendelkezhet eszközgyártó-modell kapcsolatokkal, kapcsolódhat az egyik eszközgyártói modellhez, vagy több eszközgyártói modellhez. Ha egy eszköztípus legalább egy gyártó modelljéhez kapcsolódik, akkor csak a **Gyártói modell** keresésben megadott kombinációk közül lehet választani azokon az Eszközkezelési oldalakon, ahol az eszköztípus, gyártó és modell kombinációi beállíthatók. Ezek a lapok tartalmazzák az **Összes eszköz**, **Eszköz szolgáltatási szintje**, **Alapértelmezett feladattípusok** és **Karbantartási költségvetés sorai** mezőket. Ha bizonyos típusú eszközök nem kapcsolódnak egyik gyártói modellhez sem, akkor csak ezek az eszköztípusok, valamint az eszköztípusokhoz nem kapcsolódó gyártói modellek jelennek meg az oldalakon.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Egy tárgy gyártójának és modelljének kiválasztása

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget.
2. Az **Eszköz** oszlopban válassza ki az eszköz hivatkozását. Megjelenik a **Részletek** oldal.
3. Válassza ki a **Szerkesztés** opciót.
4. Az **Általános** gyorslapon válassza ki a **Gyártó** és **Modell** mezők értékeit.
