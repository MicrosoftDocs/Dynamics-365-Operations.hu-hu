---
title: "A pénztárjutalékok nyomon követése értékesítési csoportok használatával"
description: "Általános kereskedelmi gyakorlat az értékesítés nyomon követése az ügyféllel foglalkozó dolgozóra lebontva – segítségnyújtást, értéknövelt értékesítést, keresztértékesítést és a tranzakció feldolgozását nyújtva."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dfefdede8f3bc884b230109d6c915127a1361ecd
ms.lasthandoff: 03/31/2017


---

# <a name="track-commissions-in-pos-using-sales-groups"></a>A pénztárjutalékok nyomon követése értékesítési csoportok használatával

[!include[banner](includes/banner.md)]


Általános kereskedelmi gyakorlat az értékesítés nyomon követése az ügyféllel foglalkozó dolgozóra lebontva – segítségnyújtást, értéknövelt értékesítést, keresztértékesítést és a tranzakció feldolgozását nyújtva.

Az értékesítő szerint értékesítések nyomon követése az ügyféllel foglalkozó dolgozók értékesítési képességeit mutatja, miközben a pénztáros szerinti értékesítés a sebességet és a hatékonyságot méri. Az értékesítő szerint nyomon követett eladásokat gyakran használják a jutalékok vagy más ösztönzők kiszámításához.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Dolgozó konfigurálása értékesítőként a pénztárban
Amikor egy dolgozót hozzáadunk egy értékesítési csoporthoz, jogosulttá válik jutalékra, és a rendszerben értékesítőként azonosítható. A dolgozó, aki nem szerepel az értékesítési csoportban, nem jogosult jutalékra, és nem jelenik meg értékesítési képviselőként a pénztáralkalmazásban. A pénztárban az értékesítési képviselők listája minden olyan értékesítési csoportból származik, amelyik tartalmaz legalább egy, az üzlethez társított dolgozót. A lista a pénztárban az értékesítési csoport azonosítója és a név (Azonosító: Név) kombinációjaként jelenik meg. Alapértelmezett értékesítési csoport rendelhető a dolgozókhoz, az olyan forgatókönyvek támogatására, ahol a kiskereskedő úgy dönt, hogy automatikusan beállítja az értékesítőt a pénztársorokban. A felhasználók minden értékesítési csoportból választhatnak, amelynek a dolgozó a tagja.

## <a name="functionality-profile-settings"></a>Funkcióprofil-beállítások
Számos funkcióprofilbeállítás tartozik az üzletekhez, amelyek meghatározzák a pénztárak eljárásait és a folyamatait, amelyek magukban foglalja az értékesítési képviselőket.

|                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Profil**                           | **Leírás**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Alapértelmezés szerint a pénztáros, ha elérhető** | Ha ez a beállítás engedélyezve van, a POS automatikusan feltölti a tranzakciósorokat a jelenlegi pénztáros alapértelmezett értékesítési csoportjával. Ha a pénztároshoz nincs megadva alapértelmezett értékesítési csoport, az érték nem állítható be. A felhasználó manuálisan is beállíthatja az értékesítési csoportot a pénztár gombrács gombjának segítségével.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Üzletkötő megadásának kérése**   | Ennek a lehetőségnek három lehetséges értéke van: ** Nem **- Ha ez a beállítás be van jelölve, a felhasználótól a rendszer nem kéri, hogy válasszon értékesítési csoport. Az érték a pénztáros alapértelmezett értékesítési csoportjának használatával továbbra is beállítható, vagy manuálisan is beállítható a gombrács pénztárgomb segítségével. **A tranzakció kezdetén** - Ha ezt a beállítást választja, és vagy nincs engedélyezve az **Alapértelmezés szerint a pénztáros** beállítás, vagy a jelenlegi pénztáros nem rendelkezik alapértelmezett értékesítési csoporttal, a felhasználót a rendszer minden tranzakció elején arra kéri, jelölje ki az értékesítési csoportot. Ha ennél a kérdésnél kiválaszt egy értékesítési csoportot, alapértelmezés szerint minden további sor a kijelölt értékesítési csoporthoz fog tartozni. A felhasználó manuálisan is beállíthatja az értékesítési csoportot a pénztár gombrács gombjának segítségével. **Mindegyik sornál** - Ha ezt a beállítást választja, és vagy nincs engedélyezve az **Alapértelmezés szerint a pénztáros** beállítás, vagy a jelenlegi pénztáros nem rendelkezik alapértelmezett értékesítési csoporttal, a felhasználót a rendszer minden sor hozzáadása után arra kéri, jelölje ki az értékesítési csoportot. A felhasználó manuálisan is beállíthatja az értékesítési csoportot a pénztár gombrács gombjának segítségével. |
| **Szükséges**                           | Ez a beállítás csak akkor alkalmazható, ha pénztár úgy van beállítva, hogy a program kérje az értékesítési képviselőt. Ha engedélyezve van, a felhasználónak a folytatáshoz választania kell egy értékesítési csoport. Ellenkező esetben a felhasználó megkapja a kérést, de kiválasztás nélkül is folytathatja. A sor hozzáadása után a megfelelő engedélyekkel rendelkező felhasználó továbbra is eltávolíthatja az értékesítési csoportot a sorból. A rendszer ebben a helyzetben nem kényszeríti ki az „Üzletkötő megkövetelése” lehetőséget.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Az értékesítési képviselő információinak megjelenítése a pénztár tranzakciók képernyőjén
A pénztár tranzakció képernyő elrendezése és tartalma a képernyőelrendezés-tervezővel és hozzárendelt képernyő-elrendezések segítségével konfigurálható az üzletek, nyilvántartások vagy dolgozók számára. Az **Üzletkötő** mező hozzáadható a Nyugta panel Sorok lapjához.  A tranzakció képernyőn ekkor megjelenik az egyes sorokhoz a megadott értékesítési csoport azonosítója.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Üzletkötői műveletek hozzáadása a pénztár gombrácsaihoz
A pénztár lehetővé teszi a felhasználók számára a képernyő-elrendezésekben található, a pénztárműveletekhez való hozzáférést biztosító gombrácsok konfigurálását. A következő, az értékesítési képviselőkre vonatkozó pénztárműveletek rendelhetők a gombrács gombjaihoz.

|                                           |                                                                                                                                                                                                                                                                                              |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                             | **Leírás**                                                                                                                                                                                                                                                                              |
| Üzletkötő beállítása a sorban          | Ez a pénztárművelet a jogosult értékesítési csoportok listáját (Azonosító: Név) jeleníti meg az üzlethez. Egy értékesítési csoport kiválasztása a listából az aktuális tranzakciósorhoz állítja be az értéket.                                                                                                            |
| Üzletkötő törlése a sorban        | Ez a pénztárművelet eltávolítja az aktuális tranzakciósorból az aktuális értékesítésicsoport-értéket.                                                                                                                                                                                                  |
| Üzletkötő beállítása a tranzakcióban   | Ez a pénztárművelet a jogosult értékesítési csoportok listáját (Azonosító: Név) jeleníti meg az üzlethez. Egy értékesítési csoport kiválasztása a listából az aktuális tranzakcióhoz állítja be az alapértelmezett értéket. A hozzárendelt értékesítési csoport nélküli összes meglévő sornak a beállítása megtörténik, ahogy a később hozzáadott soroké is. |
| Üzletkötő törlése a tranzakcióban | Ez a pénztárművelet eltávolítja az aktuális tranzakciósorból az alapértelmezett értékesítésicsoport-értéket. Nem érinti a tranzakcióban már meglévő sorokat.                                                                                                                             |

## <a name="calculating-commissions"></a>Jutalék kiszámítása
A jutalék kiszámítása a meghatározott értékesítési csoporthoz tartozó munkavállalók számára a kimutatásfeladás vagy az értékesítési rendelés feladása során történik. A jutalékösszeg meghatározásának alapja a dolgozó jutalékmegosztása, amelyet az értékesítési csoport határoz meg, valamint a kapcsolódó jutalékszámítási beállítások, amelyek a tranzakcióban szereplőre vevőre és/vagy termékekre vonatkoznak.




