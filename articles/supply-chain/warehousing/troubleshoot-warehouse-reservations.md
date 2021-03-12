---
title: Foglalások a raktárkezelési modulban – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári foglalási munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a1ea23059d56ebf387a95a1378e2a3cd47556d5f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993863"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Foglalások a raktárkezelési modulban – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári foglalási munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>A következő hibaüzenet jelenik meg: „Foglalások nem távolíthatók el, mert van olyan munkafolyamat, amely a foglalásokon alapul”.

### <a name="issue-description"></a>Probléma leírása

Egy értékesítési sorban nem lehet lefoglalni a készletet, mert nyitott munka van a sornál.

### <a name="issue-resolution"></a>Probléma megoldása

Vizsgálja meg, hogy nyitott csomagolási csoportmunka létrezik-e, hogy a cikkeket egy csomagoló állomástól egy másik helyre (például *Baydoor*) vigye. A **Munkalétrehozási előzmények naplója** és **Munkarészletek** lapján található rekordok áttekintésével határozza meg, hogy mi a készlet tényleges foglalása, majd töltse ki vagy törölje a foglalást kiadó munkát.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>A következő hibaüzenet jelenik meg: „Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2...”

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz. Íme a hibaüzenet teljes szövege:

> „Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2 a következő méretekkel: Méret=%3, Szí=%4, Kiegészítések=%5, Telephely=%6, Raktár=%7, Hely=%8, Készletállapot=Elérhető, Azonosítótábla=%9, Kötegszám=%10 referenciaazonosítónak %11 a tételazonosítóhoz %12.

### <a name="issue-resolution"></a>Probléma megoldása

Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget. Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>A következő hibaüzenet jelenik meg: „Tényleges aktuális készlet... nem foglalható le, mert csak 0,00 érhető el a készletben."

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz. Íme a hibaüzenet teljes szövege:

> Tényleges aktuális Telephely=%1, Raktár=%2, Készletállapot=Elérhető, Kötegszám=%3, Tulajdonos=%4: %5 nem foglalható le, mert csak 0,00 érhető el a készletben.

### <a name="issue-resolution"></a>Probléma megoldása

Ezt a problémát valószínűleg a nyitott munka okozza. Vagy hajtsa végre a munkát vagy fogadja a munka létrehozása nélkül. Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget. Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>A következő hibaüzenet jelenik meg: „A hullámhoz hozzárendelni kívánt soroknak meg kell adni a hely fölötti dimenzióit. Ezeknek a dimenzióknak a hozzárendeléséhez foglalja le és hozza létre újból a rakománysort.”

### <a name="issue-description"></a>Probléma leírása

Ha olyan cikket használ, amelyben a „köteg felett” foglalási hierarchia szerepel (a **Hely** dimenzió *fölött* megadott **Kötegszám** dimenzióval), akkor a részleges mennyiséghez tartozó **Rakománytervezési** munkaterület lap **Kiadás a raktárba** parancsa nem használható. Ez a hibaüzenet jelenik meg, és a rendszer nem hoz létre munkát a részleges mennyiséghez.

Azonban ha olyan cikket használ, amelyben a „köteg alatt” foglalási hierarchia szerepel (a **Hely** dimenzió *alatt* megadott **Kötegszám** dimenzióval), akkor a részleges mennyiséghez tartozó **Rakománytervezési munkaterület** lapról kiadhatja a rakományt.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. Ha a foglalási hierarchiában a **Hely** dimenzió felett helyez fel egy dimenziót, akkor azt a raktárba történő kiadás előtt meg kell határozni. A Microsoft kiértékelte ezt a hibát, és azt állapította meg, hogy a rakománytervezési munkaterületről a raktárba történő kiadások jellemzően korlátozást jelentenek. A részleges mennyiségek nem adhatók ki, ha a **Hely** fölötti egy vagy több dimenzió nincs meghatározva.

További információ: [Rugalmas raktárszintű dimenzió foglalási irányelv](flexible-warehouse-level-dimension-reservation.md).
