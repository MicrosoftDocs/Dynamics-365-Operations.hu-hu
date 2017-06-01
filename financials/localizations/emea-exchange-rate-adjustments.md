---
title: "Árfolyam-korrekciók"
description: "Ez a témakör ismerteti az árfolyam-korrekció funkciót az Észtországban, Magyarországon, a Cseh Köztársaságban, Lettországban, Litvániában, Lengyelországban és Oroszországban levő jogi személyek felhasználói számára."
author: ShylaThompson
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Operations, Core
ms.custom: 272683
ms.assetid: cd1b9f11-4640-41a1-a114-222483333972
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f78be567be1f151ab8fcd4e4b721e5c39be4d7ea
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="exchange-rate-adjustments"></a>Árfolyam-korrekciók

[!include[banner](../includes/banner.md)]


Ez a témakör ismerteti az árfolyam-korrekció funkciót az Észtországban, Magyarországon, a Cseh Köztársaságban, Lettországban, Litvániában, Lengyelországban és Oroszországban levő jogi személyek felhasználói számára.

Az Észtországra, Magyarországra, Csehországra, Lettországra, Litvániára, Lengyelországra és Oroszországra vonatkozó árfolyam-korrekciós funkció a következő, a Kinnlevőségek és a Kötelezettségek szempontjából releváns kiterjesztéseket tartalmazza:

-   Az árfolyam-korrekciók feladásait az eredeti kiigazítások helyesbítéseként (negatív összegek) lehet sztornírozni.
-   Egymást követő nem realizált kiigazítások feladásakor a rendszer azonos főkönyvi feladási számlát és tranzakciótípust használ, függetlenül attól, hogy a kiigazítások nyereséget vagy veszteséget képviselnek.
-   A számított árfolyamnyereségeket mindig nyereségszámlákra adja fel, és a számított árfolyamveszteségeket pedig mindig eredményszámlákra adja fel.

Azon jogi személyek, akik elsődleges címe a Cseh Köztársaságban van, speciális árfolyam-korrekciós módot használhatnak. Ezt a módot Növekményes módnak nevezik. Ha ez a mód be van kapcsolva, az aktuális funkció által bevezetett módosításokat a rendszer nem alkalmazza. A nem realizált és a realizált nyereségek vagy veszteségek számítása az utolsó használt árfolyamon történik. A helyesbített eredeti összeg az eredeti összeg helyett használatos a számítás alapjaként. A Növekményes árfolyam-korrekciós módra történő váltáshoz a **Főkönyvi paraméterek** lapon a **Devizaátértékelés** szakaszban található **Számítási mód** mezőben válassza a **Növekményes** lehetőséget. A következő példa bemutatja az árfolyam-korrekció funkció működését Észtországban, Magyarországon, Csehországban, Lettországban, Litvániában, Lengyelországban és Oroszországban. Lássuk a következő üzleti esetet:

-   2012. december 1-jén devizában adtak fel egy számlát.
-   A devizában történő kifizetés feladása 2013. január 3-án történt.
-   A kiegyenlítés a kifizetés számlára történő alkalmazásával történik.
-   Az árfolyam-korrekciót 2012. december 31-én hajtják végre (mód = Normál).
-   Az árfolyam-korrekciót 2013. január 1-jén hajtják végre (mód = Számla dátuma).

Ebben a példában a kanadai dollár (CAD) amerikai dollárra (USD) történő átváltási árfolyamai:

-   2012. december 1.: 400,0000
-   2012. december 31.: 450,0000
-   2013. január 3.: 420,0000

| Esemény                                       | Dátum                             | Tartozik/követel | Összegek               | Főkönyvi számla    | Tranzakció típusa             | Feladás típusa       | Követel | Korrekció |
|---------------------------------------------|----------------------------------|--------------|-----------------------|--------------------------------|------------------------------|--------------------|--------|------------|
| Számla                                     | 12-dec-1                         | Tartozik        | 10 000 CAD/40 000 USD | Kinnlevőségek                             | Számla                      | Vevői egyenleg   |        |            |
| Számla                                     | 12-dec-1                         | Követel       | 10 000 CAD/40 000 USD | Ellenoldal                         | Számla                      | Főkönyvi napló     | X      |            |
| Fizetés                                     | 13-jan-3                         | Tartozik        | 10 000 CAD/42 000 USD | Ellenoldal                         | Fizetés                      | Főkönyvi napló     |        |            |
| Fizetés                                     | 13-jan-3                         | Követel       | 10 000 CAD/42 000 USD | Kinnlevőségek                             | Fizetés                      | Vevői egyenleg   | X      |            |
| Kiegyenlítés                                  | 2013. január 3. (= kifizetési dátum) | Tartozik        | 0 CAD/2 000 USD       | Kinnlevőségek                             | Vevő                     | Árfolyamnyereség |        |            |
| Kiegyenlítés                                  | 2013. január 3. (= kifizetési dátum) | Követel       | 0 CAD/2 000 USD       | Realizált árfolyam-korrekciós nyereség   | Vevő                     | Árfolyamnyereség | X      |            |
| Átértékelés  (normál módszer; dátum = 2012. december 31.) | 12-dec-31           | Tartozik        | 0 CAD/5 000 USD       | Kinnlevőségek                             | Devizaátértékelés | Árfolyamnyereség |        |            |
| Átértékelés  (normál módszer; dátum = 2012. december 31.) | 12-dec-31           | Követel       | 0 CAD/5 000 USD       | Nem realizált árfolyam-korrekciós nyereség | Devizaátértékelés | Árfolyamnyereség | X      |            |
| Átértékelés  (normál módszer; dátum = 2012. december 31.) | 13-jan-3            | Tartozik        | 0 CAD/5 000 USD       | Kinnlevőségek                             | Devizaátértékelés | Árfolyamnyereség |        | X          |
| Átértékelés  (normál módszer; dátum = 2012. december 31.) | 13-jan-3            | Követel       | 0 CAD/5 000 USD       | Nem realizált árfolyam-korrekciós nyereség | Devizaátértékelés | Árfolyamnyereség | X      | X          |



Az előző átértékelésben figyelje meg, hogy a 2013. január 3-i bejegyzés a fölötte levő bejegyzés (2012. december 31.) közvetlen sztornírozása. Még a főkönyvi számlák és a feladási típusok is megegyeznek. Ezenkívül figyelje meg, hogy a **Helyesbítés** jelző van beállítva.
||||||||||
|-----------------------------------------------------------|----------|--------|-----------------|--------------------------------|------------------------------|--------------------|---|---|
|Átértékelés (Számlázás dátuma mód; dátum = 2013. január 1.)  | 13-jan-1 | Tartozik  | 0 CAD/5 000 USD | Kinnlevőségek                             | Devizaátértékelés | Árfolyamnyereség |   | X |
| Átértékelés (Számlázás dátuma mód; dátum = 2013. január 1.) | 13-jan-1 | Követel | 0 CAD/5 000 USD | Nem realizált árfolyam-korrekciós nyereség | Devizaátértékelés | Árfolyamnyereség | X | X |
| Átértékelés (Számlázás dátuma mód; dátum = 2013. január 1.) | 13-jan-3 | Tartozik  | 0 CAD/5 000 USD | Kinnlevőségek                             | Devizaátértékelés | Árfolyamnyereség |   |   |
| Átértékelés (Számlázás dátuma mód; dátum = 2013. január 1.) | 13-jan-3 | Követel | 0 CAD/5 000 USD | Nem realizált árfolyam-korrekciós nyereség | Devizaátértékelés | Árfolyamnyereség | X |   |

Az előző átértékelésben figyelje meg, hogy a 2013. január 1-i bejegyzés az alatta levő bejegyzés (2013. január 3.) közvetlen sztornírozása. Még a főkönyvi számlák és a feladási típusok is megegyeznek. Ezenkívül figyelje meg, hogy a **Helyesbítés** jelző van beállítva.

A rendszer viselkedése megegyezik, függetlenül attól, hogy a **Helyesbítés** lehetőség beállítása a **Tranzakció sztornírozása** szakaszban a **Főkönyvi paraméterek** lapon **Igen** vagy **Nem**.





