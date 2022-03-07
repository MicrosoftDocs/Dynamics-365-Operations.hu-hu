---
title: A Finance and Operations alkalmazások frissítéseivel kapcsolatos problémák elhárítása
description: Ez a témakör hibaelhárítási információkat tartalmaz, amelyek segíthetnek a Finance and Operations alkalmazások frissítésével kapcsolatos problémák megoldásában.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c7c036ef44b0470c9b3f8087e7b5b1e16dde1b34
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062825"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>A Finance and Operations alkalmazások frissítéseivel kapcsolatos problémák elhárítása

[!include [banner](../../includes/banner.md)]





Ez a témakör hibaelhárítási információkat tartalmaz a Finance and Operations alkalmazások és a kettős írási integrációhoz Dataverse. Konkrétan olyan információkat nyújt, amelyek segíthetnek a Finance and Operations alkalmazások frissítésével kapcsolatos problémák megoldásában.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="database-synchronization-errors"></a>Adatbázis szinkronizálási hibái

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő példához hasonló hibaüzenet jelenhet meg, amikor megpróbálja használni a **DualWriteProjectConfiguration** táblázat a Finance and Operations alkalmazás frissítéséhez a 30-as platformfrissítésre.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Egy hiba javításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a virtuális gépbe (VM) a Finance and Operations alkalmazáshoz.
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

1. Jelentkezzen be a virtuális gépbe a Finance and Operations alkalmazáshoz.
2. Lépjen a **Munkaterületek \> Adatkezelés** pontra, válassza a **Keretrendszer paraméterei** csmepét, majd az **Táblabeállítások** lapon válassza a **Táblalista frissítése** parancsot a táblák frissítéséhez.
3. Lépjen a **Munkaterületek \> Adatkezelés** részre, válassza az **Adatáblák** lapot, és ellenőrizze, hogy a tábla szerepel a listában. Ha a táblázat nem szerepel a listában, jelentkezzen be a Finance and Operations alkalmazás virtuális gépébe, és győződjön meg arról, hogy a táblázat elérhető.
4. Nyissa meg a **Táblázat leképezés** oldal a **Kettős írás** oldalon a Finance and Operations alkalmazásban.
5. Az táblaleképezések oszlopainak automatikus kitöltéséhez válassza a **Táblalista frissítése** elemet.

Ha a hiba továbbra sincs kijavítva, hajtsa végre az alábbi lépéseket.

> [!IMPORTANT]
> Ezekkel a lépésekkel egy tábla törlési folyamatát hajthatja végre, majd hozzáadhatja újra. A problémák elkerüléséhez ügyeljen arra, hogy a lépéseket pontosan kövesse.

1. A Finance and Operations alkalmazásban lépjen a következőre: **Munkaterületek \> Adatkezelés**, és válassza ki a lehetőséget **Adattáblák** csempe.
2. Keresse meg azt a táblát, amelynek hiányzik az attribútuma. Kattintson a **Cél-hozzárendelés módosítása** elemre az eszköztárban.
3. Az **Előkészítés hozzárendelése a célhoz** panelen kattintson a **Leképezés létrehozása** elemre.
4. Nyissa meg a **Táblázat leképezés** oldal a **Kettős írás** oldalon a Finance and Operations alkalmazásban.
5. Ha az attribútum nincs automatikusan kitöltve a leképezésen, vegye fel kézzel az **Attribútum hozzáadása** gombra kattintva, majd kattintson a **Mentés** gombra. 
6. Válassza ki a leképezést, és kattintson a **Futtatás** lehetőségre.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]