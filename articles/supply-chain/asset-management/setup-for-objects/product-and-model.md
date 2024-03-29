---
title: Eszközgyártók és modellek
description: Ez a cikk bemutatja, hogy hogyan lehet beállítani az eszköz gyártókat és a kapcsolódó modelleket az Eszközkezelésben.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b00cb62926f3a482ec655235b6e2f5880edbcd04
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016275"
---
# <a name="asset-manufacturers-and-models"></a>Eszközgyártók és modellek

[!include [banner](../../includes/banner.md)]

 

Ez a cikk bemutatja, hogy hogyan lehet beállítani az eszköz gyártókat és a kapcsolódó modelleket az Eszközkezelésben. A modellek az eszköztípusokhoz kapcsolhatók.

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

1. Válassza ki **az Eszközkezelés**\> **_– Összes_*\>**eszköz lehetőséget**.
2. Az **Eszköz** oszlopban válassza ki az eszköz hivatkozását. Megjelenik a **Részletek** oldal.
3. Válassza ki a **Szerkesztés** opciót.
4. Az **Általános** gyorslapon válassza ki a **Gyártó** és **Modell** mezők értékeit.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]