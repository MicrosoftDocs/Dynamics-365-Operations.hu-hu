---
title: A Pénzügyi és műveletalkalmazások frissítésével kapcsolatos problémák elhárítása
description: Ez a cikk olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak a pénzügyi és műveleti alkalmazások frissítésével kapcsolatos problémák megoldásához.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: b75034cbc8ca7a24472cfec1ad93d3dfef4a8fdc
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111140"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások frissítésével kapcsolatos problémák elhárítása

[!include [banner](../../includes/banner.md)]





Ez a témakör hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, valamint a Dataverse. Konkrétabban: olyan információkat tartalmaz, amelyek segítséget nyújtnak a pénzügyi és műveleti alkalmazások frissítésével kapcsolatos problémák megoldásához.

> [!IMPORTANT]
> Az ebben a témakörben említett problémák egy része a rendszergazdai szerepkörhöz vagy a Microsoft Azure Active Directory (Azure AD) bérlői rendszergazdai hitelesítő adatokhoz lehet szükséges. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="database-synchronization-errors"></a>Adatbázis szinkronizálási hibái

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

Előfordulhat, **hogy a Következő példához hasonló hibaüzenet jelenik meg, amikor a DualWriteProjectConfiguration** táblát a Platform 30 frissítésére próbálja frissíteni a pénzügyek és műveletek alkalmazásában.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Egy hiba javításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Pénzügy és műveletek alkalmazás virtuális gépbe (VM).
2. Nyissa meg Visual Studio alkalmazást adminisztrátorként, és nyissa meg az alkalmazásobjektum-fát (AOT).
3. Keresse meg a **DualWriteProjectConfiguration** elemet.
4. Az alkalmazásobjektum-fában kattintson a jobb gombbal a **DualWriteProjectConfiguration** elemre, majd válassza a **Hozzáadás új projekthez** parancsot. Az **ok** gombra kattintva hozza létre az alapértelmezett beállításokat használó új projektet.
5. A Solution Explorer alkalmazásban kattintson a jobb gombbal a **Projekt tulajdonságai** elemre, és állítsa az **Adatbázis szinkronizálása kialakításkor** beállítást **Igaz** értékre.
6. Hozza létre a projektet, és erősítse meg a létrehozás sikerességét.
7. Válassza a **Dynamics 365** menü **Adatbázis szinkronizálása** pontját.
8. A teljes adatbázis-szinkronizálás végrehajtásához válassza a **Szinkronizálás** parancsot.
9. A teljes adatbázis-szinkronizálás sikeres végrehajtása után futtassa újra az adatbázis-szinkronizálási lépést a Microsoft Dynamics Lifecycle Services (LCS) modulban, és szükség szerint használja a manuális frissítési parancsfájlokat, hogy folytathassa a frissítést.

## <a name="missing-table-columns-issue-on-maps"></a>Hiányzó táblaoszlop-probléma a leképezésekben

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:

*Hiányzó forrásmező mező (\<field name\>) a sémában.*

![Példa a hiányzó forrásoszlop hibaüzenetére.](media/error_missing_field.png)

A hiba javításához kövesse az alábbi lépéseket, és győződjön meg arról, hogy az oszlopok szerepelnek a táblában.

1. Jelentkezzen be az VM-be a Pénzügy és műveletek alkalmazásba.
2. Lépjen a **Munkaterületek \> Adatkezelés** pontra, válassza a **Keretrendszer paraméterei** csmepét, majd az **Táblabeállítások** lapon válassza a **Táblalista frissítése** parancsot a táblák frissítéséhez.
3. Lépjen a **Munkaterületek \> Adatkezelés** részre, válassza az **Adatáblák** lapot, és ellenőrizze, hogy a tábla szerepel a listában. Ha a tábla nincs felsorolva, jelentkezzen be az VM-be a Pénzügy és műveletek alkalmazásba, és ellenőrizze, hogy elérhető-e a tábla.
4. A Táblaleképezés **lap** megnyitása **a Pénzügy és** műveletek alkalmazás Kétírásos lapról.
5. Az táblaleképezések oszlopainak automatikus kitöltéséhez válassza a **Táblalista frissítése** elemet.

Ha a hiba továbbra sincs kijavítva, hajtsa végre az alábbi lépéseket.

> [!IMPORTANT]
> Ezekkel a lépésekkel egy tábla törlési folyamatát hajthatja végre, majd hozzáadhatja újra. A problémák elkerüléséhez ügyeljen arra, hogy a lépéseket pontosan kövesse.

1. A Pénzügy és műveletek alkalmazásban menjen **\>** a Munkaterületek adatai kezelése lapra, és válassza az Adattáblák **csempe** lehetőséget.
2. Keresse meg azt a táblát, amelynek hiányzik az attribútuma. Kattintson a **Cél-hozzárendelés módosítása** elemre az eszköztárban.
3. Az **Előkészítés hozzárendelése a célhoz** panelen kattintson a **Leképezés létrehozása** elemre.
4. A Táblaleképezés **lap** megnyitása **a Pénzügy és** műveletek alkalmazás Kétírásos lapról.
5. Ha az attribútum nincs automatikusan kitöltve a leképezésen, vegye fel kézzel az **Attribútum hozzáadása** gombra kattintva, majd kattintson a **Mentés** gombra. 
6. Válassza ki a leképezést, és kattintson a **Futtatás** lehetőségre.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
