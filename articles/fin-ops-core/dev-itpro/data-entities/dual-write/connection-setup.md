---
title: Útmutató a kettős írás beállításához
description: Ez a témakör azt mutatja be, hogy milyen eseteket támogat a kettős írás beállítás.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6de449b14bcdd82336e3e255bf62ad069d3daaf5
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061604"
---
# <a name="guidance-for-dual-write-setup"></a>Útmutató a kettős írás beállításához

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Beállíthat kettős írási kapcsolatot a Finance and Operations környezet és a Dataverse környezet.

+ A **Pénzügyi és működési környezet** biztosítja a mögöttes platformot **Finance and Operations alkalmazások** (például a Microsoft Dynamics 365 Finance,Dynamics 365 Supply Chain Management,Dynamics 365 Commerce, és Dynamics 365 Human Resources).
+ A **Dataverse-környezet** biztosítja az **ügyfélkapcsolati alkalmazások** alapjául szolgáló platformot (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing és Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> A Human Resources modul a Dynamics 365 Finance kettős írás kapcsolatok használatát támogatják, de az Dynamics 365 Human Resources alkalmazás nem.

A beállítási mechanizmus az előfizetéstől és a környezettől függően változik:

+ A Finance and Operations alkalmazások új példányainál a kettős írási kapcsolat beállítása itt kezdődik Microsoft Dynamics Életciklus-szolgáltatások (LCS). Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Dataverse-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.
+ A meglévő Finance and Operations alkalmazások esetében a kettős írási kapcsolat beállítása a Finance and Operations környezetben kezdődik.

Mielőtt elkezdené a kettős írást egy entitáson, lefuttathat egy kezdeti szinkronizálást, hogy kezelje a meglévő adatokat mindkét oldalon: a Finance and Operations és az ügyfél-elköteleződési alkalmazásokban. Ha nem szükséges szinkronizálni a két környezet adatait, akkor ki lehet hagyni a kezdeti szinkronizálást.

A kezdeti szinkronizálás lehetővé teszi a meglévő adatok másolását egyik alkalmazásból a másikba. Számos telepítési eset van, attól függően, hogy mely környezetekkel rendelkezik már, és milyen típusú adatok találhatók a környezetben.

A következő beállítású forgatókönyvek támogatottak:

+ [Egy új Finance and Operations alkalmazáspéldány és egy új ügyfél-elköteleződési alkalmazáspéldány](#new-new)
+ [Egy új Finance and Operations alkalmazáspéldány és egy meglévő ügyfél-elköteleződési alkalmazáspéldány](#new-existing)
+ [Egy új Finance and Operations alkalmazáspéldány, amely adatokat és egy új ügyfél-elköteleződési alkalmazáspéldányt tartalmaz](#new-data-new)
+ [Egy új Finance and Operations alkalmazáspéldány, amely adatokat és egy meglévő ügyfél-elköteleződési alkalmazáspéldányt tartalmaz](#new-data-existing)
+ [Egy meglévő Finance and Operations alkalmazáspéldány és egy új ügyfél-elköteleződési alkalmazáspéldány](#existing-new)
+ [Egy meglévő Finance and Operations alkalmazáspéldány és egy meglévő ügyfél-elköteleződési alkalmazáspéldány](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a> Egy új Finance and Operations alkalmazáspéldány és egy új ügyfél-elköteleződési alkalmazáspéldány

Ha kettős írási kapcsolatot szeretne létrehozni egy új, adatokkal nem rendelkező Finance and Operations alkalmazás és egy ügyfél-elköteleződési alkalmazás új példánya között, kövesse a következő lépéseit: [A Lifecycle Services kettős írási beállítása](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Egy új, üres Finance and Operations környezet van kiépítve.
- Az ügyfélkapcsolati alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a> Egy új Finance and Operations alkalmazáspéldány és egy meglévő ügyfél-elköteleződési alkalmazáspéldány

Ha kettős írási kapcsolatot szeretne létrehozni egy új, adatokkal nem rendelkező Finance and Operations alkalmazáspéldány és egy ügyfélelköteleződési alkalmazás meglévő példánya között, kövesse a következő lépéseit: [A Lifecycle Services kettős írási beállítása](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Egy új, üres Finance and Operations környezet van kiépítve.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

A meglévő szinkronizálásához Dataverse adatokat a Finance and Operations alkalmazásba, kövesse az alábbi lépéseket.

1. Hozzon létre egy új céget a Finance and Operations alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a témakör későbbi [Példa](#example) részében találhatja meg.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a> Egy új Finance and Operations alkalmazáspéldány, amely adatokat és egy új ügyfél-elköteleződési alkalmazáspéldányt tartalmaz

Ha kettős írási kapcsolatot szeretne létrehozni egy új, adatokat tartalmazó Finance and Operations alkalmazáspéldány és egy ügyfél-elköteleződési alkalmazás új példánya között, kövesse a [Egy új Finance and Operations alkalmazáspéldány és egy új ügyfél-elköteleződési alkalmazáspéldány](#new-new) részben ebben a témában. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Finance and Operations alkalmazást az LCS oldalról, jelentkezzen be, majd lépjen a következőre **Adatkezelés \> Kettős írás**.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a> Egy új Finance and Operations alkalmazáspéldány, amely adatokat és egy meglévő ügyfél-elköteleződési alkalmazáspéldányt tartalmaz

Ha kettős írási kapcsolatot szeretne létrehozni egy adatokat tartalmazó Finance and Operations alkalmazás új példánya és egy ügyfél-elköteleződési alkalmazás meglévő példánya között, kövesse a [Egy új Finance and Operations alkalmazáspéldány és egy meglévő ügyfél-elköteleződési alkalmazáspéldány](#new-existing) részben ebben a témában. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Finance and Operations alkalmazást az LCS oldalról, jelentkezzen be, majd lépjen a következőre **Adatkezelés \> Kettős írás**.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A meglévő szinkronizálásához Dataverse adatokat a Finance and Operations alkalmazásba, kövesse az alábbi lépéseket.

1. Hozzon létre egy új céget a Finance and Operations alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs ISO vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a> Egy meglévő Finance and Operations alkalmazáspéldány és egy új ügyfél-elköteleződési alkalmazáspéldány

A Finance and Operations alkalmazás egy meglévő példánya és egy ügyfél-elköteleződési alkalmazás új példánya közötti kettős írási kapcsolat beállítása a Finance and Operation környezetben történik.

1. [Állítsa be a kapcsolatot a Finance and Operations alkalmazásból](enable-dual-write.md).
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a> Egy meglévő Finance and Operations alkalmazáspéldány és egy meglévő ügyfél-elköteleződési alkalmazáspéldány

A Finance and Operations alkalmazás meglévő példánya és egy ügyfél-elköteleződési alkalmazás meglévő példánya közötti kettős írási kapcsolat beállítása a Finance and Operations környezetben történik.

1. [Állítsa be a kapcsolatot a Finance and Operations alkalmazásból](enable-dual-write.md).
2. A meglévő szinkronizálásához Dataverse adatokat a Finance and Operations alkalmazásba, [bootstrap](bootstrap-company-data.md) a Dataverse adatokat hárombetűs ISO cégkóddal.
3. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="example"></a>Példa

Példa: [a Vevők v3-a kapcsolattartó-tábla leképezésének engedélyezése](enable-entity-map.md#enable-table-map)

A kezdeti szinkronizálás futtatását igénylő entitások adatmennyiségein alapuló alternatív megközelítéshez lásd [a kezdeti szinkronizálás szempontjait](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]