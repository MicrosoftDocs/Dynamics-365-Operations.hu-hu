---
title: Tevékenységek a folyamatban
description: Ez a témakör a felvételi folyamatban használható különféle tevékenységekkel kapcsolatban tartalmaz tájékoztatást.
author: ''
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c32db1f563466f05b9fef1a03578392888c0b7e6
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2019
ms.locfileid: "374757"
---
# <a name="activities-in-the-hiring-processes"></a>Tevékenységek a felvételi folyamatban

[!include[banner](../includes/banner.md)]

A tevékenységek a felvételi folyamat részeként adhatók hozzá a Dynamics 365 for Talent: Attract esetében. A tevékenységeket folyamatsablonhoz lehet hozzáadni, vagy közvetlenül az állásnál adhatók hozzá a felvételi folyamathoz. Ha megadott egy állást, ki lesz választva egy folyamat, és a tevékenységek, amelyek szerepelnek a sablonban, az álláshoz adódnak. Az alapértelmezett sablont használja a rendszer, ha nincs sablon kiválasztva. A felvételi folyamat is módosítható az álláson a sablon alkalmazása után.

> [!NOTE] 
> A folyamatsablonok az Átfogó felvételi bővítmény részeként érhetők el.

## <a name="prospect-activity"></a>Potenciális tevékenység

A potenciális tevékenység azt szabályozza, hogy a potenciális jelöltek hozzáadhatók-e egy álláshoz. Alapértelmezés szerint potenciális jelöltek adhatók az álláshoz. A potenciális tevékenység kikapcsolásához állítsa a **Potenciális jelöltek engedélyezése** lehetőséget **Ki** beállításra. A potenciális tevékenység bekapcsolásakor a felvételi vezetők hozzáadhatják és megtekinthetik a potenciális jelölteket, és a **Potenciális jelölt** lap megjelenik az állásnál.

## <a name="application-activity"></a>Pályázat tevékenység

A Pályázat tevékenység kötelező a felvételi folyamat sablonban. E-mail küldéséhez a pályázóknak a jelentkezésük benyújtásakor vagy amikor hozzáadják őket a Pályázat szakaszhoz, állítsa az **E-mail küldése a pályázónak** lehetőséget az **Igen** beállításra.

## <a name="interview-schedule-and-feedback-activity"></a>Interjú ütemezése és visszajelzés tevékenység

A tevékenység három összetevőből áll: pályázó elérhetőségének lekérése, ütemezés és visszajelzés. Használja az állássablon interjú tevékenységét, ha szeretné szerepeltetni a folyamatban a jelölt rendelkezésre állásának kérését, ütemezést és visszajelzést, ahelyett, hogy egyenként a felvételi folyamat részeként használná őket. További tudnivalókért lásd: [Interjú ütemezése és visszajelzés](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>PowerApps tevékenység

A PowerApps tevékenység lehetővé teszi Microsoft PowerApps alkalmazás beágyazását a felvételi folyamatba. Az alkalmazás összes jelentkező, csak a belső pályázók, csak a külső pályázók vagy egy pályázó számára sem lehet szükséges. Ha az alkalmazás kötelezőként van megjelölve, akkor el kell végezni a következő szakaszba való továbblépés előtt. Ha az alkalmazás nem szükséges, a tevékenység (nem kötelező), és a fokozat lehet előbbre akkor is, ha az alkalmazás nem befejeződött.

A PowerApps tevékenység mentéséhez a felvételi folyamatba, meg kell adnia egy PowerApps-azonosítót. A PowerApps-azonosító megkereséséhez ugorjon ide: [PowerApps](https://web.powerapps.com), válassza az **Alkalmazások**, majd a **Részletek** lehetőséget.

Ha kiválasztja a **Résztvevők tevékenységhez való hozzáadásának engedélyezése** lehetőséget, a PowerApps tevékenység használó alkalmazásokhoz további munkatársak is hozzáadhatók. Például egy szervezet létrehozott egy PowerApps alkalmazást, amely interjúkérdések tára a műszaki szerephez. A szervezet most felvesz egy új szoftverfejlesztőt, és hozzáadta a PowerApps tevékenységet a felvételi folyamathoz a szoftverfejlesztők szerepkörhöz. Ha a **Résztvevők tevékenységhez való hozzáadásának engedélyezése** beállítás be van jelölve, a szoftverfejlesztő szerepkörre pályázót megnyitó toborzó vagy felvételi vezető embereket vehet fel a PowerApps tevékenységhez. Ezek a személyek ezt követően megtekinthetik az alkalmazást, amely az interjúkérdéseket tartalmazza.

> [!NOTE]
> A PowerApps tevékenység csak az átfogó felvételi bővítménnyel érhető el.

## <a name="youtube-activity"></a>YouTube-tevékenység

A YouTube tevékenység segítségével megoszthat a felvételi folyamat részeként YouTube videókat. A felvételi folyamatba a YouTube tevékenység mentéséhez meg kell adnia a YouTube videó URL-címét. Mint a PowerApps tevékenységnél, engedélyezheti a résztvevők hozzáadását a tevékenységhez. Ha bejelöli a **Megjelenítés csak a pályázónak** lehetőséget, a videó csak a pályázói élmény részeként jelenik meg. Nem látható a felvételi folyamat során Attractban.

> [!NOTE]
> A YouTube tevékenység csak az átfogó felvételi bővítménnyel érhető el.

## <a name="web-content-activity"></a>Webes tartalom tevékenység

A webes tartalom tevékenységgel online tartalom ágyazható be a felvételi folyamatba. A felvételi folyamatba a webes tartalom tevékenység mentéséhez meg kell adnia a webes tartalom URL-címét. Mint a PowerApps és a YouTube tevékenységnél, engedélyezheti a résztvevők hozzáadását a tevékenységhez. Ha bejelöli a **Megjelenítés csak a pályázónak** lehetőséget, a tartalom csak a pályázói élmény részeként jelenik meg. Nem látható a felvételi folyamat során Attractban. A megjelenő tartalom mérete kiválasztható.

> [!NOTE]
> A webes tartalom tevékenység csak az átfogó felvételi bővítménnyel érhető el.

## <a name="microsoft-forms-activity"></a>Microsoft Forms tevékenység

A Microsoft Forms tevékenység lehetővé teszi Microsoft Forms űrlap beágyazását a felvételi folyamatba. A Microsoft Forms segítségével teszteket, felméréseket és lekérdezéseket hozhat létre. A felvételi folyamatba a Microsoft Forms tevékenység mentéséhez meg kell adnia az űrlap URL-címét. Mint a PowerApps, a YouTube és a webes tartalom tevékenységnél, engedélyezheti a résztvevők hozzáadását a tevékenységhez. Ha bejelöli a **Megjelenítés csak a pályázónak** lehetőséget, az űrlap csak a pályázói élmény részeként jelenik meg. Nem látható a felvételi folyamat során Attractban.

A Microsoft Forms esetében a szerző módosíthatja a beállításokat, hogy a szervezeten kívüli felhasználók válaszolhassanak a felmérésre vagy a tesztre. Ebben az esetben a felhasználók névtelenül küldik a válaszok. Ha meg szeretné nézni, hogy ki töltötte ki a felmérést vagy a tesztet, előírhatja, hogy a válaszadók írják be a nevüket a felmérés vagy teszt részeként.

> [!NOTE]
> A Microsoft Forms tevékenység csak az átfogó felvételi bővítménnyel érhető el.
