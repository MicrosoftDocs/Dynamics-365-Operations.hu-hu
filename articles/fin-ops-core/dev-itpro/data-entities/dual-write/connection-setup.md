---
title: Útmutató a kettős írás beállításához
description: Ez a témakör a két írásos beállításnál támogatott helyzeteket ismerteti.
author: RamaKrishnamoorthy
ms.date: 06/28/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 15dfb609b5e25b4faf2b913cc2310df71c88a74d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111249"
---
# <a name="guidance-for-dual-write-setup"></a>Útmutató a kettős írás beállításához

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Két írásos kapcsolatot állíthat be a pénzügyi és műveleti környezet és a környezet Dataverse között.

+ A **pénzügyi és műveleti környezet** **biztosítja** a pénzügyi és műveletalkalmazások alapjául szolgáló platformot (Microsoft Dynamics például 365 Pénzügy, Dynamics 365 Supply Chain Management és ).Dynamics 365 Commerce Dynamics 365 Human Resources
+ A **Dataverse-környezet** biztosítja az **ügyfélkapcsolati alkalmazások** alapjául szolgáló platformot (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing és Dynamics 365 Project Service Automation).


> [!IMPORTANT]
> A Dynamics 365 Pénzügy emberierőforrás-modulja támogatja a kettős írású kapcsolatokat, Dynamics 365 Human Resources de az alkalmazást nem.

A beállítási mechanizmus az előfizetéstől és a környezettől függően változik:

+ A pénzügyi és műveleti alkalmazások új példányainál a kettős írású kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik. Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Dataverse-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.
+ A meglévő pénzügyi és műveleti alkalmazásoknál a kettős írású kapcsolat beállítása a pénzügyi és műveleti környezetben kezdődik.

Mielőtt kettős írásba kezd egy entitáson, kezdeti szinkronizálást futtathat, hogy mindkét oldalon kezelni tudja a meglévő adatokat: a Pénzügyi és műveleti alkalmazások, valamint az ügyfél-kapcsolati alkalmazások. Ha nem szükséges szinkronizálni a két környezet adatait, akkor ki lehet hagyni a kezdeti szinkronizálást.

A kezdeti szinkronizálás lehetővé teszi a meglévő adatok másolását egyik alkalmazásból a másikba. Számos telepítési eset van, attól függően, hogy mely környezetekkel rendelkezik már, és milyen típusú adatok találhatók a környezetben.

A következő beállítású forgatókönyvek támogatottak:

+ [Egy új pénzügyi és műveleti alkalmazáspéldány és egy új vevői megbízási alkalmazáspéldány](#new-new)
+ [Egy új pénzügyi és műveleti alkalmazáspéldány és egy létező vevői megbízási alkalmazáspéldány](#new-existing)
+ [Egy új pénzügyi és műveleti alkalmazáspéldány, amely adatokat és egy új vevői megbízási alkalmazáspéldányt tartalmaz.](#new-data-new)
+ [Egy új pénzügyi és műveleti alkalmazáspéldány, amely adatokat és egy meglévő vevői megbízási alkalmazáspéldányt tartalmaz.](#new-data-existing)
+ [Egy meglévő pénzügyi és műveleti alkalmazáspéldány és egy új vevői megbízási alkalmazáspéldány](#existing-new)
+ [Egy meglévő pénzügyi és műveleti alkalmazáspéldány és egy létező vevői megbízási alkalmazáspéldány](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a> Egy új pénzügyi és műveleti alkalmazáspéldány és egy új vevői megbízási alkalmazáspéldány

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveleti alkalmazással, amely nem rendelkezik adatokkal, és egy ügyfél-kapcsolati alkalmazás egy új példánya között, [kövesse a Lifecycle Services](lcs-setup.md) két írásos beállításának lépéseit. A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Új, üres pénzügyi és műveleti környezet van létesítve.
- Az ügyfélkapcsolati alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a> Egy új pénzügyi és műveleti alkalmazáspéldány és egy létező vevői megbízási alkalmazáspéldány

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveleti alkalmazással, amely nem rendelkezik adatokkal, [és egy vevői kapcsolat alkalmazásának egy meglévő példánya között, hajtsa végre a Lifecycle Services két írásos beállításának lépéseit](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Új, üres pénzügyi és műveleti környezet van létesítve.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

A következő lépésekkel Dataverse szinkronizálhatja a meglévő adatokat a Pénzügy és műveletek alkalmazással.

1. Új vállalat létrehozása a Pénzügy és műveletek alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

Egy példára és egy [alternatív megközelítésre mutató hivatkozásokat a témakör későbbi Példa](#example) szakaszában talál.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a> Egy új pénzügyi és műveleti alkalmazáspéldány, amely adatokat és egy új vevői megbízási alkalmazáspéldányt tartalmaz.

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveletalkalmazás új példánya, amely adatokat tartalmaz, valamint egy ügyfél-szerződés alkalmazás egy új példánya, [kövesse](#new-new) a cikk korábbi, Az új Pénzügyi és műveleti alkalmazás példánya és az új vevői szerződés alkalmazáspéldány című szakaszának lépéseit. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Pénzügy és műveletek alkalmazást az LCS lapról, jelentkezzen be, majd lépjen **be az Adatkezelés \> kettős írása lapra**.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a> Egy új pénzügyi és műveleti alkalmazáspéldány, amely adatokat és egy meglévő vevői megbízási alkalmazáspéldányt tartalmaz.

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveletalkalmazás új példánya, amely adatokat tartalmaz, valamint egy ügyfél-szerződés alkalmazás egy meglévő példánya között, [hajtsa végre az Új](#new-existing) pénzügy és műveletek alkalmazáspéldány és a cikk korábbi vevői szerződési alkalmazáspéldányának lépéseit. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Pénzügy és műveletek alkalmazást az LCS lapról, jelentkezzen be, majd lépjen **be az Adatkezelés \> kettős írása lapra**.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A következő lépésekkel Dataverse szinkronizálhatja a meglévő adatokat a Pénzügy és műveletek alkalmazással.

1. Új vállalat létrehozása a Pénzügy és műveletek alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs ISO vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a> Egy meglévő pénzügyi és műveleti alkalmazáspéldány és egy új vevői megbízási alkalmazáspéldány

Egy pénzügyi és műveleti alkalmazás egy meglévő példánya, valamint egy vevői kapcsolat alkalmazásának egy új példánya közötti kettős írásos kapcsolat a Pénzügyi és műveleti környezetben történik.

1. [A kapcsolat beállítása a Pénzügy és műveletek alkalmazásból](enable-dual-write.md).
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a> Egy meglévő pénzügyi és műveleti alkalmazáspéldány és egy létező vevői megbízási alkalmazáspéldány

Egy pénzügyi és műveleti alkalmazás egy meglévő példánya, valamint az ügyfél-kapcsolat alkalmazásának egy meglévő példánya közötti kettős írásos kapcsolat a Pénzügyi és műveleti környezetben történik.

1. [A kapcsolat beállítása a Pénzügy és műveletek alkalmazásból](enable-dual-write.md).
2. Ha szinkronizálni Dataverse kell a meglévő adatokat a Pénzügy és műveletek alkalmazással, [...](bootstrap-company-data.md)Dataverse akkor hárombetűs ISO-vállalati kód használatával kell szinkronizálni az adatokat.
3. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="example"></a>Példa

Példa: [a Vevők v3-a kapcsolattartó-tábla leképezésének engedélyezése](enable-entity-map.md#enable-table-map)

A kezdeti szinkronizálás futtatását igénylő entitások adatmennyiségein alapuló alternatív megközelítéshez lásd [a kezdeti szinkronizálás szempontjait](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
