---
title: Készletláthatóság bővítményének áttekintése
description: Ez a téma elmagyarázza, hogy mi a Készletláthatóság, és ismerteti a funkcióit.
author: yufeihuang
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dfc1bc0d457d0b0b2632aa2e2e5ba6a3c2f3fae7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575171"
---
# <a name="inventory-visibility-add-in-overview"></a>Készletláthatóság bővítményének áttekintése

[!include [banner](../includes/banner.md)]

A Készletláthatóság Add-in (más néven *Készletláthatóság*) egy független és nagymértékben skálázható mikroszolgáltatás, amely lehetővé teszi a valós idejű készletkövetést. Ezért átfogó képet nyújt a készletről.

A külső rendszerek RESTful API-kon keresztül érik el a szolgáltatást. Ily módon vagy lekérdezhetik a készletinformációkat adott dimenziókészletekre vonatkozóan, vagy különböző testreszabott adatforrásokban módosíthatják a készletét.

A Microsoft Dataverse rendszerre épülő mikroszolgáltatásként a Készletláthatóság bővíthetőséget biztosít. A Power Apps segítségével alkalmazásokat készíthet. Alkalmazhatja a Power BI rendszert is, hogy az üzleti követelményeknek megfelelő, testreszabott funkciókat biztosítson.

A készlet láthatóságát több harmadik fél rendszerével is integrálhatja a szabványosított készletméretekre vonatkozó konfigurációs opciók beállításával és a tranzakciótípusok beállításával. A készlet láthatósága támogatja az egyéni bővíthetőséget is a konfigurálható számított mennyiségek révén.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Készletláthatóság integráció a Dynamics 365 Supply Chain Management rendszerbe

Az integrált megoldás a készletadatokat a Dynamics 365 Supply Chain Management rendszerből tölti le, és folyamatosan nyomon követi a készletváltozásokat. A további tudnivalókat lásd a [Készlet láthatóságának telepítése és beállítása](inventory-visibility-setup.md), valamint a [Készlet láthatóságának beállítása](inventory-visibility-configuration.md) részben.

## <a name="get-a-global-view-of-inventory"></a>A készlet globális áttekintése

Az integrált megoldás lehetővé teszi saját adatforrásainak meghatározását és a készletadatok központosítását. További információért lásd: [Készlet láthatóságának konfigurálása](inventory-visibility-configuration.md).

A készlet megtekintéséhez kétféle megközelítés létezik:

- Küldjön lekérdezést a nagy teljesítményű API-n keresztül. Ez az API közel valós idejű készletadatokat tud visszaadni közvetlenül egy gyorsítótárazott példányból. Szerződéseket és mintákat a [Készletláthatóság nyilvános API-k](inventory-visibility-api.md) között talál.
- Tekintse meg a nyers készletlistát. Ez a lista rendszeresen szinkronizálódik egy gyorsítótárazott példányból, és a Dataverse rendszerben látható. További információért lásd: [Készletláthatóság alkalmazás](inventory-visibility-power-platform.md).

## <a name="soft-reservations"></a>Lágy foglalások

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A lágy foglalás akkor alkalmazható, amikor egy vállalkozásnak meghatározott mennyiségű terméket kell lefoglalnia, például az értékesítési megrendelések teljesítése érdekében, hogy elkerülje a túlértékesítést. Amikor egy értékesítési megrendelés létrejön és visszaigazolásra kerül a Supply Chain Managementtben vagy más megrendeléskezelő rendszerben, a mennyiség lefoglalására vonatkozó kérés elküldésre kerül a Készletláthatósághoz. A Készletláthatóság lehetővé teszi, hogy lefoglalja a méretadatokkal és meghatározott készleti tranzakciótípusokkal rendelkező termékeket. (További információért lásd a [Készletláthatóság alkalmazásban](inventory-visibility-power-platform.md).) A mennyiség sikeres lefoglalása után a rendszer egy foglalási azonosítót küld vissza. Ezt a foglalási azonosítót használhatja az eredeti megrendeléshez való visszakapcsoláshoz a Supply Chain Managementtben vagy más megrendeléskezelő rendszerekben.

A funkciót úgy tervezték, hogy a készlet láthatóságában történő foglalás nem változtatja meg a teljes mennyiséget. Ehelyett csak a lefoglalt mennyiséget jelzi. (Emiatt nevezik *lágy lefoglalásnak*.) A lágy lefoglalt mennyiség kiegyenlíthető, amikor a termékeket a Supply Chain Managementtben vagy egy harmadik fél rendszerében elfogyasztják, az API újbóli meghívásával, hogy a mennyiség levonása és a teljes mennyiség frissítése a Készletláthatóságban megtörténjen. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
