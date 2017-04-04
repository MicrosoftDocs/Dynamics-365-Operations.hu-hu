---
title: "Ajánlások vezérlő hozzáadása a POS eszközök tranzakció lap"
description: "Ez a témakör ismerteti a ajánlások vezérlő hozzáadása a tranzakció képernyőn alapuló értékesítés (POS) eszköz használata a képernyő-elrendezés tervezője Microsoft Dynamics 365 műveletek."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Ajánlások vezérlő hozzáadása a POS eszközök tranzakció lap

Ez a témakör ismerteti a ajánlások vezérlő hozzáadása a tranzakció képernyőn alapuló értékesítés (POS) eszköz használata a képernyő-elrendezés tervezője Microsoft Dynamics 365 műveletek.

Termék ajánlások megjelenítheti a POS eszköz a Microsoft Dynamics 365 műveletek használata esetén. *Ajánlások* a cikkek, a vevő lehet, hogy érdekli a Vásárlási előzmények, azok kívánságát lista elemeinek és más felhasználók online vásárolt cikkek alapján, és a tégla és habarcs üzlet. Termék ajánlások megjelenítéséhez szükséges vezérlő hozzáadása a tranzakciók képernyőn a képernyő-elrendezés tervezője.

## <a name="open-layout-designer"></a>Képernyőelrendezés-tervező megnyitása
1.  Ugrás a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS**&gt;**képernyő elrendezése**.
2.  A gyors szűrő segítségével keresse meg a képernyőn, és a vezérlőelemet hozzá szeretnénk. Például a szűrésre a **képernyő-elrendezés azonosítója** "F2CP16:9M" érték használata mező.
3.  Keresse meg és jelölje ki a kívánt rekordot a listán. Például válassza a "név: F2CP16:9M képernyő-elrendezés azonosítója: F2CP16:9M".
4.  Kattintson a **Képernyőelrendezés-tervező**.
5.  Kövesse az utasításokat a képernyőelrendezés-tervező elindítására. Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel kerültek a képernyőelrendezés-tervező elindult a **képernyő elrendezése** oldalon.
6.  A bejelentkezést, alább hasonló oldal jelenik meg. Az elrendezés a testreszabásokat végzett a tároló függően eltérő lesz.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) válasszon egy megjelenítési beállítást
-----------------------

Konfigurációk két lehetőség áll rendelkezésre. Válasszuk ki a legjobban a tárban, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez. A következő két lehetőség van:
-   Ajánlások mindig láthatók.
-   A **ajánlások** lap jelenik meg a képernyő jobb oldalán lévő rácsban.

#### <a name="to-make-recommendations-always-visible"></a>Ajánlásokat mindig látható

1.  A tranzakció sorok részleteknél magasságának csökkentése, úgy, hogy a magassága megegyezik a vevő panel bal oldalán. [](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  A bal oldali menüből húzással a ajánlásokról vezérlő tranzakció sor részletei terület és a központ a tranzakciók képernyő alján a gombrács. Méretezzük a vezérlőelemet, hogy elférjen. [](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Kattintson a **X** mentéséhez és bezárásához a képernyőelrendezés-tervező.
4.  Műveletek 365 Dynamics, Ugrás **kereskedelmi és kereskedelmi**&gt;**kiskereskedelmi IT**&gt;**terjesztési ütemezések**.
5.  A listában jelölje ki a **1090 regisztrálja az**.
6.  Kattintson a **futtatása most**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>A képernyő jobb oldalán a gombrács a ajánlásokról lap hozzáadása

1.  Kattintson a jobb gombbal az üres terület alatt található az oldal jobb oldalán a gombrács utolsó lapján.
2.  Kattintson a **testre**. [![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Kattintson a **új lap**.
4.  A most felvett új lapon található. Szükség lehet a Görgetés lefelé.
5.  A a **tartalma** legördülő menü, select **ajánlott termékek**. [![PIC-6](./media/pic-6.png)](./media/pic-6.png)
6.  A a **címke** mezőjébe írjon be egy nevet a ajánlásokról fülre. Írja be például a "Ajánlott termékek".
7.  A a **kép** mezőben, válassza ki a kép jelenik meg a lapon.
8.  Click **OK**. Az új lap a gombrács megjelenik.
9.  Kattintson a **X** mentéséhez és bezárásához a képernyőelrendezés-tervező.
10. Műveletek 365 Dynamics, Ugrás **kereskedelmi és kereskedelmi**&gt;**kiskereskedelmi IT**&gt;**terjesztési ütemezések**.
11. A listában jelölje ki a **1090 regisztrálja az**.
12. Kattintson a **futtatása most**.


<a name="see-also"></a>Lásd még
--------

[Személyre szabott termék-ajánlások áttekintése](personalized-product-recommendations.md)


