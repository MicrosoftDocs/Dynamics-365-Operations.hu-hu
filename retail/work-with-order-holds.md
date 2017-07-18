---
title: "Rendelésvárakoztatások"
description: "Ez a témakör bemutatja a Dynamics 365 for Retail rendszer használatával történő rendelésvárakoztatást."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: c0c0e9a0f863eb33d544f63e40e0531cdaaf6426
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="order-holds"></a>Rendelésvárakoztatások

[!include[banner](includes/banner.md)]


Ez a témakör bemutatja a Dynamics 365 for Retail rendszer használatával történő rendelésvárakoztatást.

Egy rendelés visszatartásának több oka is lehet. Például előfordulhat, hogy egy megrendelés mindaddig várakoztatva van, amíg a vevő címe, vagy a fizetési mód ellenőrzésre nem kerül, vagy amíg a vezető ellenőrzi a vevő hitelkeretét. Az értékesítési folyamat során vannak olyan időszakok, amikor várakoztatni kell az értékesítési rendeléseket. Például egy értékesítési rendelés várakoztatásának oka lehet vevői kifizetéssel kapcsolatos probléma, csalás vagy a vezető felülvizsgálatára történő várakozás miatt. Amikor az értékesítési rendelés várakoztatva van, egy rendelési várakoztatási kódot társítunk az értékesítési rendeléshez, hogy jelezze a várakoztatás okát. Az értékesítési rendelések várakoztatási kódjai az **Értékesítés és marketing** &gt; **Beállítás** &gt; **Értékesítési rendelések** &gt; **Rendelésvárakoztatási kódok** részben konfigurálhatók. Egy értékesítési rendeléshez be lehet állítani a várakoztatást manuálisan a rendelések létrehozásakor vagy később. Emellett egy rendelés automatikusan is várakoztatható a csalási szabályok alapján. Amíg egy értékesítési rendelés várakoztatva van, előfordulhat, hogy további információkkal kell frissíteni. Azt is megteheti, hogy kiveszi az értékesítési rendelést, miközben tovább dolgozik rajta. Kivehet egy értékesítési rendelést, visszarakhatja, illetve felülbírálhat más felhasználók által végrehajtott kivételeket a rendelésvárakoztatási munkaterület segítségével (**Kiskereskedelem** &gt; **Vevők** &gt; **Rendelésvárakoztatások**). Ha egy rendelést már be lehet fejezni, a befejezés előtt el kell távolítania a várakoztatást.




