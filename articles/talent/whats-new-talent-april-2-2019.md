---
title: Új vagy módosult elemek a Dynamics 365 Talent (2019. április 2.) szolgáltatásban
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 04b5a006d4580fe419d81986a90851bc8d611722
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528219"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-2-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent (2019. április 2.) szolgáltatásban

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="approval-emails-in-attract"></a>Jóváhagyó e-mailek az Attract megoldásban
Az új jóváhagyási e-mailek javítják a rálátást a jóváhagyási folyamatra. Az alábbi esetekben e-mail lesz küldve a jóváhagyók számára:

- Kérelmező elküld egy feladatot jóváhagyásra.
- Feladat elutasítva vagy jóváhagyva.
- A jóváhagyó nem csinál semmit a jóváhagyási kéréssel kapcsolatosan 24 órán belül.

A jóváhagyó e-mailek tartalmát új sablonokkal testre szabhatja.

### <a name="application-and-profile-attachments"></a>Jelentkezés és a profil mellékletek
Fejlesztések a **Dokumentumok** lapon a jelentkezések és tehetségállomány profilokban immár megjelenítik a dokumentum nevét és típusát is.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban
A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="coming-soon-attract-and-onboard"></a>Hamarosan (Attract és Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Lifecycle Services (LCS) integráció probléma jelentésével
Attract és Onboard megoldásokban a végfelhasználók által naplózott problémák a probléma jelentése szolgáltatással automatikusan támogatási problémákat hoznak létre az ügyfél LCS projektjében. Az adminisztrátorok ezt követően besorolhatják a problémákat, majd elküldhetik azokat a Microsoftnak, amikor szükséges. Ez megfelel annak, ahogy a Core HR kezeli a végfelhasználói támogatási problémákat.

## <a name="changes-in-core-hr"></a>A Core HR módosításai
A szakaszban ismertetett módosítások a 8.1.2216-ös buildre vonatkoznak.

### <a name="platform-update-25-for-finance-and-operations"></a>A Finance and Operations 25-es platformfrissítése
A Finance and Operations 25. Platform frissítésével kapcsolatos további tudnivalókat lásd: [Előzets funkciók a Dynamics 365 for Finance and Operations 25. platformfrissítésében (2019. április)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Haladó kompenzációs biztonsági (fix és változó)
Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők előfordulhat, hogy csak a bizonyos kompenzációs rekordokhoz férnek hozzá. Ezeket a rekordokat tartalmazhatnak a vezetőkhöz és regionális alkalmazottakhoz Ez a módosítás lehetővé teszi a HR számára kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz. Biztonsági szerepköröket rendelhet a fix és változó konstrukciókhoz. Ezek a biztonsági szerepkörök szabályozzák a konstrukciók és a kapcsolódó alkalmazott adatok, például a fizetés vagy bónuszrekordok elérést, hogy csak ezek dolgozhassanak fel kompenzációt az alkalmazotti csoportokhoz.

### <a name="upgrade-to-common-data-service"></a>Frissítés Common Data Service megoldásra
A Common Data Service frissítés gyorsan közeledik. Jelentkezzen a Microsoft Power Apps felügyeleti központba annak meghatározásához, hogy kell-e az adatbázist frissíteni. Határidőkkel és frissítéséhez szükségesek további lépésekkel kapcsolatos tudnivalókat lásd: [Frissítés a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds) megoldásra.

## <a name="in-preview"></a>Előnézetben

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Okkódok megadásának engedélyezése a szabadságtípusoknál
A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban. Immár megadhat okkódokat egy adott távolléttípushoz, és engedélyezheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Okkódok kérése egy szabadságtípusokhoz a távollétkérelmek során
Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmet nyújtanak be. Ennek oka lehet a vállalat szabályzata vagy szabályozási követelmények. Immár meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.

## <a name="coming-soon"></a>Hamarosan

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>A felhasználói felület fejlesztései az ismétlődő alkalmazottak ellenőrzéséhez
Ez a módosítással az ismétlődések észleli a program, amikor névmezőket ad meg, és egy állapot jelenik meg a talált ismétlődések számával. A hivatkozás kiválasztásával megnyithat egy új lapot, hogy megállapítsa, hogy használja-e az észlelt egyezést. Az adatbevitel megzavarása elkerülése érdekében az ismétlődéseket tartalmazó űrlap nem nyílik meg automatikusan.

###  <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez
A Finance and Operations 25-ös platformfrissítésével a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek, a kapcsolattartóknak, ha egy esemény kezdeményezi azt. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]