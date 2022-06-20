---
title: Útmutató a kettős írás beállításához
description: Ez a témakör a két írásos beállításnál támogatott helyzeteket ismerteti.
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: a0d1b4e1f093874a8fd37cf7aadb331cd1e7adc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873149"
---
# <a name="guidance-for-dual-write-setup"></a>Útmutató a kettős írás beállításához

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Két írásos kapcsolatot állíthat be a Pénzügyi és üzemeltetési környezet és a környezet Dataverse között.

+ A **Pénzügyi és műveleti környezet** **biztosítja** a Pénzügy és művelet alkalmazások alap platformját (Microsoft Dynamics például a 365 Pénzügy, Dynamics 365 Supply Chain Management az és Dynamics 365 Commerce az stb Dynamics 365 Human Resources.).
+ A **Dataverse-környezet** biztosítja az **ügyfélkapcsolati alkalmazások** alapjául szolgáló platformot (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing és Dynamics 365 Project Service Automation).

> [!IMPORTANT]
> A Dynamics 365 Pénzügy emberierőforrás-modulja támogatja a kettős írású kapcsolatokat, Dynamics 365 Human Resources de az alkalmazást nem.

A beállítási mechanizmus az előfizetéstől és a környezettől függően változik:

+ A Pénzügy és a Műveletek alkalmazás új példányainál a kettős írású kapcsolat beállítása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban kezdődik. Ha rendelkezik licenccel a Microsoft Power Platform szolgáltatáshoz, akkor új Dataverse-környezetbe kerül, ha a bérlő nem rendelkezik eggyel.
+ A meglévő Pénzügy és Műveletek alkalmazásoknál a két írásos kapcsolat beállítása a Pénzügy és műveletek környezetben kezdődik.

Mielőtt kettős írásba kezd egy entitáson, kezdeti szinkronizálást futtathat, hogy mindkét oldalon kezelni tudja a meglévő adatokat: a Pénzügy és üzemeltetési alkalmazások, valamint az ügyfél-kapcsolati alkalmazások. Ha nem szükséges szinkronizálni a két környezet adatait, akkor ki lehet hagyni a kezdeti szinkronizálást.

A kezdeti szinkronizálás lehetővé teszi a meglévő adatok másolását egyik alkalmazásból a másikba. Számos telepítési eset van, attól függően, hogy mely környezetekkel rendelkezik már, és milyen típusú adatok találhatók a környezetben.

A következő beállítású forgatókönyvek támogatottak:

+ [Egy új Pénzügyi és Műveleti alkalmazáspéldány és egy új vevői megbízási alkalmazáspéldány](#new-new)
+ [Egy új Pénzügyi és Műveleti alkalmazáspéldány és egy létező vevői megbízási alkalmazáspéldány](#new-existing)
+ [Egy új Pénzügyi és Műveleti alkalmazáspéldány, amely adatokat és egy új vevői megbízási alkalmazáspéldányt tartalmaz.](#new-data-new)
+ [Egy új Pénzügyi és Műveleti alkalmazáspéldány, amely adatokat és egy meglévő vevői megbízási alkalmazáspéldányt tartalmaz.](#new-data-existing)
+ [A Pénzügy és műveletek egy meglévő alkalmazáspéldánya és egy új vevői megbízási alkalmazáspéldány](#existing-new)
+ [A Pénzügy és műveletek egy meglévő alkalmazáspéldánya és egy létező vevői megbízási alkalmazáspéldány.](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a> Egy új Pénzügyi és Műveleti alkalmazáspéldány és egy új vevői megbízási alkalmazáspéldány

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveleti alkalmazással, amely nem rendelkezik adatokkal, és egy ügyfél-kapcsolati alkalmazás egy új példánya között, [kövesse a Lifecycle Services](lcs-setup.md) két írásos beállításának lépéseit. A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Új, üres Pénzügyi és Műveleti környezet van létesítve.
- Az ügyfélkapcsolati alkalmazások egy új, üres példánya létesítésre kerül, ahol a CRM Prime megoldást telepítik.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a> Egy új Pénzügyi és Műveleti alkalmazáspéldány és egy létező vevői megbízási alkalmazáspéldány

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveleti alkalmazás egy új példánya között, amely nem rendelkezik adatokkal, [és egy vevői kapcsolat alkalmazásának egy meglévő példánya között, hajtsa végre a Lifecycle Services kétírásos beállításának lépéseit](lcs-setup.md). A kapcsolat beállításának végeztével a következő műveletek történnek automatikusan:

- Új, üres Pénzügyi és Műveleti környezet van létesítve.
- A DAT vállalati adatokhoz egy kettős írás kapcsolat jön létre.
- A táblaleképezések engedélyezve vannak az élő szinkronizáláshoz.

A két környezet készen áll az élő adatszinkronizálására.

A következő lépésekkel szinkronizálhatja Dataverse a meglévő adatokat a Pénzügy és műveletek alkalmazással.

1. Hozzon létre egy új vállalatot a Pénzügy és műveletek alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs Nemzetközi Szabványügyi Szervezet (ISO) vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

Egy példára és egy [alternatív megközelítésre mutató hivatkozásokat a témakör későbbi Példa](#example) szakaszában talál.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a> Egy új Pénzügyi és Műveleti alkalmazáspéldány, amely adatokat és egy új vevői megbízási alkalmazáspéldányt tartalmaz.

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveleti alkalmazás, amely adatokat tartalmaz, és egy ügyfél-szerződés alkalmazás egy új példánya között, [hajtsa végre az Új](#new-new) Pénzügy és műveletek alkalmazáspéldány és a cikk korábbi részében található új ügyfél-szerződési alkalmazáspéldány lépéseit. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Pénzügy és műveletek alkalmazást az LCS lapról, jelentkezzen be, majd lépjen **be az Adatkezelés \> kettős írása lapra**.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a> Egy új Pénzügyi és Műveleti alkalmazáspéldány, amely adatokat és egy meglévő vevői megbízási alkalmazáspéldányt tartalmaz.

Ha kettős írású kapcsolatot kell létesíteni egy olyan pénzügyi és műveleti alkalmazás egy új példánya, amely adatokat tartalmaz, valamint egy ügyfél-szerződés alkalmazás egy meglévő példánya között, [hajtsa végre az Új](#new-existing) Pénzügy és műveletek alkalmazáspéldány és a cikk korábbi vevői szerződési alkalmazáspéldányának lépéseit. Ha befejezte a kapcsolat beállítását, hajtsa végre az alábbi lépéseket, ha szinkronizálni szeretné az adatait az ügyfélkapcsolati alkalmazással.

1. Nyissa meg a Pénzügy és műveletek alkalmazást az LCS lapról, jelentkezzen be, majd lépjen **be az Adatkezelés \> kettős írása lapra**.
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A következő lépésekkel szinkronizálhatja Dataverse a meglévő adatokat a Pénzügy és műveletek alkalmazással.

1. Hozzon létre egy új vállalatot a Pénzügy és műveletek alkalmazásban.
2. Adja hozzá a vállalatot a kettős írás kapcsolat beállításhoz.
3. [Rendszerindítás](bootstrap-company-data.md) a Dataverse-adatokkal a három betűs ISO vállalati kóddal.
4. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a> A Pénzügy és műveletek egy meglévő alkalmazáspéldánya és egy új vevői megbízási alkalmazáspéldány

A Pénzügy és művelet alkalmazás egy meglévő példánya és egy vevői kapcsolat alkalmazásának egy új példánya közötti kettős írásos kapcsolat a Pénzügyi és műveleti környezetben történik.

1. [A kapcsolat beállítása a Pénzügy és műveletek alkalmazásból](enable-dual-write.md).
2. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a> A Pénzügy és műveletek egy meglévő alkalmazáspéldánya és egy létező vevői megbízási alkalmazáspéldány.

A Pénzügy és műveletek alkalmazás egy meglévő példánya és az ügyfél-kapcsolat alkalmazásának egy meglévő példánya közötti kettős írásos kapcsolat a Pénzügyi és műveleti környezetben történik.

1. [A kapcsolat beállítása a Pénzügy és műveletek alkalmazásból](enable-dual-write.md).
2. Ha szinkronizálni Dataverse kell a meglévő adatokat a Pénzügy és műveletek alkalmazással, [...](bootstrap-company-data.md)Dataverse akkor hárombetűs ISO-vállalati kód használatával kell eltenni az adatokat.
3. Futtassa a **kezdeti szinkronizálási** funkciókat azon táblák esetében, amelyekhez szinkronizálni szeretné az adatokat.

A példaekre mutató hivatkozásokat és az alternatív megközelítést a [Példa](#example) részben találhatja meg.

## <a name="example"></a>Példa

Példa: [a Vevők v3-a kapcsolattartó-tábla leképezésének engedélyezése](enable-entity-map.md#enable-table-map)

A kezdeti szinkronizálás futtatását igénylő entitások adatmennyiségein alapuló alternatív megközelítéshez lásd [a kezdeti szinkronizálás szempontjait](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]