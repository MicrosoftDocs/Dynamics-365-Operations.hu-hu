---
title: Karbantartási ellenőrzőlisták
description: Ez a témakör az Eszközkezelés karbantartási ellenőrzőlistájait ismerteti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 25e9139ce57283482d8da4b7f1e5d6275c74ad28
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854529"
---
# <a name="maintenance-checklists"></a>Karbantartási ellenőrzőlisták

[!include [banner](../../includes/banner.md)]



A karbantartási ellenőrzőlisták a karbantartási feladattípusokon állíthatók be. A karbantartási ellenőrzőlisták kitöltése egy munkarendelés elvégzési folyamatának része. További információért lásd a **Karbantartási feladattípus-kategóriák és a karbantartási feladattípusok, a karbantartási feladattípus változatok és karbantartási ellenőrzőlisták** szakaszt a karbantartási beállításával a karbantartási feladattípusokhoz folyamatával kapcsolatban. a [Karbantartási feladattípusok alapértelmezései](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) képernyőn.

Amikor egy munkarendelésen dolgozik a karbantartási ellenőrző, kitöltheti a karbantartási feladattípusokhoz kapcsolódó előre definiált karbantartási ellenőrzőlistákat. További karbantartási ellenőrzőlistákat is hozzáadhat.


## <a name="fill-in-a-maintenance-checklist"></a>Egy karbantartási ellenőrzőlista kitöltése

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést, majd a Művelet panel **Munkarendelés** lapján a **Sorok** csoportban válassz a **Karbantartási ellenőrzőlista** pontot.

3. A **Munkarendelés karbantartásifeladat-ellenőrzőlista** megmutatja munkarendelési feladattokkal kapcsolatos karbantartási ellenőrzőlistákat. Ha a munkarendelés-feladatok különböző karbantartási feladattípusokkal rendelkeznek, akkor az egyes munkarendelések feladatai esetében a karbantartási ellenőrzőlisták eltérők lehetnek. Válassza ki a munkarendelési feladatot. amely a kapcsolódó karbantartási ellenőrzőlistával működik. A kiválasztott karbantartási ellenőrzőlistasor részletei a **Sor részletei** gyorslapon láthatók.

4. Hajtsa végre az összes karbantartási ellenőrzőlista-sort, egyesével a megjelenési sorrendben. A karbantartási ellenőrzőlista sor kitöltését a **Sor részletei** gyorslap mezőinek kitöltésével végezheti el. A sorok teljesítéséhez szükséges információk a sor típusától függően változhatnak. Ha például egy **Szöveg** típusú sornál egy megjegyzést ad meg, elmagyarázhatja, hogy mi volt az ellenőrzés eredménye. A **Mérés** típusú sorokban megadhatja a berendezésen leolvasott számláló értékét, és szükség esetén megjegyzést is hozzáadhat. A **Fejléc** típusú karbantartásiellenőrzőlista-sor az alatta megjelenő karbantartásiellenőrzőlista-sorok csoportosításához használatos. Nem kell a fejlécet kitöltenie. Az összes többi típusú karbantartási ellenőrzőlista-sor esetében a **Fejléc** típusú sorhoz hozzáadhat egy típust.

5. Ha a karbantartási ellenőrzőlista sorához kapcsolódnak utasítások, akkor a **Utasítások** jelölőnégyzet be van jelölve. A kiválasztott karbantartási ellenőrzőlista sorához tartozó utasításokat olvassa el a **Sor részletei** gyorslap **Utasítások** mezőjében.

6. Ha befejezte a karbantartási ellenőrzőlista sorát, jelölje be az **Ellenőrizve** jelölőnégyzetet a soron annak befejezettként való megjelöléséhez. A karbantartási ellenőrzőlista sorának elvetéséhez, mert az nem releváns a munkarendeléshez, jelölje be az **N/A** jelölőnégyzetet a sorban. Ha a karbantartás ellenőrzőlista sorában a **Kötelező** jelölőnégyzet be van jelölve, akkor be kell jelölni a **Bejelölt** jelölőnégyzetet vagy az **N/A** a jelet.

>[!NOTE]
>Csak akkor frissítheti a karbantartási ellenőrzőlista-regisztrációkat, ha a munkarendelés [Aktív](../setup-for-work-orders/work-order-lifecycle-states.md) életciklus-állapotban van.  


## <a name="add-a-maintenance-checklist-line"></a>Karbantartási ellenőrzőlista sor hozzáadása

A karbantartási ellenőrzőlisták a karbantartási feladattípus alapértelmezése definíciója alapján hozza létre a program, és átviszi a munkarendelés feladatára. Igény szerint a karbantartási ellenőrzőlista sorait felveheti egy munkarendelés feladatához. A manuálisan hozzáadott karbantartási ellenőrzőlista sorok a **Manuális** hivatkozást kapják.

1. A **Munkarendelés karbantartásifeladat-ellenőrzőlista** oldalon válassza ki a munkarendelés-feladatot, amelyet hozzá szeretne adni a karbantartási ellenőrzőlistához.

2. A **Karbantartási ellenőrzőlista-sorok** gyorslapon válasszon egy karbantartási ellenőrzőlista sort. Új sor beszúrásához nyomja le a kijelölt sor alá nyomja meg a **Lefele nyíl** billentyűt. A sorozatban következő szám automatikusan be lesz illesztve a **Sor száma** mezőbe. Ha új sort szeretne beszúrni a kiválasztott sor elé, válassza a **Sor hozzáadása** lehetőséget. 

3. A **Név** mezőben adja meg az új karbantartásiellenőrzőlista-sor nevét.

4. A **Típus** mezőben válasszon egy típust karbantartásiellenőrzőlista-sorhoz. Minden karbantartásiellenőrzőlista-típushoz a **Sor részletei** gyorslap tartalmazza a kapcsolódó mezőket.
    - **Szöveg** – Ezzel a típussal hozzáadhat egy olyan karbantartási ellenőrzőlista-sort, amely leírja, hogy mit kell tenni. Például ezt a típust akkor használhatja, ha azt szeretné, hogy a dolgozó ellenőrizzen vagy megvizsgáljon valamit, de nem vár konkrét (mérhető) eredményt. Miután kiválasztotta ezt a típust, a **Sorok részletei** gyorslap **Utasítások** mezőjébe írja be azt a szöveget, amely leírja, hogy mit kell tenni.
    - **Fejléc** – Az ilyen típusú karbantartásiellenőrzőlista-sor az alatta megjelenő karbantartásiellenőrzőlista-sorok csoportosításához használatos. Ez a típus akkor hasznos, ha több karbantartásiellenőrzőlista-sor van, amelyek meghatározott területekre oszthatók fel. Miután kiválasztotta a típust, írjon be egy leíró nevet a **Név** mezőbe.
    - **Sablon** – Ez a típus nem alkalmazható, ha manuálisan ad hozzá egy munkarendelés-feladathoz egy karbantartási ellenőrzőlista sort.  
    - **Változó** – Egy karbantartási ellenőrzőlista-sor lehetséges eredményének tartománya meghatározásához használja ezt a típust. A karbantartási ellenőrzőlisták változóinak beállításával kapcsolatos további információért lásd: [Karbantartásifeladat-típusok kategóriái és karbantartásifeladat-típusok, karbantartásifeladat-típusok változatai, karbantartási szakmák és karbantartási ellenőrző listák](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Miután kiválasztotta a típust, írjon be egy leíró nevet a változóhoz a **Név** mezőbe. Válassza ki **Sor részletei** gyorslapon, a **Változó** mezőben válassza ki a változót. A **Utasítások** mezőbe írja be a szöveget, ami leírja hogy mi a feladat.
    - **Mérés** – Ezzel a típussal rögzítheti a karbantartási ellenőrzőlista sorában az adott mérést. Miután kiválasztotta a típust, írjon be egy nevet a mérésnek a **Név** mezőbe. Válassza ki a **Sor részletei** gyorslap **Számláló** és **Egység** mezőiben a megfelelő értékeket. A **Utasítások** mezőbe írja be a szöveget, ami leírja hogy mi a feladat.

5. Amikor befejezte a karbantartási ellenőrzőlista sorainak manuális hozzáadását, töltse ki a sorokat a fenti **Karbantartási ellenőrzőlista** kitöltése című részben leírtak szerint.

>[!NOTE]
>A **Munkarendelés karbantartási feladatának ellenőrzőlistája** oldalon a **Feladattípus** hivatkozással rendelkező karbantartási ellenőrzőlista sorokat nem törölheti. Csak a **Manuális** hivatkozással rendelkező karbantartási ellenőrzőlista sorokat lehet törölni, amelyekhez Ön vagy más karbantartó dolgozók készítettek manuálisan.

A következő ábrán egy karbantartási ellenőrzőlista példája látható.

![1. ábra](media/14-work-orders.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]