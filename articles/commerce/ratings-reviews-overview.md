---
title: Minősítések és értékelések áttekintése
description: Ez a témakör a Microsoft Dynamics 365 Commerce minősítéseit és értékeléseit mutatja be.
author: gvrmohanreddy
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0788091755fb784621e972a0573f7004952e8e11
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792099"
---
# <a name="ratings-and-reviews-overview"></a>Minősítések és értékelések áttekintése


[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce minősítéseit és értékeléseit mutatja be.

## <a name="overview"></a>Áttekintés

A minősítések és az értékelések fontosak az e-kereskedelmi vevők számára, akik szeretnék megismerni, hogy a vevők milyen véleménnyel vannak a termékekről. Emellett segítséget jelenthetnek a vásárlók számára a vásárlási döntések meghozatalában. A Dynamics 365 Commerce alkalmazásban, a minősítések és a vélemények lehetővé teszik a kereskedők számára, hogy rögzítsék a vevőktől származó minősítéseket és értékeléseket. A kiskereskedők ezután az átlagos minősítéseket és az értékeléseket megjeleníthetik e-Commerce-webhelyükön.

Az átlagos minősítési információ a pénztár (POS) és hívásközpont csatornákon jelenik meg. Ennek megfelelően az értékesítési társítások segítenek a felhasználóknak a döntéshozatalban. A minősítések és a vélemények visszajelzési mechanizmusként is szolgálhatnak, amellyel a kiskereskedők egy termék minőségét javíthatják, így növelve az értékesítéseket.

A Dynamics 365 Commerce minősítések és értékelések funkciója egy többcsatornás megoldás, amely natív módon érhető el a platform részeként. A minősítések és a értékelések megoldás a Microsoft Azure felületre épül, amely magas színtű méretezhetőséget és megbízhatóságot biztosít.

A következő ábra bemutatja, hogyan működik a Dynamics 365 Commerce minősítések és a vélemények megoldása.

![Értékelések és vélemények a Dynamics 365 for Commerce megoldásban](media/Dynamics-365-Commerce-Ratings-and-Reviews-Overview.jpg)

Az értékelések és vélemények a Dynamics 365 Commerce megoldásban az Azure Cognitive Services szolgáltatásokat kínálja, a sértő szavak automatikus szűrésére 40 nyelven. Mivel az emberi jóváhagyás nem szükséges, a moderálási költségeket csökkenti a program. A rendszer olyan moderátori eszközöket is kínál, amelyek a vevői aggályok, visszajelzések és levételi kérelmek megválaszolására, valamint a felhasználóktól érkező adatkérések megválaszolására is használhatók.

Az értékelések és vélemények megoldás olyan minialkalmazásokat tartalmaz, amelyek a termékek listáiban, a keresési eredmények között, a termék részletei oldalon és más helyeken a minősítési összesítőket megjelenítik. A minialkalmazások teljes ellenőrzési listákat jelenítenek meg, és rendezési és szűrési beállításokat is tartalmaznak.

Az értékelések és vélemények megoldás egy üzleti intelligencia (BI) sablont is tartalmaz, amely olyan mérőszámokat tartalmaz, amelyek betekintést nyújtanak az értékelésekkel és véleményekkel kapcsolatosan. Az értékelések és a vélemények adatait további elemzések céljából is exportálni lehet.

## <a name="additional-resources"></a>További erőforrások

[A minősítések és ellenőrzések használatának kiválasztása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]