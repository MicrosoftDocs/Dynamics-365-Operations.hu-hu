---
title: A(z) Finance and Operations alkalmazások frissítésével kapcsolatos problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások frissítésével kapcsolatos problémák.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
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
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c76b35ed3af766f42484a118a4a0407d969b5240
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683599"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a>A(z) Finance and Operations alkalmazások frissítésével kapcsolatos problémák elhárítása

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások frissítésével kapcsolatos problémák.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="database-synchronization-errors"></a>Adatbázis szinkronizálási hibái

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

Előfordulhat, hogy egy hibaüzenet jelenik meg, amely a következő példához hasonlít, amikor megpróbálja használni a **DualWriteProjectConfiguration** entitást egy Finance and Operations-alkalmazás frissítésekor a Platform update 30 verzióra.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Egy hiba javításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre (VM).
2. Nyissa meg Visual Studio alkalmazást adminisztrátorként, és nyissa meg az alkalmazásobjektum-fát (AOT).
3. Keresse meg a **DualWriteProjectConfiguration** elemet.
4. Az alkalmazásobjektum-fában kattintson a jobb gombbal a **DualWriteProjectConfiguration** elemre, majd válassza a **Hozzáadás új projekthez** parancsot. Az **ok** gombra kattintva hozza létre az alapértelmezett beállításokat használó új projektet.
5. A Solution Explorer alkalmazásban kattintson a jobb gombbal a **Projekt tulajdonságai** elemre, és állítsa az **Adatbázis szinkronizálása kialakításkor** beállítást **Igaz** értékre.
6. Hozza létre a projektet, és erősítse meg a létrehozás sikerességét.
7. Válassza a **Dynamics 365** menü **Adatbázis szinkronizálása** pontját.
8. A teljes adatbázis-szinkronizálás végrehajtásához válassza a **Szinkronizálás** parancsot.
9. A teljes adatbázis-szinkronizálás sikeres végrehajtása után futtassa újra az adatbázis-szinkronizálási lépést a Microsoft Dynamics Lifecycle Services (LCS) modulban, és szükség szerint használja a manuális frissítési parancsfájlokat, hogy folytathassa a frissítést.

## <a name="missing-entity-fields-issue-on-maps"></a>Hiányzó entitásmezők problémája a leképezésekben

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:

*Hiányzó forrásmező mező (\<field name\>) a sémában.*

![Példa a hiányzó forrásmező hibaüzenetére](media/error_missing_field.png)

A hiba javításához kövesse az alábbi lépéseket, és győződjön meg arról, hogy a mezők szerepelnek az entitásban.

1. Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre.
2. Lépjen a **Munkaterületek \> Adatkezelés** pontra, válassza a **Keretrendszer paraméterei** csmepét, majd az **Táblabeállítások** lapon válassza az **Entitáslista frissítése** parancsot a táblák frissítéséhez.
3. Lépjen a **Munkaterületek \> Adatkezelés** részre, válassza az **Adatáblák** lapot, és ellenőrizze, hogy az entitás szerepel a listában. Ha az entitás nem szerepel a listában, jelentkezzen be a Finance and Operations alkalmazás virtuális gépére, és győződjön meg róla, hogy az entitás elérhető.
4. Nyissa meg az **Táblaleképezés** oldalt a Finance and Operations alkalmazás **Kettős írás** oldalán.
5. Az táblaleképezések mezőinek automatikus kitöltéséhez válassza az **Entitáslista frissítése** elemet.

Ha a hiba továbbra sincs kijavítva, hajtsa végre az alábbi lépéseket.

> [!IMPORTANT]
> Ezekkel a lépésekkel egy entitás törlési folyamatát hajthatja végre, majd hozzáadhatja újra. A problémák elkerüléséhez ügyeljen arra, hogy a lépéseket pontosan kövesse.

1. A Finance and Operations alkalmazásban nyissa meg a **Munkaterületek \> Adatkezelés** pontot, és válassza az **Adatáblák** csempét.
2. Keresse meg azt az entitást, amelynek hiányzik az attribútuma. Kattintson a **Cél-hozzárendelés módosítása** elemre az eszköztárban.
3. Az **Előkészítés hozzárendelése a célhoz** panelen kattintson a **Leképezés létrehozása** elemre.
4. Nyissa meg az **Táblaleképezés** oldalt a Finance and Operations alkalmazás **Kettős írás** oldalán.
5. Ha az attribútum nincs automatikusan kitöltve a leképezésen, vegye fel kézzel az **Attribútum hozzáadása** gombra kattintva, majd kattintson a **Mentés** gombra. 
6. Válassza ki a leképezést, és kattintson a **Futtatás** lehetőségre.
