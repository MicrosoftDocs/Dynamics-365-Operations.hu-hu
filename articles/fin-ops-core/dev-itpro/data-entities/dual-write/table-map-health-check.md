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
ms.openlocfilehash: c2d1f1e39a5ddccddf6fbbf524ff7eb0945b3c32
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782236"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Hibakódok a táblaleképezési állapot-ellenőrzéshez

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör hibakódokat ír le a táblaleképezési állapot-ellenőrzéshez.

## <a name="error-100"></a>100-as hiba

A hibaüzenet az, hogy "A Finance and Operations ajánlások futtatásához a minimálisan szükséges Finance and Operations platformverzió a PU 43."

A funkcióhoz platformfrissítések szükségesek a 10.0.19-es vagy újabb Finance and Operations alkalmazásokhoz.

## <a name="error-400"></a>400-as hiba

A hibaüzenet az, hogy "Nincsenek üzleti eseményregisztrációs adatok az \{Finance and Operations entitás UniqueEntityName értékéhez\}, ami azt jelenti, hogy a leképezés nem fut, vagy az összes mező-hozzárendelés egyirányú."

## <a name="error-500"></a>500-as hiba

A hibaüzenet: "Nem találhatók projektkonfigurációk a projekt\{ projektnév\} elemhez. Lehet, hogy a projekt nincs engedélyezve, vagy az összes mezőleképezés egyirányú, az ügyfélkapcsolati alkalmazások a Finance and Operations között."

A táblaleképezés megfeleltetésének ellenőrzése. Ha egyirányúak az ügyfél-kapcsolati alkalmazásoktól a Finance and Operations alkalmazásokba, nincs forgalom generálva a Finance and Operations és Dataverse élő szinkronizációjához.

## <a name="error-900"></a>900-as hiba

A hibaüzenet az, hogy "Érvénytelen forrásszűrő \{ sourceFilter\} formátum a \{Finance and Operations UniqueEntityName\} entitáshoz."

A Finance and Operations alkalmazásokhoz a táblaleképezésen megadott forrásszűrő nem szintaktikailag nem megfelelő. A szűrési feltételek ellenőrzésével kapcsolatosan lásd: [Élő szinkronizálási problémák elhárítása](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps) témakörben látható.

## <a name="error-1000"></a>1000-as hiba

A hibaüzenet a következő "A \{Finance and Operations UniqueEntityName\} entitás lekérdezése kettős írású élő szinkronizáláshoz \{Finance and Operations EntityFilterQueryString\}. A lekérdezési feltételeknek megfelelő rekordokat élő szinkronizálásra veszi át a rendszer."

A visszaadott entitáslekérdezés az entitáshoz tartozó háttér-SQL-lekérdezés. A lekérdezés belső illesztéseit és szűrőit ellenőrizze, amelyek meghatározzák az élő szinkronizálásra felvett üzleti adatokat. A belső illesztések és szűrők kötelező feltételek, amelyeknek teljesülnie kell minden rekordnál, amely kettős írású élő szinkronizálásra van felvéve.

## <a name="error-1300"></a>1300-as hiba

A hibaüzenet: "Az \{ s.EntityFieldName\} virtuális mezők a \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} entitáshoz lehetséges, hogy nincsenek követve kettős íráshoz."

A Finance and Operations táblák virtuális mezői nem engedélyezettek nyomon követéshez. Az élő szinkronizálás szinkronizálhatja az adatokat, de nem tudja felvenni az oszlopokon végrehajtott módosításokat.

## <a name="error-1500"></a>1500-as hiba

A hibaüzenet: "Az \{ datasource.DataSourceName\} adatforrás nyomon követéséhez legalább egy mezőt le kell képezni egy nem keresési mezőhöz az ügyfélkapcsolati alkalmazásoknál."

Az entitásból származó adatforrásnak egyetlen olyan mezője sincs, amely kettős íráshoz van hozzárendelve. Az alapul szolgáló tábla módosításait nem fogja kettős íráshoz nyomon követni a rendszer.

## <a name="error-1600"></a>1600-as hiba

A hibaüzenet , "Adatforrás: \{ datasource.DataSourceName\} a \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} entitáshoz tartománnyal rendelkezik. Csak a tartomány-feltételnek megfelelő rekordok lesznek felvéve kimenőnek."

A Finance and Operations alkalmazásokban az entitásokhoz olyan adatforrások is engedélyezhetők, amelyekben engedélyezve vannak a szűrőtartományok. Ezek a tartományok határozzák meg az élő szinkronizálás részeként felvett rekordokat. Ha egyes rekordokat kihagy a Finance and Operations alkalmazások és a Dataverse között, ellenőrizze, hogy a rekordok megfelelnek-e az entitás tartományfeltételeinek. Az ellenőrzés egyszerű módja a következő példához hasonló SQL-lekérdezés futtatása.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>1700-as hiba

A hibaüzenet a következő: "Tábla: \{ datasourceTable.Key.subscribedTableName\} az \{ datasourceTable.Key.entityName\} entitáshoz követve van az \{ origTableToEntityMaps.EntityName\} entitáshoz. A több entitáshoz nyomon követett táblák hatással lehetnek a rendszer teljesítményére az élő szinkronizálási tranzakcióknál."

Ha ugyanazt a táblát több entitás is követi, a tábla minden módosítása kettős írású értékelést indít a kapcsolt entitásokhoz. Bár a szűrőfeltételek csak az érvényes rekordokat küldik el, az értékelés teljesítményproblémát okozhat, ha hosszú ideig futó lekérdezések vagy nem optimális lekérdezési tervek futnak. Előfordulhat, hogy ez a probléma üzleti szempontból nem kerülhető el. Ha azonban sok egymást átfedő tábla van több entitás között, érdemes megfontolni az entitás egyszerűsítését, vagy az entitáslekérdezések optimalizálásának ellenőrzését.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
