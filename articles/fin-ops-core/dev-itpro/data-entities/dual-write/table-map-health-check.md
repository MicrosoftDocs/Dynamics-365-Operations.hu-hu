---
title: Hibakódok a táblaleképezési állapot-ellenőrzéshez
description: Ez a témakör hibakódokat ír le a táblaleképezési állapot-ellenőrzéshez.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 916f3cfca3bae7a073ce4e956a12080ee01c8d31
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061278"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Hibakódok a táblaleképezési állapot-ellenőrzéshez

[!include [banner](../../includes/banner.md)]



Ez a témakör hibakódokat ír le a táblaleképezési állapot-ellenőrzéshez.

## <a name="error-100"></a>100-as hiba

A hibaüzenet a következő: "A Finance and Operations platform minimális verziója a PU 43 a Finance and Operations ajánlásainak futtatásához."

A funkcióhoz platformfrissítések szükségesek a Finance and Operations alkalmazások 10.0.19-es vagy újabb verziójához.

## <a name="error-400"></a>400-as hiba

A hibaüzenet a következő: „Az entitáshoz nem található üzleti események regisztrációs adata\{ Finance and Operations UniqueEntityName\} ami azt jelenti, hogy vagy a térkép nem fut, vagy az összes mezőtérkép egyirányú."

## <a name="error-500"></a>500-as hiba

A hibaüzenet: "Nem találhatók projektkonfigurációk a projekt\{projektnév\} elemhez. Ennek az lehet az oka, hogy a projekt nincs engedélyezve, vagy az összes mező-leképezés egyirányú az ügyfél-elköteleződéstől a Finance and Operations felé.

A táblaleképezés megfeleltetésének ellenőrzése. Ha egyirányúak az ügyfél-elköteleződési alkalmazásoktól a Finance and Operations alkalmazásokig, akkor nem generál forgalmat a Finance and Operations alkalmazásokból a következőre történő élő szinkronizáláshoz Dataverse.

## <a name="error-900"></a>900-as hiba

A hibaüzenet a következő: "Érvénytelen forrásszűrő\{ forrásszűrő\} entitás formátuma\{ Finance and Operations UniqueEntityName\} ."

A Finance and Operations alkalmazások táblázattérképén megadott forrásszűrő szintaktikailag nem megfelelő. A szűrési feltételek ellenőrzésével kapcsolatosan lásd: [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps) témakörben látható.

## <a name="error-1000"></a>1000-as hiba

A hibaüzenet a következő: „Entity\{ Finance and Operations UniqueEntityName\} a kettős írású élő szinkronizáláshoz használt lekérdezés\{ Finance and Operations EntityFilterQueryString \}. A lekérdezési feltételeknek megfelelő rekordokat élő szinkronizálásra veszi át a rendszer."

A visszaadott entitáslekérdezés az entitáshoz tartozó háttér-SQL-lekérdezés. A lekérdezés belső illesztéseit és szűrőit ellenőrizze, amelyek meghatározzák az élő szinkronizálásra felvett üzleti adatokat. A belső illesztések és szűrők kötelező feltételek, amelyeknek teljesülnie kell minden rekordnál, amely kettős írású élő szinkronizálásra van felvéve.

## <a name="error-1300"></a>1300-as hiba

A hibaüzenet a következő: „Virtuális mezők\{ s.EntityFieldName\} entitás számára\{ Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} nem lehet nyomon követni a kettős írást."

A Finance and Operations táblák virtuális mezőiben nincs engedélyezve a nyomon követés. Az élő szinkronizálás szinkronizálhatja az adatokat, de nem tudja felvenni az oszlopokon végrehajtott módosításokat.

## <a name="error-1500"></a>1500-as hiba

A hibaüzenet: "Az \{datasource.DataSourceName\} adatforrás nyomon követéséhez legalább egy mezőt le kell képezni egy nem keresési mezőhöz az ügyfélkapcsolati alkalmazásoknál."

Az entitásból származó adatforrásnak egyetlen olyan mezője sincs, amely kettős íráshoz van hozzárendelve. Az alapul szolgáló tábla módosításait nem fogja kettős íráshoz nyomon követni a rendszer.

## <a name="error-1600"></a>1600-as hiba

A hibaüzenet a következő: „Adatforrás:\{ adatforrás.DataSourceName\} entitás számára\{ Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} tartománya van. Csak a tartomány-feltételnek megfelelő rekordok lesznek felvéve kimenőnek."

A Finance and Operations alkalmazások entitásai rendelkezhetnek olyan adatforrásokkal, amelyekben engedélyezve vannak a szűrőtartományok. Ezek a tartományok határozzák meg az élő szinkronizálás részeként felvett rekordokat. Ha egyes rekordok kimaradnak a Finance and Operations alkalmazásból ide Dataverse, ellenőrizze, hogy a rekordok megfelelnek-e az entitás tartománykritériumainak. Az ellenőrzés egyszerű módja a következő példához hasonló SQL-lekérdezés futtatása.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>1700-as hiba

A hibaüzenet a következő: "Tábla: \{datasourceTable.Key.subscribedTableName\} az \{datasourceTable.Key.entityName\} entitáshoz követve van az \{origTableToEntityMaps.EntityName\} entitáshoz. A több entitáshoz nyomon követett táblák hatással lehetnek a rendszer teljesítményére az élő szinkronizálási tranzakcióknál."

Ha ugyanazt a táblát több entitás is követi, a tábla minden módosítása kettős írású értékelést indít a kapcsolt entitásokhoz. Bár a szűrőfeltételek csak az érvényes rekordokat küldik el, az értékelés teljesítményproblémát okozhat, ha hosszú ideig futó lekérdezések vagy nem optimális lekérdezési tervek futnak. Előfordulhat, hogy ez a probléma üzleti szempontból nem kerülhető el. Ha azonban sok egymást átfedő tábla van több entitás között, érdemes megfontolni az entitás egyszerűsítését, vagy az entitáslekérdezések optimalizálásának ellenőrzését.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
