---
title: "A pénzügyi jelentési adatpiac alaphelyzetbe állítása."
description: "Ez a témakör a pénzügyi jelentési adatpiac alaphelyzetbe állítását ismerteti."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: hu-hu
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a>A pénzügyi jelentési adatpiac alaphelyzetbe állítása.

[!include[banner](../includes/banner.md)]

Ez a témakör a pénzügyi jelentési adatpiac alaphelyzetbe állítását mutatja be a következő verziókhoz :

- Microsoft Dynamics 365 for Finance and Operations: Financial Reporting, 7.2.6.0-s és későbbi verziók
- Microsoft Dynamics 365 for Finance and Operations: Financial Reporting, 7.0.10000.4-es és későbbi verziók
- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (on-premises)

A Finance and Operations Financial Reporting 7.2.6.0-s verziójának beszerzéséhez töltse le a 4052514-es tudásbáziscikket a <https://support.microsoft.com/en-us/help/4052514> oldalról.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>A pénzügyi jelentési adatpiac alaphelyzetbe állítása a Finance and Operations Financial Reporting 7.2.6.0-s és későbbi verzióinál

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>A pénzügyi jelentési adatpiac alaphelyzetbe állítása a Jelentéstervezőből

> [!NOTE]
> Ezen folyamat lépései a Finance and Operations Financial Reporting 7.2.6.0 és későbbi verzióiban támogatottak. Ha Ön korábbi kiadást használ, forduljon a támogatási csapathoz segítségért.

Bizonyos esetekben előfordulhat, hogy alaphelyzetbe kell állítania a pénzügyi jelentési adatpiacot. A feladat a Jelentéstervező ügyfélprogramban végezhető el. Íme néhány forgatókönyv, ahol alaphelyzetbe kell állítania az adatpiacot:

- A Finance and Operations adatbázist visszaállították, de az adatpiac adatbázis visszaállítására nem került sor.
- Egy adott időszakban hibás adatok jelennek meg.
- A Támogatás arra utasítja, hogy hibaelhárítás részeként állítsa alaphelyzetbe az adatpiacot.

Az adatpiac alaphelyzetbe állítása csak olyan időszakokban végezhető el, amikor az adatbázisban az adatfeldolgozás mennyisége kicsi. A pénzügyi jelentések nem érhetők el a visszaállítási folyamat során.

#### <a name="reset-the-data-mart"></a>Az adatpiac alaphelyzetbe állítása

Az adatpiac visszaállításához a Jelentéstervezőben az **Eszközök** menüben válassza a **Data Mart alaphelyzetbe állítása** lehetőséget. A megjelenő párbeszédpanel két részből áll: **Statisztika** és **Alaphelyzetbe állítás**.

[![Data Mart alaphelyzetbe állítása párbeszédpanel](./media/Statistics.png)](./media/Statistics.png)

##### <a name="integration-attempts"></a>Integrációs kísérletek

Az **Integrációs kísérletek** rács mutatja, hogy a rendszer hányszor próbált tranzakciókat integrálni. A rendszer napokon keresztül továbbra is törekszik az adatok integrálására, ha az első néhány kísérlet sikertelen volt. Akkor tudhatja, hogy az adatpiacot alaphelyzetbe kell állítani, ha a kísérletek száma 8 vagy több, és ha sok dimenziókombináció vagy tranzakciós rekord van jelen. Ebben a helyzetben az adatokból nem lehet jelentést készíteni.

##### <a name="data-status"></a>Adatok állapota

Az **Adatok állapota** rács pillanatképet ad az adatpiacon található tranzakciókról, átváltási árfolyamokról és dimenzióértékekről. Az elavult rekordok nagy száma azt jelzi, hogy számos rekordfrissítésre került sor. Ebben a helyzetben a jelentések generálása lassabb lehet.

##### <a name="misaligned-main-account-categories"></a>Rosszul igazított főszámla-kategóriák

Ha olyan kiadást használ, amely korábbi, mint a Microsoft Dynamics 365 for Finance and Operations Financial Feporting 7.2.1-es kiadása, előfordulhat, hogy vissza kell állítania az adatpiacot, ha átnevez számlákat, illetve áthelyez számlákat a számlakategóriák között. Ezek a műveletek a főszámla-kategóriák téves igazítását okozhatják. A **Rosszul igazított főszámla-kategóriák** mező mutatja, hogy tapasztalja-e ezt a problémát.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Az adatpiac alaphelyzetbe állítása a Finance and Operations Financial Reporting 7.2.6.0 kiadásában

Az adatpiac alaphelyzetbe állításához a Finance and Operations Financial Reporting 7.2.6.0 és korábbi kiadásában a **Data Mart alaphelyzetbe állítása** párbeszédablakban jelölje be a **Data Mart alaphelyzetbe állítása** jelölőnégyzetet, majd válassza az **OK** gombot. A data mart alaphelyzetbe állítását csakis ütemezett leállás során kell elvégezni.

[![Data Mart alaphelyzetbe állítása jelölőnégyzet](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Az adatpiac alaphelyzetbe állítása és okának kiválasztása a Microsoft Dynamics 365 for Finance and Operations Financial reporting 7.3.0 kiadásában

Ha úgy dönt, hogy az adatpiac alaphelyzetbe állítására van szükség, jelölje be a **Data Mart alaphelyzetbe állítása** jelölőnégyzetet, majd válasszon ki egy okot az **Ok** mezőben. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Hiányzó vagy hibás adatok** – A statisztikák alapján megállapította, hogy adatok hiányozhatnak. A folytatás előtt azt javasoljuk, hogy a Támogatással együtt állapítsa meg, mi volt ennek a legfőbb oka.
- **Adatbázis visszaállítása** – A Finance and Operations adatbázist visszaállították, de a pénzügyi jelentési adatpiac visszaállítására nem került sor.
- **Egyéb** – más okból kerül sor az adatpiac alaphelyzetbe állítására. Ha aggódik amiatt, hogy probléma van, forduljon a Támogatáshoz annak azonosításához.

> [!NOTE]
> Ellenőrizze, hogy az összes meglévő feladat integrálása befejeződött-e, mielőtt elvégezné a lépéseket. Az integráció állapotának megtekintéséhez válassza az **Eszközök** &gt; **Integráció állapota** elemet.

#### <a name="clear-users-and-companies"></a>Felhasználók és vállalatok törlése

Jelölje be a **Felhasználók és vállalatok törlése** jelölőnégyzetet, ha visszaállította az adatbázist, de ezt követően módosította a felhasználókat vagy a vállalatokat. Ezt a jelölőnégyzetet ritkán kell kiválasztania.

Ha készen áll az alaphelyzetbe állítás megkezdéséhez, válassza az **OK** gombot. A rendszer kéri, hogy erősítse meg, hogy készen áll a folyamat elindítására. Ne feledje, hogy a pénzügyi jelentéskészítés nem lesz elérhető a visszaállítás alatt és az azt követő kezdeti adatintegráció során.

Ha szeretné ellenőrizni az integráció állapotát, akkor válassza az **Eszközök** &gt; **Integráció állapota** lehetőséget az integráció utolsó futtatásának és állapotának megjelenítéséhez.

[![Az integráció állapotának megjelenítése](./media/Integration.png)](./media/Integration.png)

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>A pénzügyi jelentési adatpiac alaphelyzetbe állítása a Finance and Operations Financial Reporting 7.0.10000.4-s és későbbi verzióinál

Ha bármikor visszaállítja a Dynamics 365 for Operations adatbázist egy biztonsági másolatból, vagy átmásolja az adatbázist egy másik környezetből, az e szakaszban található lépéseket kell követnie annak érdekében, hogy a pénzügyi jelentési adatpiac megfelelően használja a visszaállított Finance and Operations adatbázist.

> [!NOTE]
> A folyamat lépései a Microsoft Dynamics AX 7.0.1 verzió (2016. május) kiadásánál támogatottak (7.0.1265.23014 alkalmazásbuild és 7.0.10000.4 Financial reporting build), valamint az újabb verzióknál. Ha a Finance and Operations egy korábbi verziójával rendelkezik, lépjen kapcsolatba támogatással segítségért.

### <a name="export-report-definitions"></a>Jelentésdefiníciók exportálása

Először kövesse ezeket a lépéseket a jelentéstervek exportálásához a Jelentéskészítőből.

1. A Jelentéstervezőben válassza a **Vállalat** &gt; **Építőelem-csoportok** lehetőséget.
2. Válassza ki az exportálandó építőelem-csoportot, majd válassza az **Export** lehetőséget.

    > [!NOTE]
    > A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.

3. Válassza ki a jelentésdefiníciókat az exportáláshoz:

    - Ha az összes jelentésdefiníciót és társított építőelemet exportálni szeretné, válassza az **Az összes kijelölése** elemet.
    - Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához válassza a megfelelő lapot, majd válassza ki az exportálandó tételeket. Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl billentyűt. Ha jelentéseket jelöl ki az exportálásához, a rendszer a társított sorokat, oszlopokat, fákat és dimenziókészleteket is kijelöli.

4. Válassza az **Exportálás** lehetőséget.
5. Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyet, ahol menteni szeretné az exportált jelentésdefiníciókat.
6. Válassza a **Mentés** lehetőséget.

A fájlt átmásolhatja vagy feltöltheti egy biztonságos helyre. Ily módon a fájl később importálható egy másik környezetbe. A Microsoft Azure tárolófiók használatával kapcsolatos információkért lásd: [Adatátvitel az AzCopy parancssori segédprogrammal](/azure/storage/storage-use-azcopy).

> [!NOTE]
> A Dynamics 365 for Finance and Operations megállapodás részeként a Microsoft nem biztosít tárolófiókot. Be kell szereznie egy tárolófiókot, vagy egy külön Azure-előfizetésből származó tárolófiókot kell használnia.

> [!WARNING]
> Legyen tisztában a D meghajtó viselkedésével az Azure virtuális gépeken (VM-eken). Az exportált épületblokk-csoportokat ne tárolja véglegesen a D meghajtón. További információ az ideiglenes meghajtókról: [A Windows Azure virtuális gépek ideiglenes meghajtóinak ismertetése](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Szolgáltatások leállítása

A következő Microsoft Windows szolgáltatások nyitott kapcsolatot létesítenek a Finance and Operations adatbázissal. Ezért a Távoli asztal segítségével csatlakoznia kell az összes számítógéphez a környezetében, és le kell állítania le ezeket a szolgáltatásokat a services.msc segítségével:

- Webes közzétételi szolgáltatás (az összes Application Object Servers [AOS] számítógépen)
- Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)
- Management Reporter 2012 Process Service (csak a Business intelligence [BI] számítógépeken)

### <a name="reset"></a>Alaphelyzet

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Töltse le a legújabb MinorVersionDataUpgrade.zip csomagot

Töltse le a legújabb MinorVersionDataUpgrade.zip csomagot. Az adatfrissítési csomag helyes verziójának megkeresésével és letöltésével kapcsolatban lásd: [A legfrissebb adatfrissítési telepíthető csomag letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). A MinorVersionDataUpgrade.zip csomag letöltéséhez nincs szükség frissítésre. Ezért csak kövesse az adott témakör „A legfrissebb adatok frissítési telepíthető csomag letöltése” szakaszában leírt lépéseket. A témakörben szereplő minden egyéb lépést kihagyhat.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Parancsfájl-műveletek futtatása a Dynamics 365 for Finance and Operations adatbázison

Futtassa a következő parancsfájlokat a Dynamics 365 for Finance and Operations adatbázison (nem a Financial reporting adatbázison):

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Ezeket a parancsfájlok segítenek garantálni, hogy helyesek legyenek a felhasználók, a szerepkörök és a változáskövetési beállítások.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Futtasson egy Windows PowerShell parancsot az adatbázis visszaállításához

Az AOS-számítógépen indítsa el a Microsoft Windows PowerShell szolgáltatást rendszergazdaként, majd futtassa a következő parancsokat a Dynamics 365 for Finance and Operations és a Financial reporting közti integráció alaphelyzetbe állításához.

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

Itt a **Reset-DatamartIntegration** utasítás paramétereinek magyarázata:

- Az **-Reason** érvényes értékei: **SERVICING**, **BADDATA** és **OTHER**.
- A **ReasonDetail** paraméter szabad szöveg.
- A távmérő/környezet felügyelete végzi az ok és az ok részletei rögzítését.

> [!NOTE]
> Miután futtatta a parancsokat, az **Y** megadásával meg kell erősítenie, hogy vissza akarja állítani az adatbázist.

#### <a name="restart-services"></a>Szolgáltatások újraindítása

A korábban leállított szolgáltatások újraindításához használja a Services.msc parancsot:

- Webes közzétételi szolgáltatás (az összes AOS-számítógépen)
- Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)
- Management Reporter 2012 Process Service (csak a BI-számítógépeken)

#### <a name="import-report-definitions"></a>Jelentésdefiníciók importálása

Importálja a jelentésterveket a Jelentéstervezőből az exportálás során létrehozott fájl használatával.

1. A Jelentéstervezőben válassza a **Vállalat** &gt; **Építőelem-csoportok** lehetőséget.
2. Válassza ki az exportálandó építőelem-csoportot, majd válassza az **Export** lehetőséget.

    > [!NOTE]
    > A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.

3. Válassza ki az **Alapértelmezett** építőelemet, majd válassza az **Importálás** lehetőséget.
4. Válassza ki az exportált jelentésdefiníciókat tartalmazó fájlt, és válassza a **Megnyitás** lehetőséget.
5. Az **Importálás** párbeszédpanelen válassza ki az importálni kívánt jelentésdefiníciókat:

    - Ha az összes jelentésdefiníciót és társított építőelemet importálni szeretné, válassza **Az összes kijelölése** elemet.
    - Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálni kívánt elemeket.

6. Válassza az **Importálás** lehetőséget.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Az adatpiac alaphelyzetbe állítása a Finance and Operations (on-premises) rendszerben

1. Az összes felhasználót utasítsa arra, hogy lépjen ki a Jelentéstervezőből és a Finance and Operations pénzügyi jelentési területéről.
2. Futtassa a következő parancsfájlt a Financial reporting adatbázison (MRDB).

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. A Finance and Operations adatbázis (AXDB) FINANCIALREPORTS táblájának összes rekordját csonkolja vagy törölje.
4. A Finance and Operations adatbázis esetlegesen létező FINANCIALREPORTVERSION táblájának összes rekordját csonkolja vagy törölje. Ha a tábla nem létezik a Finance and Operations adatbázisban, hagyja ki ezt a lépést.
5. Futtassa a **ResetDatamart.sql** parancsfájlt a Financial reporting adatbázison. Ez a parancsfájl letiltja az adatpiac integrációját, törli az adatpiac összes adatát, majd újraindítja az adatpiac integrációját.

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. A alaphelyzetbe állítás után manuálisan ellenőrizheti az adatok újbóli betöltését a Financial reporting adatbázison futtatott következő lekérdezéssel.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Győződjön meg arról, hogy rendelkezik-e az összes sor egy **LastRunTime** értékkel, és hogy a **StateType** értéke **5**. A **StateType** **5** értéke jelzi, hogy az adatok újratöltése sikeres volt. A **7** érték a hibás állapotot jelzi. Előfordul, a szervezeti hierarchia leképezése ezt az állapotot tartalmazza az első futtatáskor. Azonban a hibaállapot ilyenkor elvileg automatikusan megoldódik.

