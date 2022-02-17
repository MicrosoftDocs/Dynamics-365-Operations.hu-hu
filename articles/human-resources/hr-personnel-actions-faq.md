---
title: Személyzeti műveletek GYIK
description: Ez a témakör azokra a kérdésekre ad válaszokat, amelyek akkor merülhetnek fel, ha szervezete személyzeti műveleteket használ.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c952bdc95b49c92fea34aef63b57c7e193b2f09a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065151"
---
# <a name="personnel-actions-faq"></a>Személyzeti műveletekkel kapcsolatos GYIK


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör azokra a kérdésekre ad válaszokat, amelyek akkor merülhetnek fel, ha szervezete személyzeti műveleteket használ. A személyzeti műveletek olyan kiegészítő lépések, amelyeket bizonyos személyzeti feladatok végrehajtásakor kell elvégeznie. 

Példák azokra a feladatokra, amelyek személyzeti tevékenységet igényelhetnek:
 - Amikor új pozíciókat hoz létre. 
 - Módosítsa a meglévő pozícióértékeket. 
 - Vegyél fel új dolgozókat. 
 - Munkavállalók áthelyezése. 
 - Munkavállalói kompenzáció módosítása. 
 - Pozíció-hozzárendelések módosítása. 
 - Munkavállalók megszüntetése.

> [!NOTE]
> A személyi intézkedések csak akkor érhetők el, ha a **Munkavállalói műveletek engedélyezése** és **Pozícióműveletek engedélyezése** mezők be vannak állítva **Igen**, ban,-ben **Személyzeti intézkedések** fülön a **Az emberi erőforrások megosztott paraméterei** oldalon. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Honnan tudhatom, hogy a szervezetemnél szükség van személyzeti műveletekre?
Ha a szervezet előír bizonyos személyzet műveleteket, akkor a rendszer felszólítja ezek elvégzésére olyankor, amikor új beosztásokat hoz létre, meglevő beosztásokat módosít, új dolgozókat vesz fel, dolgozókat visz át, dolgozók kompenzációját módosítja, beosztás-hozzárendeléseket módosít, dolgozóknak felmond, vagy amikor távollétet rögzít. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Mi a különbség egy beosztásművelet és egy dolgozói művelet között?
A személyzeti műveleteket két típusra osztjuk:

- **Pozíció** művelet – A pozícióművelet a meglévő vagy új pozíciókon történik. Beosztásműveletre lehet például szükség, ha módosítja egy létező beosztás értékét, vagy új szezonális beosztást hoz létre. 

- **Munkás** művelet – A dolgozói művelet végrehajtása meglévő alkalmazottakon vagy új alkalmazottakon történik. Dolgozói műveletre van szükség például akkor, ha egy új alkalmazottat vesz fel, vagy egy meglévő alkalmazottat előléptet. 

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Mit jelentenek a személyzeti műveletek állapotai?
A személyzeti műveletek a következő állapotokat vehetik fel:

- **Tervezet** – Ha munkafolyamatokat használ, akkor művelet még nem lett elküldve. Ha nem használ munkafolyamatokat, akkor a művelet nem lett befejezve.
- **Ellenőrzés alatt** – A személyzeti műveletet beküldték a munkafolyamatba, de a munkafolyamat nem fejeződött be.
- **Jóváhagyva várakozik** – A munkafolyamat befejeződött, de a módosítások még folyamatban vannak. **Törölve** – A munkafolyamatot megszakították vagy a személyzeti műveletet visszahívták. **Elutasítva** – Az intézkedési kérelmet a jóváhagyó elutasította.
- **Művelet feldolgozása** – A műveletkérelmet jóváhagyták, a módosítások feldolgozás alatt állnak.
- **Munkafolyamat befejezve** – A munkafolyamat befejeződött és a módosításokat feldolgozták. **nem sikerült** – A munkafolyamat meghiúsult, mert az információ elavult. Kattintson **Aktiválja újra** a legfrissebb információk megjelenítéséhez és a folytatáshoz.
- **Befejezve** – A beosztást sikeresen létrehozták vagy módosították, vagy az alkalmazottat sikeresen felvették, átvették vagy elbocsátották, vagy kompenzációját sikeresen megváltoztatták. **Hiba** – Az információ elavultságától eltérő probléma történt. Nyissa meg a **Személyzeti műveletek üzenetnaplója** a hiba okának megállapításához.
- **Megtagadva** – A műveletkérelmet elutasította a jóváhagyó.

## <a name="can-i-delete-a-personnel-action"></a>Lehetséges személyzeti műveleteket törölni?
Igen, törölheti az olyan személyzeti műveleteket, amelyek állapota **Tervezet**, **Hiba**, **Sikertelen** vagy **Megszakítva**. Csak akkor törölhet **Befejeződött** állapotú személyzeti műveleteket, ha a **Befejeződött dolgozói műveletek törlésének engedélyezése** lehetőséget a **Human Resources megosztott paraméterei** oldalon **Igen** állapotúra állította.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Hogyan tudom a leggyorsabban ellenőrizni egy személyzeti művelet kérelmének állapotát?
Nyissa meg bármelyiket **Személyzeti intézkedés** listázza az oldalakat, és válasszon egy személyzeti műveletet.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Mit tegyek, ha egy személyzeti műveletkérelem sikertelen?
Ha egy személyzeti műveleti kérelem sikertelen, az alábbi lépésekkel tudja megoldani a hibát és újraküldeni a kérelmet:

> 1. A **Műveleti ablaktáblában** kattintson a **Hibaüzenet** gombra a hibaüzenet szövegének megtekintéséhez.
> 
> 2. A **Műveleti ablaktáblában** az **Újraaktiválása** gombra kattintva betöltheti a legutóbbi információkat, és a személyzeti műveletet visszaállíthatja **Tervezet** állapotba.
> 
> 3. Oldja meg a hibát, majd kattintson a **Befejezés** vagy a **Küldés** opcióra.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Mi történik a munkafolyamatot használó személyzeti műveletekkel a végleges jóváhagyás után?
Ha nincsenek hibák, a személyzeti művelet írásvédetté válik. (Az előzményeket megtekintheti a **Minden munkás tevékenység** lista oldalon, de a személyi műveletet nem módosíthatja.) Amikor a személyi művelet állapota az **Befejezve**, a pozíció vagy a munkavállaló rekordja már frissült. A végrehajtott módosítások megtekintéséhez nyissa meg a **Beosztások** vagy a **Dolgozók** listaoldalt.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Miért jelenik meg a következő hiba, ha nem nullát adok meg a Fizetési díjalap mezőben? "Az érték kívül esik az érvényes tartományon: 0,00 és 0,00 között kell lennie"
Ezt az üzenetet azért kapja, mert a **Szint** mező a **Munka** oldal üres a kiválasztott pozícióhoz társított munkánál.

A hiba elhárításához kövesse az alábbi lépéseket:

> 1. A **Munkavállalói beosztási feladatok** oldalt, kattintson rá **Pozíció** terület.  
> 2. Kattints a **Munka** mező értékét a **Munka** oldalon.
> 3. A Művelet ablaktáblán kattintson a gombra **Szerkesztés**.
> 4. Kattints a **Kártérítés** lapon.
> 5. Ban,-ben **Szint** mezőben válassza ki a szintet.
> 6. Csukja be a **Munka** oldalon.
> 7. Csukja be a **Pozíció** oldalon.
> 8. Vissza a **Kártérítés** fülön a **Munkás** oldal, válassza ki **Fix kompenzáció**.  Válassza ki **Új** és írja be a munkavállaló pozícióját a **Pozíció** terület.  Adjon meg egy értéket a **Terv** mezőbe, majd írja be a munkavállaló kompenzációját a **Fizetési besorolás** terület.

## <a name="why-cant-i-change-the-effective-date-on-the-header-of-the-worker-action-page"></a>Miért nem tudom megváltoztatni a hatálybalépés dátumát a Munkavállalói művelet oldal fejlécében?
Az érvénybe lépési dátum nem módosítható, mert a mezőbe a rendszer a művelettípusra vonatkozóan leginkább logikus dátumot írja be.

Példa:

- A **Felmondás egy dolgozónak** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Munkaviszony megszűnésének dátuma** mezőben adott meg.
- A **Dolgozó felvétele** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Foglalkoztatás kezdő dátuma** mezőben adott meg.
- A **Dolgozó áthelyezése** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Megbízás kezdési dátuma** mezőben adott meg a dolgozó vonatkozásában.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
