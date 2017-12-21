---
title: "A potenciális ügyfelek készpénzre váltása"
description: "Ez a témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition és a Microsoft Dynamics 365 for Sales szolgáltatásokban."
author: ChristianRytt
manager: AnnBe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 788e64476094e84eb4d438890776306c05b20582
ms.openlocfilehash: 762699cf68ec8a9df5db20d7dd33bc9248f0a36e
ms.contentlocale: hu-hu
ms.lasthandoff: 12/11/2017

---

# <a name="prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása

[!include[banner](../includes/banner.md)]

A potenciális ügyfelek készpénzre váltása megoldás közvetlen szinkronizálást biztosít a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition és a Microsoft Dynamics 365 for Sales között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésének használatával.

A jelenlegi verzióban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú közvetlen szinkronizálást biztosítja:

- [Sales-fiókok fenntartása és azok szinkronizálása közvetlenül a Sales-től a Finance and Operations szolgáltatással](accounts-template-mapping-direct.md)
- [Termékek fenntartása és azok közvetlen szinkronizálása a Finance and Operations és a Sales szolgáltatás között](products-template-mapping-direct.md)
- [A Sales-kapcsolatok karbantartása és közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)
- [Értékesítési ajánlat szinkronizálása közvetlenül a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping-sales-fin.md)
- [Vevői rendelések szinkronizálása közvetlenül a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping-direct.md)
- [Értékelési rendelések szinkronizálása közvetlenül a Sales és a Finance and Operations között](sales-order-template-mapping-direct-two-ways.md)
- [Értékesítési számla szinkronizálása közvetlenül a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)

A korábbi verziókban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú nem közvetlen szinkronizálásokat biztosította:

- [Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással](accounts-template-mapping.md)
- [Sales-kapcsolattartók fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással](contacts-template-mapping.md)
- [Termékek fenntartása és azok szinkronizálása a Finance and Operations és a Sales szolgáltatás között](products-template-mapping.md)
- [Értékesítési ajánlatok létrehozása a Sales-ben és azok szinkronizálása a Finance and Operations szolgáltatással](sales-quotation-template-mapping.md)
- [Értékesítési ajánlatok létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással](sales-order-template-mapping.md)
- [Értékesítési számlák létrehozása a Finance and Operationsben és azok szinkronizálása a Sales szolgáltatással](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez

A Potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következő összetevőket:

### <a name="july-2017"></a>július 2017. 

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (2017. július) with 8-as platformfrissítéssel (alkalmazás buildszáma 7.2.11792.56024, platform buildszáma 7.0.4565.16212)
- A következő gyorsjavítások a Finance and Operations rendszerhez:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Sales rendszerből a Finance and Operations alkalmazásba. Ezenkívül számos más fejlesztést is biztosít.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítésirendelés-sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.

    > [!NOTE]
    > Csak a KB4045570-et kell telepíteni, mivel a telepítés tartalmazza a Microsoft Tudásbázis (KB) többi cikkének változásait.

### <a name="november-2016-version-1611"></a>2016. november (1611-es verzió)

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (2016. november) 8-as vagy újabb platformfrissítéssel

- A következő gyorsjavítások a Finance and Operations rendszerhez:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - lehetővé teszi az értékesítési rendelések szinkronizálását az adatintegrációs szolgáltatással a Microsoft Dynamics 365 for Finance and Operations rendszerből a Sales alkalmazásba. 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - lehetővé teszi az értékesítési rendelési fejlécek és sorok szinkronizálását az adatintegrációs szolgáltatással a Microsoft Dynamics 365 for Finance and Operations rendszerből a Sales alkalmazásba.
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - A potenciális ügyfelek készpénzre váltása támogatása szükséges adatentitások révén
    
    > [!NOTE]
    > A gyorsjavítások telepítése után a következő kötegelt munkát kell aktiválnia a SalesPopulateProspectToCash űrlapról. Ez az űrlap el van rejtve, mivel csak egyszer van rá szükség. Az eléréséhez adja hozzá a böngésző címéhez a következőket, amikor bejelentkezik a környezetbe: &mi=action:SalesPopulateProspectToCash - pl. https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash A megnyíló űrlapon kattintson az OK gombra.
    Ez egyedi értékekkel tölt ki egy új „LineCreationSequnceNumber” mezőt a „SalesLine”, „SalesQuotationLine” és „CustInvoiceTrans” táblákban, és frissíti a terméklistát. Ez szükséges ahhoz, hogy a P2C-integráció működjön a 7.1 verzión


## <a name="system-requirements-for-sales"></a>A Sales rendszerkövetelményei

A Potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következő összetevőket:

- Microsoft Dynamics 365 for Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online
- A potenciális ügyfelek készpénzre váltása megoldás Microsoft Dynamics 365 for Sales szolgáltatáshoz, 1.15.0.0 (v15) 

   > [!NOTE]
   >
   > Az 1.0.0.0 és 1.0.0.1 verziójú sablonok támogatottak Microsoft Dynamics 365 for Sales rendszerhez tartozó A potenciális ügyfelek készpénzre váltása szolgáltatás 1.14.1.0 verziójánál
   >
   > Az 2.0.0.0 és 2.1.0.0 verziójú sablonok támogatottak Microsoft Dynamics 365 for Sales rendszerhez tartozó A potenciális ügyfelek készpénzre váltása szolgáltatás 1.15.0.0 verziójánál

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Salesbe

1. Töltse le a [A potenciális ügyfelek készpénzre váltása Dynamics 365 for Saleshez megoldás csomagolt zip-fájlját](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) a CustomerSource-ról.
2. Ellenőrizze, hogy a zip-fájl zárolatlan. Ellenkező esetben a megoldási csomag telepítésekor a következő hibaüzenet jelenik meg: „Nem található importálási csomag”. A zip-fájl zárolásának feloldásához kattintson rá a jobb gombbal, majd válassza a **Tulajdonságok** elemet. Ezután válassza a **Blokkolás feloldása** lehetőséget.
3. Bontsa ki, majd futtassa a **PackageDeployer.exe** fájlt.
4. Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Sales-példányba:

    1. Válassza az **Office 365** telepítési típust.
    2. Válassza a **Speciális megjelenítése** lehetőséget.
    3. A gyors telepítéshez válasszon régiót. Ha a **Nem tudom** lehetőséget választja, a rendszer az összes régiót végigkeresi, és a telepítés hosszabb ideig tart.
    4. Adja meg egy olyan adminisztrátori felhasználó felhasználónevét és jelszavát, aki telepítési felhasználói jogosultságokkal rendelkezik.

