---
title: "Rendelésvárakoztatások"
description: "Ez a témakör a következővel kapcsolatban kínál információkat: rendelésvárakoztatás a Kiskereskedelem és kereskedelem a Dynamics AX rendszerben használatával."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Rendelésvárakoztatások

Ez a témakör a következővel kapcsolatban kínál információkat: rendelésvárakoztatás a Kiskereskedelem és kereskedelem a Dynamics AX rendszerben használatával.

Egy rendelés visszatartásának több oka is lehet. Például előfordulhat, hogy egy megrendelés mindaddig várakoztatva van, amíg a vevő címe, vagy a fizetési mód ellenőrzésre nem kerül, vagy amíg a vezető ellenőrzi a vevő hitelkeretét. Az értékesítési folyamat során vannak olyan időszakok, amikor várakoztatni kell az értékesítési rendeléseket. Például egy értékesítési rendelés várakoztatásának oka lehet vevői kifizetéssel kapcsolatos probléma, csalás vagy a vezető felülvizsgálatára történő várakozás miatt. Amikor az értékesítési rendelés várakoztatva van, egy rendelési várakoztatási kódot társítunk az értékesítési rendeléshez, hogy jelezze a várakoztatás okát. Értékesítési rendelés tartsa kódok van konfigurálva, **értékesítési és marketing**&gt;**telepítő**&gt;**értékesítési rendelések**&gt;**rendelés rendelkezik kódok**. Egy értékesítési rendeléshez be lehet állítani a várakoztatást manuálisan a rendelések létrehozásakor vagy később. Emellett egy rendelés automatikusan is várakoztatható a csalási szabályok alapján. Amíg egy értékesítési rendelés várakoztatva van, előfordulhat, hogy további információkkal kell frissíteni. Azt is megteheti, hogy kiveszi az értékesítési rendelést, miközben tovább dolgozik rajta. Lefoglalhatják a értékesítési rendelés ellenőrizze ismét, és a kivételt, a rendelés használatával egy másik felhasználó is felülbírálása tartsa workbench (**kereskedelmi és kereskedelmi**&gt;**vevők**&gt;**rendelés-tartás**). Ha egy rendelést már be lehet fejezni, a befejezés előtt el kell távolítania a várakoztatást.


