---
title: "Vevői rendelések áttekintése"
description: "Ez a témakör a kiskereskedelmi Modern POS (MPOS) vevői rendelések adatait. Vevői rendelések speciális rendelések is ismertek. A témakör a kapcsolódó paraméterek és tranzakció egy vitafórum."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>Vevői rendelések áttekintése

Ez a témakör a kiskereskedelmi Modern POS (MPOS) vevői rendelések adatait. Vevői rendelések speciális rendelések is ismertek. A témakör a kapcsolódó paraméterek és tranzakció egy vitafórum.

Az omni-csatorna kiskereskedelmi világ számos kiskereskedő a vevő beállítást adja meg, vagy speciális rendelések különböző termék- és teljesítési követelményeknek. Íme néhány tipikus forgatókönyvet:

-   A vevő egy adott napon egy adott címre kiszállítandó termékek kíván.
-   Emelje fel a tárolóból vagy a hely, amely eltér az üzlet vagy hely, ahol az ügyfél vásárolt termékek termékek egy ügyfél szeretne.
-   Egy ügyfél által kért valaki merül fel, amely a vevő által vásárolt termékek.

Kiskereskedők a minimálisra csökkentése érdekében, amelyek tőzsdei kimaradások egyébként okozhatnak, mert az árut szállítani, vagy különböző időben vagy helyen felvett elveszett értékesítési megrendelések is használható.

## <a name="set-up-customer-orders"></a>Vevői rendelések beállítása
Az alábbiakban néhány, a beállított paraméterek az **a kiskereskedelmi paraméterek** oldalra húzva definiálhatja, hogyan teljesülnek a vevői rendelések:

-   **Letét százalékban alapértelmezett** – adja meg az összeget, amelyet a vevőnek ki kell fizetnie letétként, mielőtt megrendelés lehet megerősíteni. Az alapértelmezett betét összegét számítja ki a rendelés értékének százalékaként. Jogosultságok, függően összeget használatával felülbírálhatók, hogy lehet a Kiskereskedelmi munkatárs **Letét felülbírálása**.
-   **Érvénytelenítési díj százalékos értéke** – Ha a díjat kell alkalmazni, a vevői rendelés visszavonásakor adja meg, hogy a költség összegét.
-   **Érvénytelenítési díj kódja** – Ha díjat alkalmazzák a vevői rendelés visszavonásakor, hogy ingyenesen jelennek meg a költségkód szerint a Microsoft Dynamics AX értékesítési rendelésen. Ez a paraméter segítségével határozza meg a lemondási díj kódját.
-   **Szállítási költség kódjának** – kiskereskedők egy külön díjat az áru szállítása a vevő felszámíthat. A Dynamics AX értékesítési rendelési megjelennek a költségkód szerint a szállítási költség összegét. Használja ezt a paramétert, a szállítási költség kódja hozzárendelése a vevői rendelés szállítási költségeket.
-   **Szállítási költségek visszatérítése** – adja meg, hogy egy vevői rendeléshez kapcsolódó szállítási költségek visszatéríthető.
-   **Maximális összeg jóváhagyása nélkül** – Ha a szállítási költségek visszatéríthető, adja meg a maximális szállítási költség-visszatérítési visszárurendelések keresztül. Ha túllépi ezt az összeget, kezelő felülbírálása szükséges annak érdekében, hogy folytassa a visszatérítés. Az alábbi esetekben befogadásához szállítási költségek visszatérítése túlléphetik az eredetileg kifizetett összeg:
    -   Költségek az értékesítési rendelés fejlécében, valamint a szinten érvényesek, ha bizonyos mennyiség egy termékkör vissza, a maximális visszatérítés a szállítási költségeket a termékek engedélyezett, és a mennyiség nem határozható meg, amely minden kiskereskedelmi vevők módon.
    -   Minden példányának szállítási felmerülő szállítási költségek. Ha a vevő termékek többször vissza, és a kiskereskedő a házirend határozza meg, hogy a kiskereskedő visszatérési szállítási költségek költségét viseli, a visszatérési szállítási költségek több, mint a tényleges szállítási költségek lesz.

## <a name="transaction-flow-for-customer-orders"></a>Vevői rendelések tranzakciós forgalom
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Modern a Retail POS rendszerben vevői rendelés létrehozása

1.  Vevő hozzáadása a tranzakcióhoz
2.  Termékek hozzáadása a kosárhoz.
3.  Kattintson a **létrehozása vevői rendelés**, majd válassza ki a rendelés típusát. A rendelés típusa lehet **vevői rendelés** vagy **ajánlat**.
4.  Kattintson a **a kijelölt hajó** vagy **összes hajó** a termékek címre szállítja a vevői számla, adja meg a kért szállítási dátum, és adja meg a szállítási költségek.
5.  Kattintson a **felvétele a kijelölt** vagy **felvétel minden** kell megadni a jelenlegi vagy egy másik tárolóba egy adott napon termékek kiválasztásához.
6.  Gyűjtsük össze a letét összege, ha betét szükség.

### <a name="edit-an-existing-customer-order"></a>Egy meglévő vevői rendelés szerkesztése

1.  A kezdőlapon kattintson a **található egy rendelés**.
2.  Keresse meg és jelölje ki a szerkesztendő rendelést. A lap alján kattintson a **Szerkesztés**.

### <a name="pick-up-an-order"></a>Egy rendelés felvétele

1.  A kezdőlapon kattintson a **található egy rendelés**.
2.  Válassza ki azt a rendelést, hogy emelje fel. A lap alján kattintson a **válogatási és csomagolási**.
3.  Kattintson a **vegyen fel**.

### <a name="cancel-an-order"></a>Megrendelés visszavonása

1.  A kezdőlapon kattintson a **található egy rendelés**.
2.  Válassza ki a rendelés visszavonása. A lap alján kattintson a **Mégse**.

#### <a name="create-a-return-order"></a>Visszárurendelés létrehozása

1.  A kezdőlapon kattintson a **található egy rendelés**.
2.  Válassza ki a vissza, válassza a rendeléshez tartozó számlát, és válassza ki a termék sort az áru vissza.
3.  A lap alján kattintson a **visszárurendelés**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Vevői rendelések aszinkron tranzakciós forgalom
Vevői rendelések hozhatók létre pontról történő értékesítés (POS) ügyfél vagy szinkron vagy aszinkron üzemmódban.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Aszinkron módban létrejön a vevői rendelések engedélyezése

1.  A Dynamics AX rendszerben kattintson a **kereskedelmi és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS profil**&gt;**Funkcióprofilok**.
2.  A a **általános** gyorslapon állítsa a **vevői rendelés létrehozása aszinkron módban** be **Igen**.

Ha a **vevői rendelés létrehozása aszinkron módban** beállítás **Igen**, a vevői rendelések létrehozása mindig aszinkron módban, akkor is, ha a Retail Transaction Service (RTS) érhető el. Ha ebben a beállításban megadott **nem**, vevői rendelések mindig RTS segítségével készülnek szinkron módban. Vevői rendelések létrehozásakor aszinkron módban ezeket lekért és lekéréses (P) feladatok által a Dynamics AX illeszteni. A megfelelő eladási rendeléseket készít a Dynamics AX Ha **rendelések szinkronizálása** kézzel vagy egy kötegelt feldolgozás futtatásakor.

<a name="see-also"></a>Lásd még
--------

[Hibrid vevői rendelések](hybrid-customer-orders.md)


