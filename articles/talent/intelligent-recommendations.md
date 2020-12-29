---
title: Intelligens ajánlások az Attract szolgáltatásban
description: Ez a cikk bemutatja, hogyan használható a gépi tanulás ajánlások nyújtására a feladatokhoz és a feladatokra pályázóknak a Microsoft Dynamics 365 Talent - Attract szolgáltatásban.
author: andreabichsel
manager: AnnBe
ms.date: 05/16/2019
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
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: fa06821c98e42dcd8590a764db9beb4a5c33fca2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461354"
---
# <a name="intelligent-recommendations-in-attract"></a>Intelligens ajánlások az Attract szolgáltatásban

[!include [banner](includes/banner.md)]

A gépi tanulás segít a toborzóknak és a felvételi menedzsereknek a munkakör legjobb jelöltjeinek gyors azonosításában. A potenciális jelölteknek is segíthet olyan munkakör keresésében, amely leginkább illik a profiljukhoz és az érdeklődésükhöz. A funkciók használatával és a beérkező visszajelzésekkel az ajánlások javulni fognak.

> [!NOTE] 
> - Az intelligens ajánlási funkciók csak az [Átfogó felvételi bővítménnyel](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) érhetők el.
> - A témakörben megjegyzett funkciók rendelkezésére állnak egy előzetes kiadás részeként. A tartalom és a funkciók megváltozhatnak. A funkció használatához kérje meg a rendszergazdát az engedélyezésére a **Felügyeleti központ** pontban az Attract megoldásban. Állítsa **Jelölt ajánlás**, **Állás ajánlás**, és **Potenciális jelöltek ajánlása** mezőket **Be** értékre. További tudnivalókért lásd: [Előzetes funkciókhoz való hozzáférés a Microsoft Dynamics 365 Talent szolgáltatásban](./access-preview-feature.md). 


## <a name="candidate-recommendations"></a>Jelentkező ajánlásai

Mivel az álláshirdetések több száz pályázót is vonzhatnak, nehéz lehet a toborzók és a felvételi menedzserek számára olyan jelentkezőket találni, akiknek a szakértelme és a háttere a legjobban megfelel a beosztásnak. A munkaköri leírás és a követelmények összefüggéseinek, és a pályázók önéletrajzának és profiladatainak elemzésével a gépi tanulás felhasználható jelöltajánlások létrehozásához. A jelöltajánlások segíthetnek a toborzók és a felvételi menedzserek számára azonosítani a legígéretesebb tehetségeket, és gyorsan továbbjuttatni őket az interjúk fázisába. Minden munkakörnél, ahol van tíznél több jelentkező vagy potenciális jelölt önéletrajzzal vagy teljes profillal, a jelentkezők vagy potenciális jelöltek, akik leginkább megfelelnek a munkakör követelményeinek, megjelennek a **Figyelembe veendő pályázók** szakaszban a **Munkakör** lapon.

Bármely javasolt jelöltnél választhatja a **Jelölt megtekintése** lehetőséget a pályázó kartonján, hogy áttekintse a jelentkező profilját, és műveletet végezzen az illető jelentkezésén. Használhatja a három pontos gombról (**...**) a pályázói profil egy új lapon való megnyitásához. A gombról segítségével az ajánlás kapcsolatban adhat visszajelzést is. Ezzel a módszerrel segítséget nyújthat az ajánlási motor finomhangolásához, és a jövőbeli ajánlások javításához. A nem tetsző ajánlásokat a rendszer eltávolítja a **Figyelembe veendő pályázók** szakaszból a **Munkakör** lap frissítésekor. A visszajelzés kártya használatával megadhatja, hogy miért nem találta az ajánlást hasznosnak.

## <a name="job-recommendations"></a>Munkakörajánlások 

Ha egy potenciális alkalmazott az előmeneteli webhely segítségével egy munkakörre jelentkezik, az Attract a szervezet más nyitott pozícióra is ajánlja. Ezek a javaslatok a potenciális jelölt múltbeli jelentkezésein, illetve a pályázó önéletrajzán és jelöltprofilján alapulnak. Ezért a munkakörajánlások segítenek a potenciális jelölteknek gyorsan azonosítani a számukra legjobban illő munkaköröket. A munkakörajánlások akkor állnak a potenciális jelentkező rendelkezésre, ha tíznél több munkakör van az előmeneteli webhelyen. Potenciális jelentkező megnyithatja az ajánlás kartonról az álláshirdetés részletes adatait. A jövőbeli ajánlások javítása érdekében az ajánlásokról visszajelzést is adhatnak.

## <a name="prospect-recommendations"></a>Potenciális jelöltekre vonatkozó javaslatok 

Ha egy új beosztást válik elérhetővé, a múltbeli pályázók és a tehetséghálózaton áttekintése eltarthat egy ideig. Az Attract segíthet ebben, intelligens gép tanulás algoritmus használatával. Ez azt jelenti, hogy Attract áttekinti az összes jelentkezőt, és ajánlja a megfelelőket már az állás létrehozásánál. Ezen javaslatok megtekintéséhez engedélyezze a **Potenciális** jelölt fázist az álláshoz. Eltarthat egy ideig az Attract számára a teljes jelölti adatbázis átvizsgálása ajánlások készítéséhez.

A javaslatok kártyaként jelennek meg a **Potenciális jelöltek** lapon minden álláshoz, ahol engedélyezve van **Potenciális jelölt** fázis. Ezeket a kártyák listázzák a szakértelmeket a potenciális jelölt profiljában, valamint az esetleges végzettségre, képesítésre vonatkozó információkat. Ha talál egy szimpatikus ajánlást a pályázót hozzáadhatja potenciális jelöltként ahhoz a munkához.

> [!NOTE]
> Ha nemrég kezdte el használni az Attract megoldást, várjon, amíg legalább 10 vagy több pályázók, akik teljes profillal vagy önéletrajzzal rendelkezik rendelkezésre áll, mielőtt elkezdené használni ezt a képességet.

Az elfogult ajánlások elkerülése érdekében, az Attract csak szakértelmeket, képesítéseket és egyéb kulcsszavakat keres a jelentkezői profilokban, amelyek megfelelnek az állás leírásának. Ezenkívül Attract a személyes azonosító adatokat eltávolítja a jelölt profilok kiértékelése előtt.
