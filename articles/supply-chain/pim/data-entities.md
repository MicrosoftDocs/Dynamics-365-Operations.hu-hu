---
title: Termékadat-entitások
description: Ez a témakör a termékadatok importálásához és exportálásához használt különböző entitásokkal kapcsolatos információkat tartalmazza.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 2784e552d7984bbea9c74ad800c6305ab2a216e9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567151"
---
# <a name="product-data-entities"></a>Termékadat-entitások

[!include [banner](../includes/banner.md)]

Termékadatok importálásához és exportálásához az adatentitásokat kell használnia. A következő táblázat részletesen ismerteti a termékkel kapcsolatos adatentitásokat, és leírja az egyes elemek rendeltetését.

| Entitás | Alkalmazásobjektum-fa (AOT) neve (típus) | Jegyzetek |
|--------|-------------------------------------------|-------|
| Termékek V2 | `EcoResProductV2Entity` | Ez az entitás megosztott termékek – egyedi termékek és alaptermékek importálásához és exportálásához használható. Lehetővé teszi a frissítéseket. Nem támogatja a készletalapú SQL-műveleteket. Engedélyezett az Open Data Protocol (OData) esetében. |
| Kiadott termékek V2 | `EcoResReleasedProductV2Entity` | Ez az entitás kiadott termékek – egyedi termékek és alaptermékek importálásához és exportálásához használható. Lehetővé teszi a frissítéseket. A megosztott terméknek már létrehozott állapotban kell lennie. Amikor egy új, megjelent terméket importálnak, a megosztott termék kiadása történik. Külön entitások is léteznek, amelyek a kiadott alaptermék és a kiadott egyéni változatok importálására és exportálására használhatók. Ez az entitás nem támogatja a halmazalapú SQL-műveleteket és a törlési műveleteket. Engedélyezett az OData esetében. |
| Kiadott termék létrehozása V2 | `EcoResReleasedProductCreationV2Entity` | Ezzel az entitással egy lépésben importálhatók a megosztott termékek és a kiadott termékek. Bár támogatja az exportokat, a használata nem ajánlott, mivel az entitás célja a termék létrehozása. Nem támogat frissítéseket. Mezők korlátozott készletét támogatja (a terméklétrehozásban elérhető mezőket). Nem támogatja a készletalapú SQL-műveleteket. Nem jelenik meg az OData-n keresztül. |
| Termékváltozatok | `EcoResProductVariantEntity` | Ez az entitás a megosztott termékváltozatok importálásához és exportálásához használható. Lehetővé teszi a frissítéseket. Szükséges, hogy a dimenzióértékek már létre legyenek hozva. Az integrációs kulcs az alaptermék és a termékdimenziók. Az entitás nem támogatja a készletalapú SQL-műveleteket. Engedélyezett az OData esetében. Támogatja a törlési műveleteket. Nem terjeszthető ki új termékdimenziók hozzáadásával. |
| Termékváltozatok termékazonosító alapján | `EcoResProductNumberIdentifiedProductVariantEntity` | Ez az entitás a megosztott termékváltozatok importálásához és exportálásához használható. Lehetővé teszi a frissítéseket. Szükséges, hogy a dimenzióértékek már létre legyenek hozva. Az integrációs kulcs a termékszám (míg a **Termékváltozatok** entitás integrációs kulcsa az alaptermék és a termékdimenziók). |
| Kiadott termékváltozatok | `EcoResReleasedProductVariantEntity` | Ez az entitás a kiadott termékváltozatok importálásához és exportálásához használható. Lehetővé teszi a frissítéseket. A megosztott termékváltozatoknak már létrehozott állapotban kell lenniük. Amikor egy új, kiadott termékváltozatot importálnak, a megosztott termékváltozat kiadása történik. Az entitás nem támogatja a készletalapú SQL-műveleteket. Engedélyezett az OData esetében. Bár támogatja a törlési műveleteket, jelenleg ez a használat az aktuális platform hibája miatt az adatok sérülését okozza. Az entitás nem terjeszthető ki új termékdimenziók hozzáadásával. |
| Kiadott termékváltozatok termékazonosító alapján | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | Ez az entitás a **Kiadott termékváltozatok** entitásra hasonlít, de az integrációs kulcs a termékszám az alaptermék és a termékdimenziók helyett. Kiterjeszthető ki új termékdimenziók hozzáadásával. |
| Értékesíthető kiadott termékek | `EcoResSellableReleasedProductEntity` | Ez az entitás csak értékesíthető termékek exportálására szolgál. Az értékesíthető termékek olyan termékek, amelyek rendelkeznek az általuk megkövetelt információkkal annak érdekében, hogy azokat értékesítési rendelésekben használják. Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve van az **Érvényesítés** funkcióval a **Kiadott termékek** oldalon. |
| Egyedi termékek kiadása V2 | `EcoResDistinctProductV2Entity` | Ez az entitás csak egyedi termékek exportálására szolgál. Ezek az egyedi termékek lehetnek termékek, termékaltípusok és termékváltozatok. |
| Kiadott alaptermékek V2 | `EcoResProductMasterV2Entity` | Ez az entitás a megosztott alaptermékek importálásához és exportálásához használható. Az adatkezelés nem engedélyezett. |
| Cikk – vonalkód | `EcoResProductBarcodeEntityV3` | Ez az entitás csak termékek és vonalkódok exportálására szolgál. Ez az entitás nem engedélyezi a változások követését, a frissítéseket vagy a törléseket. A vonalkódok változáskövetésének, frissítésének vagy törlésének használatához használja az **Elem - vonalkód társítási** entitást. |
| Cikk–vonalkód társítás | `EcoResProductBarcodeAssociationEntity` | Ez az entitás csak termékek és vonalkódok exportálására szolgál. Ez lehetővé teszi a változások nyomon követését, frissítéseket, és törléseket. Az entitás használatához engedélyezni kell a *Cikk – vonalkód fejlesztések* funkciót a [szolgáltatáskezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Az entitáskulcsa az `AssociationID`, amely létrehozza a vonalkód és a termék közötti kapcsolatot. E kulcs támogatásának hozzáadásához a `InventitemBarcodeAssociation` táblázat a funkció bekapcsolásakor feltöltődik a meglévő tétel vonalkódadatokkal. A táblázat feltöltése kötegelt feladat segítségével történik, és ha a vonalkódtábla nagyszámú rekordot tartalmaz, a kötegelt feladat futtatása jelentős időt vehet igénybe. Ezért azt javasoljuk, hogy tervezze meg a szolgáltatás engedélyezését (és ezért futtassa a kötegelt feldolgozást) az üzletmenete szempontjából a legalkalmasabb időpontban. |
| Termékéletciklus állapotai | `EcoResProductLifecycleSateEntity` | Ez az entitás a termékhez rendelhető különböző termékéletciklus-állapotok importálására és exportálására szolgál. |

> [!NOTE]
> A **Kiadott termékek V2** adatentitással csak akkor importálhat termékeket a rendszerbe, ha már létrehozta a megosztott terméket. Ellenkező esetben, ha termékeket szeretne importálni a rendszerbe, a **Termék létrehozása** adatentitást kell használnia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]