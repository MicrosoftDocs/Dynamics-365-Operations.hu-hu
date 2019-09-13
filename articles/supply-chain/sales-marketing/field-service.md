---
title: A Microsoft Dynamics 365 for Field Service integráció áttekintése
description: Ez a témakör a Microsoft Dynamics 365 for Field Service szolgáltatással való integrációról nyújt áttekintést.
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
ms.openlocfilehash: 22abe83f06b7fc57c73fb82ccafc4b426667e7c6
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865197"
---
# <a name="integration-with-microsoft-dynamics-365-for-field-service-overview"></a>A Microsoft Dynamics 365 for Field Service integráció áttekintése

[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations lehetővé teszi a Finance and Operations és Microsoft Dynamics 365 for Field Service közti üzleti folyamatok szinkronizálását. Az integrációs forgatókönyvek konfigurálása bővíthető adatintegrációs sablonok és a Common Data Service (CDS) segítségével történik az üzleti folyamatok szinkronizálása érdekében.
Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és az üzleti igények teljesítésére. 

A field service integráció a meglévő Potenciális vevő készpénzre váltása funkcióra épül.

![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/field-service-integration.png)

A Field Service és a Finance and Operations közötti integráció első fázisa a Field Service szolgáltatásban lévő munkarendelések és szerződések a Finance and Operations szolgáltatásban történő számlázásának lehetővé tételére irányul. A támogatott forgalom a Field Service-ben kezdődik, ahol a munkarendelésekből származó információk értékesítési rendelésekként szinkronizálódnak a Finance and Operations szolgáltatásba. A Finance and Operations szolgáltatásban megtörténik az értékesítési rendelések számlázása számlabizonylatok létrehozásához. Emellett a Field Service-ben lévő szerződéses számlákban lévő információk szinkronizálódnak a Finance and Operations szolgáltatásba. A Microsoft Dynamics 365 adatintegrátor testreszabható projektek használatával szinkronizálja az adatokat. Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és speciális követelmények teljesítésére.

A Field Service és a Finance and Operations közötti integráció első fázisa a következő elemek szinkronizálását teszi lehetővé:

- [Termékek a Finance and Operations szolgáltatásból termékekké a Field Service szolgáltatásban, amelyek terméktípus-információkat tartalmaznak](field-service-product.md)
- [Finance and Operations-munkarendelések Field Service vevői rendelésekké](field-service-work-order.md)
- [Finance and Operations-számlák Field Service szabadszöveges számlákká](field-service-invoice.md)

A Field Service és a Finance and Operations közötti szinkronizálás példamódjának megtekintéséhez tekintse meg a rövid YouTube videót: [Munkarendelések szinkronizálása a Microsoft Dynamics 365 integrációval](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Integráció a Microsoft Dynamics 365 for Field Service szolgáltatással, beleértve a készlet- és a projektadatokat

A második fázisban a további funkciók célja, hogy a szerviztechnikusok betekintést kapjanak a készletinformációkba a Finance and Operations alkalmazásban, így lehetőségük legyen a készletszintek frissítése és anyagmozgatásra. Ezenkívül az eladott áruk karbantartásával és telepítésével foglalkozó vállalatok számára előnyt jelent az, hogy jobban kezelhetik a teljes értékesítési és szervizfolyamatot, illetve rálátást kapnak arra a projektintegrációnak köszönhetően.

### <a name="functionality-includes-integration-of"></a>Funkciók között a következő integrációk szerepelnek:
- Raktárinformációk
- Aktuálisan készlettel kapcsolatos információk
- Készletátvitelek
- Készlethelyesbítések
- Dynamics 365 for Finance and Operations projektek a Dynamics 365 for Field Service munkarendelésekhez kapcsolva
- A Dynamics 365 for Field Servicemunkarendelések, amelyek hivatkozással rendelkeznek Dynamics 365 for Finance and Operations projektekre, alkalmazzák ezt a projektszámot a Dynamics 365 for Finance and Operations értékesítési rendelésre, amelyek így számlázhatók a projektből. 

![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>A Field Service és a Finance and Operations közötti integráció második fázisa a következő sablonokkal történő szinkronizálást teszi lehetővé:
- Raktárak (Fin and Ops – Field Service) - Raktárak a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Termékkészlet (Fin and Ops – Field Service) - Termékkészlet a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Készletkiigazítás (Fin and Ops – Field Service) - Készletkiigazítások a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Készletáthelyezések (Fin and Ops – Field Service) - Készletáthelyezések a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Projektek (Fin and Ops – Field Service) - Projektek a Finance and Operations alkalmazásból a Field Service alkalmazásba 
- Munkamegrendelések projekttel (Fin and Ops – Field Service) - Munkarendelések a Field Service alkalmazásból értékelési rendelésekbe a Finance and Operations alkalmazásba projekttámogatással [Speciális lekérdezés] 
- Filed Srevice termékek készletegységgel(Fin and Ops – Sales) - Finance and Operations „Értékesíthető kiadott termékek” a Field Service, Értékesítési „termékeibe” beleértve a raktáregységet is 

## <a name="system-requirements"></a>Rendszerkövetelmények

### <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez
A Field Service integráció a következő verziókat támogatja:

- Dynamics 365 for Finance and Operations 8.1.2-es verziója (2018. december) 2018. decemberben jelent meg, az alkalmazás buildszáma pedig 8.1.195, valamint Platform Update 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>A Field Service rendszerkövetelményei
A Field Service integrációs megoldás használatához telepítenie kell a következő összetevőket:

- Field Service for Dynamics 365 (8.2.0.286-os verzió) vagy újabb verziója a Dynamics 365 9.1.x – 2018. novemberben kiadott verzióján
- A potenciális ügyfelek készpénzre váltása (P2C) megoldás Dynamics 365 szolgáltatáshoz, 1.15.0.1 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3) felületéről.
- „Field Service Integration, Project and Inventory” megoldás Dynamics 365-höz, 2.0.0.0 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2) felületéről.
