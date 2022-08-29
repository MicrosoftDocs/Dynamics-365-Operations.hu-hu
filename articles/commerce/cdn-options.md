---
title: Tartalomkézbesítési hálózat végrehajtási beállításai
description: Ez a cikk a tartalomszállítási hálózat (CDN) megvalósítás különböző, környezetekben használható Microsoft Dynamics 365 Commerce beállításait vizsgálja meg. Ilyen lehetőségek például az Azure Front Door és a vevő által birtokolt Azure Front Door natív, Commerce rendszerbeli példányai.
author: BrianShook
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: de2ecab86809af3ace64ba06956f00137d254ab7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275147"
---
# <a name="content-delivery-network-implementation-options"></a>Tartalomkézbesítési hálózat végrehajtási beállításai

[!include [banner](includes/banner.md)]

Ez a cikk a tartalomszállítási hálózat (CDN) megvalósítás különböző, környezetekben használható Microsoft Dynamics 365 Commerce beállításait vizsgálja meg. Ilyen lehetőségek például az Azure Front Door és a vevő által birtokolt Azure Front Door natív, Commerce rendszerbeli példányai.

A Commerce-vevőknek számos lehetőségük van, amikor a CDN-szolgáltatás Commerce-környezetben történő használatát fontolgatják. A Commerce rendszer alapvető Azure Front Door támogatással jelenik meg, amely alapvető tárhely- és egyéni tartománykövetelményeket fed le. Olyan vállalatok esetén, amelyek nagyobb ellenőrzést és konkrétabb biztonsági képességeket, például webalkalmazási tűzfalat (WAF) szeretnének, a legjobb lehetőség az Azure Front Door vevő által birtokolt példánya vagy külső CDN-szolgáltatás használata.

A Commerce-környezetekben a következő három CDN-végrehajtási beállítás használható:

- A Commerce által biztosított Azure Front Door-példány
- Az Azure Front Door vevő által birtokolt példánya (a jobb ellenőrzési és további biztonsági funkciók érdekében)
- Külső CDN-szolgáltatás

Mind a három CDN-bégrehajtási beállítás csak dinamikus HTML-tartalmat nyújt egyéni tartományokból. A Commerce-rendszer automatikusan kezeli az összes JavaScript-, egymásra épülő stílusalap- (CSS), kép-, video- és egyéb statikus tartalmat a Microsoft által kezelt CDN-ek segítségével. A kiválasztott lehetőség határozza meg az elérhető üzemeltetési lehetőségeket, az ellenőrzési lehetőségeket és további biztonsági lehetőségeket.

A következő ábrán látható a Commerce architektúrája.

![A Commerce architektúrájának áttekintése.](media/Commerce_CDN-Option_ComparisonModels.png)

Az Azure Front Door-példányának Commerce rendszerbeli beállításával kapcsolatban lásd: [CDN-támogatás hozzáadása](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>A Commerce által biztosított Azure Front Door-példány használata

Az alábbi táblázat felsorolja a Commerce által a tartalomvégpontok kezelésére biztosított Azure Front Door-példány előnyeit és hátrányait.

| Előnyök | Hátrányok |
|------|------|
| <ul><li>A példány szerepel a Commerce költségeiben.</li><li>Mivel a példányt a Commerce csapata kezeli, kevesebb karbantartás szükséges, és megosztott beállítási lépések vannak.</li><li>Az Azure-környezetben tárolt infrastruktúra méretezhető, biztonságos és megbízható.</li><li>Az SSL-tanúsítványt egyszer kell beállítani, utána automatikusan megújul.</li><li>A Commerce csapata figyeli a példányt, hogy vannak-e hibák és anomáliák.</li></ul> | <ul><li>A WAF nem támogatott.</li><li>Nincsenek egyedi testreszabások és beállítási módosítások.</li><li>A példány frissítései vagy módosításai Commerce csapatától függnek.</li><li>Az apex-tartományokhoz külön Azure Front Door-példány szükséges, és további munka szükséges az apex-tartományok és az Azure DNS integrálásához.</li><li>A másodpercenkénti válaszokról (RPS) vagy a hibaarányról nem biztosítanak telemetriai adatokat a vevőnek.</li></ul> |

Az alábbi ábra a Commerce-rendszer által biztosított Azure Front Door-példány architektúráját mutatja be.

![A Commerce által biztosított Azure Front Door-példány.](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Vevő által birtokolt Azure Front Door példány használata

Az alábbi táblázat felsorolja a vevő által birtokolt, a tartalomvégpontok kezelésére biztosított Azure Front Door-példány előnyeit és hátrányait.

| Előnyök | Hátrányok |
|------|------|
| <ul><li>A telepítés biztonságos és könnyen kezelhető.</li><li>Az Azure-környezetben tárolt infrastruktúra méretezhető, biztonságos és megbízható.</li><li>A példány lehetővé teszi a WAF-integrációt és a részletességi szabályvezérlőket a kifejezetten az ön webhelyére finomhangolt biztonsághoz.</li><li>A példány lehetővé teszi az SSL-tanúsítványok finomhangolását (a vevő által birtokolt és az Azure Front Door által kezelt esetében egyaránt) és a tartomány-összekapcsolásokat.</li><li>A példány apex-tartományokkal kapcsolatos megoldást kínál, ha közvetlenül párosítva van az Azure DNS-sel.</li><li>A rendszer telemetriai adatokat és riasztást biztosít.</li><li>Az SSL-tanúsítványt egyszer kell beállítani, utána automatikusan megújul.</li></ul> | <ul><li>A példányt Ön kezeli.</li><li>Ehhez kezdeti tudásra is szükség van.</li></ul> |

A következő ábra egy Commerce-infrastruktúrát mutat be, amely egy vevő által birtokolt Azure Front Door-példányt tartalmaz.

![Vevő által birtokolt Azure Front Door-példányt tartalmazó Commerce-infrastruktúra.](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>Külső CDN-szolgáltatás használata

Az alábbi táblázat felsorolja a tartalomvégpontok kezelésére használt külső CDN-szolgáltatás előnyeit és hátrányait.

| Előnyök | Hátrányok |
|------|------|
| <ul><li>Ez a lehetőség akkor hasznos, ha a meglévő tartomány már egy külső CDN-en található.</li><li>WAF: Külső szolgáltatótól függ.</li></ul> | <ul><li>Külön szerződés és további költségszámítás szükséges.</li><li>Az SSL-lel kapcsolatban további költségek merülhetnek fel.</li><li>Mivel a szolgáltatás nem az Azure felhőstruktúra része, egy további infrastruktúra kezelésére van szükség.</li><li>Előfordulhat, hogy a szolgáltatás hosszabb időbeli befektetést igényel a végponti és a biztonsági beállítások során.</li><li>A szolgáltatást Ön kezeli.</li><li>A szolgáltatást Ön felügyeli.</li></ul> |

Az alábbi ábra egy külső CDN-szolgáltatást tartalmazó Commerce-infrastruktúrát mutat be.

![Külső CDN-szolgáltatást tartalmazó Commerce-infrastruktúra.](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>További erőforrások

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)
