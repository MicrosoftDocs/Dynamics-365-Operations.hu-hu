---
title: Hívásközpont eladási funkciói
description: Ez a témakör áttekintést ad a hívásközpont értékesítési funkcióiról a Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f1660399e7e88a8f7c96714f9af271b73a17eca2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799613"
---
# <a name="call-center-sales-functionality"></a>Hívásközpont értékesítési funkciói

[!include [banner](includes/banner.md)]


A Dynamics 365 Commerce szolgáltatásban a hívásközpont egyfajta csatorna, amelyet az alkalmazásban lehet megadni. Ha meghatároznak egy adott csatornát a hívásközpont-entitásokhoz, az lehetővé teszi, hogy a hívásközponti csatorna felhasználója által létrehozott specifikus adatalapértelmezéseket és a rendelési alapértelmezéseket a rendszer értékesítési rendelésekhez kapcsolja.

A hívásközpont funkciói speciális promóciókat tartalmaznak az árra vonatkozóan, valamint katalógusokat, ajándékutalványokat, hűségprogramokat és kuponokat. A hívásközpont által lebonyolított rendeléseket segíti a pénztári (POS) alkalmazás, amely támogatja a párhuzamos csatornákon történő rendelések teljesítését.

Fontos megjegyezni, hogy míg a hívásközpont-modul a kereskedelmi kívül más ágazatokban is használható, a telefonos ügyfélszolgálati alkalmazás jelenlegi kiadása még nem lett optimalizálva vállalatok közötti (B2B) rendelésfeldolgozási forgatókönyvekhez, illetve olyan forgatókönyvekhez, ahol a rendelésekhez nagy számú értékesítési sorok tartoznak. Azt ajánljuk, hogy azok a felhasználók, akik a hívásközpont funkcióit a szokásos, közvetlenül az ügyféllel lebonyolított műveleteken túlmenően akarják a megrendelések feldolgozására használni, szánjanak rá elegendő időt a telefonos ügyfélszolgálat tesztelésére és annak ellenőrzésére, hogy az teljesíti-e funkcionális és teljesítménybeli elvárásokat.

A rendelések létrehozásának támogatásán felül a hívásközpont-modul felhasználóbarát ügyfélszolgálati alkalmazást is tartalmaz, amely megkönnyíti a felhasználók számára, hogy megkeressék a vevői számlákat és áttekintsék az összes kapcsolódó, vevői megrendeléshez kapcsolódó adatot és attribútumot. Az ügyfélszolgálati képernyő lehetővé teszi, hogy a felhasználó gyorsan elérje a rendeléshez kapcsolódó adatokat, amelyek lehetővé teszik, hogy gyorsan megválaszolja az ügyfelektől a rendelésekkel kapcsolatban kapott, leggyakoribb kérdéseket.

Ez a lap a következőkhöz kapcsolódó dokumentációkhoz biztosít hivatkozásokat: beállítás, konfiguráció és a hívásközpont funkcióinak használata.


## <a name="configure-the-call-center"></a>Hívásközpont konfigurálása

[Hívásközponti csatornák beállítása](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>A megrendelés feldolgozásának konfigurálása

[Hívásközpontban jelentkező csalás-ellenőrzési figyelmeztetések beállítása és használata](set-up-fraud-alerts.md)

[Hívásközpont rendeléseinek várakoztatása – konfigurálás és használat](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Fizetés feldolgozásának konfigurálása

[Fizetési módok hívásközpontoknál](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Szállítási módok beállítása

[Szállítási módok és díjak beállítása a hívásközponthoz](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Közvetlen marketing konfigurálása

[Hívásközpont-katalógusok](call-center-catalogs.md)

[Frissesség, gyakoriság és pénzügyi szempont szerinti (Recency, Frequency, Monetary, RFM) elemzés beállítása](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Folytonossági programok konfigurálása

[Folytonossági programok beállítása hívásközpontok számára](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]