---
title: "Integráció a Microsoft Dynamics 365 for Field Service szolgáltatással"
description: "Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 for Field Service szolgáltatással való integrációról."
author: ChristianRytt
manager: AnnBe
ms.date: 08/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 95031534c43dc0578e258bc3e5376c429d72b0ab
ms.openlocfilehash: 673ab2a101cee1a3dbbb1249f582d959cecc7f7f
ms.contentlocale: hu-hu
ms.lasthandoff: 12/23/2018

---

# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integráció a Microsoft Dynamics 365 for Field Service szolgáltatással

[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations lehetővé teszik az üzleti folyamatok szinkronizálását a Finance and Operations és a Microsoft Dynamics 365 for Field Service között. Az integrációs forgatókönyvek konfigurálása bővíthető adatintegrációs sablonok és a Common Data Service (CDS) segítségével történik az üzleti folyamatok szinkronizálása érdekében.
Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és az üzleti igények teljesítésére. 

A field service integráció a meglévő Potenciális vevő készpénzre váltása funkcióra épül.

![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/field-service-integration.png)

A Field Service és a Finance and Operations közötti integráció első fázisa a Field Service szolgáltatásban lévő munkarendelések és szerződések a Finance and Operations szolgáltatásban történő számlázásának lehetővé tételére irányul. A támogatott forgalom a Field Service-ben kezdődik, ahol a munkarendelésekből származó információk értékesítési rendelésekként szinkronizálódnak a Finance and Operations szolgáltatásba. A Finance and Operations szolgáltatásban megtörténik az értékesítési rendelések számlázása számlabizonylatok létrehozásához. Emellett a Field Service-ben lévő szerződéses számlákban lévő információk szinkronizálódnak a Finance and Operations szolgáltatásba. A Microsoft Dynamics 365 adatintegrátor testreszabható projektek használatával szinkronizálja az adatokat. Szabványos sablonok használhatók egyéni integrációs projektek létrehozására, ahol további szabványos és egyéni mezők, valamint entitások is leképezhetők az integráció módosítására és speciális követelmények teljesítésére.

A Field Service és a Finance and Operations közötti integráció első fázisa a következő elemek szinkronizálását teszi lehetővé:

- [Termékek a Finance and Operations szolgáltatásból termékekké a Field Service szolgáltatásban, amelyek terméktípus-információkat tartalmaznak](field-service-product.md)
- [Finance and Operations-munkarendelések Field Service vevői rendelésekké](field-service-work-order.md)
- [Finance and Operations-számlák Field Service szabadszöveges számlákká](field-service-invoice.md)

A Field Service és a Finance and Operations közötti szinkronizálás példamódjának megtekintéséhez tekintse meg a rövid YouTube videót [Munkarendelések szinkronizálása a Microsoft Dynamics 365 integrációval](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez
A Field Service integráció a következő verziókat támogatja:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Dynamics 365 for Finance and Operations 8.0-es verzió (2018. április) vagy újabb

- A Dynamics 365 for Finance and Operations 8.0 verziója (2018. április) 2018 áprilisában jelent, meg, az alkalmazás buildszáma 8.0.30.8020, 15-ös platformfrissítés (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>A Field Service rendszerkövetelményei
A Field Service integrációs megoldás használatához telepítenie kell a következő összetevőket:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 vagy újabb

- Dynamics 365 for Field Service, verzió: 1612 (9.0.1.733) (DB 9.0.1.733) online vagy későbbi verzió.
- A potenciális ügyfelek készpénzre váltása (P2C) megoldás Dynamics 365 szolgáltatáshoz, 1.15.0.1 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3)-ból.
- Field Service integrációs megoldás Dynamics 365-höz, 1.0.0.0 vagy későbbi verzió.. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegration)-ból.

# <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Integráció a Microsoft Dynamics 365 for Field Service alkalmazással, beleértve a készlet és a projekt adatait

A második fázisban a további funkciók célja, hogy a szerviztechnikusok betekintést kapjanak a készletinformációkba a Finance and Operations alkalmazásban, így lehetőségük legyen a készletszintek frissítése és anyagmozgatásra. Ezenkívül az eladott áruk karbantartásával és telepítésével foglalkozó vállalatok számára előnyt jelent az, hogy jobban kezelhetik a teljes értékesítési és szervizfolyamatot, illetve rálátást kapnak arra a projektintegrációnak köszönhetően.

### <a name="functionality-includes-integration-of"></a>Funkciók között a következő integrációk szerepelnek:
- Raktárinformációk
- Aktuálisan készlettel kapcsolatos információk
- Készletátvitelek
- Készlethelyesbítések
- A Dynamics 365 for Finance and Operations projektek össze vannak kapcsolva a Dynamics 365 for Field Service munkarendelésekkel
- A Dynamics 365 for Field Service munkarendelések, amelyek kapcsolva vannak a Dynamics 365 for Finance and Operations projektekhez ezt a projektszámot rendelik a Dynamics 365 for Finance and Operations étékesítési rendelésekhez, hogy lehetséges legyen a számlázás a projektből. 

![Üzleti folyamatok szinkronizálása a Finance and Operations és a Field Service között](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>A Field Service és a Finance and Operations közötti integráció második fázisa a következő sablonokkal történő szinkronizálást teszi lehetővé:
- Raktárak (Fin and Ops – Field Service) - Raktárak a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Termékkészlet (Fin and Ops – Field Service) - Termékkészlet a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Készletkiigazítás (Fin and Ops – Field Service) - Készletkiigazítások a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Készletáthelyezések (Fin and Ops – Field Service) - Készletáthelyezések a Finance and Operations alkalmazásból a Field Service alkalmazásba [Speciális lekérdezés] 
- Projektek (Fin and Ops – Field Service) - Projektek a Finance and Operations alkalmazásból a Field Service alkalmazásba 
- Munkamegrendelések projekttel (Fin and Ops – Field Service) - Munkarendelések a Field Service alkalmazásból értékelési rendelésekbe a Finance and Operations alkalmazásba projekttámogatással [Speciális lekérdezés] 
- Filed Srevice termékek készletegységgel(Fin and Ops – Sales) - Finance and Operations „Értékesíthető kiadott termékek” a Field Service, Értékesítési „termékeibe” beleértve a raktáregységet is 

## <a name="system-requirements-for-finance-and-operations"></a>Rendszerigény a Finance and Operations rendszerhez
A Field Service integráció a következő verziókat támogatja:

- A Dynamics 365 for Finance and Operations 8.1.2 verziója (2019. december) 2019 decemberében jelent, meg, az alkalmazás buildszáma 8.1.195, 22-ös platformfrissítés (7.0.5095). 

## <a name="system-requirements-for-field-service"></a>A Field Service rendszerkövetelményei
A Field Service integrációs megoldás használatához telepítenie kell a következő összetevőket:

- Field Service for Dynamics 365 (8.2.0.286 verzió) vagy újabb verzió Dynamics 365 9.1.x példányon - 2018. novemberében kiadva
- A potenciális ügyfelek készpénzre váltása (P2C) megoldás Dynamics 365 szolgáltatáshoz, 1.15.0.1 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3)-ból.
- „Field Service Integration, Project and Inventory” megoldás Dynamics 365-höz, 2.0.0.0 vagy későbbi verzió. A megoldás letölthető az [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2)-ból.

