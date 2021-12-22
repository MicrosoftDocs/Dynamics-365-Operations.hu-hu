---
title: Adókódok beállítása
description: Ez a témakör leírja, hogyan lehet adókódokat beállítani az adószámítási szolgáltatásban.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 8bdb194e7d8b704d1e58d3c25bf2e1f6bff1ba00
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883901"
---
# <a name="set-up-tax-codes"></a>Adókódok beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet adókódokat beállítani az adószámítási szolgáltatásban. Egy egyszerű helyzet beállítását is tartalmazza az adókódok munkához, illetve információk az összetett helyzetekben használható speciális adókód-funkciókról.

> [!IMPORTANT]
> Az adószámítási szolgáltatásban az adókódok beállítása jogi személy–nem független. Ezt a beállítást csak egyszer lehet végrehajtani az RCS (Regulatory Configuration Service) szolgáltatásban. A program automatikusan szinkronizálja az adókódokat a Microsofttal, amikor engedélyezi az adószámítási szolgáltatást a Pénzügyben kiválasztott Dynamics 365 Finance jogi személy számára.

## <a name="simple-setup"></a>Egyszerű beállítás

A következő lépések szerint használhatja az adókódot egy egyszerű, például olyan helyzetben, amikor csak egy adókulcs van.

1. Jelentkezzen be a [szabályozó konfigurációs szolgáltatásba](https://marketing.configure.global.dynamics.com/).
2. Ugrás a **Munkaterületek** \> **globalizációs funkciói –** \> **Adószámítás**
3. Válassza ki a beállítani kívánt szolgáltatást és verziót, és válassza a **Szerkesztés lehetőséget**.
4. Az Általános **lapon válassza ki a Konfiguráció** **verziót**.
5. Az **Adókódok** lapon válassza a **Hozzáadás** lehetőséget, és adja meg az adókódot és a leírást.
6. Számítás **eredetének kiválasztása**. A számítási forrás olyan módszerek csoportja, amelyek a kiválasztott adókonfigurációs verzióban vannak meghatározva. Erre az egyszerű helyzetre a Nettó összeg **alapján választ**.
7. Válassza a **Mentés** lehetőséget. A kiválasztott számítási forrástól függően több mező is elérhetővé válik.
8. A **Mértékek gyorsététen válassza a Hozzáadás lehetőséget, ha ehhez az adókódhoz egy adókulcsot** **szeretne** hozzáadni.
9. Válassza a **Mentés** lehetőséget.

## <a name="calculation-origin"></a>Számítás eredete

A számítás eredete meghatározza az adóalap és az adó összegének számítási módját. Az elektronikusjelentés-munkaterület **adókonfigurációja** szerint van konfigurálva. A Számítás eredete mezőben **a következő értékek** érhetők el:

- Nettó összeg alapján
- Bruttó összeg alapján
- Mennyiség alapján
- Árrés alapján
- Adó az adón

### <a name="by-net-amount"></a>Nettó összeg alapján

Ha a Nettó összeg beállítás van megadva a Számítás eredete mezőben, az adó összegét a beszerzési vagy értékesítési összeg százalékaként számítja ki a program, minden **egyéb** **adókód** kizárása nélkül.

Például az áfakulcs 25 százalék, a számlasor 10 darabos mennyiséget mutat 1,00 egységenként, és a vevő 10 százalékos sorengedményt kap. Ebben az esetben az összegek kiszámítása a következőképpen történik:

- **Nettó összeg:** (10 × 1,00) – 10 százalék = 9,00 
- **Áfa:** 9,00 × 25 százalék = 2,25 
- **Teljes számlaösszeg:** 9,00 + 2,25 = 11,25

### <a name="by-gross-amount"></a>Bruttó összeg alapján

Ha a Bruttó összeg alapján lehetőséget választja a Számítás eredete mezőben, az adó összegét a bruttó értékesítési **összeg** **százalékaként** számítja ki a program. A bruttó összeg a sor nettó összege plusz a sor összes adója és díja, kivéve azt az adót, amelyben a Számítás eredete mező a bruttó összeg **alapján** van **beállítva**.

Az adóhatóság például különleges adókat szabott ki egy cikkre. A program az adó összegét az adó számítása előtt hozzáadja a nettó összeghez. A következő adókódok használatosak:

- **1. adó – a díj 10 százalék, és a nettó összeg** **számítási** módszerét használja a program.
- **2. adó – az árfolyam 20 százalék, és a nettó összeg** **számítási** módszerét használja a program.
- **Adómérték** – az árfolyam 25 százalék, és a Bruttó összeg számítási módszer **használatos**.

Ha a nettó összeg 10,00, az 1. adó összege 1.00 (10.00 × 10 százalék), és a 2. adó összege 2.00 (10.00 × 20 százalék). Ebben az esetben az összegek kiszámítása a következőképpen történik: 

- **Bruttó összeg:** Nettó összeg + 1. adó összege + 2. adó összege = 10,00 + 1,00 + 2,00 = 13,00 
- **Adó összege:** 13,00 × 25 százalék = 3,25 
- **Összes vám és adó:** 1,00 + 2,00 + 3,25 = 6,25 
- **Teljes számlaösszeg:** 10,00 + 6,25 = 16,25

### <a name="by-quantity"></a>Mennyiség alapján

Ha a Mennyiség szerint lehetőséget választja a Számítás eredete mezőben, az adó összegét a program egységenkénti rögzített összegként számítja ki, és megszorozza a bizonylatsoron **megadott** **mennyiséggel**. Az egységenkénti összeg a Díj gyorsban **van** meghatározva.

Az áfakód beállítása például egységenként 1,20. Az értékesítési számla sorában a cikk 25 egysége van eladva. Ebben az esetben az adó összege 25, × 1,20 = 30,00.

### <a name="by-margin"></a>Árrés alapján

Ha a Számítás eredete mezőben az Árrés alapján lehetőséget választja, az adó összegét az értékesítési **árrés** **százalékaként** számítja ki a rendszer. Az értékesítési árrés az értékesítési összeg mínusz a költségösszeg. Ez a számítási mód csak értékesítési tranzakciókra vonatkozik.

Például az áfakulcs 25 százalék, a számlasor 10 darabos mennyiséget mutat 10,00 egységenként, és a cikkenkénti költség 6. Ebben az esetben az összegek kiszámítása a következőképpen történik:

- **Eladási** árrés: 10 × ( 10,00 - 6,00) = 40,00
- **Adó összege:** 40,00 × 25 százalék = 10,00
- **Teljes számlaösszeg:** 100,00 + 10,00 = 110,00

### <a name="tax-on-tax"></a>Adó az adón

Ha a Számítás eredete mezőben az Adó az adón lehetőséget választja, az áfa számítása a bizonylatsor többi **adóösszegének** **százalékaként** történik.

Például a következő adókódok használhatók:

- **1. adó – a díj 10 százalék, és a nettó összeg** **számítási** módszerét használja a program.
- **2. adó – az árfolyam 20 százalék, és a nettó összeg** **számítási** módszerét használja a program.
- **Adó -** az adó mértéke 25 százalék, és az adószámítási módszert használja a **program**.

Ebben az esetben az összegek kiszámítása a következőképpen történik:

- **Nettó összeg:** 10,00 
- **1. adó:** 10,00 × 10 százalék = 1,00 
- **2. adó:** 10,00 × 20 százalék = 2,00 
- **Adó adója:** 3,00 × 25 százalék = 0,75
- **Adó összesen:** 1,00 + 2,00 + 0,75 = 3,75 
- **Teljes számlaösszeg:** 10,00 + 3,75 = 13,75

## <a name="advanced-functionality"></a>Speciális funkciók

Ez a szakasz bemutatja az összetett helyzetek adókód-beállításának egyes speciális funkcióit.

### <a name="tax-exemption"></a>Adómentesség

Ha az Általános gyorsététen az Adómentesség lehetőséget Igen beállításra állítja, az adó összegét a rendszer mindig nullára (0) bírálja felül, függetlenül a **tényleges** **·** **adómkulcstól**.

A Mentesség kódja **mezőben** megadható az adómentesség indoka. 

Az alapadat-keresés engedélyezhető a Mentességi kód **mezőben**. Így választhat a Pénzügyben megadott mentességi kódértékek közül. Az alapadat-keresés engedélyezésével kapcsolatos tudnivalókat lásd: Alapadat-keresés [engedélyezése adószámítási](tax-service-set-up-environment-master-data-lookup.md) konfigurációhoz.

Például az áfakulcs 25 százalék, és a Mentesség beállítása Igen **az** **áfakódnál**. A számlasoron 10 cikk van, mindegyik 1,00-at tartalmaz, és a vevő 10 százalékos sorengedményt kap. Ebben az esetben az összegek kiszámítása a következőképpen történik:

- **Nettó összeg:** (10 × 1,00) – 10 százalék = 9,00 
- **Áfa:** 0,00 
- **Teljes számlaösszeg:** 9,00 + 0,00 = 9,00

### <a name="use-tax"></a>Importadó

Ha az Általános gyorsététen az Is Use Tax lehetőséget igenre állítva adja fel az adóösszeget, akkor a rendszer a Szállító összegző számlája helyett a Fizetendő áfa használatára **vonatkozó** **·** **·** **·** **számlára adja** fel az összeget.

Például az áfakulcs 25 százalék, és az áfakódnál az Is Use Tax beállítás **Van** **beállítva** Igen beállításra. A számlasoron 10 cikk van, mindegyik 1,00-at tartalmaz, és a vevő 10 százalékos sorengedményt kap. Ebben az esetben az összegek kiszámítása a következőképpen történik:

- **Nettó összeg:** (10 × 1,00) – 10 százalék = 9,00 
- **Forgalmi adó:** 9,00 × 25 százalék = 2,25
- **Teljes számlaösszeg:** 9,00 + 0,00 = 9,00

> [!IMPORTANT]
> Ha egy adókód esetében mind Az adószám, mind az Is Use Tax beállítás Igen beállítást adja meg, a rendszer adómentesként ismeri el az értékesítési tranzakciókat és a beszerzési tranzakciókhoz **használt** **·** **adót**.

### <a name="reverse-charges"></a>Fordított adók

Ha az Általános gyorsoldalon a Fordított áfafizetés beállítása Igen, az **áfakulcs** **·** **negatívként** is konfigurálható. Fordított adózás esetén két adókódot ajánlott beállítani: egyet pozitív adókulcsú és egy negatív adókulcsot. Mindkét adókódnak azonos áfaértékkel kell rendelkezik, és a Fordított áfa beállítás értéke Igen értékre kell állítva lennie a negatív **adókulcsú** **adókódok** esetén. A fordított áfa megoldásával kapcsolatos további tudnivalókat a Finance alkalmazásban lásd: [Fordított áfamechanizmus az ÁFA/GST sémához](emea-reverse-charge.md).

Például két adókódot határoznak meg egy számlasoron. Egy adókulcs 25 százalék. A másik áfakulcs -25 százalék, a második áfakódnál pedig Igen az **Fordított** **áfafizetés** beállítás. A számlasoron 10 cikk van, mindegyik 1,00 egységben. Ebben az esetben az összegek kiszámítása a következőképpen történik:

- **Nettó összeg:** (10 × 1,00) = 10,00 
- **1-es adókód:** 10,00 × 25 százalék = 2,50
- **2. adókód:** 10 × -25 százalék = -2,50
- **Teljes számlaösszeg:** 10,00 + 2,50 -2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Kizárás az alapösszeg-számításokból

Ha az Általános gyorstára esetében az Alapösszeg számításból való kihagyás beállítása Igen beállítást adja meg, akkor az adókód számított adóösszege nem fog beleszámni az egyéb adókódszámítások adóalapösszegébe az árba nem **számít** **·** **bele**.

A további tudnivalókat lásd az Árak adószámítása, ha az árak tartalmazzák [az](global-exclude-from-tax-base-amount-calculation.md) adókat.

### <a name="rates"></a>Díjalapok

A Mérték gyorséta használhatja, ha az adóalapösszegek különböző tartományaihoz eltérő **adókulcsokat** ad meg. Az adóösszeg kiszámításához az adószámítási szolgáltatás mindig az adóalap összegének megfelelő mértéket használja.

Például az áfakulcsok a következő táblázatban látható módon konfigurálhatóak.

| Minimális összeg | Maximális összeg | Áfakulcs   |
| -------------- | -------------- | ---------- |
| 0              | 1000          | 10% |
| 1000          | 5 000          | 15% |
| 5 000          | 10,000         | 20% |
| 10,000         | 0              | 30% |

Ebben az esetben az adó összegét a következőképpen számítja ki a program:

- Ha az adóalap összege 300,00, az adó mértéke 10 százalék, és az adó összege 300,00 × 10 százalék = 30,00.
- Ha az adóalap összege 3 000,00, az adó mértéke 15 százalék, és az adó összege 3 000,00 × 15 százalék = 450,00.
- Ha az adóalap összege 6 000,00, az adókulcs 20 százalék, és az adó összege 6 000,00 × 10 százalék = 1200,00.
- Ha az adóalapösszeg 20,000.00, az áfakulcs 30 százalék, és az adó összege 20,000.00 × 30 százalék = 6 000,00.

> [!NOTE]
> Ha az adóalapösszeg megfelelhet az egyik sorban található maximális összegnek és a másik sorban minimális összegnek is, akkor az alap a minimális alapösszegnek megfelelő adókulcsot használja. Ha például az adóalap összege 1000,00, az áfakulcs 15 százalék, és az adó összege 1 000,00 × 15 százalék = 150,00.

### <a name="limits"></a>Korlátok

A Határok gyorsétét használhatja az adókorlátok meghatározására, hogy felülbírálja a számított adóösszeget, ha az adóösszeg a **minimális**/maximális tartományba esik.

- Ha a számított adóösszeg nagyobb vagy egyenlő a Határok gyorsététen konfigurált maximális adóösszeggel, a végső adóösszeg megegyezik a maximális **adóösszeggel**.
- Ha a számított adóösszeg kisebb, mint a Határok gyorsététen beállított minimális adóösszeg, a végső adóösszeg **0** (nulla).

Az adókorlátok például a következő módon vannak konfigurálva:

- **Minimális adóösszeg:** 100 
- **Adó maximális összege:** 1 000

Ha a számított adóösszeg 2000, a végső adó összege 1000.

Ha a számított adóösszeg 500, a végső adó összege 500.

Ha a számított adóösszeg 80, a végső adó összege 0 (nulla).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
