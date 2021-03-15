---
title: Személyzeti műveletekkel kapcsolatos GYIK
description: Ez a cikk azokra a kérdésekre ad válaszokat, amelyek akkor merülhetnek fel, ha szervezete személyzeti műveleteket használ. A személyzeti műveletek olyan kiegészítő lépések, amelyeket bizonyos személyzeti feladatok végrehajtásakor kell elvégeznie.
author: andreabichsel
manager: tfehr
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 43c727fa8e0508adf66109efd84a66cb31df7ea3
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115414"
---
# <a name="personnel-actions-faq"></a>Személyzeti műveletekkel kapcsolatos GYIK

Ez a cikk azokra a kérdésekre ad válaszokat, amelyek akkor merülhetnek fel, ha szervezete személyzeti műveleteket használ. A személyzeti műveletek olyan kiegészítő lépések, amelyeket bizonyos személyzeti feladatok végrehajtásakor kell elvégeznie. Számos feladat megköveteli személyzeti műveletek elvégzését, pédául az új beosztások létrehozása, a meglévő beosztások értékeinek módosítása, új dolgozók felvétele, dolgozók átvétele, dolgozók kompenzációjának módosítása, beosztás-hozzárendelések módosítása, illetve a felmondások.

**Megjegyzés:** a személyzeti műveletek csak akkor érhetők el, ha a **Dolgozói műveletek engedélyezése** és a **Beosztásműveletek engedélyezése** mezők **Igen** értékre vannak állítva a **Személyzeti műveletek** lapon az **Emberi erőforrások megosztott paraméterei** oldalon. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Honnan tudhatom, hogy a szervezetemnél szükség van személyzeti műveletekre?
Ha a szervezet előír bizonyos személyzet műveleteket, akkor a rendszer felszólítja ezek elvégzésére olyankor, amikor új beosztásokat hoz létre, meglevő beosztásokat módosít, új dolgozókat vesz fel, dolgozókat visz át, dolgozók kompenzációját módosítja, beosztás-hozzárendeléseket módosít, dolgozóknak felmond, vagy amikor távollétet rögzít. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Mi a különbség egy beosztásművelet és egy dolgozói művelet között?
A személyzeti műveleteket két típusra osztjuk:

- Beosztásművelet – A beosztásműveletet új vagy létező beosztásokon lehet elvégezni. Beosztásműveletre lehet például szükség, ha módosítja egy létező beosztás értékét, vagy új szezonális beosztást hoz létre. A beosztásműveletek használatával kapcsolatos részletes tudnivalókat lásd: Legfontosabb feladatok: Meglévő dolgozói beosztások vagy Legfontosabb feladatok: Új dolgozói beosztások.

- Dolgozói művelet – A dolgozói műveletet létező vagy új alkalmazottakon lehet elvégezni. Dolgozói műveletre van szükség például akkor, ha egy új alkalmazottat vesz fel, vagy egy meglévő alkalmazottat előléptet. A dolgozói műveletek használatával kapcsolatos részletes tudnivalókat lásd: Személyzeti műveletek hozzárendelése dolgozókhoz.

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>Mit jelentenek a személyzeti műveletek állapotai?
A személyzeti műveletek a következő állapotokat vehetik fel:

- **Tervezet** – Ha munkafolyamatokat használ, akkor művelet még nem lett elküldve. Ha nem használ munkafolyamatokat, akkor művelet nem lett befejezve.
- **Ellenőrzés alatt** – A személyzeti műveletet beküldték a munkafolyamatba, de a munkafolyamat nem fejeződött be.
- **Jóváhagyva várakozik** – A munkafolyamat befejeződött, de a módosítások még folyamatban vannak. Megszakítva – A munkafolyamatot megszakították, vagy a személyzeti műveletet visszavonták. Elutasítva – A műveletkérelmet a jóváhagyó elutasította.
- **Művelet feldolgozása** – A műveletkérelmet jóváhagyták, a módosítások feldolgozás alatt állnak.
- **Munkafolyamat befejezve** – A munkafolyamat befejeződött és a módosításokat feldolgozták. Sikertelen – A munkafolyamat nem sikerült, mert az információ elavult. Kattintson az Újraaktiválás elemre a legfrissebb információkat megjelenítéséhez, majd folytassa.
- **Befejezve** – A beosztást sikeresen létrehozták vagy módosították, vagy az alkalmazottat sikeresen felvették, átvették vagy elbocsátották, vagy kompenzációját sikeresen megváltoztatták. Hiba – Hiba történt, amelyet nem elavult információ okozott. Nyissa meg a Személyzeti műveletek üzenetnaplót, hogy megtudhassa a hiba okát.
- **Megtagadva** – A műveletkérelmet elutasította a jóváhagyó.

## <a name="can-i-delete-a-personnel-action"></a>Lehetséges személyzeti műveleteket törölni?
Igen, törölheti az olyan személyzeti műveleteket, amelyek állapota **Tervezet**, **Hiba**, **Sikertelen** vagy **Megszakítva**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Hogyan tudom a leggyorsabban ellenőrizni egy személyzeti művelet kérelmének állapotát?
Nyissa meg bármelyik személyzeti művelet listaoldalát, majd válasszon egy műveletet.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>Mit tegyek, ha egy személyzeti műveletkérelem sikertelen?
Ha egy személyzeti műveleti kérelem sikertelen, az alábbi lépésekkel tudja megoldani a hibát és újraküldeni a kérelmet:

> 1. A **Műveleti ablaktáblában** kattintson a **Hibaüzenet** gombra a hibaüzenet szövegének megtekintéséhez.
> 
> 2. A **Műveleti ablaktáblában** az **Újraaktiválása** gombra kattintva betöltheti a legutóbbi információkat, és a személyzeti műveletet visszaállíthatja **Tervezet** állapotba.
> 
> 3. Oldja meg a hibát, majd kattintson a **Befejezés** vagy a **Küldés** opcióra.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>Mi történik a munkafolyamatot használó személyzeti műveletekkel a végleges jóváhagyás után?
Ha nincsenek hibák, a személyzeti művelet írásvédetté válik. (Megtekintheti a **Minden dolgozói művelet** listaoldal előzményeit, de nem módosíthatja a személyzeti műveletet.) Ha a személyzeti művelet állapota **Befejezve**, a beosztás vagy a dolgozói rekord már frissítve van. A végrehajtott módosítások megtekintéséhez nyissa meg a **Beosztások** vagy a **Dolgozók** listaoldalt.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Miért jelenik meg a következő hiba, ha nem nullát adok meg a Fizetési díjalap mezőben? "Az érték kívül esik az érvényes tartományon: 0,00 és 0,00 között kell lennie"
Ilyen üzenetet akkor kap, ha a kiválasztott beosztáshoz tartozó feladatnál a Szint mező üres a Munkakör képernyőn.

A hiba elhárításához kövesse az alábbi lépéseket:

> 1. A dolgozó beosztáshoz megbízások űrlapjának kattintson Beosztás mező.  
> 2. Kattintson a Munka mező tartalmára, amely megnyitja a Feladat lapot.
> 3. Kattintson a Műveleti ablak Szerkesztés elemére.
> 4. Kattintson a Kompenzáció fülre.
> 5. Válasszon egy szintet a Szint mezőben.
> 6. Zárja be a Feladat lapot.
> 7. Zárja be a Beosztás lapot.
> 8. Lépjen vissza a Kompenzáció lapra vissza a Dolgozó lapon, és válassza a Fix kompenzáció lehetőséget.  Válassza az Új lehetőséget, és adja meg a Beosztás mezőben az alkalmazott pozícióját.  A Terv mezőben adjon meg egy értéket, és a Fizetési díjalap mezőben adja meg az alkalmazotti kompenzációt.

## <a name="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form"></a>Miért nem tudom módosítani az érvénybe lépési dátumot dolgozói művelet képernyő fejlécében?
Az érvénybe lépési dátum nem módosítható, mert a mezőbe a rendszer a művelettípusra vonatkozóan leginkább logikus dátumot írja be.

Példa:

- A **Felmondás egy dolgozónak** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Munkaviszony megszűnésének dátuma** mezőben adott meg.
- A **Dolgozó felvétele** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Foglalkoztatás kezdő dátuma** mezőben adott meg.
- A **Dolgozó áthelyezése** művelet fejlécének érvénybe lépési dátuma az a dátum lesz, amelyet a **Megbízás kezdési dátuma** mezőben adott meg a dolgozó vonatkozásában.



[!INCLUDE[footer-include](../includes/footer-banner.md)]