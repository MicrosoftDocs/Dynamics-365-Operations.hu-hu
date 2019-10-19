---
title: Tevékenységek a Microsoft Dynamics 365 Talent – Attract folyamataiban
description: Ez a témakör a Microsoft Dynamics 365 Talent – Attract felvételi folyamatában használható különféle tevékenységekkel kapcsolatban tartalmaz tájékoztatást.
author: hasrivas
manager: AnnBe
ms.date: 05/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 2e40250bb801f6222d16400b2698e5b0df47a404
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008685"
---
# <a name="activities-in-hiring-processes"></a>Tevékenységek a toborzási folyamatban

[!include[banner](../includes/banner.md)]

A tevékenységek a felvételi folyamat részeként adhatók hozzá a Microsoft Dynamics 365 Talent: Attract esetében. A tevékenységeket folyamatsablonhoz lehet hozzáadni, vagy közvetlenül az állásnál adhatók hozzá a felvételi folyamathoz. Ha megadott egy állást, ki lesz választva egy folyamat, és a tevékenységek, amelyek szerepelnek a sablonban, az álláshoz adódnak. Az alapértelmezett sablont használja a rendszer, ha nincs sablon kiválasztva. A felvételi folyamat is módosítható az álláson a sablon alkalmazása után.

> [!NOTE] 
> A folyamatsablonok az Átfogó felvételi bővítmény részeként érhetők el. További információért lásd: [Az Attract Átfogó felvételi bővítmény lehetőségei](./attract-comprehensive-hiring.md)

## <a name="prospect-activity"></a>Potenciális tevékenység

A potenciális tevékenység azt szabályozza, hogy a potenciális jelöltek hozzáadhatók-e egy álláshoz. Alapértelmezés szerint potenciális jelöltek adhatók az álláshoz. A potenciális tevékenység kikapcsolásához állítsa a **Potenciális jelöltek engedélyezése** lehetőséget **Ki** beállításra. A potenciális tevékenység bekapcsolásakor a felvételi vezetők hozzáadhatják és megtekinthetik a potenciális jelölteket, és a **Potenciális jelölt** lap megjelenik az állásnál.

> [!NOTE]
> Ha engedélyezni szeretné, hogy a jelentkezők hozzá legyenek álláshoz a LinkedIn webhelyről, állítsa a **Potenciális jelöltek** elemet **Be** értékre.

## <a name="application-activity"></a>Pályázat tevékenység

A Pályázat tevékenység kötelező a felvételi folyamat sablonban. E-mail küldéséhez a pályázóknak a jelentkezésük benyújtásakor vagy amikor hozzáadják őket a Pályázat szakaszhoz, állítsa az **E-mail küldése a pályázónak** lehetőséget az **Igen** beállításra.

## <a name="interview-schedule-and-feedback-activity"></a>Interjú ütemezése és visszajelzés tevékenység

A tevékenység három összetevőből áll: pályázó elérhetőségének lekérése, ütemezés és visszajelzés. Használja az állássablon interjú tevékenységét, ha szeretné szerepeltetni a folyamatban a jelölt rendelkezésre állásának kérését, ütemezést és visszajelzést, ahelyett, hogy egyenként a felvételi folyamat részeként használná őket. További tudnivalókért lásd: [Interjú ütemezése és visszajelzés](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>PowerApps-tevékenység

A PowerApps tevékenység lehetővé teszi Microsoft PowerApps alkalmazás beágyazását a felvételi folyamatba. Az alkalmazás összes jelentkező, csak a belső pályázók, csak a külső pályázók vagy egy pályázó számára sem lehet szükséges. Ha az alkalmazás kötelezőként van megjelölve, akkor el kell végezni a következő szakaszba való továbblépés előtt. Ahhoz, hogy befejezettnek lehessen tekinteni, a **JobApplicationStatus** mezőnek **Kész** állapotúnak kell lennie. A mező a JobApplicationActivity entitásban található, így a PowerApps alkalmazásnak frissítenie kell ezt a mezőt, mielőtt a fokozatot előre lehet léptetni. Ha az alkalmazás nem szükséges, a tevékenység (nem kötelező), és a fokozat lehet előbbre akkor is, ha az alkalmazás nem befejeződött.

A PowerApps tevékenység mentéséhez a felvételi folyamatba, meg kell adnia egy PowerApps-azonosítót. A PowerApps-azonosító megkereséséhez ugorjon ide: [PowerApps](https://web.powerapps.com), válassza az **Alkalmazások**, majd a **Részletek** lehetőséget.

Alapértelmezés szerint a PowerApps tevékenység a felvételi vezető, a toborzó és az ő delegáltjaik számára elérhető. Ha kiválasztja a **Résztvevők tevékenységhez való hozzáadásának engedélyezése** lehetőséget, a PowerApps tevékenység használó alkalmazásokhoz további résztvevők is hozzáadhatók a felvételi csapatból. Például egy szervezet létrehozott egy PowerApps alkalmazást, amely interjúkérdések tára a műszaki szerephez. A szervezet most felvesz egy új szoftverfejlesztőt, és hozzáadta a PowerApps tevékenységet a felvételi folyamathoz a szoftverfejlesztők szerepkörhöz. Ha a **Résztvevők tevékenységhez való hozzáadásának engedélyezése** beállítás be van jelölve, a szoftverfejlesztő szerepkörre pályázót megnyitó toborzó vagy felvételi vezető interjúkészítőket vehet fel a PowerApps tevékenységhez. Ezek a személyek ezt követően megtekinthetik az alkalmazást, amely az interjúkérdéseket tartalmazza.

> [!NOTE]
> A PowerApps tevékenység csak az átfogó felvételi bővítménnyel érhető el. További információért lásd: [Az Attract Átfogó felvételi bővítmény lehetőségei](./attract-comprehensive-hiring.md)

## <a name="youtube-activity"></a>YouTube-tevékenység

A YouTube tevékenység segítségével megoszthat a felvételi folyamat részeként YouTube videókat. A felvételi folyamatba a YouTube tevékenység mentéséhez meg kell adnia a YouTube videó URL-címét. Választhat, hogy a tartalmat a **Felvételi csapat**, **Csak belső jelöltek**, **Csak külső jelöltek** vagy **Minden jelölt** számára megjeleníti. Mint a PowerApps tevékenységnél, engedélyezheti a felvételi csapatból származó résztvevők hozzáadását a tevékenységhez. Ha úgy dönt, megjeleníti a tartalmat a jelölteknek, a videó csak a jelölti élmény részeként jelenik meg, és nem a felvételi folyamatban.

> [!NOTE]
> A YouTube tevékenység csak az átfogó felvételi bővítménnyel érhető el. További információért lásd: [Az Attract Átfogó felvételi bővítmény lehetőségei](./attract-comprehensive-hiring.md)

## <a name="web-content-activity"></a>Webes tartalom tevékenység

A webes tartalom tevékenységgel online tartalom ágyazható be a felvételi folyamatba. A felvételi folyamatba a webes tartalom tevékenység mentéséhez meg kell adnia a webes tartalom URL-címét. Választhat, hogy a tartalmat a **Felvételi csapat**, **Csak belső jelöltek**, **Csak külső jelöltek** vagy **Minden jelölt** számára megjeleníti. Mint a PowerApps és YouTube tevékenységeknél, engedélyezheti a felvételi csapatból származó résztvevők hozzáadását a tevékenységhez. Ha úgy dönt, megjeleníti a tartalmat a jelölteknek, a webes tartalom csak a jelölti élmény részeként jelenik meg, és nem a felvételi folyamatban. A megjelenő tartalom mérete kiválasztható.

> [!NOTE]
> A webes tartalom tevékenység csak az átfogó felvételi bővítménnyel érhető el. További információért lásd: [Az Attract Átfogó felvételi bővítmény lehetőségei](./attract-comprehensive-hiring.md)

## <a name="microsoft-forms-activity"></a>Microsoft Forms tevékenység

A Microsoft Forms tevékenység lehetővé teszi Microsoft Forms tevékenység beágyazását a felvételi folyamatba. A Microsoft Forms segítségével teszteket, felméréseket és lekérdezéseket hozhat létre. A felvételi folyamatba a Microsoft Forms tevékenység mentéséhez meg kell adnia az űrlap URL-címét. Választhat, hogy a tartalmat a **Felvételi csapat**, **Csak belső jelöltek**, **Csak külső jelöltek** vagy **Minden jelölt** számára megjeleníti. Mint a PowerApps, YouTube és webes tartalomhoz kapcsolódó tevékenységeknél, engedélyezheti a felvételi csapatból származó résztvevők hozzáadását a tevékenységhez. Ha úgy dönt, megjeleníti a tartalmat a jelölteknek, az űrlap csak a jelölti élmény részeként jelenik meg, és nem a felvételi folyamatban.

A Microsoft Forms esetében a szerző módosíthatja a beállításokat, hogy a szervezeten kívüli felhasználók válaszolhassanak a felmérésre vagy a tesztre. Ebben az esetben a felhasználók névtelenül küldik a válaszok. Ha meg szeretné nézni, hogy ki töltötte ki a felmérést vagy a tesztet, előírhatja, hogy a válaszadók írják be a nevüket a felmérés vagy teszt részeként.

> [!NOTE]
> A Microsoft Forms tevékenység csak az átfogó felvételi bővítménnyel érhető el. További információért lásd: [Az Attract Átfogó felvételi bővítmény lehetőségei](./attract-comprehensive-hiring.md)

## <a name="offer-activity"></a>Ajánlattal kapcsolatos tevékenység

A felvételi folyamat sablonjához szükséges az Ajánlattal kapcsolatos tevékenység. Az integrált ajánlatkezelési alkalmazás használatához állítsa a **Offer Management alkalmazás futtatása az ajánlatkészítésben** beállítást **Be** értékre. Ha ez a beállítás ki van kapcsolva, akkor a jelölt nem jelenik meg az Offer alkalmazásban, így a jelölt ajánlattal kapcsolatos tevékenységében végzett frissítéseket manuálisan kell nyomon követnie. Ha be szeretné állítani, hogy a felvételi vezető ajánlatot készíthet elő a jelölt számára az Offer alkalmazásban, állítsa az **A felvételi vezető létrehozhat ajánlatot** beállítást **Be** értékre. Ha ehhez az álláshoz több társított pozíció is tartozik, eldöntheti, hogy több ajánlatot készít-e elő ugyanannyi pozíciószámhoz. Ha csak egy ajánlat létrehozását szeretné engedélyezni pozíciónként és állásonként, állítsa az **A pozíciók álláson belüli ismételt használatának engedélyezése** beállítást **Ki** értékre.

> [!NOTE]
> Az integrált Offer Management alkalmazás csak az Átfogó felvételi bővítménnyel érhető el. További információért lásd: [Az Attract Átfogó felvételi bővítmény lehetőségei](./attract-comprehensive-hiring.md)


