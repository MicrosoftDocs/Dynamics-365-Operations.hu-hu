---
title: "Követelések és beszedések beállítása"
description: "Ez a cikk a beszedési funkciók beállítását ismerteti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4d3682c486e80afd03ec5805575357f4e87781f2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-credit-and-collections"></a>Követelések és beszedések beállítása

[!include[banner](../includes/banner.md)]


Ez a cikk a beszedési funkciók beállítását ismerteti.

<a name="set-up-aging-period-definitions"></a>Korosítási időszakok definícióinak beállítása
-------------------------------

Állítson be egy korosítási időszak meghatározást. Egy korosításiidőszak-definíció meghatározza az oszlopokat, amelyek megjelennek a **Korosított egyenlegek**, **beszedési tevékenységek**, és **beszedési esetek** listaoldalon. Meghatározza továbbá a **beszedés** lapon megjelenő időszakokat. Ha be van állítva a vevőgyűjtő, akkor az ahhoz megadott definíció szerinti korosítási időszakok lesznek használatban. Ha nincsenek beállítva gyűjtők, akkor az alapértelmezett korosításiidőszak-definíció kerül használatra, amely a **Kinnlevőségek paraméterei** lapon van megadva. Ha nincs megadva alapértelmezett korosításiidőszak-definíció, akkor a **korosításiidőszak-definíciók** lapon található első korosításiidőszak-definíció kerül használatra.

## <a name="create-an-aging-snapshot"></a>Korosítási pillanatkép létrehozása
Létrehozhat korosítási pillanatképrekordokat minden vevőre vagy egy adott vevőgyűjtőben levő vevőkre vonatkozóan. A korosítási pillanatkép információ megjelenik a**korosított egyenlegek** listaoldalon és a **beszedés** lapon. A listalap használatához előbb létre kell hozni egy korosítási pillanatképet. A listaoldal csak olyan vevőkről mutat információt, amelyek számára lett korosítási pillanatkép készítve.

## <a name="optional-set-up-customer-pools"></a>Vevőgyűjtők beállítása (nem kötelező)
A vevők csoportosítására vevőgyűjtőket hozhat létre. Használhatja a vevőgyűjtőket szűrőkként a vevői információhoz, amely a **beszedések** lap **beszedések** listaoldalán jelenik meg, vagy amikor korosítási pillanatképet hoz létre.

## <a name="optional-create-a-collections-team"></a>Beszedési csapat létrehozása (nem kötelező)
Ha a szervezetben többen foglalkoznak pénzbeszedéssel, beszedési csapatot hozhat létre. Kiválaszthatja a csapatot a **Kinnlevőségek paraméterei** lapon. Ha nem hoz létre egy kinnlevőségkezelő csapatot, akkor a csapat automatikusan létrejön, amikor beállítja a kinnlevőségkezelőket a **kinnlevőségkezelő** lapon.

## <a name="set-up-a-collections-case-category"></a>Beszedési esetkategória beállítása
Ha eseteket fog használni a beszedési munka megszervezéséhez, akkor állítson be egy esetkategóriát, amely rendelkezik a **beszedések** kategóriatípussal. Ez a beállítás csak akkor szükséges, ha használni akarja az eset funkciót a **beszedések** lapon.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Naplónevek beállítása (kiegyenlítés, leírás és elégtelen fedezet)
Állítson be naplóneveket, amelyek akkor használatosak, amikor a tranzakciók feldolgozásra kerülnek a **beszedések** oldalon. Ez a feldolgozás magában foglalja egy tranzakció kiegyenlítését, leírását és az elégtelen fedezetű (NSF) fizetés feldolgozását.

| Leírás | Naplótípus     |
|-------------|------------------|
| Kiegyenlítés  | Vevői kifizetés |
| Veszteségleírás   | Napi            |
| Elégtelen fedezet         | Vevői kifizetés |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Leírási tranzakciók okkódjainak beállítása
Állítsa be az alapértelmezett ok-kódot, amely akkor használatos, amikor a tranzakciók leírásra kerülnek a **beszedések** lapon. Módosíthatja a kódot a leírási folyamat ideje alatt.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Mappa beállítása e-mail mellékletekhez, e-mail sablonok létrehozása
Ha e-mail üzeneteket fog küldeni a **beszedések** lapról, amelyek Microsoft Excel mellékletekkel rendelkeznek, akkor létrehozhat opcionális e-mail sablonokat ezekhez az üzenetekhez.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Kinnlevőségek paramétereinek beállítása a beszedésekhez
Állítsa be a kinnlevőségek paramétereit, amelyek a **beszedések** lapon jelennek meg.

## <a name="optional-set-up-collections-agents"></a>Pénzbehajtók beállítása (nem kötelező)
Ha a szervezetben többen foglalkoznak pénzbeszedéssel, pénzbehajtókat adhat meg. A kinnlevőségkezelő egy olyan dolgozó, aki felhasználóként van beállítva a **felhasználói kapcsolatok** lapon. Hozzárendelhet vevőgyűjtőket (vevőlekérdezéseket) a kinnlevőségkezelőkhöz, hogy segítse őket a munkájuk szervezésében. A kinnlevőségkezelők hozzáadódnak a **kinnlevőségek paraméterei** lapon kijelölt csapathoz. Ha egy csapat nincs kijelölve ezen az oldalon, akkor automatikusan létrejön egy új csapat **beszedések** névvel és a kinnlevőségkezelők hozzáadódnak a csapathoz.

## <a name="set-up-a-writeoff-account"></a>Leírási számla beállítása
A leírási számla beállítása, amely a főkönyvi számla leírásához használatos a tranzakciók leírásakor. Ez a számla a vevő feladási profilján van tárolva.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Elégtelen fedezettel kapcsolatos adatok megadása bankszámlákhoz
Frissítse a bankszámlákat, hogy a megfelelő naplóval rendelkezzenek, amikor az elégtelen fedezetű fizetések azonosításra kerülnek a **beszedések** lapon. A **pénznemek kezelése** lapon a **elégtelen fedezetű kifizetések naplója** mezőben, válasszon ki egy kifizetési naplót.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Outlook beállítások felvétele a felhasználók számára a beszedések lapon
Mielőtt a dolgozók műveleteket tudnak létrehozni, vagy e-mail üzeneteket küldeni a **Beszedések** lapon ellenőriznie kell, hogy a **Microsoft Outlook szinkronizáció** konfigurációs kulcs ki van jelölve és hogy az Outlook szinkronizáció be van állítva az adott dolgozóknak.

## <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>E-mail beállítások és címek megadása a vevők beszedéskezelési kapcsolattartóihoz
Állítson be e-mail címeket a vevő kapcsolattartóknak, ha e-mail üzeneteket akar küldeni ezeknek a kapcsolattartóknak a **beszedések** lapról. A beszedési kapcsolattartó használatos alapértelmezett kapcsolattartóként a **beszedések** lapon. Beállíthat egy kivonatküldési címet egy vevőhöz ha a kivonatoknak egy az elsődleges címtől eltérő címet kell használniuk. 

A vevőhöz tartozó **követelések és beszedések** gyorslapon a **beszedési kapcsolattartó** mezőben jelölje ki azt a személyt a vevő szervezetében, aki az Ön kinnlevőségkezelőjével dolgozik. Ez a személy használatos alapértelmezett kapcsolattartóként a **beszedések** lapon és az e-mail üzenetek neki kerülnek elküldésre. 

> [!NOTE] 
> Ha egy beszedési kapcsolattartó nincs megadva a vevőhöz, akkor a vevő elsődleges kapcsolattartója kerül használatra. Ha egy elsődleges kapcsolattartó nincs megadva, akkor az e-mail üzenetek a **kapcsolattartók** lapon szereplő első címre lesznek kiküldve.

## <a name="set-up-email-settings-for-salespeople"></a>Üzletkötők e-mail beállításainak megadása
Állítson be e-mail címeket az értékesítőknek, ha e-mail üzeneteket akar küldeni nekik a **beszedések** lapról. Állítson be e-mail címet az egyes értékesítési jutalékcsoportokhoz tartozó összes üzletkötőnek. Az értékesítési képviselő, akinél ki van jelölve a **kapcsolattartó** opció az alapértelmezett értékesítő, akinek az e-mail üzenetek ki lesznek küldve. 

Ha az értékesítési képviselő nincs megadva, akkor a vevőszervezethez tartozó elsődleges értékesítő kerül használatra. Ha az elsődleges értékesítő nincs megadva, akkor az e-mail üzenetek a lapon szereplő első értékesítőhöz lesznek kiküldve.




