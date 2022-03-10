---
title: Termékkonfigurációs modell számításai
description: Ez a témakör azt mutatja be, hogyan hozhat létre számításokat attribútumokhoz egy termékkonfigurációs modellben
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 349fed3ca75b94db2f421a1ff3c3553c96c202c37d59857a3d973f3de8f995ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755251"
---
# <a name="product-configuration-model-calculations"></a>Termékkonfigurációs modell számításai

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan hozhat létre számításokat attribútumokhoz egy termékkonfigurációs modellben.

## <a name="prerequisites"></a>Előfeltételek

A számításokkal számíthatók ki egy termékkonfigurációs modellben a termék konfigurációs értékei. A számítások beállításának megkezdése előtt a kapcsolódó termékkonfigurációs modellnek léteznie kell. A konfigurációs modellek beállítási folyamatának és a kapcsolódó feladatoknak az áttekintését [Termékkonfigurációs modell beállítása](set-up-maintain-product-configuration-model.md) témakörben találja.

## <a name="create-a-calculation"></a>Számítások létrehozása

A számítás egy kifejezésből és egy célattribútumból áll. További információért lásd: [Kalkulációk a termékkonfigurációs modellekhez - GYIK](calculate-product-configuration-models.md).

Meglévő termékmodell számításának létrehozásához kövesse az alábbi lépéseket.

1. Lépjen a **Termékinformációk kezelése \> Közös \> Termékkonfigurációs modellek** elemre.
1. Nyisson meg egy termékkonfigurációs modellt, majd válassza a **Szerkesztés** elemet.
1. A **Számítások** gyorslapon válassza a **Hozzáadás** parancsot egy számítás hozzáadásához, majd állítsa be a következő mezőket:

    - **Név** – Adjon meg egy nevet a számításnak.
    - **Leírás** – Adja meg a számítás leírását.
    - **Célattribútum** – Válassza ki azt az attribútumot, amelyhez a számítást végzi.

1. Válassza a **Kifejezés szerkesztése** lehetőséget.
1. A **Számítás megadása** párbeszédpanelben adja hozzá a kifejezéshez a szükséges attribútumokat, operátorokat és értékeket. További tudnivalók ezeknek az elemeknek a kezeléséről: [A termékkonfigurációs modellek kifejezés- és táblamegszorításai](expression-constraints-table-constraints-product-configuration-models.md).
1. Amikor a kifejezés elkészült, válassza az **OK** lehetőséget.

## <a name="calculation-examples"></a>Számítási példák

Ez a szakasz néhány példát mutat be arra, hogyan működnek a számítások.

### <a name="example-1"></a>1. példa

A célattribútum logikai típusú, és a számítás a következő feltételes kifejezést használja:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

A kifejezés *Igaz* értéket ad ki a célattribútumnak, ha a `decimalAttribute2` nagyobb vagy egyenlő a `decimalAttribute1` értékénél. Ellenkező esetben *Hamis* eredményt ad.

### <a name="example-2"></a>2. példa

Ez a példa a `textFixedList` szöveges attribútumot használja célattribútumként. Ez az attribútum a következő rögzített listát tartalmazza.

| Érték | A feloldó érték |
|---|---|
| A | 1a |
| milliárd | 2b |
| K | 2c |

A következő képernyőkép bemutatja, hogy hogyan nézhetnek ki az attribútum beállításai a rendszerben.

![Attribútumtípus-beállítások a 2. példához.](media/model-calculations-example2.png "Attribútumtípus-beállítások a 2. példához")

Az attribútumot a következő feltételes utasítás használja:

`If[integerAttribute < 150, 0, 2]`

Ha az `integerAttribute` értéke kisebb, mint 150, akkor ez az utasítás az *A* rögzített lista első rekordját adja vissza. Ellenkező esetben a *C* rögzített lista harmadik rekordjának szövegértéke szerepel benne.

> [!NOTE]
> A rögzített lista egy nulla alapú felsorolásnak (enum) felel meg, és értékeit a megfelelő egész érték érheti el. Ebből következően az első rögzített listaérték (*A*) a *0*-nak felel meg, a második (*B*) *1* értéknek, a harmadik (*C*) *2* értéknek felel meg.

### <a name="example-3"></a>3. példa

Ez a példa a `textFixedList` célattribútumot használja az előző példából. Másik szöveges attribútumot (`textAttribute`) is használ, amely a következő rögzített listát tartalmazza.

| Érték | A feloldó érték |
|---|---|
| AA | 1aa |
| BB | 2bb |

A következő képernyőkép bemutatja, hogy hogyan nézhetnek ki az attribútum beállításai a rendszerben.

![Attribútumtípus-beállítások a 3. példához.](media/model-calculations-example3.png "Attribútumtípus-beállítások a 3. példához")

A `textFixedList` attribútum értékét a következő feltételes kimutatás használatával számítja ki a program:

`If[textAttribute == "1aa", 0, 2]`

Ha a `textAttribute` értékének feloldási értéke *1aa*, akkor ez a kifejezés az *A* `textFixedList` rögzített lista első rekordját adja vissza. Ellenkező esetben a *C* `textFixedList` rögzített lista harmadik rekordjának szövegértéke szerepel benne.

> [!NOTE]
> - A feltételes utasításnak az attribútum feloldási értékét kell használnia.
> - A számításokban csak rögzített lista szöveges attribútumok használhatók.

## <a name="see-also"></a>Lásd még

- [Kalkulációk a termékkonfigurációs modellekhez - GYIK](calculate-product-configuration-models.md)
- [Kifejezésmegszorítás hozzáadása a termékkonfigurációs modellhez](tasks/add-expression-constraint-product-configuration-model.md)
- [Termékkonfigurálási modellek áttekintése](product-configuration-models.md)
