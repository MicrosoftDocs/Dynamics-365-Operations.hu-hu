---
title: Potenciális készpénzre váltás
description: Ez a cikk áttekintést nyújt a potenciális vevő és Dynamics 365 Supply Chain Management a Dynamics 365 értékesítés közötti készpénzes megoldásról.
author: Henrikan
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ea07b40c0a1a7eae7cd167f46796556b1e0ecc46
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103594"
---
# <a name="prospect-to-cash"></a>A potenciális vevők készpénzre váltása

[!include [banner](../includes/banner.md)]

A Potenciális vevők készpénzre váltás megoldás közvetlen szinkronizálást nyújt a Dynamics 365 Supply Chain Management és a Dynamics 365 Sales között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását. Miközben az adatok áramlanak, Ön értékesítési és marketingtevékenységeket végezhet a Sales programban, illetve kezelheti a megrendelések teljesítését a Supply Chain Management készletkezelésének használatával. 

A potenciális ügyfelek készpénzre váltásának integrációjával kapcsolatos további tájékoztatáshoz nézze meg a rövid YouTube-videót: [Potenciális ügyfél készpénzre váltása](https://www.youtube.com/watch?v=AVV9x5x-XCg).

A jelenlegi verzióban A potenciális ügyfelek készpénzre váltása megoldás a következő típusú közvetlen szinkronizálást biztosítja:

- [A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre](accounts-template-mapping-direct.md)
- [A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre](products-template-mapping-direct.md)
- [A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)
- [Értékesítésiajánlat-fejlécek és -sorok szinkronizálása közvetlenül a Sales szolgáltatásból a Supply Chain Management szolgáltatásba](sales-quotation-template-mapping-sales-fin.md)
- [Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között](sales-order-template-mapping-direct-two-ways.md)
- [Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>A Supply Chain Management rendszerkövetelményei
A potenciális ügyfelek készpénzre váltásának integrációja a következő verziókban támogatott:

### <a name="microsoft-dynamics-365-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 Pénzügy és műveletek, Enterprise kiadás 7.3 (2017. december)

- Dynamics 365 Pénzügy és Műveletek, Enterprise kiadás (2017. december) – az alkalmazás build 7.3.11971.56116 Platform Update 12 (7.0.4709.41129)

### <a name="dynamics-365-finance-enterprise-edition-july-2017"></a>Dynamics 365 Pénzügy, Enterprise kiadás (2017. július)

- Dynamics 365 Pénzügy és Műveletek, Enterprise kiadás (2017. július) – a 8. verziófrissítéssel (az alkalmazás buildszáma 7.2.11792.56024 platform build 7.0.4565.16212).
- A következők gyorsjavítások szükségesek:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Sales rendszerből a Supply Chain Management alkalmazásba. Ezenkívül számos más fejlesztést is biztosít.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés sor szinkronizálását az adatintegrációs szolgáltatással a Supply Chain Management alkalmazásból a Sales rendszerbe.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Ez a gyorsjavítás lehetővé teszi az értékesítési rendelés szinkronizálását az adatintegrációs szolgáltatással a Supply Chain Management alkalmazásból a Sales rendszerbe.

    > [!NOTE]
    > Csak a KB4045570-et kell telepíteni, mivel a telepítés tartalmazza a többi gyorsjavítás változásait. 

### <a name="dynamics-365-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 Pénzügy és Műveletek, 1611-es verzió (2016 november)

- Dynamics 365 Pénzügy és Műveletek, 1611 (2016 november) 8-as vagy újabb platformfrissítéssel

- A következők gyorsjavítások szükségesek:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - lehetővé teszi az értékesítési rendelések szinkronizálását az adatintegrációs szolgáltatással a Supply Chain Management rendszerből a Sales alkalmazásba. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - lehetővé teszi az értékesítési rendelések fejlécének és sorának szinkronizálását az adatintegrációs szolgáltatással a Supply Chain Management rendszerből a Sales alkalmazásba.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - A potenciális ügyfelek készpénzre váltása támogatása szükséges adatentitások révén.
    
    > [!NOTE]
    > A gyorsjavítások telepítése után a következő kötegelt munkát kell aktiválnia a **SalesPopulateProspectToCash** űrlapról. Ez az űrlap el van rejtve, mivel csak egyszer van rá szükség. A képernyő eléréséhez jelentkezzen be a környezetbe, és adja hozzá a böngésző címéhez a következőket: *&mi=action:SalesPopulateProspectToCash*, például, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Az űrlap megnyílásakor kattintson az OK lehetőségre. Ez egyedi értékekkel tölt ki egy új **LineCreationSequnceNumber** mezőt a **SalesLine**, **SalesQuotationLine** és **CustInvoiceTrans** táblákban, és frissíti a terméklistát. Ez a potenciális ügyfél készpénzre váltása integráció működéséhez szükség.


## <a name="system-requirements-for-sales"></a>A Sales rendszerkövetelményei

A Potenciális ügyfelek készpénzre váltása megoldás használatához telepítenie kell a következő összetevőket:

- Dynamics 365 Sales, verzió: 1612 (8.2.1.207) (DB 8.2.1.207) online vagy későbbi verzió.
- A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 Sales szolgáltatáshoz, 1.15.0.0 vagy későbbi verzió. A megoldás letölthető az AppSource felületéről. [Töltse le a Dynamics 365, potenciális vevő készpénzfizetési](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
