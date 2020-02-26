---
title: Jutalékok követése a pénztárban (POS) értékesítési csoportok révén
description: Általános kereskedelmi gyakorlat az értékesítés nyomon követése az ügyféllel foglalkozó dolgozóra lebontva – segítségnyújtást, értéknövelt értékesítést, keresztértékesítést és a tranzakció feldolgozását nyújtva.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: afbf69c072ae205e973203d97a5fbca7504ae04f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022831"
---
# <a name="track-commissions-in-the-point-of-sale-pos-by-using-sales-groups"></a>Jutalékok követése a pénztárban (POS) értékesítési csoportok révén

[!include [banner](includes/banner.md)]

Általános kiskereskedelmi gyakorlat az értékesítés nyomon követése az ügyféllel foglalkozó dolgozóra lebontva – segítségnyújtást, értéknövelt értékesítést, keresztértékesítést és a tranzakció feldolgozását nyújtva.

Az értékesítő szerint értékesítések nyomon követése az ügyféllel foglalkozó dolgozók értékesítési képességeit mutatja, miközben a pénztáros szerinti értékesítés a sebességet és a hatékonyságot méri. Az értékesítő szerint nyomon követett eladásokat gyakran használják a jutalékok vagy más ösztönzők kiszámításához.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Dolgozó konfigurálása értékesítőként a pénztárban

Amikor egy dolgozót hozzáadunk egy értékesítési csoporthoz, jogosulttá válik jutalékra, és a rendszerben értékesítőként azonosítható. A dolgozó, aki nem szerepel az értékesítési csoportban, nem jogosult jutalékra, és nem jelenik meg értékesítési képviselőként a pénztáralkalmazásban. A pénztárban az értékesítési képviselők listája minden olyan értékesítési csoportból származik, amelyik tartalmaz legalább egy, az üzlethez társított dolgozót. A lista a pénztárban az értékesítési csoport azonosítója és a név (Azonosító: Név) kombinációjaként jelenik meg. Alapértelmezett értékesítési csoport rendelhető a dolgozókhoz, az olyan forgatókönyvek támogatására, ahol a kiskereskedő úgy dönt, hogy automatikusan beállítja az értékesítőt a pénztársorokban. A felhasználók minden értékesítési csoportból választhatnak, amelynek a dolgozó a tagja.

## <a name="functionality-profile-settings"></a>Funkcióprofil-beállítások

Számos funkcióprofilbeállítás tartozik az üzletekhez, amelyek meghatározzák a pénztárak eljárásait és a folyamatait, amelyek magukban foglalja az értékesítési képviselőket.

<table>
<thead>
<tr>
<th>Profil</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Alapértelmezés szerint a pénztáros, ha elérhető</td>
<td>Ha ez a beállítás engedélyezve van, a POS automatikusan feltölti a tranzakciósorokat a jelenlegi pénztáros alapértelmezett értékesítési csoportjával. Ha a pénztároshoz nincs megadva alapértelmezett értékesítési csoport, az érték nem állítható be. A felhasználó manuálisan is beállíthatja az értékesítési csoportot a pénztár gombrács gombjának segítségével.</td>
</tr>
<tr>
<td>Üzletkötő megadásának kérése</td>
<td>Ennek a beállításnak három lehetséges értéke van:
<ul>
<li><strong>Nem</strong> – Ha ez az opció van kiválasztva, a felhasználó nem kap értesítést ahhoz, hogy kiválasszon egy értékesítési csoportot. Az érték a pénztáros alapértelmezett értékesítési csoportjának használatával továbbra is beállítható, vagy manuálisan is beállítható a gombrács pénztárgomb segítségével.</li>
<li><strong>A tranzakció kezdetén</strong> – Ha ezt a beállítást választja, és vagy nincs engedélyezve az <strong>Alapértelmezés szerint a pénztáros</strong> beállítás, vagy a jelenlegi pénztáros nem rendelkezik alapértelmezett értékesítési csoporttal, a felhasználót a rendszer minden tranzakció elején arra kéri, jelölje ki az értékesítési csoportot. Ha ennél a kérdésnél kiválaszt egy értékesítési csoportot, alapértelmezés szerint minden további sor a kijelölt értékesítési csoporthoz fog tartozni. A felhasználó manuálisan is beállíthatja az értékesítési csoportot a pénztár gombrács gombjának segítségével.</li>
<li><strong>Mindegyik sornál</strong> – Ha ezt a beállítást választja, és vagy nincs engedélyezve az <strong>Alapértelmezés szerint a pénztáros</strong> beállítás, vagy a jelenlegi pénztáros nem rendelkezik alapértelmezett értékesítési csoporttal, a felhasználót a rendszer minden sor hozzáadása után arra kéri, jelölje ki az értékesítési csoportot. A felhasználó manuálisan is beállíthatja az értékesítési csoportot a pénztár gombrács gombjának segítségével.</li>
</ul>
</td>
</tr>
<tr>
<td>Szükséges</td>
<td>Ez a beállítás csak akkor alkalmazható, ha pénztár úgy van beállítva, hogy a program kérje az értékesítési képviselőt. Ha engedélyezve van, a felhasználónak a folytatáshoz választania kell egy értékesítési csoport. Ellenkező esetben a felhasználó megkapja a kérést, de kiválasztás nélkül is folytathatja. A sor hozzáadása után a megfelelő engedélyekkel rendelkező felhasználó továbbra is eltávolíthatja az értékesítési csoportot a sorból. A rendszer ebben a helyzetben nem kényszeríti ki az „Üzletkötő megkövetelése” lehetőséget.</td>
</tr>
</tbody>
</table>

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Az értékesítési képviselő információinak megjelenítése a pénztár tranzakciók képernyőjén

A pénztár tranzakció képernyő elrendezése és tartalma a képernyőelrendezés-tervezővel és hozzárendelt képernyő-elrendezések segítségével konfigurálható az üzletek, nyilvántartások vagy dolgozók számára. Az **Üzletkötő** mező hozzáadható a Nyugta panel Sorok lapjához.  A tranzakció képernyőn ekkor megjelenik az egyes sorokhoz a megadott értékesítési csoport azonosítója.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Üzletkötői műveletek hozzáadása a pénztár gombrácsaihoz

A pénztár lehetővé teszi a felhasználók számára a képernyő-elrendezésekben található, a pénztárműveletekhez való hozzáférést biztosító gombrácsok konfigurálását. A következő, az értékesítési képviselőkre vonatkozó pénztárműveletek rendelhetők a gombrács gombjaihoz.

| Művelet                                 | Leírás |
|-------------------------------------------|-------------|
| Üzletkötő beállítása a sorban          | Ez a pénztárművelet a jogosult értékesítési csoportok listáját (Azonosító: Név) jeleníti meg az üzlethez. Egy értékesítési csoport kiválasztása a listából az aktuális tranzakciósorhoz állítja be az értéket. |
| Üzletkötő törlése a sorban        | Ez a pénztárművelet eltávolítja az aktuális tranzakciósorból az aktuális értékesítésicsoport-értéket. |
| Üzletkötő beállítása a tranzakcióban   | Ez a pénztárművelet a jogosult értékesítési csoportok listáját (Azonosító: Név) jeleníti meg az üzlethez. Egy értékesítési csoport kiválasztása a listából az aktuális tranzakcióhoz állítja be az alapértelmezett értéket. A hozzárendelt értékesítési csoport nélküli összes meglévő sornak a beállítása megtörténik, ahogy a később hozzáadott soroké is. |
| Üzletkötő törlése a tranzakcióban | Ez a pénztárművelet eltávolítja az aktuális tranzakciósorból az alapértelmezett értékesítésicsoport-értéket. Nem érinti a tranzakcióban már meglévő sorokat. |

## <a name="calculating-commissions"></a>Jutalék kiszámítása

A jutalék kiszámítása a meghatározott értékesítési csoporthoz tartozó munkavállalók számára a kimutatásfeladás vagy az értékesítési rendelés feladása során történik. A jutalékösszeg meghatározásának alapja a dolgozó jutalékmegosztása, amelyet az értékesítési csoport határoz meg, valamint a kapcsolódó jutalékszámítási beállítások, amelyek a tranzakcióban szereplőre vevőre és/vagy termékekre vonatkoznak.
