---
title: Alapadat-keresés környezetének beállítása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.
author: kai-cloud
ms.date: 04/21/2021
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
ms.openlocfilehash: e4aa941c57e8c31793d6db8ae87140cd1bb1a82b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021344"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Alapadat-keresés környezetének beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.

1. A Power Platform integráció beállítása a Lifecycle Services (LCS) szolgáltatásban. További informáciért lásd: [Microsoft Power Platform integráció – Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Dynamics 365 Finance és Microsoft Dataverse beállítása. A további tudnivalókat lásd [A megoldás beszerzése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution), valamint [Hitelesítés és engedélyezés ](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Állítsa be a következő entitásokat: További tudnivalókért lásd: [Virtuális entitások engedélyezése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).
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
4. A Dynamics 365 Regulatory Configuration Service (RCS) beállítása. 
5. Szolgáltatáskérés létrehozása a Microsoft számára a következő funkciók tesztelésének engedélyezéséhez:

      - ERCdsFeature
      - TaxServiceCDSFeature

6. A **Funkció kezelése** munkaterületen engedélyezze a következő funkciókat:

      - (Előnézet) Elektronikus jelentés Dataverse-adatforrások támogatása
      - (Előzetes verzió) Adószolgáltatás Dataverse-adatforrásainak támogatása
      - (előzetes verzió) Globalizációs funkciók

5. Jelentkezzen be az RCS-be bérlői rendszergazdai fiók használatával.
6. Ugrás az **Elektronikus jelentéskészítés** > **Kapcsolódó alkalmazások** elemhez. 
7. Rekord hozzáadásához válassza az **Új** lehetőséget, és adja meg a következő mezőadatokat. 

   - A **Név** mezőben adjon meg egy nevet.
   - A **Típus** mezőben válassza ki a **Dataverse** lehetőséget.
   - Az **Alkalmazás** mezőbe írja az Dataverse URL-címét.
   - A **Bérlő** mezőben adja meg a bérlőt.
   - Az **Egyéni URL-cím** mezőben adja meg az Dataverse URL-címet, és fűzze hozzá az "/api/data/v9.1" szöveghez.

8. Válassza a **Kapcsolat ellenőrzése** lehetőséget, és fejezze be a kapcsolódási folyamatot. 

   [![Kapcsolat ellenőrzése gomb](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Ugrás az **Elektronikus jelentés** > **Adókonfigurációk** elemhez, és importálja az adókonfigurációkat az [Adókonfigurációk](https://go.microsoft.com/fwlink/?linkid=2158352) elemből.

   [![Adókonfigurációs oldal, adóadatmodellfa](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Ha Microsoft-konfigurációt használ, lépjen az **Adóköteles dokumentummodell-hozzárendelés** vagy a **Dataverse modellleképezés** elemhez, és a **Kapcsolódó alkalmazás** mezőben válassza ki a 7. lépésben létrehozott rekordot.
11. Állítsa az **Alapértelmezett modell-hozzárendelés** beállítást **Igen** értékre.

   [![Modell-leképezés oldal](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
