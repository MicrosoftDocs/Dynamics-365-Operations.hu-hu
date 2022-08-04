---
title: Hibakódok a táblaleképezési állapot-ellenőrzéshez
description: Ez a témakör a táblatérkép állapotellenőrzésének hibakódját írja le.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 16c79a788b66830b77b2cdfb33fd2416c530f7d2
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111566"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Hibakódok a táblaleképezési állapot-ellenőrzéshez

[!include [banner](../../includes/banner.md)]



Ez a témakör a táblatérkép állapotellenőrzésének hibakódját írja le.

## <a name="error-100"></a>100-as hiba

A hibaüzenet az, hogy "A pénzügyre és a műveletekre vonatkozó ajánlások futtatásához a minimálisan szükséges pénzügyi és műveleti platformverzió a 43-as.

A funkcióhoz a pénzügyi és műveleti alkalmazások 10.0.19-es vagy újabb verziójához platformfrissítések is szükségesek.

## <a name="error-400"></a>400-as hiba

A hibaüzenet az, hogy " \{Nincsenek üzleti események regisztrációs adatai az entitás pénzügye és a műveletek UniqueEntityName\} számára, ami azt jelenti, hogy a leképezés nem fut, vagy az összes mező-hozzárendelés egyirányú."

## <a name="error-500"></a>500-as hiba

A hibaüzenet: "Nem találhatók projektkonfigurációk a projekt\{projektnév\} elemhez. Ez lehet, hogy a projekt nincs engedélyezve, vagy az összes mező-hozzárendelés egyirányú, a vevői együttműködéstől a pénzügyek és a műveletek irányában."

A táblaleképezés megfeleltetésének ellenőrzése. Ha egyirányúak az ügyfél-kapcsolati alkalmazásoktól a pénzügy és a műveletalkalmazások irányában, akkor a program nem generál forgalmat a pénzügyi és műveleti alkalmazásokból a következőbe való élő szinkronizáláshoz Dataverse.

## <a name="error-900"></a>900-as hiba

A hibaüzenet az, hogy "Érvénytelen \{forrásszűrő sourceFilter-formátum\}\{az entitás pénzügye és a UniqueEntityName művelet számára\}."

A forrásszűrő, amely a pénzügyi és műveletalkalmazások tábláján meg van adva, nem szintaktikailag nem megfelelő. A szűrési feltételek ellenőrzésével kapcsolatosan lásd: [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps) témakörben látható.

## <a name="error-1000"></a>1000-as hiba

A hibaüzenet az, hogy " \{Az entitás pénzügye és a műveletek UniqueEntityName\} lekérdezése a kettős írású élő \{szinkronizáláshoz pénzügy és az EntityFilterQueryString\} művelet. A lekérdezési feltételeknek megfelelő rekordokat élő szinkronizálásra veszi át a rendszer."

A visszaadott entitáslekérdezés az entitáshoz tartozó háttér-SQL-lekérdezés. A lekérdezés belső illesztéseit és szűrőit ellenőrizze, amelyek meghatározzák az élő szinkronizálásra felvett üzleti adatokat. A belső illesztések és szűrők kötelező feltételek, amelyeknek teljesülnie kell minden rekordnál, amely kettős írású élő szinkronizálásra van felvéve.

## <a name="error-1300"></a>1300-as hiba

A hibaüzenet az, hogy "Az \{entitás pénzügye\}\{és az EntityMetadata.EntityProperties.LogicalEntityName\} mező nem követhető két írásos típus esetén."

A pénzügyek és műveletek tábláiban található virtuális mezők nem engedélyezettek nyomon követésre. Az élő szinkronizálás szinkronizálhatja az adatokat, de nem tudja felvenni az oszlopokon végrehajtott módosításokat.

## <a name="error-1500"></a>1500-as hiba

A hibaüzenet: "Az \{datasource.DataSourceName\} adatforrás nyomon követéséhez legalább egy mezőt le kell képezni egy nem keresési mezőhöz az ügyfélkapcsolati alkalmazásoknál."

Az entitásból származó adatforrásnak egyetlen olyan mezője sincs, amely kettős íráshoz van hozzárendelve. Az alapul szolgáló tábla módosításait nem fogja kettős íráshoz nyomon követni a rendszer.

## <a name="error-1600"></a>1600-as hiba

A hibaüzenet a következő: "Adatforrás: \{adatforrás. Az entitás pénzügyéhez\} és \{az EntityMetadata.EntityProperties.LogicalEntityName\} művelethez tartomány van megadó. Csak a tartomány-feltételnek megfelelő rekordok lesznek felvéve kimenőnek."

A pénzügyi és műveleti alkalmazásokban entitások adatforrásként is használhatók, ahol engedélyezve vannak a szűrőtartományok. Ezek a tartományok határozzák meg az élő szinkronizálás részeként felvett rekordokat. Ha néhány rekordot kihagy Dataverse a pénzügyi és műveleti alkalmazásokból, ellenőrizze, hogy a rekordok megfelelnek-e az entitás tartományfeltételeinek. Az ellenőrzés egyszerű módja a következő példához hasonló SQL-lekérdezés futtatása.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>1700-as hiba

A hibaüzenet a következő: "Tábla: \{datasourceTable.Key.subscribedTableName\} az \{datasourceTable.Key.entityName\} entitáshoz követve van az \{origTableToEntityMaps.EntityName\} entitáshoz. A több entitáshoz nyomon követett táblák hatással lehetnek a rendszer teljesítményére az élő szinkronizálási tranzakcióknál."

Ha ugyanazt a táblát több entitás is követi, a tábla minden módosítása kettős írású értékelést indít a kapcsolt entitásokhoz. Bár a szűrőfeltételek csak az érvényes rekordokat küldik el, az értékelés teljesítményproblémát okozhat, ha hosszú ideig futó lekérdezések vagy nem optimális lekérdezési tervek futnak. Előfordulhat, hogy ez a probléma üzleti szempontból nem kerülhető el. Ha azonban sok egymást átfedő tábla van több entitás között, érdemes megfontolni az entitás egyszerűsítését, vagy az entitáslekérdezések optimalizálásának ellenőrzését.

## <a name="error-1800"></a>1800-as hiba
A hibaüzenet az, hogy a {} CustCustomerV3Entity entitás adatforrása tartományértéket tartalmaz. Az entitások tartományértékei hatással lehetnek a bejövő rekord upserts Dataverse rekordjaikról a pénzügyre és a műveletekre. A beállítások ellenőrzéséhez Dataverse tesztelje a pénzügyből a rekordfrissítéseket, és az olyan rekordokat, amelyek nem eznek meg a szűrési feltételeknek."

Ha az entitáshoz meg van adva egy tartomány a pénzügyi és műveleti alkalmazásokban, akkor a bejövő szinkronizálást a Pénzügy és művelet alkalmazásokból a pénzügyi és műveleti alkalmazásokba kell tesztelni, hogy a frissítési viselkedést az olyan rekordok esetében kell tesztelni, Dataverse amelyek nem eznek meg ebben a tartományban. Bármely rekordot, amely nem felel meg a tartománynak, az entitás beszúrási műveletként kezeli. Ha az alapul szolgáló táblában létezik rekord, a beszúrás sikertelen lesz. A éles telepítés előtt ajánlott tesztelni ezt a felhasználási esetet minden esetben.

## <a name="error-1900"></a>1900-as hiba
A hibaüzenet az, hogy az entitásnak {} olyan adatforrása van, amely nem nyomon követhető a kimenő kettős írás esetén. Ez a lekérdezés élő szinkronizálásának teljesítményét is befolyásolhatja. A nem használt adatforrások és táblák eltávolítása, illetve a getEntityRecordIdsImpactedByTableChange megvalósítása érdekében átalakítsa az entitást a pénzügyben és a műveletekben, hogy optimalizálja a futásidejű lekérdezéseket."

Ha sok olyan adatforrás van, amely nincs használva a tényleges, pénzügyi és műveleti alkalmazásokból származó élő szinkronizálásban való követésre, akkor lehetőség van arra, hogy az entitás teljesítménye hatással van az élő szinkronizálásra. A nyomon követhető táblák optimalizálása érdekében használja a getEntityRecordIdsImpactedByTableChange metódust.

## <a name="error-5000"></a>5000-as hiba
A hibaüzenet az, hogy az entitásfiókok adattípus-kezelési eseményeihez szinkronizált fájlok vannak regisztrálva. Ezek hatással lehetnek a kezdeti szinkronizálásra és az élő szinkronizálás importálásának teljesítményére Dataverse. A legjobb teljesítmény érdekében módosítsa az aszinkron feldolgozásra a szinkronizálási fájlokat. Regisztrált jegyzékek listája {}."

Az entitások szinkron szinkronizálása a Dataverse tranzakcióterheléshez hozzáadva hatással lehet az élő szinkronizálás és az intial szinkronizálás teljesítményére. Az ajánlott módszer az, hogy vagy kikapcsolja a rendszereket, vagy ezeket az aszinkronizálást akkor használja, ha egy adott entitásnál lassú terhelési időket használ a kezdeti, vagy egy adott entitás élő szinkronizálása során.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

