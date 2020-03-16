---
title: Eltávolított vagy elavult Platform-funkciók
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087883"
---
# <a name="removed-or-deprecated-platform-features"></a>Eltávolított vagy elavult Platform-funkciók

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="platform-update-32"></a>32-as platformfrissítés

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez biztonsági hiba volt, mert a módosítási kérelmet nem szándékolt felhasználó számára is lehetett elküldeni. Ez egy használhatósági probléma is volt, mivel a felhasználó rá volt kényszerítve, hogy meghatározza, hogy ki volt a kezdeményező, és manuálisan ki kellet jelölnie.  |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Munkafolyamat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A felhasználó kiválasztása legördülő lista el lett távolítva a 32-es platformfrissítésben. A módosítási kérelmeket a program automatikusan elküldi a létrehozónak, a szándéknak megfelelően. A funkciókkal kapcsolatos további tudnivalókat lásd: [Munkafolyamat-jóváhagyási folyamatok műveletei](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../migration-upgrade/deprecated-features.md).

