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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66fb9f2b50079b5eb4eb16da17b8a473d687d354
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054908"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Virtuális Dataverse-táblák lekérdezéseinek optimalizálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Kiadás

### <a name="overview"></a>Áttekintés

Ha a Dataverse virtuális táblák segítségével integrációkat és más adatkapcsolatokat alakít ki ezzel: Dynamics 365 Human Resources, teljesítménybeli problémákat tapasztalhat a virtuális táblákra vonatkozó lekérdezésekkel. A lekérdezés lassú végrehajtása több ügyfélen és felületen is történhet. A problémát például a következő körülmények között tapasztalhatja:

- Virtuális tábla Dataverse web API-n keresztüli lekérdezésekor
- Power App virtuális táblához való létrehozásakor
- Power BI jelentés készítése virtuális táblán

Ezeknél az interfésznél mind megvan a lehetőség a teljesítményproblémák megjelenésére.

A Human Resources Dataverse virtuális tábláinál a lassú teljesítmény egyik oka a tábla [navigációs tulajdonságaihoz](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) kapcsolódó virtuális tábla idegen kulcsoszlopai. Amikor navigációs tulajdonságokat hoz létre egy virtuális táblához, a rendszer automatikusan hozzáad egy idegenkulcs-oszlopot a táblához, amely a kapcsolódó virtuális tábla kulcsoszlopához tartozó kulcs értékét képviseli. Például a **_mshr_fk_person_id_value** oszlopot hozzáadja az **mshr_hcmworkerbaseentity** entitáshoz az **mshr_dirpersonentity** idegenkulcs-tulajdonságával. Az idegenkulcs-oszlopok értékeinek táblában való karbantartása miatt az értékek beolvasása hátrányosan befolyásolja a virtuális táblára vonatkozó lekérdezések teljesítményét.

### <a name="potential-symptoms"></a>Potenciális tünetek

Ilyen hatás például a dolgozóra (**mshr_hcmworkerentity**) vagy az alap dolgozóra (**mshr_hcmworkerbaseentity**) vonatkozó lekérdezésekben látható. A teljesítményprobléma többféleképpen is megjelenhet:

- **Lassú lekérdezés-végrehajtás**: A virtuális tábla lekérdezése visszaadhatja a várt eredményt, de a lekérdezés végrehajtása vártnál tovább tarthat.
- **Lekérdezés időtúllépése**: A lekérdezés időtúllépést okozhat, és a következő hibát adja vissza: „Token beszerezve Finance and Operations meghívására, de Finance and Operations InternalServerError típusú hibát adott vissza.”
- **Váratlan hiba**: A lekérdezés 400-as hibatípust ad vissza a következő üzenettel: „Váratlan hiba történt.”

  ![400-as hibatípus a HcmWorkerBaseEntity esetében](./media/HcmWorkerBaseEntityErrorType400.png)

- **Szabályozás**: A lekérdezés túlhasználhatja a kiszolgáló erőforrásait, és szabályozás tárgya lehet. Ebben az esetben a lekérdezés a következő hibát adja vissza: „Token beszerezve Finance and Operations meghívására, de Finance and Operations 429-es típusú hibát adott vissza.” A Human Resources szabályozásával kapcsolatos további tudnivalókat lásd: [Szabályozás – GYIK](./hr-admin-integration-throttling-faq.md).

  ![429-as hibatípus a HcmWorkerBaseEntity esetében](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Felbontás

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Az adatlekérdezésben szereplő oszlopok számának korlátozása

A virtuális tábláknál a lekérdezés teljesítményének javítására a legtöbb lehetőséget tartalmazó módszerek egyike a lekérdezésben kiválasztott oszlopok számának korlátozása. A lekérdezés teljesítményének optimalizálásához az általános útmutatás az, hogy a lekérdezés által visszaadott oszlopokat csak a szükséges tulajdonságokra korlátozza. Ez különösen igaz a virtuális táblák idegenkulcs-oszlopaira. Ha az integrációhoz vagy jelentéshez nincs szükség az idegenkulcs-oszlopok értékeire, akkor úgy struktúrálja a lekérdezést, hogy csak a szükséges oszlopokat válassza ki, kizárva az idegenkulcs-oszlopokat.

#### <a name="selecting-columns-in-an-odata-query"></a>Oszlopok kiválasztása egy OData lekérdezésben

A virtuális tábla Dataverse webes API-n keresztüli lekérdezése esetén a **$select** lekérdezési beállításával korlátozhatja a lekérdezésben szereplő oszlopok számát, és meghatározhatja, hogy mely oszlopokhoz kell visszaadni az eredményeket. A teljesítmény maximalizálása érdekében zárja ki a lekérdezésből az idegenkulcs-oszlopokat (ezek az **_mshr_FK_** előtagúak).

Például a következő lekérdezés az **mshr_hcmworkerbaseentity** entitásra csak az **$select** lekérdezési beállítási záradékban szereplő oszlopokat tartalmazza, kizárva az idegenkulcs-értékeket. Ez jelentős javulást eredményez a teljesítményben egy olyan lekérdezéshez képest, amely az összes táblaoszlopot tartalmazza.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

A kiválasztott oszlopok számának korlátozására vonatkozó javaslat akkor is érvényes, ha navigációs tulajdonságok segítségével az **$expand** lekérdezési lehetőséggel a kapcsolódó virtuális táblákra bővíti ki a lekérdezést. A következő lekérdezés például az **mshr_hcmworkerbaseentity** entitásból tartalmazza az oszlopokat, kibővített oszlopokkal az **mshr_dirpersonentity** entitásból. Ne feledje, a **$select** lekérdezési beállítás is része az **$expand** lekérdezési beállítási záradéknak.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Amikor a **$select** lekérdezési beállítással adatbeolvasására használja ezt a módszert az **$expand** lekérdezési beállítási záradékkal, akkor általában nagyobb teljesítményjavulást fog látni, amikor az entitások közötti navigációs tulajdonság több az egyhez kapcsolat. Egy-több kapcsolat kibontása során előfordulhat, hogy a lekérdezés végrehajtási ideje nem fog ugyanannyira csökkenni. A Dataverse virtuális táblák kapcsolatdefiníciójáról további tudnivalókat lásd: [Táblakapcsolatok](/powerapps/maker/data-platform/create-edit-entity-relationships).

A **$select** és az **$expand** rendszerlekérdezési lehetőségek Dataverse webes API használatával kapcsolatban lásd: [Kapcsolódó entitásrekordok beolvasása lekérdezéssel](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Oszlopok kiválasztása a következőben: Power BI

Ha a Dataverse virtuális táblára irányuló Power BI jelentés készítése során lassú teljesítményt tapasztal, akkor javíthatja a teljesítményt, ha a táblából a jelentéshez kiválasztott oszlopokból idegen kulcs oszlopokat kizár. Ha például a kiválasztott entitásra vonatkozó Power BI Desktop jelentést szeretne létrehozni **mshr_hcmworkerbaseentity** a következő lépések segítségével kiválaszthatja azokat az oszlopokat, amelyek bele szeretné foglalni őket a jelentés lekérdezésbe.

1. A Power BI Desktop esetében válassza a **További...** elemet a műveletszalag **Adat lekérése** legördülő listájáról.
2. Az **Adat bekeresése** ablakban írja be: **Common Data Service** a keresőmezőbe, válassza ki a **Common Data Service** csatlakoztatót, majd válassza a **Csatlakozás** lehetőséget.
3. Az Common Data Service ablakának **Kiszolgáló URL** mezőjében adja meg a Dataverse környezethez tartozó szervezeti URI-t, és válassza az **OK** gombot.
  
   ![Adja meg az URI-nevét a Dataverse környezetnek](./media/PowerBIDataverseURLSetup.png)
  
4. Bontsa ki az **Entitások** csomópontot a navigátor ablakban.
5. A keresési mezőbe írja be: **mshr_hcmworkerbaseentity**, majd válassza ki az entitást.
6. Válassza az **Adatok átalakítása** elemet.
7. A Power Query Editor ablakban válassza a **Speciális szerkesztő** lehetőséget.
8. A **Speciális szerkesztő** ablakban frissítse a lekérdezést úgy, hogy az alábbihoz hasonló legyen, és szükség szerint adja hozzá vagy távolítsa el az oszlopokat a tömbhöz.

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

9. Válassza a **Kész** lehetőséget.

   > [!NOTE]
   > Ha frissítés előtt 429-es típusú hibát kapott a lekérdezésből, lehet, hogy a lekérdezés sikeres befejezéséhez meg kell várnia az újrapróbálkozási időszakot.

10. Kattintson a **Bezárás és alkalmazás** elemre a Power Query Editor műveletszalagján.

Ezután el lehet kezdeni a Power BI jelentésnek a virtuális táblában kiválasztott oszlopok alapján való megépítését.

#### <a name="selecting-columns-in-power-apps"></a>Oszlopok kiválasztása a következőben: Power Apps

Hasonló a Dataverse webes API-lekérdezésekhez és ehhez: Power BI, javítható a Power Apps lekérdezések teljesítménye a Dataverse virtuális táblák alapján, ha az alkalmazásból kihagyja a kapcsolódó táblák oszlopait. Ha egy kapcsolódó tábla bármelyik oszlopa megtalálható egy oldalon, akkor az adatok beolvasására megadott kérés URL-címe a kapcsolódó tábla idegen kulcstulajdonságait is tartalmazni fogja. Ez a fenti [OData lekérdezés oszlopainak kiválasztása](#selecting-columns-in-power-apps) példához hasonlítva további adatkeresések miatt jelentkező teljesítménycsökkentést eredményez.

Ellen elkerülésére ellenőrizheti, hogy a Power App alkalmazás egyik adatképernyője sem tartalmazza a kapcsolódó táblák adatmezőit.

1. A Fa nézet ablakban válassza ki a képernyő adatképernyőjét.
2. A **Tulajdonságok** panelen válassza a **Szerkesztés** lehetőséget a **Mezők** tulajdonságnál.
3. Az **Adatok** ablakban ellenőrizze, hogy a kijelölt mezők egyike sem tartozik-e az adatforrás virtuális táblájához.

Ha például az alkalmazás egy lapján található egyik adatmező másik táblára, például a **ThisItem.Worker.Name** táblára hivatkozik, és a **Worker** a kapcsolódó tábla, akkor az adatok beolvasása során csökkenhet a teljesítmény.

A [Power Apps monitor](/powerapps/maker/monitor-overview) segítségével gondoskodhat arról, hogy a lekérdezésben csak a szükséges oszlopok szerepeljenek az adatok Power Appból történő lekéréséhez. A getRows művelethez létrehozott URL-t megtekintheti annak a biztosításához, hogy az alkalmazáshoz kiválasztott oszlopok optimálisak legyenek az adatok beolvasásához.

![A getData művelet elemzéséhez használja a Power Apps monitort.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Az adatlekérdezés szűrése

A lekérdezés végrehajtási teljesítményének javítására egy másik módszer a lekérdezés eredményeiben visszaadott rekordok számának korlátozása. Ehhez szűrni kell az eredményeket, hogy csak a szükséges rekordokat kapja meg.

További tájékoztatás a lekérdezési adatok szűréséről itt található: [Eredmények szűrése](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results).

### <a name="limiting-the-page-size-of-the-query"></a>A lekérdezés oldalméretének korlátozása

Ha nagy adathalmazokkal dolgozik, a lekérdezés eredményeit több lapra oszthatja úgy, hogy hozzáadja a `odata.maxpagesize` preferenciafejlécet az adatlekérdezésekhez.

További tájékoztatás a lapozásról: [Adja meg az egy oldalon visszaadni kívánt entitások számát](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Lásd még

- [Dataverse virtuális táblák konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md)
- [Human Resources – virtuális táblák – GYIK](hr-admin-virtual-entity-faq.md)
- [Szabályozás – GYIK](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]