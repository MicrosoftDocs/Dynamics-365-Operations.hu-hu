---
title: Éles indítás GYIK
description: Ez a cikk felsorolja azokat a Dynamics 365 Human Resources gyakori kérdéseket, amelyek arról szólnak, hogyan lehet egy megvalósítási projektben együtt működik.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfb2434b0d0573f2edab228fcca77ee653d751a5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853103"
---
# <a name="go-live-faq"></a>Éles indítás GYIK 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a cikk felsorolja azokat a Dynamics 365 Human Resources gyakori kérdéseket, amelyek arról szólnak, hogyan lehet egy megvalósítási projektben együtt működik. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>Mikor konfigurálhatom és kérelmezhetem az éles környezetemet? 

Az éles környezet általában a következő feltételek teljesítése után kerül üzembe helyezésre:

- Minden testreszabás kódja teljeskörű.
- A felhasználói elfogadási tesztelés (UAT) befejeződött.
- Az ügyfél jóváhagyta a megoldást.
- Nincsenek blokkoló problémák az éles indítással kapcsolatban. 

Ha a minősített ügyfelek ebben a szakaszban vannak, a Microsoft FastTrack csapata a projektcsapattal együttműködve élő indítási értékelést készít. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>Milyen előfeltételei vannak az éles környezet üzembe helyezésének? 

Az előfeltételek listáját a  [Felkészülés az élő indításra](hr-admin-go-live-prepare.md) című témakörben találja. 

## <a name="what-is-a-go-live-assessment"></a>Mi az az élő indítási értékelés?  

Az élő indítási értékelés a  [Microsoft FastTrack program](/dynamics365/fasttrack/) része. A felülvizsgálat során a megoldástervező felméri, hogy egy megvalósítási projekt készen áll-e a sikeres átállásra és az éles indításra. Ez a felülvizsgálat minden megvalósítási projekthez kötelező, mielőtt éles környezetben való éles indítást kérelmez. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>A tesztkörnyezetek az USA középső régiójában található adatközpontjában vannak telepítve. Azt szeretnénk, hogy éles környezeteink az USA nyugati régiójának adatközpontjában legyenek telepítve. Kiválaszthatom az USA nyugati régióját adatközpontként az éles konfigurációban? 

Az LCS nem korlátozza, hogy egy másik adatközpontot válasszon a Human Resources környezetének üzembe helyezésekor, de azt javasoljuk, hogy ne válasszon másik adatközpontot.  

Ha azt szeretné, hogy az éles környezet az USA nyugati régiójának adatközpontjában legyen, először telepítse újra a tesztkörnyezeteket a USA nyugati régiójának adatközpontjában, tesztelje őket, és hagyja jóvá. 

A megfelelő adatközpont kiválasztásáról a [Hálózati követelmények](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements) című témakörben talál további információt. 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Milyen szintű hozzáféréssel kell rendelkeznem az Azure-erőforrásokhoz a Human Resources környezeteimhez?  

A Human Resources környezethez való hozzáférés korlátozott. A virtuális gép (VM) vagy a Microsoft Internet Information Services (IIS) nem érhető el. Az adatbázis a Microsoft SQL Server Felügyeleti stúdión keresztül sem érhető el. 

Bár közvetlenül nem tud hozzáférni az Azure-erőforrásokhoz vagy a Dynamics 365 Human Resources-környezethez, további funkciókat is használhat az adatok eléréséhez:

- Az Azure SQL-adatbázist telepítheti a saját Azure-bérlőben, és a Bring Your Own Database (BYOD) szolgáltatás használatával szinkronizálhatja az adatokat. A további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).

- A Dataverse integráció segítségével szinkronizálhatja a kijelölt entitásokat a Dataverse-adatbázisba. A további tudnivalókat lásd: [Dataverse-táblák](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>Milyen gyakran készül biztonsági másolat az éles adatbázisról? 

Az adatbázisokat automatikus biztonsági mentés védi a következő frekvenciákon:

| A biztonsági mentés típusa | Gyakoriság |
| --- | --- |
| Adatbázis teljes biztonsági mentése | Heti |
| Különbözeti adatbázis biztonsági mentése | 12-24 óránként |
| Tranzakciónapló biztonsági mentése | 5-10 percenként |

A Microsoft elegendő biztonsági mentést tart meg ahhoz, hogy az elmúlt 14 napban lehetővé tegye az Időponthoz kötött visszaállítás (PITR) használatát. 

A további tudnivalókat lásd: [Tudnivalók az automatikus SQL-adatbázis biztonsági másolatokról](/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>Kérhetek másolatot az éles adatbázis biztonsági másolatáról? 

Nem. Azonban az adatbázis-frissítési szolgáltatáskérést elküldheti, hogy az éles környezetet a tesztkörnyzetbe másolja. Az Azure SQL-adatbázist telepítheti a saját Azure-bérlőben, és a BYOD funkció használatával szinkronizálhatja az adatokat az éles környezetből. A további tudnivalókat lásd: [Használja saját adatbázisát (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>Hogyan helyezhetem át a tesztkörnyezetemet az élesbe éles indításra? 

Mivel másolási szolgáltatás nem érhető el a környezet tesztkörnyezetből éles környezetbe való áthelyezéséhez, adatcsomagokat kell használnia az adatok éles környezetbe való áthelyezéséhez.  

Azt javasoljuk, hogy a projekt során a tesztkörnyezetben konfigurált entitások egyértelmű listáját tartsa fenn. Ezután tesztelje az átállás és az áttelepítés folyamatát az éles indításhoz szükséges adatcsomagok esetében. Ha készen áll az éles indításra, manuálisan kell áthelyeznie az adatcsomagokat az éles környezetbe. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>Mit tegyek, ha az éles környezetem nem üzemel? 

A termeléskimaradás jelentéséhez kövesse a  [Termeléskimaradás jelentése](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md) című részben leírt eljárást. 

 ## <a name="see-also"></a>Lásd még

 [Felkészülés az éles indításra](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
