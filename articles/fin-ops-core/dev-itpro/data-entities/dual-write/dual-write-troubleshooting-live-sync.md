---
title: Élő szinkronizálási problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók az élő szinkronizálás problémái.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 60839bbd1b3ae642cdd419c7df2388292776a461
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172737"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Élő szinkronizálási problémák elhárítása

[!include [banner](../../includes/banner.md)]



Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban, olyan információkat tartalmaz, amelyek segítségével javíthatók az élő szinkronizálás problémái.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>Az élő szinkronizálás 403 Tiltott hibát jelez, amikor létrehoz egy rekordot egy Finance and Operations alkalmazásban

A következő hibaüzenet jelenhet meg, amikor létrehoz egy rekordot a Finance and Operations alkalmazásban:

*\[{\\"hiba\\":{\\"kód\\":\\"0x80072560\\",\\"üzenet\\":\\„A felhasználó nem a szervezet tagja\\"}}\], A távoli kiszolgáló a következő hibát küldte vissza: (403) Tiltott.”}}".*

A hiba elhárításához kövesse a [Rendszerkövetelmények és előfeltételek](requirements-and-prerequisites.md) szakasz lépéseit. Ezeknek a lépéseknek a végrehajtásához Common Data Service szolgáltatásban létrehozott kettős írású felhasználóknak rendelkezniük kell a rendszergazda szerepkörrel. Az alapértelmezett tulajdonos csapatnak is rendelkeznie kell a rendszeradminisztrátori szerepkörrel.

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>Egy entitás élő szinkronizálása folyamatosan hasonló hibát ad vissza, amikor egy rekordot hoz létre a Finance and Operations alkalmazásban

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

Előfordulhat, hogy a következőhöz hasonló hibaüzenet jelenik meg minden alkalommal, amikor megpróbálja menteni az entitások adatait egy Finance and Operations alkalmazásban:

*A módosítások nem menthetők az adatbázisba. A munkaegység nem tudja véglegesíteni a tranzakciót. Nem lehet adatokat írni az entitás értékesítési mértékegységeibe. A UnitOfMeasureEntity írása hibaüzenettel megszakadt, nem lehet szinkronizálni az entitás értékesítési mértékegységeivel.*

A hiba elhárítása érdekében gondoskodni kell arról, hogy az előfeltételnek számító hivatkozási adatok mind a Finance and Operations alkalmazásban, mind a Common Data Service szolgáltatásban létezzenek. Ha például az Finance and Operations alkalmazásban lévő vevő egy adott vevőcsoport tagja, győződjön meg arról, hogy a vevő csoport létezik a Common Data Service szolgáltatásban.

Ha mindkét oldalon szerepel az adat, és megerősítette, hogy a probléma nem az adatokkal kapcsolatos kövesse ezeket a lépéseket.

1. A kapcsolódó entitás leállítása.
2. Jelentkezzen be az Finance and Operations alkalmazásba, és győződjön meg arról, hogy az DualWriteProjectConfiguration és a DualWriteProjectFieldConfiguration táblákban léteznek rekordok a hibát jelző entitásokhoz. Itt megtekintheti például, hogy a lekérdezés hogyan néz ki, ha a **Vevők** hiúsul meg.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Ha az entitás-hozzárendelés leállítása után is léteznek rekordok a hibás entitáshoz, akkor törölje a hibás entitáshoz kapcsolódó rekordokat. Jegyezze fel a DualWriteProjectConfiguration tábla **projektnév** oszlopát, és kérje le a rekordot a DualWriteProjectFieldConfiguration táblában a projektnév használatával, a rekord törléséhez.
4. Indítsa el az entitás-hozzárendelést. Ellenőrizze, hogy az adatok szinkronizálása probléma nélkül történik-e.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Olvasási vagy írási jogosultsági hibák adatok létrehozása során a Finance and Operations alkalmazásban

Előfordulhat, hogy a következő példához hasonló „Hibás kérés” hibaüzenet jelenik meg, amikor egy Finance and Operations alkalmazásban hoz létre adatokat.

![Példa a Hibás kérés hibaüzenetére](media/error_record_id_source.png)

A hiba elhárításához a hiányzó jogosultság engedélyezéséhez társítania kell a megfelelő biztonsági szerepkört a megfeleltetett Dynamics 365 Sales vagy Dynamics 365 Customer Service üzleti egység csapatához a hiányzó jogosultság engedélyezéséhez.

1. A Finance and Operations alkalmazásban keresse meg azt az üzleti egységet, amely hozzá van rendelve az Adatintegrációs csatlakozókészletben.

    ![Szervezet leképezése](media/mapped_business_unit.png)

2. Jelentkezzen be a környezetbe a modellvezérelt alkalmazásban s Dynamics 365-ban, nyissa meg a **Beállítások \> Biztonság** lehetőséget, és keresse meg a leképezett üzleti egység csapatát.

    ![A hozzárendelt üzleti egység csapata](media/setting_security_page.png)

3. Nyissa meg a csapat lapját szerkesztésre, majd válassza a **Szerepkörök kezelése** parancsot, a **Csapat szerepköreinek kezelése** párbeszédpanel megnyitásához.

    ![Szerepkörök kezelése gomb](media/manage_team_roles.png)

4. Rendelje hozzá a megfelelő entitásokhoz az olvasási/írási jogosultsággal rendelkező szerepkört, majd kattintson az **OK** gombra.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a>A szinkronizálási problémák javítása egy környezetben egy közelmúltban módosított Common Data Service környezetben

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő hibaüzenet jelenhet meg, amikor adatot hoz létre a Finance and Operations alkalmazásban:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Nem sikerült adatcsomagot generálni az CustCustomerV3Entity entitáshoz**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Adatcsinag létrehozása sikertelen érvénytelen URI hibával: Az URI üres."}\],"isErrorCountUpdated":true}*

Így néz ki a hiba a Dynamics 365 egy modellvezérelt alkalmazásában:

*Váratlan hiba történt az ISV-kódból. (ErrorType = ClientError) Váratlan kivétel a bővítménytől (végrehajtás): Microsoft.Dynamics.Integrator.CrmPlugins.Plugin: System.Exception: nem sikerült feldolgozni az entitás fiókját (Egy kapcsolódási kísérlet nem sikerült, mert a kapcsolódó fél egy adott időt követően nem válaszolt helyesen, vagy a létrejött kapcsolat megszakadt, mert a csatlakoztatott állomás nem válaszolt*

Ez a hiba akkor fordul, ha a Common Data Service környezet helytelenül van alaphelyzetbe állítva, amikor adatokat próbál létrehozni a Finance and Operations alkalmazásban.

Egy hiba javításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Finance and Operations virtuális gépére (VM), nyissa meg az SQL Server Management Studio (SSMS) szolgáltatást, és keressen rekordokat a DUALWRITEPROJECTCONFIGURATIONENTITY táblában, ahol **internalentityname** egyenlő **Customers V3** és **externalentityname** egyenlő **accounts**. A lekérdezés így néz ki.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. A előző lekérdezés eredményéből származó projektnév használható a következő elkérdezés futtatásához.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Ügyeljen arra, hogy az **externalenvironmentURL** oszlop helyes Common Data Service vagy alkalmazás URL-címmel rendelkezzen. Törölje a megfelelő Common Data Service URL-címre mutató ismétlődő rekordokat. Törölje a megfelelő rekordokat a DUALWRITEPROJECTFIELDCONFIGURATION és DUALWRITEPROJECTCONFIGURATION táblákból.
4. Állítsa le az entitások hozzárendelését, majd indítsa újra
