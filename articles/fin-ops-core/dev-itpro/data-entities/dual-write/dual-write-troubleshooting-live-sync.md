---
title: Élő szinkronizálási problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók az élő szinkronizálás problémái.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: df184decdfa900ccb5c2070575e55052b9dfc547
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062363"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Élő szinkronizálási problémák elhárítása

[!include [banner](../../includes/banner.md)]



Ez a témakör hibaelhárítási információkat tartalmaz a Finance and Operations alkalmazások és a kettős írási integrációhoz Microsoft Dataverse. Pontosabban, olyan információkat tartalmaz, amelyek segítségével javíthatók az élő szinkronizálás problémái.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazdai szerepkört vagy az Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>Az élő szinkronizálás hibát jelez sor létrehozásakor

A következő hibaüzenet jelenhet meg, amikor sort hoz létre egy Finance and Operations alkalmazásban:

*\[{\\"hiba\\":{\\"kód\\":\\"0x80072560\\",\\"üzenet\\":\\„A felhasználó nem a szervezet tagja\\"}}\], A távoli kiszolgáló a következő hibát küldte vissza: (403) Tiltott.”}}".*

A hiba elhárításához kövesse a [Rendszerkövetelmények és előfeltételek](requirements-and-prerequisites.md) szakasz lépéseit. Ezeknek a lépéseknek a végrehajtásához a Dataverse szolgáltatásban létrehozott kettős írású felhasználóknak rendelkezniük kell a rendszergazda szerepkörrel. Az alapértelmezett tulajdonos csapatnak is rendelkeznie kell a rendszeradminisztrátori szerepkörrel.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>Az élő szinkronizálás hibát jelez, amikor táblaadatokat próbál menteni

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő hibaüzenet jelenhet meg, amikor megpróbálja menteni a táblázat adatait egy Finance and Operations alkalmazásban:

*A módosítások nem menthetők az adatbázisba. A munkaegység nem tudja véglegesíteni a tranzakciót. Nem lehet adatokat írni az entitás értékesítési mértékegységeibe. A UnitOfMeasureEntity írása hibaüzenettel megszakadt, nem lehet szinkronizálni az entitás értékesítési mértékegységeivel.*

A probléma megoldásához győződjön meg arról, hogy az előfeltétel referenciaadatok léteznek mind a Finance and Operations alkalmazásban, mind a Dataverse. Ha például egy vevői rekord egy adott vevőcsoporthoz tartozik, győződjön meg arról, hogy a vevő csoport rekordja létezik a Dataverse szolgáltatásban.

Ha mindkét helyen szerepel az adat, és megerősítette, hogy a probléma nem az adatokkal kapcsolatos, kövesse ezeket a lépéseket.

1. Nyissa meg a **DualWriteProjectConfigurationEntity** entitást az Excel-bővítmény használatával. A bővítmény használatához engedélyezze a tervezési módot a Finance and Operations Excel bővítményben, és adja hozzá **DualWriteProjectConfigurationEntity** egy munkalaphoz. További információért lásd: Az [entitás adatainak megtekintése és frissítése az Excel segítségével](../../office-integration/use-excel-add-in.md).
2. Válassza ki és törölje azokat a rekordokat, amelyek problémákat okozhatnak a kettős írásos leképezésben és a projektben. Két rekord lesz minden kettős írásos leképezéshez.
3. Tegye közzé a módosításokat az Excel bővítmény segítségével. Ez a lépés azért fontos, mert törli a rekordokat az entitásból és a mögöttes táblákból.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Kezelje az olvasási vagy írási jogosultságokkal kapcsolatos hibákat, amikor adatokat hoz létre egy Finance and Operations alkalmazásban

„Bad Request” hibaüzenet jelenhet meg, amikor adatokat hoz létre egy Finance and Operations alkalmazásban.

![Példa a Hibás kérés hibaüzenetére.](media/error_record_id_source.png)

A hiba elhárításához a megfelelő biztonsági szerepkörnek a megfeleltetett Dynamics 365 Sales vagy Dynamics 365 Customer Service üzleti egység csapatához történő társításával engedélyeznie kell a hiányzó jogosultságot.

1. A Finance and Operations alkalmazásban keresse meg az adatintegrációs kapcsolatkészletben leképezett üzleti egységet.

    ![Szervezet leképezése.](media/mapped_business_unit.png)

2. Az ügyfélkapcsolati alkalmazásban jelentkezzen be a környezetbe, nyissa meg a **Beállítások \> Biztonság** lehetőséget, és keresse meg a leképezett üzleti egység csapatát.

    ![A hozzárendelt üzleti egység csapata.](media/setting_security_page.png)

3. Nyissa meg szerkesztésre a csapat lapját, majd válassza a **Szerepkörök kezelése** lehetőséget.

    ![Szerepkörök kezelése gomb.](media/manage_team_roles.png)

4. A **Csoportszerepek kezelése** párbeszédpanelen rendelje hozzá a szerepkört, amely a megfelelő táblák olvasási/írási jogosultságával rendelkezik, majd kattintson az **OK** gombra.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>A szinkronizálási problémák javítása egy környezetben egy közelmúltban módosított Dataverse környezetben

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő hibaüzenet jelenhet meg, amikor adatokat hoz létre egy Finance and Operations alkalmazásban:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Nem sikerült adatcsomagot generálni az CustCustomerV3Entity entitáshoz**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Adatcsinag létrehozása sikertelen érvénytelen URI hibával: Az URI üres."}\],"isErrorCountUpdated":true}*

Ez a hibaüzenet jelenik meg az ügyfélkapcsolati alkalmazásában:

> Váratlan hiba történt az ISV-kódból. (ErrorType = ClientError) Váratlan kivétel a bővítménytől (végrehajtás): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nem sikerült feldolgozni az entitás fiókját (Egy kapcsolódási kísérlet nem sikerült, mert a kapcsolódó fél egy adott időt követően nem válaszolt helyesen, vagy a létrejött kapcsolat megszakadt, mert a csatlakoztatott állomás nem válaszolt.

Ez a hiba akkor fordul elő, ha a Dataverse környezet hibásan visszaáll, amikor megpróbál adatokat létrehozni a Finance and Operations alkalmazásban.

> [!IMPORTANT]
> Ha újra összekapcsolta a környezeteket, akkor az összes entitásleképezést le kell állítania, mielőtt folytatja a kockázatcsökkentés lépéseit.

A probléma megoldásához mindkét esetben végre kell hajtania a lépéseket Dataverse és a Finance and Operations alkalmazást.

1. A Finance and Operations alkalmazásban kövesse az alábbi lépéseket:

    1. Nyissa meg a **DualWriteProjectConfigurationEntity** entitást az Excel-bővítmény használatával. A bővítmény használatához engedélyezze a tervezési módot a Finance and Operations Excel bővítményben, és adja hozzá **DualWriteProjectConfigurationEntity** egy munkalaphoz. További információért lásd: Az [entitás adatainak megtekintése és frissítése az Excel segítségével](../../office-integration/use-excel-add-in.md).
    2. Válassza ki és törölje azokat a rekordokat, amelyek problémákat okozhatnak a kettős írásos leképezésben és a projektben. Két rekord lesz minden kettős írásos leképezéshez.
    3. Tegye közzé a módosításokat az Excel bővítmény segítségével. Ez a lépés azért fontos, mert törli a rekordokat az entitásból és a mögöttes táblákból.
    4. A hibák elkerülése érdekében, amikor újra összekapcsolja a Finance and Operations vagy Dataverse környezetekben, ügyeljen arra, hogy ne maradjanak kettős írási konfigurációk.

2. A Dataverse-ben kövesse az alábbi lépéseket:

    1. Jelentkezzen be a Dataverse környezetbe (például: `https://*****.crm.dynamics.com/`).
    2. Ugorjon a **Speciális beállítások** \> **Speciális keresés** elemhez.
    3. Válassza ki a **DualWrite Runtime konfigurációt**.
    4. Jelölje ki a megtekinteni kívánt oszlopot.
    5. Válassza ki az **Eredmények** elemet a konfigurációk megtekintéséhez.
    6. Törölje az összes példányt.

3. A Finance and Operations alkalmazásban kövesse az alábbi lépéseket:

    1. Nyissa meg a **DualWriteProjectConfigurationEntity** entitást az Excel-bővítmény használatával. A bővítmény használatához engedélyezze a tervezési módot a Finance and Operations Excel bővítményben, és adja hozzá **DualWriteProjectConfigurationEntity** egy munkalaphoz. További információért lásd: Az [entitás adatainak megtekintése és frissítése az Excel segítségével](../../office-integration/use-excel-add-in.md).
    2. Válassza ki és törölje azokat a rekordokat, amelyek problémákat okozhatnak a kettős írásos leképezésben és a projektben. Két rekord lesz minden kettős írásos leképezéshez.
    3. Tegye közzé a módosításokat az Excel bővítmény segítségével. Ez a lépés azért fontos, mert törli a rekordokat az entitásból és a mögöttes táblákból.
    4. A hibák elkerülése érdekében, amikor újra összekapcsolja a Finance and Operations vagy Dataverse környezetekben, ügyeljen arra, hogy ne maradjanak kettős írási konfigurációk.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Élő szinkronizálási hiba a teljes adatbázis-másolás után

Ha az adatbázis teljes másolatát az egyik rendszerből a másikba futtatja, majd egy adatbázis-műveletet próbál futtatni, akkor a következő hibaüzenet jelenik meg:

*SecureConfig szervezet (???) nem egyezik meg a tényleges CRM-szervezettel (???).*

A hibaüzenet a kettős írású futásidejű beépülő modulban látható, így garantálható, hogy az egyik rendszerben beállított kettős írásos konfiguráció nem használható egy másik rendszerben.

A probléma megoldásához törölje a **msdyn_dualwriteruntimeconfig** tábla rekordjait, miután visszaállította az adatbázist. A további tudnivalókat lásd: [Kettős írásos környezetek leválasztása és összekapcsolása](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Élő szinkronizálási problémák, amelyeket a kettős írású leképezések lekérdezésszűrői helytelen szintaxisa okozott

Bár a kettős írású leképezésszűrő lekérdezési kifejezése szintaktikailag helyes, lehet, hogy nem a várt módon működik. A szűrőkifejezés egy entitáson van, nem pedig egy lekérdezésobjektum egyéni adatforrásán. Ebből következően a generált SQL-lekérdezés nem a várt eredményt küldi vissza.

Íme, egy példa.

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Előfordulhat, hogy az olyan projekteket, amelyeknél nincs szülő, kiszűri a rendszer. A szűrő azonban nem működik, mert a következő példához hasonló lekérdezésre fordítja le a rendszer.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

A tényleges eredmény az, hogy a `parentProject` mező értéke `null`. A `null` azonban nem azonos az üres sztringgel. Az eltérés miatt a lekérdezésszűrő nem küld vissza érvényes eredményt.

Egy hiba javításához kövesse az alábbi lépéseket.

1. Adjon hozzá egy számított oszlopot, amelyet hozzá lehet adni a kiterjesztési modellhez, és amely mögött olyan logika áll, amely a `null` értéket üres sztringgé alakítja át.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Használja az új számított oszlop szűrőjét az alapértelmezett oszlop helyett.

A szűrő fejlesztői környezetben való kiértékeléséhez a következő X++ kóddal ellenőrizheti az eredményeket. Futtassa ezt a kódot különálló programként. Segítségével kiértékelheti a különböző szűrőket, amelyek egy entitáshoz alkalmazhatók, mielőtt ezeket a szűrőket kettős írású leképezéseken használná. Az eltérések kiértékelése érdekében a lekérdezés az adatbázison futtatható.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>A Finance and Operations alkalmazásokból származó adatok nincsenek szinkronizálva ezzel Dataverse

Az élő szinkronizálás során olyan problémába ütközhet, hogy az adatoknak csak egy része kerül szinkronizálásra a Finance and Operations alkalmazásból a Dataverse, vagy az adatok egyáltalán nincsenek szinkronizálva.

> [!NOTE]
> A problémát a fejlesztés során kell kijavítani.

Mielőtt elkezdené kijavítani a problémát, ellenőrizze a következő előfeltételeket:

+ Győződjön meg róla, hogy az egyéni módosítások egyetlen tranzakció-hatókörbe kerülnek.
+ Az üzleti események és a kettős írású keretrendszer nem kezeli a `doinsert()`, `doUpdate()` és `recordset()` műveleteket, illetve azokat a rekordokat, ahol a `skipBusinessEvents(true)` meg van jelölve. Ha a kód ezeken a funkciókon belül van, a rendszer nem indít kettős írást.
+ A leképezett adatforráshoz üzleti eseményeket kell regisztrálni. Előfordulhat, hogy egyes adatforrások külső csatlakozást használnak, és csak olvashatóként vannak megjelölve a Finance and Operations alkalmazásokban. Ezeket az adatforrásokat nem követi nyomon a rendszer.
+ A módosítások csak akkor aktiválódnak, ha a leképezett mezőkben vannak. A nem leképezett mezőmódosítások nem váltják ki a kettős írást.
+ Ellenőrizze, hogy a szűrőértékelések érvényes eredményt adnak-e.

### <a name="troubleshooting-steps"></a>A hibaelhárítás lépései

1. Tekintse át a kettős írású rendszergazdai lapon található mezőleképezéseket. Ha egy mező nincs hozzárendelve a Finance and Operations alkalmazásból a következőre Dataverse, nem lesz nyomon követve. Például a következő ábrán a **Leírás** a mezőt a rendszer követi Dataverse, de nem a Finance and Operations alkalmazásból. A Finance and Operations alkalmazásokon belüli mező módosításait a rendszer nem követi nyomon.

    ![Nyomon követéses mező.](media/live-sync-troubleshooting-1.png)

2. Határozza meg, hogy az adatforrást nyomon követi-e a rendszer az üzleti események definíciójában. Az alábbi példában a program például nem követi nyomon a **DefaultDimensionDAVs** tábla egyetlen mezőjét sem és a mögöttes táblákat sem. Azok az adatforrások, amelyek külső illesztést használnak, és csak olvashatóként vannak megjelölve, nem követhetők nyomon.

    ![Nem nyomon követhető mező.](media/live-sync-troubleshooting-2.png)

3. Határozza meg, hogy a leképezett táblamezők megjelenjenek-e a **BUSINESSEVENTSDEFINITION** táblában, az alábbi ábrán megjelenő módon. Ha nem találja azt a mezőt, amelyet a lekérdezés eredményében keres, akkor a kettős írás nem fog aktiválódni.

    ![Nyomon követett mező a táblában.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Mintaforgatókönyv

A Finance and Operations alkalmazásokban a kapcsolattartó rekord címe frissül, de a címmódosítás nincs szinkronizálva Dataverse. Ez az eset azért fordul elő, mert a **BusinessEventsDefinition** tábla egyetlen rekordja sem tartalmazza az érintett tábla és az entitás kombinációját. Pontosabban a **LogisticsPostalAddress** tábla nem az **smmContactpersonCDSV2Entity** entitás közvetlen adatforrása. Az **smmContactpersonCDSV2Entity** entitás adatforrása az **smmContactPersonV2Entity**, és az **smmContactPersonV2Entity** adatforrása pedig a **LogisticsPostalAddressBaseEntity**. A **LogisticsPostalAddress** tábla a **LogisticsPostalAddressBaseEntity** adatforrása.

Hasonló helyzet fordulhat elő néhány nem szabványos mintában, például olyan esetekben, amikor a Finance and Operations alkalmazásokban módosítandó tábla nincs nyilvánvalóan az azt tartalmazó entitáshoz kötve. Például az elsődleges címadatok számítása az **smmContactPersonCDSV2Entity** entitás alapján történt. A kettős írású keretrendszer megpróbálja meghatározni, hogy egy alapul szolgáló tábla módosítása hogyan van leképezve az entitásokra. Ez a megközelítés általában elegendő. Bizonyos esetekben azonban a kapcsolat olyan bonyolult, hogy Önnek pontosabb megközelítést kell alkalmaznia. Meg kell győződnie arról, hogy a kapcsolódó tábla **RecId** azonosítója közvetlenül elérhető-e az entitáshoz. Ezután adjon meg egy statikus metódust a tábla változásának figyelése érdekében.

Példaként tekintse át az **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()** metódust. A **CustCustomerV3entity** és a **VendVendorV2Entity módosítása megtörtént** a helyzet kezelése érdekében.

Egy hiba javításához kövesse az alábbi lépéseket.

1. Adja hozzá a **PrimaryPostalAddressRecId** mezőt az **smmContactPersonV2Entity** entitáshoz. Legyen belső mező.

    ![Az smmContactPersonV2Entity entitáshoz hozzáadott mező.](media/Troubleshoot_live_sync_issue_1.png)

2. Adja hozzá ugyanezt a mezőt az **smmContactPersonCDSV2Entity** entitáshoz.

    ![Az smmContactPersonCDSV2Entity entitáshoz hozzáadott mező.](media/Troubleshoot_live_sync_issue_2.png)

3. Adja hozzá a következő metódust az **smmContactPersonCDSV2Entity** osztályhoz.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Szinkronizálja az adatbázist, és hozza létre az alkalmazást.
5. Az **smmContactPersonCDSV2Entity** entitáson létrehozott összes kettős írású leképezés leállítása.
6. Indítsa el a leképezést. Látnia kell egy új táblát (a példa szerint: **LogisticsPostalAddress**), amelyet a **RefTableName** oszlop segítségével kezdett el nyomon követni annak a sornak az esetében, ahol a **refentityname** érték megegyezik az **smmContactPersonCDSV2Entity** értékkel a **BusinessEventsDefinition** táblában.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Hiba olyan rekord létrehozásakor, amelyre több rekordot küld egy Finance and Operations alkalmazás Dataverse ugyanabban a tételben

A Finance and Operations alkalmazás minden tranzakcióhoz kötegben hoz létre adatokat, és kötegként küldi el a címre Dataverse. Ha két rekord ugyanannak a tranzakciónak a részeként jön létre, és ezek egymásra hivatkoznak, akkor a következő példához hasonló hibaüzenet jelenhet meg a Finance and Operations alkalmazásban:

*Nem lehet adatokat írni az aaa_fundingsources entitásba. Nem lehet keresni az ebecsfs_contracts értéket {PC00...} értékekkel. Nem lehet keresni az aaa_fundingsources értéket {PC00...} értékekkel. Az aaa_fundingsources írása sikertelen volt a következő kivételre vonatkozó hibaüzenet miatt: A távoli kiszolgáló hibát küldött vissza: (400) Hibás kérelem.*

A probléma megoldásához hozzon létre entitáskapcsolatokat a Finance and Operations alkalmazásban, jelezve, hogy a két entitás kapcsolatban áll egymással, és a kapcsolódó rekordokat ugyanabban a tranzakcióban kezelik.

## <a name="enable-verbose-logging-of-error-messages"></a>Hibaüzenetek részletes naplózásának engedélyezése

A Finance and Operations alkalmazásban olyan hibákat tapasztalhat, amelyek a következőhöz kapcsolódnak Dataverse környezet. Lehet, hogy a hibaüzenet nem tartalmazza az üzenet teljes szövegét vagy más fontos adatokat. További információkért engedélyezheti a részletes naplózást a beállításával **IsDebugMode** zászló, amely jelen van a **DualWriteProjectConfigurationEntity** entitás minden projektkonfigurációban a Finance and Operations alkalmazásokban.

1. Nyissa meg a **DualWriteProjectConfigurationEntity** entitást az Excel-bővítmény használatával. A bővítmény használatához engedélyezze a tervezési módot a Finance and Operations Excel bővítményben, és adja hozzá **DualWriteProjectConfigurationEntity** egy munkalaphoz. További információért lásd: Az [entitás adatainak megtekintése és frissítése az Excel segítségével](../../office-integration/use-excel-add-in.md).
2. Állítsa a projekt **IsDebugMode** jelölőjét **Igen** értékre.
3. Futtassa a forgatókönyvet.
4. A részletes naplók a **DualWriteErrorLog** táblában érhetők el. Ha a táblázatböngésző segítségével szeretne adatokat keresni, használja a következő URL-címet: `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`
5. Ha több naplót is rögzítenie kell hibakeresési módban, telepítse a frissítést a [KB 4595434 (Javítás a kettős írású élő szinkronizálásban propagált üres értékekre)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9) lehetőségben.

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Hiba a vevő vagy kapcsolattartó címének hozzáadásakor

A következő hibaüzenet jelenhet meg, amikor megpróbál címet adni egy ügyfélhez vagy kapcsolattartóhoz a Finance and Operations alkalmazásban vagy Dataverse:

*Nem lehet adatokat írni az msdyn_partypostaladdresses entitásba. A DirPartyPostalAddressLocationCDSEntity írása sikertelen volt a következő hibaüzenettel: A kérés BadRequest státuszkóddal és CDS hibakóddal sikertelen volt: 0x80040265 válaszüzenet: Hiba történt a beépülő modulban. Már létezik olyan rekord, amely rendelkezik a helyazonosító attribútumértékekkel. Az entitáskulcs helyazonosító kulcsához az attribútumok ezen halmazának egyedi értékeket kell tartalmaznia. Válassza ki az egyedi értékeket, majd próbálkozzon újra.*

A probléma megoldásához telepítse a kettős írású csomagverziót (2.2.2.60), hogy a **Cím** táblában található kulcsokat a következő táblázatban látható módon definiálja a program.

| Tulajdonság | Érték |
|---|---|
| Megjelenítendő név | **Helymeghatározó kulcs** |
| Név | **msdyn_locationkey** |
| Mezők | **msdyn_locationid**, **parentid** |
| Állapot | **Aktív** |
| Rendszerfeladat | Üres |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Hiba történt a vevő hozzáadásakor a következőben: Dataverse

A következő hibaüzenet jelenhet meg, amikor vevőt próbál hozzáadni a Dataverse alkalmazáshoz:

*"RecordError0":"Írási hiba történt a Vevő V3 entitásnál, ismeretlen kivétellel – Nem található félrekord a "Szervezet" típusú félhez}.*

Amikor létrejön egy vevő a Dataverse alkalmazásban, új félszámot generál a rendszer. A hibaüzenet akkor jelenik meg, ha az ügyfélrekord a féllel együtt szinkronizálva van a Finance and Operations alkalmazásokkal, de már van olyan ügyfélrekord, amely más félszámmal rendelkezik.

A probléma megoldásához keresse meg a vevőt a félre vonatkozó kereséssel. Ha a vevő nem létezik, hozzon létre egy új vevőrekordot. Ha a vevő létezik, a meglévő féllel hozza létre az új vevőrekordot.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Hiba történt az új vevő, szállító vagy kapcsolattartó létrehozásakor a Dataverse alkalmazásban

Amikor a Dataverse alkalmazáshoz egy új vevő, szállító vagy kapcsolattartó címét próbálja meg hozzáadni, a következő hibaüzenet jelenhet meg:

*A féltípus nem frissíthető "DirOrganization" típusról "DirPerson" típusra. A meglévő fél törlését és az új típussal történő beszúrásokat kell helyette végrehajtani.*

A Dataverse alkalmazásban van egy számsorozat a **msdyn_party** táblában. Egy számla Dataverse alkalmazásban történő létrehozásakor új fél jön létre (például **Szervezet** típusú **Party-001**). Ezek az adatok a Finance and Operations alkalmazásba kerülnek. Ha a Dataverse környezet visszaállításra kerül, vagy a Finance and Operations környezet egy másikhoz van kapcsolva Dataverse környezetben, majd új kapcsolatfelvételi rekord jön létre Dataverse, egy új pártérték, amely azzal kezdődik **Party-001** létrehozva. A létrehozott félrekord most **Személy** típusú **Party-001** lesz. Amikor ezeket az adatokat szinkronizálja, a Finance and Operations alkalmazások az előző hibaüzenetet jelenítik meg, mert fél rekord **Party-001** a **Szervezet** típus már létezik.

A probléma megoldásához módosítsa a másik **msdyn_partynumber** tábla **msdyn_party** mezőjének automatikus számsorozatát a Dataverse-ben egy másik automatikus számsorozatra.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Vevői vagy kapcsolattartói leképezések teljesítményével kapcsolatos probléma

Lehet, hogy a **getEntityDataSourceToFieldMapping** metódus (a **CustCustomerV3Entity** entitásban) és a **getEntityDataSourceToFieldMapping** metódus (az **smmContactPersonCDSV2Entity** entitásban) testreszabásával kis mértékben javíthatja a vevők és kapcsolattartók élő szinkronizálásának teljesítményét. Ezek a testreszabások csökkentik a **BusinessEventsDefinition** táblában található rekordok számát. A rekordok számának ez a csökkenése viszont csökkenti a bekövetkező események számát.

A **CustCustomerV3Entity** entitás **getEntityDataSourceToFieldMapping** metódusa gondoskodik róla, hogy a vevő e-mail-címének vagy postai címének frissítése üzleti eseményeket váltson ki, így a frissített adatokat elküldi a rendszer a Dataverse-be. Ha nem használ minden mezőt, és nincs szüksége az információra kettős írásban, fűzzön hozzászólást a metódus megfelelő soraihoz. Minden, ezzel a módszerrel hozzáadott mező és tábla rekordot ad hozzá a **BusinessEventsDefinition** táblához a nyomon követhető tábla és a nyomon követhető entitás kombinációja esetében.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

Hasonlóképpen az **smmContactPersonCDSV2Entity** entitás **getEntityDataSourceToFieldMapping** metódusa gondoskodik róla, hogy a kapcsolattartó e-mail-címének vagy postai címének frissítése üzleti eseményeket váltson ki, így a frissített adatokat elküldi a rendszer a Dataverse-be. A metódusban hozzászólhat a nem használt mezők soraihoz.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

A módszerek frissítése után kövesse az alábbi lépéseket.

1. Szinkronizálja az adatbázist, és hozza létre az alkalmazást.
2. Állítsa le az **smmContactPersonCDSV2Entity** és a **CustCustomerV3Entity** entitáson létrehozott összes kettős írású leképezést.
3. Indítsa el a leképezéseket. Az **smmContactPersonCDSV2Entity** és **CustCustomerV3Entity** entitásban, valamint a **BusinessEventsDefinition** táblában kevesebb rekordnak kell lennie, és a teljesítmény kismértékben javulhat.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
