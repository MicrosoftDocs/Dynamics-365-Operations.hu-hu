---
title: Elavult termékváltozatok keresése
description: Ez az eljárás bemutatja, hogyan lehet megkeresni az elavult kiadott termékeket vagy termékváltozatokat, és hogyan lehet termékéletciklus-állapotot társítani az elavult termékekhez.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 807297a87a7f0e59023d80fbd371bffbf2b086bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807992"
---
# <a name="find-obsolete-product-variants"></a>Elavult termékváltozatok keresése 

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet megkeresni az elavult kiadott termékeket vagy termékváltozatokat, és hogyan lehet termékéletciklus-állapotot társítani az elavult termékekhez. Előfeltétel: Meg kell határozni legalább egy, tervezéshez inaktív termékéletciklus-állapotot a jelen feladat-útmutató lejátszásához.


## <a name="run-a-simulation"></a>Szimuláció futtatása
1. Ugorjon a Termékinformációk kezelése > Időszakos feladatok > Elavult termékek életciklus-állapotának módosítása lehetőségre.
2. Az Új termékéletciklus-állapot mezőben adjon meg vagy válasszon ki egy értéket.
3. A Szimuláció futtatása termékadatok frissítése nélkül mezőben válassza az Igen lehetőséget.
4. Az Ennyi napon belül létrehozott termékek kizárása mezőbe írjon be egy számot.
5. A Tranzakciókban használt termékek kizárása (napokban megadva) mezőbe írjon be egy számot.
6. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
7. Kattintson a Szűrő parancsra.
8. A listában jelölje meg a kiválasztott sort.
9. Érték beírása a Feltétel mezőbe.
10. Kattintson az OK gombra.
11. Kattintson az OK gombra.

> [!NOTE]
> Ajánlott a kötegelt szimuláció futtatása, ha jelentős számú termékekre keres. Ezenkívül győződjön meg arról, hogy a szimulációt ne a vállalat a leginkább aktív munkaidejében futtassa.  

## <a name="review-the-simulation-results"></a>A szimuláció eredményeinek áttekintése
1. Ugorjon a Termékinformációk kezelése > Lekérdezések és jelentések > Termékéletciklus-állapot karbantartási előzményei lehetőségre.
   
> [!NOTE]
> Ezen az oldalon áttekintheti a szimulációs eredményeket, és kiértékelheti, hogy hány termékhez és termékváltozathoz lesz új termékéletciklus-állapot társítva, ha a frissítést szimuláció nélkül futtatjuk.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Futtassa az Elavult termékek életciklus-állapota frissítését
1. Zárja be a lapot.
2. Ugorjon a Termékinformációk kezelése > Időszakos feladatok > Elavult termékek életciklus-állapotának módosítása lehetőségre.
3. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.

> [!NOTE]
> Vegye figyelembe, hogy az utolsó kijelölés mentése megtörtént.  

4. A Szimuláció futtatása termékadatok frissítése nélkül mezőben válassza a Nem lehetőséget.
5. Bontsa ki a Futtatás a háttérben szakaszt.

> [!NOTE]
> Attól függően, hogy hány termék és termékváltozat érintett, fontolja meg a feladat kötegben történő futtatását. Győződjön meg arról, hogy ne futtasson nagy frissítési feladatokat a vállalat leginkább aktív munkaidejében.  

6. Kattintson az OK gombra.
7. Ugorjon a Termékinformációk kezelése > Lekérdezések és jelentések > Termékéletciklus-állapot karbantartási előzményei lehetőségre.

> [!NOTE]
> Tekintse át a módosított kiadott termékeket és termékváltozatokat.  

8. Keresse meg és jelölje ki a kívánt rekordot a listán.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]