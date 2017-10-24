---
title: "A potenciális ügyfelek készpénzre váltása"
description: "A témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Sales szolgáltatásokban."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása  

[!include[banner](../includes/banner.md)]

A potenciális ügyfelek készpénzre váltása megoldás az [Adatintegráció](/common-data-service/entity-reference/dynamics-365-integration) segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Sales példányai között a Common Data Service (CDS) környezetben. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésével. 

Ez a megoldás integrációt nyújt az alábbi területeken: 

-   [Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással](accounts-template-mapping.md)
-   [Sales-kapcsolattartók fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással](contacts-template-mapping.md)
-   [Termékek fenntartása és azok szinkronizálása a Finance and Operations és a Sales szolgáltatás között](products-template-mapping.md)
-   [Értékesítési ajánlatok létrehozása a Sales-ben és azok szinkronizálása a Finance and Operations szolgáltatással](sales-quotation-template-mapping.md)
-   [Értékesítési ajánlatok létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással](sales-order-template-mapping.md)
-   [Értékesítési számlák létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>A Dynamics 365 for Finance and Operations, Enterprise edition rendszerigénye

A potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következőket:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (2017. július) with 8-as platformfrissítéssel (alkalmazás 7.2.11792.56024, platform 7.0.4565.16212)

- Két gyorsjavítás a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerhez (2017. július).

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelési sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations programból a Salesbe.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations programból a Salesbe.
    
**Megjegyzés:**: csak a KB4036524-et kell telepíteni, mivel a telepítés tartalmazza a KB4036461 változásait.
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>A Dynamics 365 for Sales rendszerkövetelményei

A potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következőket:

- Dynamics 365 for Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online vagy későbbi.
- A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 for Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Salesbe

- Töltse le a [A potenciális ügyfelek készpénzre váltása Dynamics 365 for Saleshez megoldás csomagolt zip-fájlját](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) a CustomerSource-ról.

- Győződjön meg arról, hogy a zip-fájl feloldott, és nem kapja meg az „Importálási csomagok nem találhatók” hibaüzenetet a megoldáscsomag telepítésekor. A fájl feloldásához tegye a következőket:

    -  Kattintson jobb gombbal a fájlra.
    -  Válassza ki **Tulajdonságok** majd a **Feloldás** lehetőséget. 

- Bontsa ki, majd futtassa a PackageDeployer.exe fájlt.

- Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Sales-példányba.

    - Válassza az **Office 365** telepítési típust.
    - Válassza a **Speciális megjelenítése** lehetőséget.
    - Gyors telepítéshez válassza a **Régió** elemet. Ha a **Nem tudom** lehetőséget választja, a rendszer az összes régiót válasszagigkeresi, és a telepítés hosszabb ideig tart.
    - Adja meg egy olyan adminisztrátori felhasználó **Felhasználónevét** és **Jelszavát**, aki telepítési felhasználói jogosultságokkal rendelkezik.

