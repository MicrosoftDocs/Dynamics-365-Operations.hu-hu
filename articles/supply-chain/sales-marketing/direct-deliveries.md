---
title: Közvetlen kiszállítások
description: A cikk tájékoztatást nyújt a közvetlen kiszállításokkal kapcsolatban. A közvetlen kiszállítások olyan szállítások, amelyeket a rendszer közvetlenül a szállítótól küld a vevőhöz.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 540f7514a152cfba48d00a3cf863b24d23b4c30e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429682"
---
# <a name="direct-deliveries"></a>Közvetlen kiszállítások

[!include [banner](../includes/banner.md)]

A cikk tájékoztatást nyújt a közvetlen kiszállításokkal kapcsolatban. A közvetlen kiszállítások olyan szállítások, amelyeket a rendszer közvetlenül a szállítótól küld a vevőhöz.

A közvetlen szállítással időt és készletezési költséget takaríthat meg, mivel nem kell a termékeket raktárakban tárolnia, mielőtt a vevőhöz szállítaná azokat.  

Közvetlen kiszállításokat az **Értékesítési rendelés** képernyőn hozhat létre. Először hozzon létre egy értékesítési rendelést és rendeléssorokat. Ezután az **Értékesítési rendelés** lapon kattintson a **Közvetlen kiszállítás** elemre. Végül válassza ki azokat a sorokat, amelyeket közvetlen szállításként kell kezelni. Ekkor kapcsolat jön létre a közvetlen kiszállításra kiválasztott rendeléssorok és az azokra vonatkozó beszerzésirendelés-sorok között.  

**Megjegyzés:** Ha a megrendelt mennyiség egy része már leszállított, majd fel kell osztania a fennmaradó mennyiség. Hozzon létre egy új sort által közvetlenül kell szállítani, és ezt a mennyiséget, az eredeti sorban szereplő mennyiség levonása a mennyiséggel. Például, ha az eredeti mennyiség 15 és öt kiszállítása megtörtént, meg kell hozzon létre egy új sort a fennmaradó mennyiség 10, és ezt az összeget az eredeti mennyiség majd csökkenteni.  

Miután létrehozott egy közvetlen kiszállítási kapcsolatot az értékesítési rendelés sorai és a beszerzési rendelés között, csomagjegyzék használatával frissítheti az értékesítési rendelést. A beszerzési rendelésből futtasson egy csomagjegyzék-frissítést vagy számlafrissítést. Az értékesítési rendelés számlafrissítését az **Értékesítési rendelés** képernyőn kell elvégezni. Az értékesítési rendelés számlafrissítése nem lehetséges olyan formában, hogy a mennyisége nagyobb legyen mint a beérkezettként rögzített mennyiség. Tegyük fel, hogy egy értékesítésirendelés-sor 10 darabot tartalmaz, de a rendeléssorból csak ötöt frissítettek csomagjegyzékkel. Ha az értékesítési rendelés számlafrissítése során az **Összes** opciót választja a **Mennyiség** listából, akkor csak a fizikailag beérkezett és a csomagjegyzékkel frissített cikkek kerülnek számlafrissítésre. A rendzser nem frissíti a teljes értékesítésirendelés-sort.

## <a name="delivery-date"></a>Kiszállítási dátum
Ha az értékesítésirendelés-sorban frissíti a **Kért átvételi dátum** mezőt, akkor a megfelelő beszerzésirendelés-sor **Szállítás dátuma** mezője is frissül. Ehhez hasonlóan, ha a beszerzésirendelés-sor **Visszaigazolva** mezőjét frissíti, akkor a megfelelő értékesítésirendelés-sor **Visszaigazolt kézhezvételi dátum** és **Visszaigazolt szállítási dátum** mezője is frissül.

## <a name="delivery-address"></a>Szállítási cím
A beszerzési rendelés szállítási címe általában a vállalat címe. Közvetlen kiszállítás létrehozásánál azonban a vevő címe kerül a szállítási cím helyére. Ha a **Közvetlen kiszállítás** típusú beszerzésirendelés-sor szállítási címét módosítja, akkor a megfelelő értékesítésirendelés-sor szállítási címe is megváltozik. Hasonlóképpen ha az értékesítésirendelés-sor szállítási címét módosítja, akkor a megfelelő beszerzésirendelés-sor szállítási címe is frissül.

## <a name="deleting-order-lines"></a>Rendeléssorok törlése
Ha **Közvetlen kiszállítás** típusú értékesítésirendelés-sort szeretne törölni, akkor egy üzenetablak figyelmezteti arról, hogy a sorhoz beszerzésirendelés-sorok kapcsolódnak. Ha az értékesítésirendelés-sort részben már leszállították, akkor sem az ahhoz kapcsolódó értékesítésirendelés-sor, sem a beszerzésirendelés-sorok nem törölhetők.

## <a name="warehouse"></a>Raktár
Közvetlen szállítás létrehozásakor az értékesített cikk soha nem jelenik meg fizikailag a raktárban. Ennek ellenére is meg kell adnia egy raktárat az értékesítési rendelés sorában. Ehhez hasonlóan kitárolási követelményeket is meg lehet határozni a tétel cikkmodellcsoportjában. Ugyanakkor, mivel a cikk fizikailag soha nem lesz jelen a raktárban, a rendszer közvetlen szállítás típusú értékesítési rendeléseknél ezeket a követelményeket figyelmen kívül hagyja.



