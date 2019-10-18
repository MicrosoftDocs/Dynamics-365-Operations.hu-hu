---
title: Hívásközpont eladási funkciói
description: Ez a témakör áttekintést ad a hívásközpont értékesítési funkcióiról a Dynamics 365 Retail szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 902db94164b35077a876c8041c038af36561a634
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025771"
---
# <a name="call-center-sales-functionality"></a>Hívásközpont értékesítési funkciói

[!include [banner](includes/banner.md)]


A Dynamics 365 Retail szolgáltatásban a hívásközpont egyfajta kiskereskedelmi csatorna, amelyet az alkalmazásban lehet megadni. Ha meghatároznak egy adott csatornát a hívásközpont-entitásokhoz, az lehetővé teszi, hogy a hívásközponti csatorna felhasználója által létrehozott specifikus adatalapértelmezéseket és a rendelési alapértelmezéseket a rendszer értékesítési rendelésekhez kapcsolja.

A hívásközpont funkciói speciális promóciókat tartalmaznak a kiskereskedelmi árra vonatkozóan, valamint katalógusokat, ajándékutalványokat, hűségprogramokat és kuponokat. A hívásközpont által lebonyolított rendeléseket segíti a pénztári (POS) alkalmazás, amely támogatja a párhuzamos csatornákon történő rendelések teljesítését.

Fontos megjegyezni, hogy míg a hívásközpont-modul a kiskereskedelmin kívül más ágazatokban is használható, a Retail telefonos ügyfélszolgálati alkalmazás jelenlegi kiadása még nem lett optimalizálva vállalatok közötti (B2B) rendelésfeldolgozási forgatókönyvekhez, illetve olyan forgatókönyvekhez, ahol a rendelésekhez nagy mennyiségű értékesítési sorok tartoznak. Azt ajánljuk, hogy azok a felhasználók, akik a hívásközpont funkcióit a szokásos, közvetlenül az ügyféllel lebonyolított műveleteken túlmenően akarják a megrendelések feldolgozására használni, szánjanak rá elegendő időt a telefonos ügyfélszolgálat tesztelésére és annak ellenőrzésére, hogy az teljesíti-e funkcionális és teljesítménybeli elvárásokat.

A rendelések létrehozásának támogatásán felül a hívásközpont-modul felhasználóbarát ügyfélszolgálati alkalmazást is tartalmaz, amely megkönnyíti a felhasználók számára, hogy megkeressék a vevői számlákat és áttekintsék az összes kapcsolódó, vevői megrendeléshez kapcsolódó adatot és attribútumot. Az ügyfélszolgálati képernyő lehetővé teszi, hogy a felhasználó gyorsan elérje a rendeléshez kapcsolódó adatokat, amelyek lehetővé teszik, hogy gyorsan megválaszolja az ügyfelektől a rendelésekkel kapcsolatban kapott, leggyakoribb kérdéseket.

Ez a lap a következőkhöz kapcsolódó dokumentációkhoz biztosít hivatkozásokat: beállítás, konfiguráció és a Retail hívásközpont funkcióinak használata.


## <a name="configure-the-call-center"></a>Hívásközpont konfigurálása

[Rendelésfeldolgozási beállítások meghatározása](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>A megrendelés feldolgozásának konfigurálása

[Csalással kapcsolatos figyelmeztetések beállítása](set-up-fraud-alerts.md)

[Megrendelés manuális várakoztatása](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Fizetés feldolgozásának konfigurálása

[Fizetési módszerek hívásközpontnál](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Szállítási módok beállítása

[Szállítási módok és díjak beállítása a hívásközponthoz](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Közvetlen marketing konfigurálása

[Hívásközpont-katalógusok](call-center-catalogs.md)

[RFM-profilelemzés beállítása](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Folytonossági programok konfigurálása

[Folytonossági program beállítása egy hívásközpont számára](set-up-continuity-program.md)
