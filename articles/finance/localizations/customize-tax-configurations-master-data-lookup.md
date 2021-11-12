---
title: Adókonfigurációk testreszabása az alapadatok kereséséhez
description: Ez a témakör bemutatja, hogyan lehet testreszabni az adókonfigurációkat az alapadat-keresési funkció kiterjesztése érdekében.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 498201d5c0377058e86b25953ebbe401ae1af9e3
ms.sourcegitcommit: ed43ceae9b2ef3f616b81127bcf4c4b0862e23f5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2021
ms.locfileid: "7714880"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Adókonfigurációk testreszabása az alapadatok kereséséhez

[!include [banner](../includes/banner.md)]

Kövesse az alábbi lépéseket, hogy testreszabja az adókonfigurációkat az alapadat-keresési funkció kiterjesztése érdekében.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>A Microsoft által biztosított adókonfiguráció importálása

1. A Regulatory Configuration Service (RCS) az **Elektronikus jelentés** munkaterületen válassza ki a **Microsoft** konfigurációs szolgáltatót.
2. Válassza ki a **Tárházak** lehetőséget.
3. Válassza ki a **Globális**, majd a **Megnyitás** lehetőséget.
4. Válasszon egy adókonfigurációt (például **Adószámítási konfiguráció**), ezután válasszon egy verziót a **Verziók** lapon.
5. Válassza az **Importálás** lehetőséget.

> [!NOTE]
> A Dataverse modellleképezés alapértelmezés szerint importálva van. Ha a konfiguráció importálási folyamata során figyelmeztető üzeneteket kap, engedélyezze a virtuális entitásokat a Dataverse-ben. További tudnivalókért lásd: [A Dataverse Virtuális entitások engedélyezése](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Testreszabott adatmodell-konfiguráció létrehozása

1. Az **Elektronikus jelentés** munkaterületen válassza ki az **Adókonfigurációk** elemet, majd válassza ki a kibővíteni kívánt adatmodell-konfigurációt. Például válassza ki az **Adószámítás adatmodellt**.
2. Válassza a **Konfiguráció létrehozása** lehetőséget.
3. Válassza ki a **Adóköteles dokumentummodell származtatva névből: Számítási adatmodell - Microsoft** lehetőséget.
4. A **Név** mezőben írja be a **Testreszabási adatmodell** szöveget.
5. Válassza a **Konfiguráció létrehozása** lehetőséget.

## <a name="create-customized-reference-models"></a>Testreszabott hivatkozási modellek létrehozása

1. Az **Adókonfigurációk** lapon válassza a **Testreszabási adatmodellt**, majd a **Tervező** lehetőséget.
2. Válassza ki a modulhoz tartozó három pont gombot (**…**), majd válassza a **Referenciamodell** nézetet.

    [![Referenciamodell.](./media/pic2.png)](./media/pic2.png)

3. Testreszabott hivatkozási modell létrehozása. Az testreszabott modell gyökérmodell. A testreszabott entitás egy rekordlista. Az testreszabott mező egy sztringmező, amely a keresésben használható. Igény szerint hozzáadhat további mezőket.
4. Válassza ki a modulhoz tartozó három pont gombot (**…**), majd válassza a **Adóköteles dokumentum** nézetet.
5. Válassza ki az testreszabott hivatkozási modellhez kötni kívánt attribútumot. Például válassza a **Testreszabott attribútum** lehetőséget, majd hajtsa végre a következő lépéseket:

    1. Válassza **A referenciamodell kiválasztása** lehetőséget.
    2. Válassza a **Testreszabott modell** lehetőséget, majd kattintson az **OK** gombra. A referencia modell neve a **Természetes kulcs** mező értékével frissül.

        [![Válassza ki a hivatkozási modellt párbeszédpanel.](./media/pic5.png)](./media/pic5.png)

    3. Válassza a **Mentés** parancsot, majd válassza a **Kész** elemet.

## <a name="create-a-customized-model-mapping-configuration"></a>Testreszabott modell-leképezés-konfiguráció létrehozása

1. Az **Elektronikus jelentés** munkaterületen válassza ki az **Adókonfigurációk** elemet, majd válassza ki a **Dataverse modell-leképezés** konfigurációt.
2. Válassza a **Nem** lehetőséget a **Modell-leképezés alapértelmezett értéke** mezőben.
3. Válassza a **Konfiguráció létrehozása** lehetőséget.
4. Válassza ki a **Adóköteles dokumentummodell leképezése származtatva névből: Dataverse Modell-leképezés - Microsoft** lehetőséget.
5. A **Név** mezőben írja be a **Testreszabási adatmodell-leképezés** szöveget.
6. A **Célmodell mezőben** válassza ki a **Testreszabási adatmodell** adatmodellt.
7. Válassza a **Konfiguráció létrehozása** lehetőséget.

    [![Konfiguráció létrehozása legördülő párbeszédpanel.](./media/pic6.png)](./media/pic6.png)

8. Válassza a **Testreszabási modell leképezése** lehetőséget, és állítsa be a **Csatlakoztatott alkalmazás** mezőt arra a kapcsolatra, amelyet a 8. [Alapadat-keresés környezetének beállítása](tax-service-set-up-environment-master-data-lookup.md) lépésben hozott létre.
9. Állítsa az **Alapértelmezett a modell-hozzárendeléshez** mezőt **Igen** értékre.

## <a name="create-customized-model-mappings"></a>Testreszabott modellleképezések létrehozása

1. Az **Adókonfigurációk** lapon válassza a **Testreszabási modell-leképezés** lehetőséget.
2. Válassza a **Tervező** lehetőséget, majd a **Testreszabási** modell lehetőséget.

    [![Testreszabási modell](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Modellleképezés leképezése Dataverse-entitásra

1. Az **Modell-leképezés tervező** lapon válassza a **Testreszabási modell**, majd a **Tervező** lehetőséget.
2. Az **Adatforrástípusok** fán válassza a **Dataverse-tábla** lehetőséget.
3. Az **Adatforrások** lapon válassza a **Gyökér hozzáadása** elemet.
4. A **Név** mezőbe írja be a **Testreszabott Dataverse** értéket.
5. A második **Név** mezőben válasszon ki egy entitást.
6. Válassza ki az **OK** lehetőséget.

    [![A tábla adatforrás-tulajdonságok párbeszédpanele.](./media/pic9.png)](./media/pic9.png)

7. Válassza a **Testreszabott Dataverse** és a **Testreszabott entitás** elemeket, majd a **Kötés** lehetőséget.

    [![Testreszabott Dataverse és testreszabott entitás kötése.](./media/pic10.png)](./media/pic10.png)

8. Válassza a **Testreszabott Dataverse** és a **Testreszabott mező** alatt válasszon egy mezőt, majd a **Kötés** lehetőséget.

    [![Testreszabott Dataverse és testreszabott mező kötése.](./media/pic11.png)](./media/pic11.png)

9. Válassza a **Mentés** parancsot, majd válassza a **Kész** elemet.

## <a name="create-a-customized-tax-configuration"></a>Testreszabott adókonfiguráció létrehozása

1. Az **Elektronikus jelentés** munkaterületen válassza ki az **Adókonfigurációk** elemet, majd válassza ki az **Adószámítási konfiguráció** elemet.
2. Válassza a **Konfiguráció létrehozása** lehetőséget.
3. Válassza ki az **Adószolgáltatás-konfiguráció származtatva névből: Adószámítás konfiguráció - Microsoft** lehetőséget.
4. A **Név** mezőben írja be a **Testreszabási konfiguráció** szöveget.
5. Válassza a **Konfiguráció létrehozása** lehetőséget.
6. Válassza a **Testreszabási konfiguráció** lehetőséget, majd a **Tervező** lehetőséget.
7. Az **Adatmodell** mezőben válassza a **Testreszabási adatmodell** lehetőséget.
8. Az **Adatmodell verzió** mezőben válassza ki a kapcsolódó adóadat-modell verziót.

    [![Tulajdonságok szakasz.](./media/pic13.png)](./media/pic13.png)

9. Válassza a **Kész** lehetőséget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
