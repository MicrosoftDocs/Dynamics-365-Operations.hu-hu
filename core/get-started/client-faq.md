---
title: "Gyakran feltett kérdések a Dynamics 365 for Operations klienssel kapcsolatban"
description: "Ez a cikk válaszokat ad a Microsoft Dynamics 365 for Operations-klienssel kapcsolatos gyakori kérdésekre."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7e8f09b965403298630460ccb6669fd82abb0e8c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>Gyakran feltett kérdések a Dynamics 365 for Operations klienssel kapcsolatban

[!include[banner](../includes/banner.md)]


Ez a cikk válaszokat ad a Microsoft Dynamics 365 for Operations-klienssel kapcsolatos gyakori kérdésekre.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>Miért nem töltődnek be a szimbólumok a Dynamics 365 for Operations használatakor?
-----------------------------------------------------------------

A böngésző biztonsági beállításai megakadályozhatják a szimbólumok megfelelő betöltődését. A probléma megoldásához kövesse az alábbi lépéseket:

-   Ha a probléma az Internet Explorer programban merül fel, kattintson a **Beállítások**, majd az **Internetbeállítások** lehetőségre.  Az Internetbeállítások párbeszédablakban kattintson az **Adatvédelem** lapra, kattintson az **Egyéni szint** elemre, és ellenőrizze, hogy be van-e jelölve a **Betűtípus letöltése** beállítás.
-   Ellenkező esetben előfordulhat, hogy hozzá kell adnia a Dynamics 365 for Operationst a megbízható helyek listájához.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Hiányolom a menüszalagot a Dynamics AX 2012 rendszerből. Nyitva tarthatom folyamatosan a Műveleti ablaktáblát?
Terveink szerint ez a funkció hamarosan elérhetővé válik. Ezt követően a felhasználók dönthetnek úgy, hogy a lapokat a Műveleti ablaktáblákon folyamatosan nyitva tartják. Ellenkező esetben a lapok mindig össze fognak csuklani, ha azokat nem használják, így biztosítva nagyobb felületet a lap számára.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>Miért jelennek meg időnként különböző ikonok, ha az egér jobb gombjával kattintok?
Ha a jobb gombbal kattint egy szerkeszthető mezőre (vagy kijelölt szövegre), a böngésző helyi menüjének ikonjai jelennek meg. Ezen menü segítségével érheti el a **Kivágás**, a **Másolás** és a **Beillesztés** parancsokat. Ezen parancsokat nem tudjuk beágyazni a Dynamics 365 for Operations helyi menüjébe, mert biztonsági okokból a böngészők nem teszik lehetővé számunkra, hogy a rendszer vágólapjához a programban hozzáférjünk.

Ha a jobb gombbal kattint egy mező címkéjére, vagy egy csak olvasható vezérlőelem értékére, látni fogja a Dynamics 365 for Operations helyi menüjét.

Annak érdekében, hogy a billentyűket könnyebben elérhesse, a jövőben billentyűparancsokat is hozzá fogunk adni a Dynamics 365 for Operations helyi menüjéhez.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Hol található a Részletek megtekintése funkció a Dynamics 365 for Operationsben?
A **Részletek megtekintése** beállítás több módon is elérhető:

-   Ha valamelyik vezérlő rendelkezik **Részletek megtekintése**lehetőséggel, és a vezérlő értékkel is rendelkezik, ez az érték fog megjelenni hivatkozásként. Rákattinthat a hivatkozásra a további részleteket tartalmazó lap megnyitásához.
-   A **Részletek megtekintése** lehetőség is megtalálható a Dynamics 365 for Operations helyi menüjében. Amennyiben szeretne többet megtudni arról, hogy mely helyi menük jelennek meg a Dynamics 365 for Operations rendszerben az egér jobb gombjával kattintva, lásd az előző fejezetet.





