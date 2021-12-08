---
title: Alapadat-keresés engedélyezése adószámítási konfigurációhoz
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani és engedélyezni az adószámítási alapadat-keresési funkciót.
author: kai-cloud
ms.date: 11/22/2021
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
ms.openlocfilehash: 455e8becfdfa910a3733719653e1a91557b2f59a
ms.sourcegitcommit: ac23a0a1f0cc16409aab629fba97dac281cdfafb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2021
ms.locfileid: "7867352"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Alapadat-keresés engedélyezése adószámítási konfigurációhoz 

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet beállítani és engedélyezni az adószámítási alapadat-keresési funkciót. Az adószámítási konfigurációban az olyan mezők értékeit lehet kiválasztani, mint a jogi személy, a szállítókód, a cikk kódja és a **Szállítási** feltételek **legördülő** **·** **lista**. Ezek az értékek a Microsoft által csatlakoztatott Dynamics 365 Finance környezetből, az Microsoft Dataverse adatforrás használatával jönnek létre.

> [!NOTE] 
> Az adószámítási alapadat-keresési funkció nem kötelező funkció. Ha letiltja a Tax Service adatforrás-támogatási szolgáltatását az RCS (Regulatory Configuration Service) szolgáltatásban, a következő lépéseket **Dataverse** kihagyhatja. Ebben az esetben azonban az adószámítási konfigurációban nem lesz elérhető a legördülő lista.

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
