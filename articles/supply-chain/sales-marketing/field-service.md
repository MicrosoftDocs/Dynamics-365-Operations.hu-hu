---
title: A Microsoft Dynamics 365 Field Service integráció áttekintése
description: Ez a témakör a Microsoft Dynamics 365 Field Service szolgáltatással való integrációról nyújt áttekintést.
author: ChristianRytt
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
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
ms.openlocfilehash: 2a5c3e49f09bf4f1f90449db10d439f563ecc2c0
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249839"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>A Microsoft Dynamics 365 Field Service integráció áttekintése

[!include[banner](../includes/banner.md)]

A Supply Chain Management lehetővé teszi az üzleti folyamatok szinkronizálását a Dynamics 365 Supply Chain Management és a Dynamics 365 Field Service között Az integrációs forgatókönyvek konfigurálása bővíthető adatintegrációs sablonok és a Common Data Service (CDS) segítségével történik az üzleti folyamatok szinkronizálása érdekében.
Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és az üzleti igények teljesítésére. 

A field service integráció a meglévő Potenciális vevő készpénzre váltása funkcióra épül.

![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/field-service-integration.png)

A Field Service és a Supply Chain Management közötti integráció első fázisa a Field Service szolgáltatásban lévő munkarendelések és szerződések a Supply Chain Management szolgáltatásban történő számlázásának lehetővé tételére irányul. A támogatott forgalom a Field Service-ben kezdődik, ahol a munkarendelésekből származó információk értékesítési rendelésekként szinkronizálódnak a Supply Chain Management szolgáltatásba. A Supply Chain Management megoldásban az értékesítési rendelések számlázása a számlázási dokumentumokat generálásához történik. Emellett a Field Service-ben lévő szerződéses számlákban lévő információk szinkronizálódnak a Supply Chain Management szolgáltatásba. A Microsoft Dynamics 365 adatintegrátor testreszabható projektek használatával szinkronizálja az adatokat. Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és speciális követelmények teljesítésére.

A Field Service és a Supply Chain Management közötti integráció első fázisa a következő elemek szinkronizálását teszi lehetővé:

- [Termékek a Supply Chain Management szolgáltatásból termékekké a Field Service szolgáltatásban, amelyek terméktípus-információkat tartalmaznak](field-service-product.md)
- [A Field Service szolgáltatásokban lévő munkarendelések és a Supply Chain Management értékesítési rendelései](field-service-work-order.md)
- [Supply Chain Management-számlák Field Service szabadszöveges számlákká](field-service-invoice.md)

A Field Service és a Supply Chain Management közötti szinkronizálás példamódjának megtekintéséhez tekintse meg a rövid YouTube videót: [Munkarendelések szinkronizálása a Microsoft Dynamics 365 integrációval](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Integráció a Field Service szolgáltatással, beleértve a készlet- és a projektadatokat

A második fázisban a további funkciók célja, hogy a szerviztechnikusok betekintést kapjanak a készletinformációkba a Supply Chain Management alkalmazásban, így lehetőségük legyen a készletszintek frissítése és anyagmozgatásra. Ezenkívül az eladott áruk karbantartásával és telepítésével foglalkozó vállalatok számára előnyt jelent az, hogy jobban kezelhetik a teljes értékesítési és szervizfolyamatot, illetve rálátást kapnak arra a projektintegrációnak köszönhetően.

### <a name="functionality-includes-integration-of"></a>Funkciók között a következő integrációk szerepelnek:
- Raktárinformációk
- Aktuálisan készlettel kapcsolatos információk
- Készletátvitelek
- Készlethelyesbítések
- Supply Chain Management projektek összekapcsolva a Dynamics 365 Field Service munkarendelésekkel
- A Dynamics 365 Field Service munkarendelések, amelyek hivatkozással rendelkeznek Supply Chain Management projektekre, alkalmazzák ezt a projektszámot az értékesítési rendelésre, amelyek így számlázhatók a projektből. 

![Üzleti folyamatok szinkronizálása a Supply Chain Management és a Field Service között](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>A Field Service és a Supply Chain Management közötti integráció második fázisa a következő sablonokkal történő szinkronizálást teszi lehetővé:
- Raktárak (Supply Chain Management – Field Service) – Raktárak a Supply Chain Management és és a Field Service között [speciális lekérdezés] 
- Termékkészlet (Supply Chain Management – Field Service) – Készletszintű információk a Supply Chain Management és a Field Service között [speciális lekérdezés] 
- Termékkészlet kiigazítás (Field Service – Supply Chain Management) – Készletkiigazítások a Field Service és a Supply Chain Management között [speciális lekérdezés] 
- Készletátvitelek (Field Service – Supply Chain Management) – Készletátvitelek a Field Service és a Supply Chain Management között [speciális lekérdezés] 
- Projektek (Supply Chain Management – Field Service) – Projektlisták a Supply Chain Management és a Field Service között 
- Munkamegrendelések projekttel (Field Service – Supply Chain Management) - Munkarendelések a Field Service alkalmazásból értékelési rendelésekbe a Supply Chain Management alkalmazásba projekttámogatással [Speciális lekérdezés] 
- Filed Srevice termékek készletegységgel(Supply Chain Management – Sales) - Supply Chain Management „Értékesíthető kiadott termékek” a Field Service, Értékesítési „termékeibe” beleértve a raktáregységet is 

## <a name="system-requirements"></a>Rendszerkövetelmények

### <a name="system-requirements-for-supply-chain-management"></a>A Supply Chain Management rendszerkövetelményei
A Field Service integráció a következő verziókat támogatja:

- A Dynamics 365 for Finance and Operations 8.1.2-es verziója (2018. december) 2018. decemberben jelent meg, az alkalmazás buildszáma pedig 8.1.195, valamint 22-es platformfrissítés (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>A Field Service rendszerkövetelményei
A Field Service integrációs megoldás használatához telepítenie kell a következő összetevőket:

- Field Service (8.2.0.286-os verzió) vagy újabb verziója a Dynamics 365 9.1.x – 2018. novemberben kiadott verzióján
- A potenciális ügyfelek készpénzre váltása (P2C) megoldás Dynamics 365 szolgáltatáshoz, 1.15.0.1 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3) felületéről.
- „Field Service Integration, Project and Inventory” megoldás Dynamics 365-höz, 2.0.0.0 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2) felületéről.
