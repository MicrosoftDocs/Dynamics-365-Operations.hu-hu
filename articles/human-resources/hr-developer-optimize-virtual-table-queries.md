---
title: Virtuális Dataverse-táblák lekérdezéseinek optimalizálása
description: A Dataverse virtuális tábla lekérdezések teljesítményének optimalizálása és hibaelhárítása
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8026abd5c3e0f9b78e8c016731fd7785490bc945
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891102"
---
# <a name="optimize-dataverse-virtual-table-queries"></a><span data-ttu-id="49953-103">Virtuális Dataverse-táblák lekérdezéseinek optimalizálása</span><span class="sxs-lookup"><span data-stu-id="49953-103">Optimize Dataverse virtual table queries</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="49953-104">Kiadás</span><span class="sxs-lookup"><span data-stu-id="49953-104">Issue</span></span>

### <a name="overview"></a><span data-ttu-id="49953-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="49953-105">Overview</span></span>

<span data-ttu-id="49953-106">Ha a Dataverse virtuális táblák segítségével integrációkat és más adatkapcsolatokat alakít ki ezzel: Dynamics 365 Human Resources, teljesítménybeli problémákat tapasztalhat a virtuális táblákra vonatkozó lekérdezésekkel.</span><span class="sxs-lookup"><span data-stu-id="49953-106">When using Dataverse virtual tables to develop integrations and other data connections with Dynamics 365 Human Resources, you can experience performance issues with queries against the virtual tables.</span></span> <span data-ttu-id="49953-107">A lekérdezés lassú végrehajtása több ügyfélen és felületen is történhet.</span><span class="sxs-lookup"><span data-stu-id="49953-107">The slow query execution can occur across various clients or interfaces.</span></span> <span data-ttu-id="49953-108">A problémát például a következő körülmények között tapasztalhatja:</span><span class="sxs-lookup"><span data-stu-id="49953-108">For example, you may experience the issue in the following circumstances:</span></span>

- <span data-ttu-id="49953-109">Virtuális tábla Dataverse web API-n keresztüli lekérdezésekor</span><span class="sxs-lookup"><span data-stu-id="49953-109">When querying a virtual table through the Dataverse Web API</span></span>
- <span data-ttu-id="49953-110">Power App virtuális táblához való létrehozásakor</span><span class="sxs-lookup"><span data-stu-id="49953-110">When creating a Power App against a virtual table</span></span>
- <span data-ttu-id="49953-111">Power BI jelentés készítése virtuális táblán</span><span class="sxs-lookup"><span data-stu-id="49953-111">When building a Power BI report on a virtual table</span></span>

<span data-ttu-id="49953-112">Ezeknél az interfésznél mind megvan a lehetőség a teljesítményproblémák megjelenésére.</span><span class="sxs-lookup"><span data-stu-id="49953-112">All these interfaces have the potential to surface the performance issue.</span></span>

<span data-ttu-id="49953-113">A Human Resources Dataverse virtuális tábláinál a lassú teljesítmény egyik oka a tábla [navigációs tulajdonságaihoz](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) kapcsolódó virtuális tábla idegen kulcsoszlopai.</span><span class="sxs-lookup"><span data-stu-id="49953-113">One cause of slow performance with Dataverse virtual tables for Human Resources is the foreign key columns of the virtual table related to the table's [navigation properties](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span></span> <span data-ttu-id="49953-114">Amikor navigációs tulajdonságokat hoz létre egy virtuális táblához, a rendszer automatikusan hozzáad egy idegenkulcs-oszlopot a táblához, amely a kapcsolódó virtuális tábla kulcsoszlopához tartozó kulcs értékét képviseli.</span><span class="sxs-lookup"><span data-stu-id="49953-114">When navigation properties are created for a virtual table, a foreign key column is automatically added to the table to represent the value of the key for the related virtual table's key column.</span></span> <span data-ttu-id="49953-115">Például a **_mshr_fk_person_id_value** oszlopot hozzáadja az **mshr_hcmworkerbaseentity** entitáshoz az **mshr_dirpersonentity** idegenkulcs-tulajdonságával.</span><span class="sxs-lookup"><span data-stu-id="49953-115">For example, the **_mshr_fk_person_id_value** column is added to the **mshr_hcmworkerbaseentity** entity with the foreign key property from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="49953-116">Az idegenkulcs-oszlopok értékeinek táblában való karbantartása miatt az értékek beolvasása hátrányosan befolyásolja a virtuális táblára vonatkozó lekérdezések teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="49953-116">Because of how the values for these foreign key columns are maintained in a table, fetching the values can have a negative impact on the performance of a query against the virtual table.</span></span>

### <a name="potential-symptoms"></a><span data-ttu-id="49953-117">Potenciális tünetek</span><span class="sxs-lookup"><span data-stu-id="49953-117">Potential symptoms</span></span>

<span data-ttu-id="49953-118">Ilyen hatás például a dolgozóra (**mshr_hcmworkerentity**) vagy az alap dolgozóra (**mshr_hcmworkerbaseentity**) vonatkozó lekérdezésekben látható.</span><span class="sxs-lookup"><span data-stu-id="49953-118">An example where you may see this impact is in queries against the Worker (**mshr_hcmworkerentity**) or Base worker (**mshr_hcmworkerbaseentity**) entity.</span></span> <span data-ttu-id="49953-119">A teljesítményprobléma többféleképpen is megjelenhet:</span><span class="sxs-lookup"><span data-stu-id="49953-119">You may see the performance issue manifest itself in a few different ways:</span></span>

- <span data-ttu-id="49953-120">**Lassú lekérdezés-végrehajtás**: A virtuális tábla lekérdezése visszaadhatja a várt eredményt, de a lekérdezés végrehajtása vártnál tovább tarthat.</span><span class="sxs-lookup"><span data-stu-id="49953-120">**Slow query execution**: The query against the virtual table may return the expected results, but take longer than expected to complete execution of the query.</span></span>
- <span data-ttu-id="49953-121">**Lekérdezés időtúllépése**: A lekérdezés időtúllépést okozhat, és a következő hibát adja vissza: „Token beszerezve Finance and Operations meghívására, de Finance and Operations InternalServerError típusú hibát adott vissza.”</span><span class="sxs-lookup"><span data-stu-id="49953-121">**Query timeout**: The query may time out and return the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type InternalServerError."</span></span>
- <span data-ttu-id="49953-122">**Váratlan hiba**: A lekérdezés 400-as hibatípust ad vissza a következő üzenettel: „Váratlan hiba történt.”</span><span class="sxs-lookup"><span data-stu-id="49953-122">**Unexpected error**: The query may return an error type 400 with the following message: "An unexpected error occurred."</span></span>

  ![400-as hibatípus a HcmWorkerBaseEntity esetében](./media/HcmWorkerBaseEntityErrorType400.png)

- <span data-ttu-id="49953-124">**Szabályozás**: A lekérdezés túlhasználhatja a kiszolgáló erőforrásait, és szabályozás tárgya lehet.</span><span class="sxs-lookup"><span data-stu-id="49953-124">**Throttling**: The query may overuse server resources, and become subject to throttling.</span></span> <span data-ttu-id="49953-125">Ebben az esetben a lekérdezés a következő hibát adja vissza: „Token beszerezve Finance and Operations meghívására, de Finance and Operations 429-es típusú hibát adott vissza.”</span><span class="sxs-lookup"><span data-stu-id="49953-125">In this case, the query returns the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type 429."</span></span> <span data-ttu-id="49953-126">A Human Resources szabályozásával kapcsolatos további tudnivalókat lásd: [Szabályozás – GYIK](./hr-admin-integration-throttling-faq.md).</span><span class="sxs-lookup"><span data-stu-id="49953-126">For more information in throttling in Human Resources, see [Throttling FAQ](./hr-admin-integration-throttling-faq.md).</span></span>

  ![429-as hibatípus a HcmWorkerBaseEntity esetében](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a><span data-ttu-id="49953-128">Felbontás</span><span class="sxs-lookup"><span data-stu-id="49953-128">Resolution</span></span>

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a><span data-ttu-id="49953-129">Az adatlekérdezésben szereplő oszlopok számának korlátozása</span><span class="sxs-lookup"><span data-stu-id="49953-129">Limit the number of columns included in your data query</span></span>

<span data-ttu-id="49953-130">A virtuális tábláknál a lekérdezés teljesítményének javítására a legtöbb lehetőséget tartalmazó módszerek egyike a lekérdezésben kiválasztott oszlopok számának korlátozása.</span><span class="sxs-lookup"><span data-stu-id="49953-130">With virtual tables, one of the methods with the greatest potential to improve query performance is to limit the number of columns selected in the query.</span></span> <span data-ttu-id="49953-131">A lekérdezés teljesítményének optimalizálásához az általános útmutatás az, hogy a lekérdezés által visszaadott oszlopokat csak a szükséges tulajdonságokra korlátozza.</span><span class="sxs-lookup"><span data-stu-id="49953-131">The general guidance for optimizing query performance is to limit the columns returned in your query to only those properties that you need.</span></span> <span data-ttu-id="49953-132">Ez különösen igaz a virtuális táblák idegenkulcs-oszlopaira.</span><span class="sxs-lookup"><span data-stu-id="49953-132">This is particularly true with the foreign key columns on virtual tables.</span></span> <span data-ttu-id="49953-133">Ha az integrációhoz vagy jelentéshez nincs szükség az idegenkulcs-oszlopok értékeire, akkor úgy struktúrálja a lekérdezést, hogy csak a szükséges oszlopokat válassza ki, kizárva az idegenkulcs-oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="49953-133">If you don't need the values in the foreign key columns for your integration or report, then structure the query to select only the columns you need, excluding the foreign key columns.</span></span>

#### <a name="selecting-columns-in-an-odata-query"></a><span data-ttu-id="49953-134">Oszlopok kiválasztása egy OData lekérdezésben</span><span class="sxs-lookup"><span data-stu-id="49953-134">Selecting columns in an OData query</span></span>

<span data-ttu-id="49953-135">A virtuális tábla Dataverse webes API-n keresztüli lekérdezése esetén a **$select** lekérdezési beállításával korlátozhatja a lekérdezésben szereplő oszlopok számát, és meghatározhatja, hogy mely oszlopokhoz kell visszaadni az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="49953-135">When querying a virtual table through the Dataverse Web API, you can limit the number of columns included in the query by using the **$select** system query option, and define the columns for which you need results returned.</span></span> <span data-ttu-id="49953-136">A teljesítmény maximalizálása érdekében zárja ki a lekérdezésből az idegenkulcs-oszlopokat (ezek az **_mshr_FK_** előtagúak).</span><span class="sxs-lookup"><span data-stu-id="49953-136">To maximize performance, exclude foreign key columns (those with the **_mshr_FK_** prefix) from the query.</span></span>

<span data-ttu-id="49953-137">Például a következő lekérdezés az **mshr_hcmworkerbaseentity** entitásra csak az **$select** lekérdezési beállítási záradékban szereplő oszlopokat tartalmazza, kizárva az idegenkulcs-értékeket.</span><span class="sxs-lookup"><span data-stu-id="49953-137">For example, the following query against the **mshr_hcmworkerbaseentity** entity will include only the columns included in the **$select** query option clause, excluding foreign key values.</span></span> <span data-ttu-id="49953-138">Ez jelentős javulást eredményez a teljesítményben egy olyan lekérdezéshez képest, amely az összes táblaoszlopot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="49953-138">This provides significant improvements in performance over a query that includes all table columns.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="49953-139">A kiválasztott oszlopok számának korlátozására vonatkozó javaslat akkor is érvényes, ha navigációs tulajdonságok segítségével az **$expand** lekérdezési lehetőséggel a kapcsolódó virtuális táblákra bővíti ki a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="49953-139">The recommendation to limit the number of columns selected also applies when using the **$expand** query option to expand the query to related virtual tables through navigation properties.</span></span> <span data-ttu-id="49953-140">A következő lekérdezés például az **mshr_hcmworkerbaseentity** entitásból tartalmazza az oszlopokat, kibővített oszlopokkal az **mshr_dirpersonentity** entitásból.</span><span class="sxs-lookup"><span data-stu-id="49953-140">For example, the following query includes columns from the **mshr_hcmworkerbaseentity** entity with expanded columns from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="49953-141">Ne feledje, a **$select** lekérdezési beállítás is része az **$expand** lekérdezési beállítási záradéknak.</span><span class="sxs-lookup"><span data-stu-id="49953-141">Note that the **$select** query option is also included in the **$expand** query option clause.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="49953-142">Amikor a **$select** lekérdezési beállítással adatbeolvasására használja ezt a módszert az **$expand** lekérdezési beállítási záradékkal, akkor általában nagyobb teljesítményjavulást fog látni, amikor az entitások közötti navigációs tulajdonság több az egyhez kapcsolat.</span><span class="sxs-lookup"><span data-stu-id="49953-142">When using this method of retrieving data with the **$select** query option in the **$expand** query option clause, you will typically see greater performance improvements when the navigation property between the entities is a many-to-one relationship.</span></span> <span data-ttu-id="49953-143">Egy-több kapcsolat kibontása során előfordulhat, hogy a lekérdezés végrehajtási ideje nem fog ugyanannyira csökkenni.</span><span class="sxs-lookup"><span data-stu-id="49953-143">You may not see the same decrease in query execution time when expanding a one-to-many relationship.</span></span> <span data-ttu-id="49953-144">A Dataverse virtuális táblák kapcsolatdefiníciójáról további tudnivalókat lásd: [Táblakapcsolatok](/powerapps/maker/data-platform/create-edit-entity-relationships).</span><span class="sxs-lookup"><span data-stu-id="49953-144">For more information on relationship definition for Dataverse virtual tables, see [Table relationships](/powerapps/maker/data-platform/create-edit-entity-relationships).</span></span>

<span data-ttu-id="49953-145">A **$select** és az **$expand** rendszerlekérdezési lehetőségek Dataverse webes API használatával kapcsolatban lásd: [Kapcsolódó entitásrekordok beolvasása lekérdezéssel](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span><span class="sxs-lookup"><span data-stu-id="49953-145">For more information on using the **$select** and **$expand** system query options in the Dataverse Web API, see [Retrieve related entity records with a query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span></span>

#### <a name="selecting-columns-in-power-bi"></a><span data-ttu-id="49953-146">Oszlopok kiválasztása a következőben: Power BI</span><span class="sxs-lookup"><span data-stu-id="49953-146">Selecting columns in Power BI</span></span>

<span data-ttu-id="49953-147">Ha a Dataverse virtuális táblára irányuló Power BI jelentés készítése során lassú teljesítményt tapasztal, akkor javíthatja a teljesítményt, ha a táblából a jelentéshez kiválasztott oszlopokból idegen kulcs oszlopokat kizár.</span><span class="sxs-lookup"><span data-stu-id="49953-147">If you experience any of the aforementioned indications of slow performance when building a Power BI report against a Dataverse virtual table, you can improve the performance by excluding foreign key columns from the columns selected from the table for the report.</span></span> <span data-ttu-id="49953-148">Ha például a kiválasztott entitásra vonatkozó Power BI Desktop jelentést szeretne létrehozni **mshr_hcmworkerbaseentity** a következő lépések segítségével kiválaszthatja azokat az oszlopokat, amelyek bele szeretné foglalni őket a jelentés lekérdezésbe.</span><span class="sxs-lookup"><span data-stu-id="49953-148">For example, if you are using Power BI Desktop to create a report against the **mshr_hcmworkerbaseentity** entity, you can use the following steps to select the columns you want included in the report query.</span></span>

1. <span data-ttu-id="49953-149">A Power BI Desktop esetében válassza a **További...** elemet a műveletszalag **Adat lekérése** legördülő listájáról.</span><span class="sxs-lookup"><span data-stu-id="49953-149">In Power BI Desktop, select **More...** from the **Get data** drop-down list on the action ribbon.</span></span>
2. <span data-ttu-id="49953-150">Az **Adat bekeresése** ablakban írja be: **Common Data Service** a keresőmezőbe, válassza ki a **Common Data Service** csatlakoztatót, majd válassza a **Csatlakozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49953-150">In the **Get Data** window, enter **Common Data Service** in the search box, select the **Common Data Service** connector, and select **Connect**.</span></span>
3. <span data-ttu-id="49953-151">Az Common Data Service ablakának **Kiszolgáló URL** mezőjében adja meg a Dataverse környezethez tartozó szervezeti URI-t, és válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="49953-151">In the **Server Url** field of the Common Data Service window, enter the organization URI for your Dataverse environment, and select **OK**.</span></span>
  
   ![Adja meg az URI-nevét a Dataverse környezetnek](./media/PowerBIDataverseURLSetup.png)
  
4. <span data-ttu-id="49953-153">Bontsa ki az **Entitások** csomópontot a navigátor ablakban.</span><span class="sxs-lookup"><span data-stu-id="49953-153">In the Navigator window, expand the **Entities** node.</span></span>
5. <span data-ttu-id="49953-154">A keresési mezőbe írja be: **mshr_hcmworkerbaseentity**, majd válassza ki az entitást.</span><span class="sxs-lookup"><span data-stu-id="49953-154">In the search box, enter **mshr_hcmworkerbaseentity**, and select the entity.</span></span>
6. <span data-ttu-id="49953-155">Válassza az **Adatok átalakítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="49953-155">Select **Transform Data**.</span></span>
7. <span data-ttu-id="49953-156">A Power Query Editor ablakban válassza a **Speciális szerkesztő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49953-156">In the Power Query Editor window, select **Advanced Editor**.</span></span>
8. <span data-ttu-id="49953-157">A **Speciális szerkesztő** ablakban frissítse a lekérdezést úgy, hogy az alábbihoz hasonló legyen, és szükség szerint adja hozzá vagy távolítsa el az oszlopokat a tömbhöz.</span><span class="sxs-lookup"><span data-stu-id="49953-157">In the **Advanced Editor** window, update the query to look like the below, adding or removing any columns to the array as needed.</span></span>

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![A lekérdezés frissítése a Power Query Editor speciális szerkesztőjével](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. <span data-ttu-id="49953-159">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="49953-159">Select **Done**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49953-160">Ha frissítés előtt 429-es típusú hibát kapott a lekérdezésből, lehet, hogy a lekérdezés sikeres befejezéséhez meg kell várnia az újrapróbálkozási időszakot.</span><span class="sxs-lookup"><span data-stu-id="49953-160">If you previously received an error of type 429 from the query prior to updating, you may need to wait for the retry period prior to refreshing the query for it to complete successully.</span></span>

10. <span data-ttu-id="49953-161">Kattintson a **Bezárás és alkalmazás** elemre a Power Query Editor műveletszalagján.</span><span class="sxs-lookup"><span data-stu-id="49953-161">Click **Close & Apply** on the Power Query Editor action ribbon.</span></span>

<span data-ttu-id="49953-162">Ezután el lehet kezdeni a Power BI jelentésnek a virtuális táblában kiválasztott oszlopok alapján való megépítését.</span><span class="sxs-lookup"><span data-stu-id="49953-162">You're then able to begin building your Power BI report against the columns selected from the virtual table.</span></span>

#### <a name="selecting-columns-in-power-apps"></a><span data-ttu-id="49953-163">Oszlopok kiválasztása a következőben: Power Apps</span><span class="sxs-lookup"><span data-stu-id="49953-163">Selecting columns in Power Apps</span></span>

<span data-ttu-id="49953-164">Hasonló a Dataverse webes API-lekérdezésekhez és ehhez: Power BI, javítható a Power Apps lekérdezések teljesítménye a Dataverse virtuális táblák alapján, ha az alkalmazásból kihagyja a kapcsolódó táblák oszlopait.</span><span class="sxs-lookup"><span data-stu-id="49953-164">Similar to Dataverse Web API queries and Power BI, you can improve query performance for Power Apps based on Dataverse virtual tables by excluding columns of related tables from your app.</span></span> <span data-ttu-id="49953-165">Ha egy kapcsolódó tábla bármelyik oszlopa megtalálható egy oldalon, akkor az adatok beolvasására megadott kérés URL-címe a kapcsolódó tábla idegen kulcstulajdonságait is tartalmazni fogja.</span><span class="sxs-lookup"><span data-stu-id="49953-165">If any columns from a related table have been included on a page, then the request URL constructed to fetch the data will include foreign key properties of the related table.</span></span> <span data-ttu-id="49953-166">Ez a fenti [OData lekérdezés oszlopainak kiválasztása](#selecting-columns-in-power-apps) példához hasonlítva további adatkeresések miatt jelentkező teljesítménycsökkentést eredményez.</span><span class="sxs-lookup"><span data-stu-id="49953-166">This, as in the examples of [Selecting columns in an OData Query](#selecting-columns-in-power-apps) above, reduces performance by causing additional data lookups.</span></span>

<span data-ttu-id="49953-167">Ellen elkerülésére ellenőrizheti, hogy a Power App alkalmazás egyik adatképernyője sem tartalmazza a kapcsolódó táblák adatmezőit.</span><span class="sxs-lookup"><span data-stu-id="49953-167">To work around this, you can validate that no data fields from related tables have been included on any data form of your Power App.</span></span>

1. <span data-ttu-id="49953-168">A Fa nézet ablakban válassza ki a képernyő adatképernyőjét.</span><span class="sxs-lookup"><span data-stu-id="49953-168">In the Tree view pane, select the data form for the screen.</span></span>
2. <span data-ttu-id="49953-169">A **Tulajdonságok** panelen válassza a **Szerkesztés** lehetőséget a **Mezők** tulajdonságnál.</span><span class="sxs-lookup"><span data-stu-id="49953-169">In the **Properties** pane, select **Edit** on the **Fields** property.</span></span>
3. <span data-ttu-id="49953-170">Az **Adatok** ablakban ellenőrizze, hogy a kijelölt mezők egyike sem tartozik-e az adatforrás virtuális táblájához.</span><span class="sxs-lookup"><span data-stu-id="49953-170">In the **Data** pane, verify that none of the selected fields are fields of the virtual table of the data source.</span></span>

<span data-ttu-id="49953-171">Ha például az alkalmazás egy lapján található egyik adatmező másik táblára, például a **ThisItem.Worker.Name** táblára hivatkozik, és a **Worker** a kapcsolódó tábla, akkor az adatok beolvasása során csökkenhet a teljesítmény.</span><span class="sxs-lookup"><span data-stu-id="49953-171">For example, if one of the data fields included on a page in the app references another table, such as **ThisItem.Worker.Name**, where **Worker** is the related table, there is a potential for reduced performance in fetching the data.</span></span>

<span data-ttu-id="49953-172">A [Power Apps monitor](/powerapps/maker/monitor-overview) segítségével gondoskodhat arról, hogy a lekérdezésben csak a szükséges oszlopok szerepeljenek az adatok Power Appból történő lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="49953-172">You can use the [Power Apps Monitor](/powerapps/maker/monitor-overview) to ensure that only the columns you need are being included in the query to get the data for the Power App.</span></span> <span data-ttu-id="49953-173">A getRows művelethez létrehozott URL-t megtekintheti annak a biztosításához, hogy az alkalmazáshoz kiválasztott oszlopok optimálisak legyenek az adatok beolvasásához.</span><span class="sxs-lookup"><span data-stu-id="49953-173">You can view the URL constructed for the getRows operation to ensure the columns you have selected for your app will be optimal for retrieving the data.</span></span>

![A getData művelet elemzéséhez használja a Power Apps monitort.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a><span data-ttu-id="49953-175">Az adatlekérdezés szűrése</span><span class="sxs-lookup"><span data-stu-id="49953-175">Filtering the data query</span></span>

<span data-ttu-id="49953-176">A lekérdezés végrehajtási teljesítményének javítására egy másik módszer a lekérdezés eredményeiben visszaadott rekordok számának korlátozása.</span><span class="sxs-lookup"><span data-stu-id="49953-176">Another method for improving query execution performance is to limit the number of records returned in the query results.</span></span> <span data-ttu-id="49953-177">Ehhez szűrni kell az eredményeket, hogy csak a szükséges rekordokat kapja meg.</span><span class="sxs-lookup"><span data-stu-id="49953-177">You can do this by filtering the results to ensure that you are only receiving the records you need.</span></span>

<span data-ttu-id="49953-178">További tájékoztatás a lekérdezési adatok szűréséről itt található: [Eredmények szűrése](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results).</span><span class="sxs-lookup"><span data-stu-id="49953-178">See [Filter results](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) for more information on filtering query data.</span></span>

### <a name="limiting-the-page-size-of-the-query"></a><span data-ttu-id="49953-179">A lekérdezés oldalméretének korlátozása</span><span class="sxs-lookup"><span data-stu-id="49953-179">Limiting the page size of the query</span></span>

<span data-ttu-id="49953-180">Ha nagy adathalmazokkal dolgozik, a lekérdezés eredményeit több lapra oszthatja úgy, hogy hozzáadja a `odata.maxpagesize` preferenciafejlécet az adatlekérdezésekhez.</span><span class="sxs-lookup"><span data-stu-id="49953-180">If you're working with large data sets, you can divide query results into multiple pages by adding the `odata.maxpagesize` preference header to data queries.</span></span>

<span data-ttu-id="49953-181">További tájékoztatás a lapozásról: [Adja meg az egy oldalon visszaadni kívánt entitások számát](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span><span class="sxs-lookup"><span data-stu-id="49953-181">For more information on paging, see [Specify the number of entities to return in a page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span></span>

## <a name="see-also"></a><span data-ttu-id="49953-182">Lásd még</span><span class="sxs-lookup"><span data-stu-id="49953-182">See also</span></span>

- [<span data-ttu-id="49953-183">Dataverse virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="49953-183">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)
- [<span data-ttu-id="49953-184">Human Resources – virtuális táblák – GYIK</span><span class="sxs-lookup"><span data-stu-id="49953-184">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)
- [<span data-ttu-id="49953-185">Szabályozás – GYIK</span><span class="sxs-lookup"><span data-stu-id="49953-185">Throttling FAQ</span></span>](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]