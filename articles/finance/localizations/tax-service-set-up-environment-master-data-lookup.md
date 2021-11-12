---
title: Alapadat-keresés környezetének beállítása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.
author: kai-cloud
ms.date: 10/26/2021
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
ms.openlocfilehash: 901f8bcb0220355866952b68e92bc2dd906bb430
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700404"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Alapadat-keresés környezetének beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.

1. A Microsoft Power Platform integráció beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban. További informáciért lásd: [Microsoft Power Platform integráció – Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). A lépés befejezése után a Microsoft Power Platform környezet neve megjelenik a **Power Platform Integráció** szakaszban.
2. Menjen a [Microsoft Power Platform felügyeleti központba](https://admin.powerplatform.microsoft.com/environments), és válassza ki a környezet nevét. A környezet URL-címe meg van adva.
3. Dynamics 365 Finance és Dataverse beállítása. A további tudnivalókat lásd [A virtuális entitás megoldás beszerzése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution), valamint [Hitelesítés és engedélyezés](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Állítsa be a következő entitásokat: További tudnivalókért lásd: [A Microsoft Dataverse Virtuális entitások engedélyezése](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCityEntity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity

5. A Regulatory Configuration Service (RCS) beállítása. Nyissa meg a **Funkciókezelés** munkaterületet, és engedélyezze a következő funkciókat:

    - Elektronikus jelentés Dataverse-adatforrások támogatása
    - Adószolgáltatás Dataverse-adatforrásainak támogatása
    - Globalizációs funkciók

6. Jelentkezzen be az RCS-be bérlői rendszergazdai fiók használatával.
7. Ugrás az **Elektronikus jelentéskészítés** > **Kapcsolódó alkalmazások** elemhez. 
8. Rekord hozzáadásához válassza az **Új** lehetőséget, és adja meg a következő mezőadatokat. 

    - A **Név** mezőben adjon meg egy nevet.
    - A **Típus** mezőben válassza ki a **Dataverse** lehetőséget.
    - Az **Alkalmazás** mezőbe írja az Dataverse URL-címét.
    - A **Bérlő** mezőben adja meg a bérlőt.
    - Az **Egyéni URL-cím** mezőben adja meg az Dataverse URL-címet, és fűzze hozzá az "/api/data/v9.1" szöveghez.

9. Válassza a **Kapcsolat ellenőrzése** lehetőséget, és fejezze be a kapcsolódási folyamatot. 

    [![Kapcsolat ellenőrzése gomb.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Ugrás az **Elektronikus jelentés** > **Adókonfigurációk** elemhez, és importálja az adókonfigurációkat az [Adókonfigurációk](https://go.microsoft.com/fwlink/?linkid=2158352) elemből.

    [![Adókonfigurációs oldal, adóadatmodellfa.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Ha Microsoft-konfigurációt használ, lépjen az **Adóköteles dokumentummodell-hozzárendelés** vagy a **Dataverse modellleképezés** elemhez, és a **Kapcsolódó alkalmazás** mezőben válassza ki a 7. lépésben létrehozott rekordot.
12. Állítsa az **Alapértelmezett modell-hozzárendelés** beállítást **Igen** értékre.

    [![Modell-leképezés oldal.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
