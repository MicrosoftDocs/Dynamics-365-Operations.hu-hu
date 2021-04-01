---
title: Modultár áttekintése
description: Ez a témakör a Microsoft Dynamics 365 Commerce modulkönyvtárról nyújt áttekintést.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: fcb0c2317315308de51d8247d23a930f10c3de6f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234293"
---
# <a name="module-library-overview"></a>Modultár áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce modulkönyvtárról nyújt áttekintést.

A Dynamics 365 Commerce modulkönyvtár olyan modulok gyűjteménye, amelyek egy e-kereskedelmi webhely felépítésére használhatók. A modulokban felhasználói felületi (UI) szempontok és funkcionális működéssel kapcsolatos szempontok is találhatók.

A modulkönyvtár moduljaira témák is alkalmazhatók, így módosítható megjelenésük és hangulatuk. A témák egymásra épülő stílusalapokat (CSS) használnak. A „Gyár” nevű fiktív e-kereskedelmi webhely témája a elérhető a modulkönyvtár részeként, és referenciaként használható.

## <a name="module-library-modules"></a>Modulkönyvtár moduljai

A következő típusú modulok érhetők el a modellkönyvtárban:

- **Konténer modul** – Egy konténer modul egy egyszerű modul, amely más modulok számára gazdaként szolgál. A benne található modulok elrendezését szabályozza.
- **Marketing modulok** – A marketing modulokban megtalálhatók a blokk, a szövegblokk, a videólejátszó és a forgótár modulok. Ezen a modulok mindegyike a tartalom bemutatására használható. Ezeket a modulokat bármelyik lapra el lehet helyezni, és tartalomkezelő rendszer (CMS) adatai vezérlik őket.
- **Fejléc és lábléc modulok** – A fejléc és lábléc modulok az oldal összes lapjának fej- és láblécében jelennek meg. Ezek a modulok a tulajdonságokon keresztül konfigurálhatók igény szerint.
- **Keresési modulok** – A termékek a fejlécben található keresési modul segítségével fedezhetők fel. A keresési eredmények a találati lapon jelennek meg. A termékek a kategória oldalain is megtalálhatók, amelyek különálló lapok az egyes kategóriákhoz, amelyek támogatva vannak a csatornanavigációban. Ezenkívül a finomító modulok használhatók keresési eredmények és kategóriák oldalain található eredmények további szűrésére.
- **A termék részletei lap moduljai** – A termék részletei oldalak számos modult használnak a termék adatainak megjelenítésére. A vásárlásmező modul segítségével a vevők megtekintik a termékeket, és behelyezhetik őket a kosárba. Más modulok – például a műszaki adatok modul – a termék részletes adatait jelenítik meg. A minősítések és a vélemények modul a vélemények megjelenítésére és adására használható.
- **Online vásárlás, felvétel az üzletben modul** – Az Online vásárlás, felvétel az üzletben modul integrálva van a Bing Maps-térképpel. Felhasználható a közelben található üzletek megtalálására, ahol a vevők a megvásárolt termékeket átvehetik.
- **Beszerzési modulok** – A beszerzési modulok tartalmazzák a kosár modult, amely a cikkek kosárba helyezésére használható. A pénztári modul rögzíti a szállítási címet, a szállítási lehetőségeket és az ajándékutalvány, a hűségprogram- és a hitelkártya-adatokat, hogy fel lehessen dolgozni a rendelést. A rendelés leadását követően a rendelés visszaigazolása modul a visszaigazolás részleteinek megjelenítésére is használható.
- **Fiókkezelési modulok** – A bejelentkezési modulban a vevők be tudnak jelentkezni egy már létező fiókba, és a feliratkozási modul új fiók létrehozását teszi lehetővé. A fiók létrehozása után a rendelési előzmények modulban megtekintheti a legutóbbi rendeléseket, és a rendelés részletei modulban megtekintheti a rendelés adatait.
- **Javaslatok modul** – A javaslatok a termékmegjelenítés modul használatával jeleníthetők meg. Ez a modul olyan algoritmus alapú és szerkesztői listákat támogat, amelyek bármelyik lapon megjeleníthetők.

## <a name="additional-resources"></a>További erőforrások

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]