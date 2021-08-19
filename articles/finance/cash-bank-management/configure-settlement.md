---
title: Kiegyenlítés konfigurálása
description: A tranzakciók elrendezésének ideje és módja összetett feladat lehet, ezért kiemelten fontos, hogy megértse és pontosan meghatározza az ön üzleti igényeinek megfelelő paramétereket. Ez a témakör a kötelezettségek és a kinnlevőségek elrendezéséhez használt paramétereket mutatja be.
author: kweekley
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 323a1e6d426208a880a72dd89f7be04bacbf13a8e6c5d8ab7599217cfc18f2c0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720574"
---
# <a name="configure-settlement"></a>Kiegyenlítés konfigurálása

[!include [banner](../includes/banner.md)]

A tranzakciók elrendezésének ideje és módja összetett feladat lehet, ezért kiemelten fontos, hogy megértse és pontosan meghatározza az ön üzleti igényeinek megfelelő paramétereket. Ez a témakör a kötelezettségek és a kinnlevőségek elrendezéséhez használt paramétereket mutatja be. 

A következő paraméterek befolyásolják, hogyan hajtja végre a Microsoft Dynamics 365 Finance a kiegyenlítéseket. A kiegyenlítés az a folyamat, amikor a számlát kiegyenlítjük egy kifizetéssel vagy jóváírással szemben. Ezek a paraméterek a **Kiegyenlítés** területen, a **Kinnlevőségek paraméterei** és a **Kötelezettségek paraméterei** lapokon találhatók.

- **Automatikus kiegyenlítés** – Állítsa be az **Igen** értéket, ha a tranzakciót automatikusan más nyitott tranzakciókkal szemben kell állítani feladáskor. Ha a **Nem** értéket állítja be, a felhasználók manuálisan egyenlíthetik ki a tranzakciókat, amikor kifizetést adnak meg, vagy később a **Tranzakciók kiegyenlítése** lap segítségével.
- **Készpénzfizetési engedmény adminisztrációja** – Határozza meg, hogyan [kell kezelni a kézpénzfizetési engedményt, ha egy számla túlfizetett](cash-discount-handling-overpayments.md). Túlfizetés esetén a készpénzfizetési engedmény csökkenthető, kezelhető különbözetként, vagy maradhat a szállító vagy a vevő számláján.
  -   **Meghatározatlan** – A készpénzfizetési engedmény összegét a túlfizetés összegével csökkentjük. A rendszer mindig ezt a viselkedést alkalmazza attól függetlenül, hogy a túlfizetett összeg meghaladja-e vagy kevesebb-e a **Maximális túl- vagy alulfizetés** mezőben megadott összegnél.
  -   **Specifikus** – A túlfizetés összegét vagy feladja egy készpénzfizetési engedménykülönbözeti számlára, vagy megmarad a vevői vagy a szállítói számlán. A specifikus viselkedés attól függ, hogy a túlfizetés összege 0,00 és a **Maximális túl- vagy alulfizetés** mezőben megadott összeg között van-e, vagy meghaladja a **Maximális túl- vagy alulfizetés** összegét.
- **Maximális filléreltérés** – A tranzakciók kiegyenlítésénél elfogadott maximális filléreltérés megadása. Ha a filléreltérés kisebb az ebben a mezőben megadott értéknél vagy egyenlő vele, a filléreltérést automatikusan feladja a program a **Számlák automatikus tranzakciókhoz** oldalon megadott fillérkülönbözeti főkönyvi számlára.
- **Maximális túl- vagy alulfizetés** – A túlfizetés és az alulfizetés elfogadott összegeinek megadása. A túl- vagy alulfizetések forgalmi adójának kiszámításához a **Főkönyvi paraméterek** lapon kattintson a **Forgalmi adó** menüpontra, majd válassza ki az **Túlfizetések vagy alulfizetések forgalmi adója** lehetőséget.
  -   Ha a túl-/alulfizetés a **Maximális filléreltérés** mezőben megadottnál kisebb filléreltérést eredményez, a program feladja a fillérkülönbözet összegét a fillérkülönbözeti számlára.
  -   Ha a túl-/alulfizetés a **Maximális filléreltérés** mezőben megadottnál nagyobb filléreltérést eredményez, akkor a program feladja a fillérkülönbözet összegét a **Vevő készpénzfizetési engedménye** vagy a **Szállító készpénzfizetési engedménye** feladási típus **Számlák automatikus tranzakciókhoz** képernyőn beállított különbözeti számlájára.
- **Részleges kifizetések készpénzfizetési engedményeinek számítása** – Állítsa be az **Igen** értéket a készpénzfizetési engedmények automatikus kiszámításához a részleges kifizetések esetében.
  -   A beállítás hatása függ a **Készpénzfizetési engedmény használata** mező értékétől a **Tranzakciók kiegyenlítése** oldalon. Ha ez a beállítás az **Igen** értékre van állítva, az engedményt akkor alkalmazza a rendszer, ha a **Készpénzfizetési engedmény használata** mező **Normál** értékre van állítva. Ha a **Készpénzfizetési engedmény használata** mező **Mindig** értékre van állítva, a készpénzfizetési engedmény mindig figyelembe van véve, függetlenül attól, milyen beállítás szerepel ebben a mezőben. Ha a **Készpénzfizetési engedmény használata** mező **Soha** értékre van állítva, a készpénzfizetési engedmény soha nincs figyelembe véve, függetlenül attól, milyen beállítás szerepel ebben a mezőben.
  -   Ha ez a beállítás **Igen** értékre van állítva, és a felhasználó megváltoztatja a **Kiegyenlítendő összeg** mező tartalmát a **Kiegyenlítési tranzakciók** oldalon, akkor a rendszer automatikusan kiszámítja az engedményt, és alapértelmezett bejegyzésként jeleníti meg azt az **Alkalmazandó készpénzfizetési engedmény összege** mezőben.
  -   Ha a **Nem** érték van beállítva, és a **Nyitott tranzakciók kiegyenlítése** oldalon módosítja a **Kiegyenlítendő összeg** mező tartalmát egy felhasználó, akkor az **Alkalmazandó készpénzfizetési engedmény összege** mező alapértelmezett értéke **0** (nulla) lesz.
- **Jóváírások készpénzfizetési engedményeinek számítása** – Állítsa be az **Igen** értéket a készpénzfizetési engedmények jóváírásainak automatikus kiszámításához. A Kinnlevőségekben a jóváírás tranzakció egy negatív tranzakció, amelynek az értéke a **Számla** mezőben jelenik meg a **Szabadszöveges számla** oldalon vagy a **Értékesítési rendelés** lapon visszaadott értékként.
  - A beállítás hatása függ a <strong>Készpénzfizetési engedmény használata</strong> mező értékétől a <strong>Tranzakciók kiegyenlítése</strong> oldalon. Ha ez a beállítás az <strong>Igen</strong> értékre van állítva, az engedményt akkor alkalmazza a rendszer, ha a *<strong><em>Készpénzfizetési engedmény használata</em></strong>* mező <strong>Normál</strong> értékre van állítva. Ha a *<strong><em>Készpénzfizetési engedmény használata</em></strong>* mező <strong>Mindig</strong> értékre van állítva, a készpénzfizetési engedmény mindig figyelembe van véve, függetlenül attól, milyen beállítás szerepel ebben a mezőben. Ha a *<strong><em>Készpénzfizetési engedmény használata</em></strong>* mező <strong>Soha</strong> értékre van állítva, a készpénzfizetési engedmény soha nincs figyelembe véve, függetlenül attól, milyen beállítás szerepel ebben a mezőben.
  - Ha ez a beállítás **Igen** értékre van állítva, és a **Tranzakciók kiegyenlítése** lapon meg van adva egy jóváírás, akkor a rendszer automatikusan kiszámítja az engedményt, és alapértelmezett bejegyzésként megjeleníti az **Alkalmazandó készpénzfizetési engedmény összege** mezőben.
  - Ha ez a beállítás **Nem** értékre van állítva, és a **Tranzakciók kiegyenlítése** oldalon meg van adva egy jóváírás, akkor az **Alkalmazandó készpénzfizetési engedmény** mező alapértelmezett összege **0** (nulla).

- **Kedvezmény ellenszámlák (csak AP)** – Az alapértelmezett készpénzfizetési engedmény főkönyvi számla megadása, amely a készpénzfizetési engedmények könyvelési tételeként használható.
  -   **Fő számla használata szállítói kedvezményekhez** – A készpénzfizetési engedmény feladása a megadott fő számlára a **Készpénzfizetési engedmény beállítása** oldalon.
  -   **A számla soraiban szereplő számlák** – A készpénzfizetési engedmény feladása a főkönyvi számlákhoz az eredeti számlán.
- **Sorok megjelölése a szabadszöveges számlákon és a kamatleveleken (csak AR)** – Állítsa be az **Igen** értéket a **Számlasorok megjelölése** gomb engedélyezéséhez a **Vevői kifizetések megadása**, a **Naplóbizonylat**, és a **Tranzakciók kiegyenlítése** oldalakon. Ennek a gombnak a segítségével a felhasználók kijelölhetnek egyes sorokat kiegyenlítésre.
- **Kiegyenlítés rangsorolása (csak AR)** – Állítsa be az **Igen** értéket a **Megjelölés prioritás szerint** gomb engedélyezéséhez a **Vevői kifizetések megadása** és a **Tranzakciók kiegyenlítése** oldalakon. Ennek a gombnak a segítségével a felhasználók megadhatják a tranzakciók előre meghatározott kiegyenlítési sorrendjét.  Miután a kiegyenlítési sorrendet alkalmaztuk a tranzakciókra, a sorrend és a kifizetések felosztása a Megjelölés prioritás szerint gombbal feladás előtt módosíthatók.
- **Rangsor használata automatikus kiegyenlítésekhez** – Állítsa be az **Igen** értéket meghatározott rangsor használatához a tranzakciók automatikus kiegyenlítése közben. Ez a mező akkor érhető el, ha a **Kiegyenlítés rangsorolása** és az **Automatikus kiegyenlítés** **Igen** értékre vannak állítva.

## <a name="fixed-dimensions-on-accounts-receivableaccounts-payable-main-accounts"></a>Rögzített dimenziók a kinnlévőségek/kötelezettségek főszámlákon

Ha a kinnlevőségek/kötelezettségek főszámlákon rögzített dimenziókat használunk, további könyvelési tételeket és két további szállítói tranzakciót ad fel az elszámolási folyamat. A kiegyenlítés összehasonlítja a kinnlevőségek/kötelezettségek főkönyvi számlát a számla és a fizetés alapján.  Amikor a fizetés és az elszámolás együtt teljesül, és jellemzően így történik, a fizetés könyvelési bejegyzése nem kerül be a főkönyvbe, amíg be nem fejeződik az elszámolási folyamat is. A feldolgozási események sorrendje miatt az elszámolás nem tudja meghatározni a tényleges kinnlevőségek/kötelezettségek főkönyvi számlát a fizetés könyvelési bejegyzése alapján. Az elszámolás rekonstruálja, hogy mi lesz a főkönyvi számla a fizetés esetén. Ez akkor jelent problémát, ha rögzített dimenziót használunk a kinnlévőségek/kötelezettségek fő számlához.

A főkönyvi számla rekonstruálásához megtörténik a kinnlevőségek/kötelezettségek fő számlá beolvasása a feladási profilból, és a pénzügyi dimenziók beolvasásra kerülnek a fizetéshez tartozó szállítói tranzakció rekordjából, a fizetési naplóban meghatározottak szerint. A rögzített dimenziók nem alapértelmezettek a fizetési naplóhoz, helyette a feladási folyamat utolsó lépéseként alkalmazzák őket a fő számlára. Emiatt a rögzített dimenzió értékét valószínűleg nem tartalmazza a szállítói tranzakció, csak ha már forrásból származik, például a szállítótól. A rekonstruált számla nem tartalmazza a rögzített dimenziót. Az elszámolás feldolgozása határozza meg, hogy létre kell-e hozni korrekciós bejegyzést, mivel a rögzített dimenziós értékkel feladott számlából és a rekonstruált fizetési számlából ez nem derül ki.  Ahogy az elszámolás folytatódik a korrekciós bejegyzés feladásával, a feladás utolsó lépése a rögzített dimenzió alkalmazása lesz. Ha megtörténik a rögzített dimenzió hozzáadása a korrekciós bejegyzéshez, feladásra kerül egy tartozik és egy követel tétellel ugyanahhoz a főkönyvi számlához. Az elszámolás nem tudja visszaállítani a könyvelési bejegyzést.

A további könyvelési bejegyzések (tartozik és követel tételek ugyanahhoz a főkönyvi számlához) elkerülése érdekében érdemes figyelembe venni a következő megoldásokat az üzleti követelményektől függően. 

-   A szervezetek gyakran használnak rögzített dimenziókat az olyan pénzügyi dimenziók kitöltésére, melyekre nincs szükség. Ez a helyzet általában a mérlegszámlák, például a kinnlevőségekből/kötelezettségek esetén. A számlastruktúrákat lehet úgy használni, hogy ne kövessék azokat a pénzügyi dimenziókat, amelyek általában kitöltésre kerülnek.  Eltávolíthatja a mérlegszámlák esetében a pénzügyi dimenziókat, feleslegessé téve a rögzített dimenziókat használatát.
-   Ha a szervezet előírja a rögzített dimenziók használatát a kinnlevőségek/kötelezettségek fő számla esetén, állítsa be alapértelmezettként a rögzített dimenziót a fizetéshez, így a rögzített dimenzió értékét tárolja a fizetéshez tartozó szállítói tranzakció. Ez lehetővé teszi a rendszer számára, hogy helyreállítása a kinnlevőségek/kötelezettségek fő számlát, a rögzített dimenziók értékeit is tartalmazva. A rögzített dimenzió értékét meg lehet adni alapértelmezettként a szállítókra vagy a napló nevére vonatkozóan a fizetési naplónál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]