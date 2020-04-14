---
title: A kettős írás beállítás támogatott forgatókönyvei
description: Ez a témakör azt mutatja be, hogy milyen eseteket támogat a kettős írás beállítás.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d7ff514768ee8e4797b591da89e190a855385885
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172854"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>A kettős írás beállítás támogatott forgatókönyvei

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Egy Finance and Operations-környezet és egy Common Data Service-környezet között kettős írás kapcsolatot állíthat be.

+ Egy **Finance and Operations-környezet** a háttérplatformot biztosítja a **Finance and Operations-alkalmazásokhoz** (például a Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail és Dynamics 365 Human Resources).
+ A **Common Data Service-környezet** biztosítja a **Dynamics 365 modellvezérelt alkalmazások alapjául szolgáló platformot** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, és Dynamics 365 Project Service Automation).

A beállítási mechanizmus az előfizetéstől és a környezettől függően változik.

+ A Finance and Operations-alkalmazások új példányainál a kettős írás kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik. Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Common Data Service-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.
+ A meglévő példányú Finance and Operations-alkalmazások esetében a kettős írás kapcsolat beállítása a Finance and Operations-környezetben kezdődik.

A következő beállítású forgatókönyvek támogatottak:

+ [Egy új Finance and Operations-alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány](#new-new)
+ [Egy új Finance and Operations-alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány](#new-existing)
+ [Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy új modellvezérelt alkalmazáspéldány](#new-demo-new)
+ [Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő modellvezérelt alkalmazáspéldány](#new-demo-existing)
+ [Egy meglévő Finance and Operations-alkalmazáspéldány és egy új vagy meglévő modellvezérelt alkalmazáspéldány](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>Egy új Finance and Operations-alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 modellvezérelt alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Egy új, üres Finance and Operations-környezet létesítése megtörténik.
- A modellvezérelt alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- Az entitás-leképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>Egy új Finance and Operations-alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 modellvezérelt alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Egy új, üres Finance and Operations-környezet létesítése megtörténik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- Az entitás-leképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Common Data Service-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.

Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy új modellvezérelt alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben bemutatóadatok vannak, és a Dynamics 365 modellvezérelt alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy új modellvezérelt alkalmazáspéldány](#new-new) szakaszt a témakör korábbi részében. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné a demó adatait a modell alapú alkalmazással.

1. Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon entitások esetében, amelyekhez szinkronizálni szeretné az adatokat.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő modellvezérelt alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben bemutatóadatok vannak, és a Dynamics 365 modellvezérelt alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy meglévő modellvezérelt alkalmazáspéldány](#new-existing) szakaszt a témakör korábbi részében. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné a demó adatait a modell alapú alkalmazással.

1. Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon entitások esetében, amelyekhez szinkronizálni szeretné az adatokat.

Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Common Data Service-adatokkal a három betűs ISO vállalati kóddal.

Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>Egy meglévő Finance and Operations-alkalmazáspéldány és egy új vagy meglévő modellvezérelt alkalmazáspéldány

A Finance and Operations alkalmazás egy létező példánya és a Dynamics 365 modellvezérelt alkalmazás új vagy létező példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.

1. A kapcsolat beállítása az Finance and Operations alkalmazásból.
2. Ha a meglévő Common Data Service-adatokat szinkronizálni szeretné Finance and Operations alkalmazással, [indítson rendszerindítást](bootstrap-company-data.md) a Common Data Service adatokkal a három betűs ISO vállalati kóddal.

Mivel a kettős írás élő szinkronizálási módban van, a Common Data Service adatai automatikusan átáramlanak a Finance and Operations alkalmazásba.
