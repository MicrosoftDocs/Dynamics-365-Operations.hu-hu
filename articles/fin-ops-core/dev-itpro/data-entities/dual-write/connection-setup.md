---
title: Útmutató a kettős írás beállításához
description: Ez a témakör azt mutatja be, hogy milyen eseteket támogat a kettős írás beállítás.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 78a7cdc18476a1c523c83c92ca6f354c3ba806dc
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744853"
---
# <a name="guidance-for-dual-write-setup"></a>Útmutató a kettős írás beállításához

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Egy Finance and Operations-környezet és egy Dataverse-környezet között kettős írás kapcsolatot állíthat be.

+ Egy **Finance and Operations-környezet** a háttérplatformot biztosítja a **Finance and Operations-alkalmazásokhoz** (például a Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce és Dynamics 365 Human Resources).
+ A **Dataverse-környezet** biztosítja az **ügyfélkapcsolati alkalmazások** alapjául szolgáló platformot (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing és Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> A Human Resources modul a Dynamics 365 Finance kettős írás kapcsolatok használatát támogatják, de az Dynamics 365 Human Resources alkalmazás nem.

A beállítási mechanizmus az előfizetéstől és a környezettől függően változik:

+ A Finance and Operations-alkalmazások új példányainál a kettős írás kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik. Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Dataverse-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.
+ A meglévő példányú Finance and Operations-alkalmazások esetében a kettős írás kapcsolat beállítása a Finance and Operations-környezetben kezdődik.

Mielőtt egy entitásra kettős írást alkalmaz, futtathatja a kezdeti szinkronizálást, amely az Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások mindkét oldalán meglévő adatokat kezeli. Ha nem szükséges szinkronizálni a két környezet adatait, akkor ki lehet hagyni a kezdeti szinkronizálást.

A kezdeti szinkronizálás lehetővé teszi a meglévő adatok másolását egyik alkalmazásból a másikba. Számos telepítési eset van, attól függően, hogy mely környezetekkel rendelkezik már, és milyen típusú adatok találhatók a környezetben.

A következő beállítású forgatókönyvek támogatottak:

+ [Egy új Finance and Operations-alkalmazáspéldány és egy új ügyfélkapscsolati alkalmazáspéldány](#new-new)
+ [Egy új Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány](#new-existing)
+ [Egy új Finance and Operations-alkalmazáspéldány, amely adatokkal rendelkezik, és egy új ügyfélkapcsolati alkalmazáspéldány](#new-data-new)
+ [Egy új Finance and Operations-alkalmazáspéldány, amely bemutatóadatokkal rendelkezik, és egy meglévő ügyfélkapcsolati alkalmazáspéldány](#new-data-existing)
+ [Egy meglévő Finance and Operations-alkalmazáspéldány és egy új ügyfélkapcsolati alkalmazáspéldány](#existing-new)
+ [Egy meglévő Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Egy új Finance and Operations-alkalmazáspéldány és egy új ügyfélkapscsolati alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Egy új, üres Finance and Operations-környezet létesítése megtörténik.
- Az ügyfélkapcsolati alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Egy új Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben nincsenek adatok, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Kettős írás beállítása a Lifecycle Services szolgáltatásból](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Egy új, üres Finance and Operations-környezet létesítése megtörténik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

Ha a meglévő Dataverse-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a témakör későbbi [Példa](#example) részében találhatja meg.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Egy új Finance and Operations-alkalmazáspéldány, amely adatokkal rendelkezik, és egy új ügyfélkapcsolati alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben adatok vannak, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy új példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy új ügyfélkapcsolati alkalmazáspéldány](#new-new) szakaszt a témakör korábbi részében. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Egy új Finance and Operations-alkalmazáspéldány, amely adatokkal rendelkezik, és egy meglévő ügyfélkapcsolati alkalmazáspéldány

Ha a kettős írás kapcsolatot olyan Finance and Operations-alkalmazás új példányával szeretné beállítani, amelyben adatok vannak, és a Dynamics 365 ügyfélkapcsolati alkalmazásainak egy meglévő példányával, kövesse a lépéseket itt: [Az új Finance and Operations alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány](#new-existing) szakaszt a témakör korábbi részében. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Finance and Operations alkalmazást a LCS oldalon, jelentkezzen be, majd kattintson az **Adatkezelés \> kettős írás** elemre.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

Ha a meglévő Dataverse-adatokat szinkronizálni szeretné Finance and Operations-alkalmazással, hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy új vállalatot az Finance and Operations alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs ISO vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Egy meglévő Finance and Operations-alkalmazáspéldány és egy új ügyfélkapcsolati alkalmazáspéldány

A Finance and Operations alkalmazás egy létező példánya és egy ügyfélkapcsolati alkalmazás új példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.

1. [A kapcsolat beállítása a Finance and Operations alkalmazásból](enable-dual-write.md).
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Egy meglévő Finance and Operations-alkalmazáspéldány és egy meglévő ügyfélkapcsolati alkalmazáspéldány

A Finance and Operations alkalmazás egy létező példánya és egy ügyfélkapcsolati alkalmazás meglévő példánya között egy kettős írás kapcsolat létrehozása a Finance and Operation környezetben történik.

1. [A kapcsolat beállítása a Finance and Operations alkalmazásból](enable-dual-write.md).
2. Ha a meglévő Dataverse-adatokat szinkronizálni szeretné Finance and Operations alkalmazással, [indítson rendszerindítást](bootstrap-company-data.md) a Dataverse adatokkal a három betűs ISO vállalati kóddal.
3. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="example"></a>Példa

Példa: [a Vevők v3-a kapcsolattartó-tábla leképezésének engedélyezése](enable-entity-map.md#enable-table-map)

A kezdeti szinkronizálás futtatását igénylő entitások adatmennyiségein alapuló alternatív megközelítéshez lásd [a kezdeti szinkronizálás szempontjait](initial-sync-guidance.md).
