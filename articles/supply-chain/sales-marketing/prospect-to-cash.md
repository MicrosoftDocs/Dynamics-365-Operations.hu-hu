---
title: A potenciális ügyfelek készpénzre váltása
description: Ez a témakör a Potenciális vevő készpénzre váltása megoldásról a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Sales között megoldásról,nyújt áttekintést.
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b46ece384a28f8e78989253fcf467fbf3feaf1b7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "309495"
---
# <a name="prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása

[!include [banner](../includes/banner.md)]

A Potenciális vevők készpénzre váltás megoldás közvetlen szinkronizálást nyújt a Dynamics 365 for Finance and Operations és a Dynamics 365 for Sales között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. Miközben az adatok áramlanak a Finance and Operations és a Sales között, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Finance and Operations készletkezelésének használatával. 

A potenciális ügyfelek készpénzre váltásának integrációjával kapcsolatos további tájékoztatáshoz nézze meg a rövid YouTube-videót: [Potenciális ügyfél készpénzre váltása](https://www.youtube.com/watch?v=AVV9x5x-XCg).

A jelenlegi verzióban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú közvetlen szinkronizálást biztosítja:

- [Sales-fiókok fenntartása és azok szinkronizálása közvetlenül a Sales-től a Finance and Operations szolgáltatással](accounts-template-mapping-direct.md)
- [Termékek karbantartása a Finance and Operations szolgáltatásban, majd szinkronizálásuk közvetlenül a Sales szolgáltatásba](products-template-mapping-direct.md)
- [Névjegyek karbantartása a Sales szolgáltatásban, majd szinkronizálásuk névjegyekként vagy ügyfelekként közvetlenül a Finance and Operations szolgáltatásba](contacts-template-mapping-direct.md)
- [Értékesítési ajánlat közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping-sales-fin.md)
- [Értékesítési rendelések közvetlen szinkronizálása a Sales és a Finance and Operations szolgáltatások között](sales-order-template-mapping-direct-two-ways.md)
- [Értékesítési számla közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez
A potenciális ügyfelek készpénzre váltásának integrációja a következő verziókban támogatott:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (2017. december)

- Dynamics 365 for Finance and Operations, Enterprise Edition (December 2017) - Alkalmazásbuild 7.3.11971.56116 12-es platformfrissítéssel (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise edition (2017. július)

- Dynamics 365 for Finance and Operations, Enterprise Edition (2017. július) - 8-as platformfrissítéssel (7.2.11792.56024 alkalmazásbuild 7.0.4565.16212 platformbuilddel).
- A következők gyorsjavítások szükségesek:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Sales rendszerből a Finance and Operations alkalmazásba. Ezenkívül számos más fejlesztést is biztosít.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítésirendelés-sor szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.

    > [!NOTE]
    > Csak a KB4045570-et kell telepíteni, mivel a telepítés tartalmazza a többi gyorsjavítás változásait. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations 1611-es verzió (2016 november)

- Dynamics 365 for Finance and Operations 1611 verzió (2016. november) 8-as vagy újabb platformfrissítéssel

- A következők gyorsjavítások szükségesek:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - lehetővé teszi az értékesítési rendelések szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - lehetővé teszi az értékesítési rendelések fejlécénak és sorainak szinkronizálását az adatintegrációs szolgáltatással a Finance and Operations rendszerből a Sales alkalmazásba.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - A potenciális ügyfelek készpénzre váltása támogatása szükséges adatentitások révén.
    
    > [!NOTE]
    > A gyorsjavítások telepítése után a következő kötegelt munkát kell aktiválnia a **SalesPopulateProspectToCash** űrlapról. Ez az űrlap el van rejtve, mivel csak egyszer van rá szükség. A képernyő eléréséhez jelentkezzen be a környezetbe, és adja hozzá a böngésző címéhez a következőket: *&mi=action:SalesPopulateProspectToCash*, például, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Az űrlap megnyílásakor kattintson az OK lehetőségre. Ez egyedi értékekkel tölt ki egy új **LineCreationSequnceNumber** mezőt a **SalesLine**, **SalesQuotationLine** és **CustInvoiceTrans** táblákban, és frissíti a terméklistát. Ez a potenciális ügyfél készpénzre váltása integráció működéséhez szükség.


## <a name="system-requirements-for-sales"></a>A Sales rendszerkövetelményei

A Potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következő összetevőket:

- Dynamics 365 for Sales 1612 verzió (8.2.1.207) (DB 8.2.1.207) online vagy újabb verzió
- A potenciális ügyfelek készpénzre váltása megoldás a Dynamics 365 for Sales 1.15.0.0 vagy későbbi verziójához. A megoldás letölthető az AppSource felületéről. [Töltse le a Dynamics 365, potenciális vevő készpénzfizetési](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
