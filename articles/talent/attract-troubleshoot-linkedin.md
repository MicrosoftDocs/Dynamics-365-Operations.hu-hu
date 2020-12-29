---
title: A LinkedIn és a Microsoft Dynamics 365 Talent - Attract közötti integráció hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet elhárítani a hibákat, amikor megpróbál állást feladni a LinkedIn felületére a Microsoft Dynamics 365 Talent - Attract megoldásból.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: ec095642f556b8d0087dd22f35097671a30047a6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461365"
---
# <a name="troubleshoot-integration-with-linkedin-and-attract"></a>A LinkedIn és az Attract közötti integráció hibaelhárítása

[!include [banner](includes/banner.md)]

A következő információk segítségével elháríthatja azokat a problémákat, amelyek akkor merülnek fel, amikor a LinkedIn felületére próbál állásokat feltenni a Microsoft Dynamics 365 Talent: Attract megoldásból.

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a>Nem lehet bejelentkezni a LinkedIn rendszerbe az Attract megoldásból

Ha nem sikerül bejelentkeznie a LinkedIn webhelyre az Attract megoldásból, próbálja meg ezeket a lépéseket:

1. Győződjön meg róla, hogy az Attract megoldásban megadott LinkedIn hitelesítő adatok érvényesek és helyesek.
2. Ha a hitelesítő adatok érvényesek és helyesek forduljon a [LinkedIn támogatáshoz](https://www.linkedin.com/help/linkedin).
3. Ha a probléma továbbra is fennáll, forduljon [Microsoft támogatáshoz](./talent-support.md).

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a>Az Attract állásai nem jelennek meg a LinkedIn felületén

Ha az állás 24 órelt eltével nem jelent meg a LinkedIn felületén, próbálja meg ezeket a lépéseket:

1. Győződjön meg róla, hogy a LinkedIn vállalat azonosítója a LinkedIn vállalati oldalhoz hozzárendelve, és helyesen van megadva az Attract felügyeleti központjában. A LinkedIn beállításainak a felügyeleti központban történő módosításáról a következő témakör tartalmaz további tájékoztatást: [A LinkedIn integrációjának beállítása a Microsoft Dynamics 365 Talent – Attract megoldáshoz](attract-admin-linkedin.md). A LinkedIn vállalati azonosíótval kapcsolatos további tudnivalókat lásd [A LinkedIn vállalati azonosítójának társítása a LinkedIn Job Boarddal - Gyakran ismételt kérdések](https://www.linkedin.com/help/linkedin/answer/98972).
2. Ellenőrizze az állás adatait a LinkedIn felületén, és győződjön meg arról, hogy a cím teljes. Az állások sikeres feladásához a LinkedIn szolgáltatásnak legalább az állás városát és országát vagy régióját meg kell adni.
3. Győződjön meg róla, hogy az állás nem egy másik állás másolata , amely fel van adva a LinkedIn felületére. A LinkedIn nem fog olyan állásokat feladni, amelyek egy LinkedIn Premium Job Slot vagy Limited Listing másolatai egy másik forrásból. Győződjön meg róla, hogy a vállalat egy másik munkatársa már nem adta fel manuálisan az állást.

## <a name="see-also"></a>Lásd még

[Az Attact és a LinkedIn integrációjával kapcsolatos gyakori kérdések](./attract-linkedin-faq.md)

[Állások feladása a LinkedIn felületére a Microsoft Dynamics 365 Talent – Attract szolgáltatásból](./attract-post-jobs-to-linkedin.md)

[Jelöltek felkutatása a LinkedIn Recruiter megoldással a Microsoft Dynamics 365 Talent – Attract szolgáltatásban](./attract-linkedin-recruiter.md)

[Állás létrehozása, jóváhagyása és feladása az Attract alkalmazásban](./creating-jobs-attract.md)

[A LinkedIn és a Microsoft Dynamics 365 Talent – Attract közötti integráció hibaelhárítása](./attract-troubleshoot-linkedin.md)
