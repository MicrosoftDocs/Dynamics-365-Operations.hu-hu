---
title: Aszinkron vevőlétrehozási mód – GYIK
description: Ez a cikk a vevők aszinkron létrehozási módjával kapcsolatos gyakori kérdésekre ad választ Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: bd5741aeb3278f1d40d63bb02ca57571a907dc21
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474069"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>Aszinkron vevőlétrehozási mód – GYIK

[!include [banner](includes/banner.md)]

Ez a cikk az aszinkron (async) vevő-létrehozási móddal kapcsolatos gyakori kérdésekre ad választ a következőben:Microsoft Dynamics 365 Commerce

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>Miért nem lehet engedélyezni az "Aszinkron módban való vevőszerkesztés" funkciót?

Mielőtt engedélyezi a vevők **aszinkron módban való szerkesztését**, engedélyeznie kell a következő funkciókat:

- A vevői rendelések és a vevői tranzakciók teljesítményének javítása
- Továbbfejlesztett async Customer-létrehozás engedélyezése
- Aszinkron létrehozás engedélyezése a vevői címekhez

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>Miért létezik a Commerce Headquarters alkalmazásba való valós idejű szolgáltatási hívásoknak az aszinkron módban való szerkesztésének engedélyezése után?

Ez a probléma akkor fordul elő Commerce Data Exchange, amikor nem futtattak CDX-feladatokat annak érdekében, hogy a funkció állapota és más csatorna-metaadatai szinkronizálva lefuttassanak a csatornával. Mielőtt újra próbálkozik az esettel, győződjön meg arról, hogy a Commerce Headquarters a következő CDX-feladatokat futtatja:

- 1110 (Globális konfiguráció)
- 1010 (Vevők)
- 1070 (Csatorna konfigurálása )

Előfordulhat, hogy a CDX-feladatok futtatása után a Commerce Scale Unit (STB) gyorsítótárazott adatai nem tükröződnek azonnal a Commerce Headquarters alkalmazásban.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>Miért nem mutatja a Commerce Headquarters a vevők létrehozását vagy a pénztári (POS) frissítéseket vagy az e-commerce csatornát?

Győződjön meg arról, hogy a következő műveletek végrehajtása a felsorolásuk sorrendjében történt.

1. Futtassa a CDX P-feladatot a Commerce Headquarters alkalmazáson, hogy a **RETAILASYNCCUSTOMERV2, RETAILASYNCADDRESSV2** **,** **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** **és RETAILASYNCCUSTOMERATTRIBUTEV2** táblákban tárolt async Customer Data elérhető legyen a Commerce Headquarters szolgáltatásban.
1. A Vevők és **csatornakérések szinkronizálása** kötegelt feladat futtatása a Commerce Headquartersban A kötegelt feladat sikeres **végrehajtása után a korábban említett táblákból sikeresen feldolgozott összes rekord onlineOperationCompleted** **mezőjének beállítása 1** lesz.
