---
title: Raktár konfigurálása – Hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben konfigurálja a Microsoft Dynamics 365 Supply Chain Management szolgáltatást.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646107"
---
# <a name="troubleshoot-warehouse-configuration"></a>Raktár konfigurálása – Hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben konfigurálja a Microsoft Dynamics 365 Supply Chain Management szolgáltatást.

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a>A következő hibaüzenet jelenik meg: „Az azonosítótábla vagy hely nem érvényes”.

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet jelenik meg, amikor beolvas egy azonosítótábla-azonosítót vagy egy helyet.

### <a name="issue-resolution"></a>Probléma megoldása

Győződjön meg róla, hogy az azonosítótábla azonosítója nincs máshoz lefoglalva. Ez a probléma akkor szokott előfordulni, ha a raktári alkalmazásban a felhasználó által beolvasott érték egy érvényes hely és egy érvényes azonosítótábla-azonosító. Ez a probléma azonban a 10.0.11 verzióban ki lett javítva.

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a>A következő hibaüzenet jelenik meg: „Azonosítótáblát meg kell határozni ehhez a helyhez”.

### <a name="issue-description"></a>Probléma leírása

Ez a hibaüzenet akkor jelenik meg, ha egy olyan raktárat hoz létre, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt.

### <a name="issue-resolution"></a>Probléma megoldása

Az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában. A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban. Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a>A következő hibaüzenet jelenik meg: „Nem hozható létre munkasablonsor a Készletállapot módosításához, mert a munka típusa érvénytelen. Válasszon másik munkatípust.”

### <a name="issue-description"></a>Probléma leírása

Egy munkasablon esetében nem lehet kiválasztani a *Készletállapot módosítás* lehetőséget a **Munkasablon részletei** szakasz **Munka típusa** oszlopban.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. A *Készletállapot módosítás* munkatípust csak rendszerfolyamatok használják. Ezt nem lehet konfigurálni. Mivel a munkatípusok listája számbavételként van rögzítve, a program nem tudja kiszűrni a **Munka típusa** legördülő menüből a felesleges bejegyzéseket.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>A következő hibaüzenet jelenik meg: „A mennyiség nem érvényes az 1% egységre”.

### <a name="issue-description"></a>Probléma leírása

A mennyiség nem érvényes az *ea* egységre, amikor olyan kitárolási munka van, amelynek egy helyén több azonosítótábla szerepel.

### <a name="issue-resolution"></a>Probléma megoldása

Ellenőrizze, hogy a kiadott termék vagy termék változatának **Egységszekvenciacsoport-azonosítója** és **Egységek átváltása** mezők helyesen vannak beállítva.

Ne felejtse el, hogy a 10.0.15 (lásd: [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)) verzióban ki lett javítva a hibaüzenet. Az új hibaüzenet: „A mennyiség érvénytelen. Elvárt %1 %2.”

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Az értékesítési rendelés kitárolására szolgáló hely irányelveiben a több termékváltozat beállítás nem értékeli a több helyen utasítási műveleteket.

### <a name="issue-description"></a>Probléma leírása

Az *Értékesítési rendelések* munkarendelési típusának és a *Kitárolás* munkatípusnak nem kell több helyre vonatkozó irányelv-műveleteket kiértékelnie, ha a **Több termékváltozat** beállítás van kiválasztva. Csak az első hely irányelv-művelet van kiértékelve.

### <a name="issue-resolution"></a>Probléma megoldása

Egy új funkció, a *Több termékváltozatos helyirányelvek összes műveletének kiértékelése* hozzá lett adva a 10.0.15 verzióhoz (lásd: [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Ez a funkció kiértékeli a több termékváltozatos helyirányelvek összes műveletét. Ha szüksége van erre a funkcióra, használja a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőséget a funkció bekapcsolásához.

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a>A raktári alkalmazás nem használható részleges kitárolásra.

### <a name="issue-description"></a>Probléma leírása

Az értékesítési és átmozgatási rendelések esetében nem lehet kihagyni a cikkeket, és a részleges kitárolást.

### <a name="issue-resolution"></a>Probléma megoldása

A **Mobileszköz menüpontjai** lapon az értékesítési rendelések és átmozgatási rendelések feldolgozására beállított menüelemekhez állítsa be az **Általános** gyorslap **Munka felosztásának engedélyezése** beállítást *Igen* értékre.

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a>Hogyan lehet létrehozni egy készletállapot módosítást a részleges mennyiségi munkához?

### <a name="issue-description"></a>Probléma leírása

Egy köteg részleges mennyiségéről szeretne létrehozni egy készletállapot módosítást.

### <a name="issue-resolution"></a>Probléma megoldása

Ha engedélyezni szeretné, hogy a dolgozók elvégezzék ezt a módosítást, akkor létrehozhat egy menüelemet a raktári alkalmazás számára. A **Mobileszköz menüpontok** oldalon hozzon létre (vagy szerkesszen) egy menüpontot a következő beállításokkal:

- **Mód:** *Munka*
- **Meglévő munka használata:** *Nem*
- **Munkalétrehozási folyamat:** *Áthelyezés*
- **Készletállapot megjelenítése:** *Igen*

A lapon szükség szerint megadhat más mezőket is.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]