---
title: Személyzeti műveletek GYIK
description: Ez a témakör azokra a kérdésekre ad válaszokat, amelyek akkor merülhetnek fel, ha szervezete személyzeti műveleteket használ.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 0782f686c9c91d434214724e2f621225a9e268b3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692142"
---
# <a name="personnel-actions-faq"></a>Személyzeti műveletekkel kapcsolatos GYIK


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör azokra a kérdésekre ad válaszokat, amelyek akkor merülhetnek fel, ha szervezete személyzeti műveleteket használ. A személyzeti műveletek olyan kiegészítő lépések, amelyeket bizonyos személyzeti feladatok végrehajtásakor kell elvégeznie. 

Példák személyzeti műveleteket igénylő feladatokra:
 - Új beosztások létrehozásakor. 
 - Meglévő beosztásértékek módosítása. 
 - Új dolgozók felvétele. 
 - Dolgozók átvitele. 
 - Dolgozói kompenzáció módosítása 
 - Beosztás-hozzárendelések módosítása 
 - Felmondás a dolgozóknak.

> [!NOTE]
> Személyzeti műveletek csak akkor érhetők **el** **·** **, ha a Dolgozói műveletek engedélyezése és a Beosztásműveletek engedélyezése mező Beállítása Igen** beállítású, **·** **az Emberi erőforrások megosztott paraméterei lap Személyzeti műveletek lapján.** 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Honnan tudhatom, hogy a szervezetemnél szükség van személyzeti műveletekre?
Ha a szervezet előír bizonyos személyzet műveleteket, akkor a rendszer felszólítja ezek elvégzésére olyankor, amikor új beosztásokat hoz létre, meglevő beosztásokat módosít, új dolgozókat vesz fel, dolgozókat visz át, dolgozók kompenzációját módosítja, beosztás-hozzárendeléseket módosít, dolgozóknak felmond, vagy amikor távollétet rögzít. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Mi a különbség egy beosztásművelet és egy dolgozói művelet között?
A személyzeti műveleteket két típusra osztjuk:

- **Beosztás** művelete – beosztási művelet történik a meglévő beosztásokkal vagy az új beosztásokkal. Beosztásműveletre lehet például szükség, ha módosítja egy létező beosztás értékét, vagy új szezonális beosztást hoz létre. 

- **Dolgozói** művelet – a dolgozói művelet a meglévő alkalmazottakon vagy az új alkalmazottakon történik. Dolgozói műveletre van szükség például akkor, ha egy új alkalmazottat vesz fel, vagy egy meglévő alkalmazottat előléptet. 

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Mit jelentenek a személyzeti műveletek állapotai?
A személyzeti műveletek a következő állapotokat vehetik fel:

- **Tervezet** – Ha munkafolyamatokat használ, akkor művelet még nem lett elküldve. Ha nem használ munkafolyamatokat, akkor a művelet nem lett befejezve.
- **Ellenőrzés alatt** – A személyzeti műveletet beküldték a munkafolyamatba, de a munkafolyamat nem fejeződött be.
- **Jóváhagyva várakozik** – A munkafolyamat befejeződött, de a módosítások még folyamatban vannak. **Megszakítva** – a munkafolyamatot megszakította, vagy visszahívta a személyzeti műveletet. **Elutasítva** – a műveletkkérést a jóváhagyó elutasította.
- **Művelet feldolgozása** – A műveletkérelmet jóváhagyták, a módosítások feldolgozás alatt állnak.
- **Munkafolyamat befejezve** – A munkafolyamat befejeződött és a módosításokat feldolgozták. **Sikertelen** – a munkafolyamat nem sikerült, mert az információ elavult. A **legfrissebb adatok megjelenítéséhez és a folytatáshoz** kattintson az Újraaktiválás gombra.
- **Befejezve** – A beosztást sikeresen létrehozták vagy módosították, vagy az alkalmazottat sikeresen felvették, átvették vagy elbocsátották, vagy kompenzációját sikeresen megváltoztatták. **Hiba** – a hiba a dátumon kívül más probléma lépett fel. A Személyzeti műveletek **üzenetnapló megnyitása** a hiba okának meghatározásához.
- **Megtagadva** – A műveletkérelmet elutasította a jóváhagyó.

## <a name="can-i-delete-a-personnel-action"></a>Lehetséges személyzeti műveleteket törölni?
Igen, törölheti az olyan személyzeti műveleteket, amelyek állapota **Tervezet**, **Hiba**, **Sikertelen** vagy **Megszakítva**. Csak akkor törölhet **Befejeződött** állapotú személyzeti műveleteket, ha a **Befejeződött dolgozói műveletek törlésének engedélyezése** lehetőséget a **Human Resources megosztott paraméterei** oldalon **Igen** állapotúra állította.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Hogyan tudom a leggyorsabban ellenőrizni egy személyzeti művelet kérelmének állapotát?
A Személyzeti művelet listaoldalak **bármelyikének** megnyitása és egy személyzeti művelet kiválasztása.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Mit tegyek, ha egy személyzeti műveletkérelem sikertelen?
Ha egy személyzeti műveleti kérelem sikertelen, az alábbi lépésekkel tudja megoldani a hibát és újraküldeni a kérelmet:

> 1. A **Műveleti ablaktáblában** kattintson a **Hibaüzenet** gombra a hibaüzenet szövegének megtekintéséhez.
> 
> 2. A **Műveleti ablaktáblában** az **Újraaktiválása** gombra kattintva betöltheti a legutóbbi információkat, és a személyzeti műveletet visszaállíthatja **Tervezet** állapotba.
> 
> 3. Oldja meg a hibát, majd kattintson a **Befejezés** vagy a **Küldés** opcióra.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Mi történik a munkafolyamatot használó személyzeti műveletekkel a végleges jóváhagyás után?
Ha nincsenek hibák, a személyzeti művelet írásvédetté válik. (Az előzményeket a következőben lehet megtekinteni: **A dolgozói műveletek** listaoldala, de nem lehet módosítani a személyzeti műveletet.) Ha egy személyzeti művelet állapota Befejeződött **, a** beosztás vagy a dolgozó rekordja már frissítve lett. A végrehajtott módosítások megtekintéséhez nyissa meg a **Beosztások** vagy a **Dolgozók** listaoldalt.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Miért jelenik meg a következő hiba, ha nem nullát adok meg a Fizetési díjalap mezőben? "Az érték kívül esik az érvényes tartományon: 0,00 és 0,00 között kell lennie"
Ez az üzenet azért jelenik meg, **·** **mert** a Feladat lap Szint mezője üres a kiválasztott beosztáshoz társított feladathoz.

A hiba elhárításához kövesse az alábbi lépéseket:

> 1. A Dolgozó beosztás-hozzárendelések **lapján kattintson a Pozíció mezőre** **.**  
> 2. A Feladat **lap megnyitásához** kattintson a Feladat mező **értékre**.
> 3. A műveletpanelen kattintson a Szerkesztés **gombra**.
> 4. Kattintson a Kompenzáció **fülre**.
> 5. A Szint **mezőben** válasszon ki egy szintet.
> 6. Zárja be **a Feladat** lapot.
> 7. Zárja be **a Pozíció lapot**.
> 8. Visszatérés a Dolgozó **lap** **Kompenzáció lapjára**, válassza a Fix kompenzáció **lehetőséget**.  Válassza az **Új** lehetőséget, és adja meg az alkalmazott pozícióját a Beosztás **mezőben**.  Adjon meg egy értéket **a Terv** mezőben, majd adja meg az alkalmazott kompenzációját a Fizetés **mezőben**.

## <a name="why-cant-i-change-the-effective-date-on-the-header-of-the-worker-action-page"></a>Miért nem lehet módosítani az hatályos dátumot a Dolgozó műveletlap fejlécében?
Az érvénybe lépési dátum nem módosítható, mert a mezőbe a rendszer a művelettípusra vonatkozóan leginkább logikus dátumot írja be.

Példa:

- A **Felmondás egy dolgozónak** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Munkaviszony megszűnésének dátuma** mezőben adott meg.
- A **Dolgozó felvétele** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Foglalkoztatás kezdő dátuma** mezőben adott meg.
- A **Dolgozó áthelyezése** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Megbízás kezdési dátuma** mezőben adott meg a dolgozó vonatkozásában.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
