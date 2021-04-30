---
title: Alapadat-keresés környezetének beállítása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.
author: kai-cloud
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869070"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Alapadat-keresés környezetének beállítása

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet beállítani a környezetet az adószámítási alapadat-keresési funkció használatához.

1. A Power Platform integráció beállítása a Lifecycle Services (LCS) szolgáltatásban. További informáciért lásd: [Microsoft Power Platform integráció – Bővítmények áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Dynamics 365 Finance és Microsoft Dataverse beállítása. A további tudnivalókat lásd [A megoldás beszerzése](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution), valamint [Hitelesítés és engedélyezés ](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Importálja az *Előfeltétel-adó szolgáltatás virtuális entitás megoldást* az [Adószolgáltatás virtuális entitásból](https://go.microsoft.com/fwlink/?linkid=2158160).
4. A Dynamics 365 Regulatory Configuration Service (RCS) beállítása. 
5. Szolgáltatáskérés létrehozása a Microsoft számára a következő funkciók tesztelésének engedélyezéséhez:

      - ERCdsFeature
      - TaxServiceCDSFeature

6. Engedélyezze a következő funkciót a **Funkció kezelése** munkaterületen a Finance megoldásban:

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
