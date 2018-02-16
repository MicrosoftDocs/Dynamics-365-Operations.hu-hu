---
title: "A potenciális ügyfelek készpénzre váltása"
description: "Ez a témakör áttekintést nyújt A potenciális ügyfelek készpénzre váltása megoldásról a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition és a Microsoft Dynamics 365 for Sales szolgáltatásokban."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 602873e8af976c57f27ce53b76391516351755e3
ms.openlocfilehash: 29d33d3ecf97c15fed0247d172ff6fb3bbdaa018
ms.contentlocale: hu-hu
ms.lasthandoff: 01/25/2018

---

# <a name="prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása

[!include[banner](../includes/banner.md)]

A potenciális ügyfelek készpénzre váltása megoldás közvetlen szinkronizálást biztosít a Dynamics 365 for Finance and Operations, Enterprise Edition és a Dynamics 365 for Sales között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésének használatával. 

A potenciális ügyfelek készpénzre váltásának integrációjával kapcsolatos további tájékoztatáshoz nézze meg a rövid YouTube-videót:

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

A jelenlegi verzióban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú közvetlen szinkronizálást biztosítja:

- [Sales-fiókok fenntartása és azok szinkronizálása közvetlenül a Sales-től a Finance and Operations szolgáltatással](accounts-template-mapping-direct.md)
- [Termékek karbantartása a Finance and Operations szolgáltatásban, majd szinkronizálásuk közvetlenül a Sales szolgáltatásba](products-template-mapping-direct.md)
- [Névjegyek karbantartása a Sales szolgáltatásban, majd szinkronizálásuk névjegyekként vagy ügyfelekként közvetlenül a Finance and Operations szolgáltatásba](contacts-template-mapping-direct.md)
- [Értékesítési ajánlatok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba (sablon kiadása függőben)](sales-quotation-template-mapping-sales-fin.md)
- [Értékesítési rendelések közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping-direct.md)
- [Értékesítési rendelések közvetlen szinkronizálása a Sales és a Finance and Operations szolgáltatások között (sablon kiadása függőben)](sales-order-template-mapping-direct-two-ways.md)
- [Értékesítési számla közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)

A korábbi verziókban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú nem közvetlen szinkronizálásokat biztosította:

- [Sales-fiókok fenntartása és azok szinkronizálása a Finance and Operations szolgáltatással](accounts-template-mapping.md)
- [Névjegyek karbantartása a Sales szolgáltatásban, majd szinkronizálásuk a Finance and Operations szolgáltatásba](contacts-template-mapping.md)
- [Termékek karbantartása a Finance and Operations szolgáltatásban, majd szinkronizálásuk a Sales szolgáltatásba](products-template-mapping.md)
- [Értékesítési ajánlatok létrehozása a Sales szolgáltatásban, majd szinkronizálásuk a Finance and Operations szolgáltatásba](sales-quotation-template-mapping.md)
- [Értékesítési rendelések létrehozása a Finance and Operations szolgáltatásban, majd szinkronizálásuk a Sales szolgáltatásba](sales-order-template-mapping.md)
- [Értékesítési számlák létrehozása a Finance and Operations szolgáltatásban, majd szinkronizálásuk a Sales szolgáltatásba](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez

A potenciális ügyfelek készpénzre váltásának integrációja a következő verziókban támogatott:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (2017. december)

- Dynamics 365 for Finance and Operations, Enterprise Edition (2017. december - Alkalmazás buildszáma 7.3.11971.56116, 12-es platformfrissítéssel (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise Edition (2017. július)

- Dynamics 365 for Finance and Operations, Enterprise Edition (2017. július) - 8-as platformfrissítéssel (alkalmazás buildszáma 7.2.11792.56024, platform buildszáma 7.0.4565.16212).
- A következők gyorsjavítások szükségesek:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Sales rendszerből a Finance and Operations alkalmazásba. Ezenkívül számos más fejlesztést is biztosít.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítésirendelés-sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.

    > [!NOTE]
    > Csak a KB4045570-et kell telepíteni, mivel a telepítés tartalmazza a többi gyorsjavítás változásait. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations 1611-es verzió (2016. november)

- Dynamics 365 for Finance and Operations, 1611-es verzió (2016. november) 8-as vagy újabb platformfrissítéssel

- A következők gyorsjavítások szükségesek:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - lehetővé teszi az értékesítési rendelések szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba. 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - lehetővé teszi az értékesítési rendelések fejlécénak és sorainak szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - A potenciális ügyfelek készpénzre váltása támogatása szükséges adatentitások révén.
    
    > [!NOTE]
    > A gyorsjavítások telepítése után a következő kötegelt munkát kell aktiválnia a **SalesPopulateProspectToCash** űrlapról. Ez az űrlap el van rejtve, mivel csak egyszer van rá szükség. Az űrlap eléréséhez jelentkezzen be a környezetbe, és adja hozzá a következőt az URL-címhez a böngésző címsorában: &mi=action:SalesPopulateProspectToCash, for example, https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash. Az űrlap megnyílásakor kattintson az OK lehetőségre. Ez egyedi értékekkel tölt ki egy új **LineCreationSequnceNumber** mezőt a **SalesLine**, **SalesQuotationLine** és **CustInvoiceTrans** táblákban, és frissíti a terméklistát. Ez a potenciális ügyfél készpénzre váltása integráció működéséhez szükség.


## <a name="system-requirements-for-sales"></a>A Sales rendszerkövetelményei

A Potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következő összetevőket:

- Dynamics 365 for Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online
- A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 for Sales szolgáltatáshoz, 1.15.0.0 (v15) 

   > [!NOTE]
   >
   > Az 1.0.0.0 és 1.0.0.1 verziójú sablonok támogatottak Dynamics 365 for Sales rendszerhez tartozó A potenciális ügyfelek készpénzre váltása szolgáltatás 1.14.1.0 verziójánál
   >
   > Az 2.0.0.0 és 2.1.0.0 verziójú sablonok támogatottak Dynamics 365 for Sales rendszerhez tartozó A potenciális ügyfelek készpénzre váltása szolgáltatás 1.15.0.0 verziójánál

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Salesbe

1. Töltse le a [A potenciális ügyfelek készpénzre váltása Dynamics 365 for Saleshez megoldás csomagolt zip-fájlját](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) a CustomerSource-ról.
2. Ellenőrizze, hogy a zip-fájl zárolatlan. Ellenkező esetben a megoldási csomag telepítésekor a következő hibaüzenet jelenhet meg: „Nem található importálási csomag”. A zip-fájl zárolásának feloldásához kattintson rá a jobb gombbal, majd válassza a **Tulajdonságok** elemet. Válassza a **Blokkolás feloldása** lehetőséget.
3. Bontsa ki, majd futtassa a **PackageDeployer.exe** fájlt.
4. Telepítse A potenciális ügyfelek készpénzre váltása megoldást a Sales-példányba:

    1. Válassza az **Office 365** telepítési típust.
    2. Válassza a **Speciális megjelenítése** lehetőséget.
    3. A gyors telepítéshez válasszon régiót. Ha a **Nem tudom** lehetőséget választja, a rendszer az összes régiót végigkeresi, és a telepítés hosszabb ideig tart.
    4. Adja meg egy olyan adminisztrátori felhasználó felhasználónevét és jelszavát, aki telepítési felhasználói jogosultságokkal rendelkezik.



