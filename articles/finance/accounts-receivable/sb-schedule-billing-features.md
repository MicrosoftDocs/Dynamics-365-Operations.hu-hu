---
title: Számlázási ütemezés funkciói
description: Ez a témakör bemutatja a számlázási ütemezések jellemzőit, mint például az árképzési módszerek, az eszkalációk és engedmények, az igazítási dátumok, a proráció, a sztornószámlázás és a cikkcsoportok felosztása.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ce323565a94e8e70d90a65b7a3143e984a1c159
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8696646"
---
# <a name="billing-schedule-features"></a>Számlázási ütemezés funkciói

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a számlázási ütemezések és a számlázási ütemezési sorok jellemzőit. Ismerteti az árképzéshez használt különböző módszereket, az eszkalációk és engedmények használatát, valamint a számlázási időszak sztornírozhatóságát. Példákat tartalmaz a prorációszámításra és a megosztott cikkcsoportokra is.

## <a name="pricing-methods"></a>Árképzési módszerek

A cikkek egységárának kiszámítására a következő árképzési módszerek egyikét használhatja:

* Egységes
* Normál
* Szint
* Egyszintű

### <a name="flat-pricing"></a>Egyszerű árképzés

Ha a lakásáras árképzési módszert használja, akkor az **Összes** számlázási ütemezés lapon található számlázási ütemezési sor cikkegységét bármilyen értékre lehet szerkeszteni. Az **áregység** mindig **1**. Emiatt egy **cikk egységár** **- és nettóösszeg-értéke** megegyezik.

### <a name="standard-pricing-without-a-trade-agreement"></a>Szokásos árképzés (kereskedelmi megállapodás nélkül)

Ha az általános árképzési módszert kereskedelmi megállapodás nélkül használja, akkor a Termékadatok kiadása lapon a Termékinformációk kezelése **lehetőség** kiválasztásával beállíthatja egy számlázási **ütemezési sor cikkéhez az egységárat**. Az egységár az Alap eladási **ár szakaszban látható**. Számítása az Ár ára *mennyiség*&divide;*.*

### <a name="standard-pricing-with-a-trade-agreement"></a>Szokásos árképzés (kereskedelmi megállapodással)

Az alábbi példák bemutatják az általános árképzési számításokat, ha létezik kereskedelmi megállapodás. Kereskedelmi megállapodásokat a Termék részleteinek kiadása **lapon hozhat létre**.

Mindkét példa olyan cikket használ, amely a következő szögletes zárójellel rendelkezik.

| Mennyiség a 1000-esből | Mennyiség a 2012-hez | M(E) | Ár | Áregység |
|---|---|---|---|---|
| 0 | 100 | Mindegyik | 1.50 | 1 |
| 100 | 200 | Mindegyik | 1.25 | 1 |
| 200 | 999999 | Mindegyik | 1,00 | 1 |

**1. példa**

A számlázott mennyiség 250, és a szokásos árképzési módszert használja a program. Mivel a mennyiség a 200–999 999 ár mennyiségi tartományba esik, az egységár 1,00. 

A nettó összeg számítása a következőképpen történik:

*Nettó összeg* = (*Mennyiségár*&times;*·*) &divide;*Áregység* = (250 &times; 1,00) &divide; 1 = 250

**2. példa**

A számlázott mennyiség 100, és a szokásos árképzési módszert használja a program. Mivel a számlázott mennyiség a 0–100 ár mennyiségi tartományba esik, az egységár 1,50.

> [!NOTE]
> A számlázott mennyiség a 100–200 tartomány helyett 0–100 tartományban van, mivel a szokásos mennyiségegyeztetési viselkedésben a *mennyiség* megfelel, ha nagyobb vagy egyenlő, mint a "1"-es mennyiség, és kisebb, mint a "to" *mennyiség*.

A nettó összeg számítása a következőképpen történik:

*Nettó összeg* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Szint árképzése

A következő példában egy cikkhez a következő szögletes zárójelek közül választhat.

| Mennyiség a 1000-esből | Mennyiség a 2012-hez | M(E) | Ár | Áregység |
|---|---|---|---|---|
| 0 | 100 | Mindegyik | 1.50 | 10 |
| 100 | 200 | Mindegyik | 1.25 | 10 |
| 200 | 999999 | Mindegyik | 1,00 | 10 |

Ha a számlázott mennyiség 250, és a többszintű árképzési módszert használja, akkor a cikkek árát a következőképpen számítja ki a program az árképzés zárójelei alapján:

- **Első 100 cikk:** 100 &times; 1,50 = 150,00
- **Második 100 cikk:** 100 &times; 1,25 = 125,00
- **Fennmaradó cikkek:** 50 &times; 1,00 = 50,00

A nettó összeg számítása a következőképpen történik:

*Nettó összeg* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

A nettó összeg számítása után az egységár a nettó összeg és a mennyiség osztója:

*Egységár* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Lakásszintű árképzés

A következő példában egy cikkhez a következő szögletes zárójelek közül választhat.

| Mennyiség a 1000-esből | Mennyiség a 2012-hez | M(E) | Egyszintű összeg | Áregység |
|---|---|---|---|---|
| 0 | 50 | Mindegyik | 100.00 | 50 |
| 50 | 200 | Mindegyik | 150.00 | 200 |

A következő táblázat bemutatja a különböző beszerzett mennyiségek számláit és egységárát. Először a nettó összeget, majd az egységárat számítja ki a program.

| Számla | Beszerzett mennyiség | Egységár | Nettó összeg |
|---|---|---|---|
| 1 | 25 | 2,00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2,00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2,00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0,75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Eszkalációk és engedmények

Az *eszkaláció* áremelést jelent egy jövőbeli számlázási időszakra, amelyről még nem készült számla. *Az* engedmény árcsökkentés egy jövőbeli számlázási időszakra vonatkozóan, amelyről még nem készült számla.

Az előfizetési számlázásban az eszkalációk és engedmények nem alkalmazhatók újraaktiválva egy számlázási ütemezésre. Például három hónapra nem lehet eszkalációt alkalmazni egy számlázási ütemezésre, és feldolgozni azt. Más szóval nem alkalmazhat áremelést, amely három hónappal ezelőtt történt.

Eszkalációt vagy engedményt alkalmazhat számlázási ütemezésre vagy számlázási ütemezési sorra a következő helyeken:

- A **Mind/Aktív számlázási ütemezések** listaoldal
- Adott számlázási ütemezés
- Adott számlázási ütemezési sor

### <a name="apply-an-escalation-or-discount"></a>Eszkaláció vagy engedmény alkalmazása

A következő lépések szerint alkalmazhat eszkalációt vagy engedményt a számlázási ütemezésre.

1. Válasszon ki egy számlázási ütemezést vagy egy számlázási ütemezési sort.
2. Az **Eszkaláció és** engedmény kiválasztása vagy az **Eszkaláció** és engedmény lapon, vagy a számlázási ütemezés sorában.
3. Ha az eszkaláció vagy engedmény számításához egy felhasználói árindexet használ, válasszon ki egy értéket a **Felhasználói árindex számítása mezőben**.
4. Eszkalációs **vagy** engedménysor hozzáadásához válassza az Új lehetőséget.
5. Engedményhez jelölje be az **Engedmény** jelölőnégyzetet. Eszkalációhoz hagyja az **Engedmény** jelölőnégyzetet törölve.
6. A Kezdő **dátum és Gyakoriság** **mezők** beállítása.
7. Halasztott cikkeknél, amelyek a nemszámlázandó bevétel funkciót használják, állítsa be a Záró **dátum mezőt**.
8. A **Százalék**, **Összeg** **vagy Felhasználói árindex ütemezése mező** beállítása.
9. A Záró **dátum mező** beállítása.
10. Válassza ki az **OK** lehetőséget.
11. Ismételje meg a 4–10. lépést minden további szükséges eszkalációs vagy engedménysorra.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Mezők a Számlázási ütemezés sorai lapon

A **Számlázási ütemezés sorai** lap a következő mezőket tartalmazza.

| Mező | Leírás |
|---|---|
| Cikkszám | A számlázási ütemezési sor cikkszáma. Ez a mező csak akkor érhető el, ha a lapot számlázási ütemezési sortételből nyitották meg. |
| Fogyasztói árindex számítása | <p>Válassza ki a felhasználói árindex eszkalálásának kiszámításához használt módszert:</p><ul><li>**Korábbi felhasználói árindex** – az eszkaláció kiszámításához használja a korábbi felhasználói árindex értékét.</li><li>**A felhasználói árindex alapértéke** – az eszkaláció kiszámításához a felhasználói árindex alapértékét használja.</li></ul> |
| **Sorrács** | |
| Kedvezmény | <p>A jelölőnégyzet beadásával adhatja meg, hogy az összeg módosítása eszkaláció vagy engedmény legyen:</p><ul><li>**Bejelölve** – a módosítás engedményt alkalmaz a számlázási ütemezésre vagy a számlázási ütemezés sorra.</li><li>**Törölve** – a módosítás eszkalációt alkalmaz egy számlázási ütemezésre vagy ütemezési sorra.</li></ul><p>Ennek a jelölőnégyzetnek a beállítása nem módosítható olyan cikkeknél, amelyeknél a nemszámlázatlan bevétel szolgáltatást használják. Ezenkívül engedmények nem alkalmazhatók olyan cikkekre, amelyek bevétel-felosztást alkalmaznak.</p> |
| Kezdés dátuma | Az eszkaláció vagy engedmény kezdő dátumának kiválasztása. |
| Gyakoriság | Az eszkaláció vagy engedmény gyakoriságának kiválasztása: Nincs, Havi, Negyedéves **·**, Féléves, **Évenkénti** **vagy Éves.** **·** **·** |
| Százalék | Adja meg az eszkaláció vagy az engedmény százalékos arányát. |
| Összeg | Az eszkaláció vagy engedmény összegének megadása. |
| Fogyasztói árindex ütemezése | A számításokhoz használt felhasználóiár-index ütemezésének kiválasztása. |
| Befejezés dátuma | <p>Az eszkaláció vagy engedmény záró dátumának kiválasztása.</p><p>**Megjegyzés:** Ez a mező szükséges a nem beszámlázatlan bevétel szolgáltatást használata esetén.</p> |
| Halasztási ütemezés száma | <p>A halasztás ütemezési száma.</p><p>Ez a mező csak akkor érhető el, ha az oldalt számlázási ütemezési sorból nyitotta meg.</p> |
| Napló kötegszáma | <p>A napló kötegszáma.</p><p>Ez a mező csak akkor érhető el, ha az oldalt számlázási ütemezési sorból nyitotta meg.</p> |
| Teljes engedmény összege | <p>A rács minden sorára vonatkozó engedményösszegek összege.</p><p>Ez a mező csak akkor érhető el, ha az oldalt számlázási ütemezési sorból nyitotta meg.</p> |
| Aktuális rövid távú nemszámlázatlan bevételösszeg | <p>A jelenlegi rövid távú nemszámlázatlan bevételösszeg.</p><p>Ez az összeg akkor jelenik meg, ha az Ismétlődő szerződés számlázási paraméterei oldalon rövid távú halasztás van kiválasztva, és a sorcikk számlái be vannak állítva a **Nem** számlázható bevétel beállítási lapon **.**</p> |
| A jelenlegi hosszú távú nemszámlázatlan bevételösszeg | <p>A jelenlegi hosszú távú nemszámlázatlan bevételösszeg.</p><p>Ez az összeg akkor jelenik meg, ha az Ismétlődő szerződés számlázási paraméterei oldalon rövid távú halasztás van kiválasztva, és a sorcikk számlái be vannak állítva a **Nem** számlázható bevétel beállítási lapon **.**</p> |

## <a name="proration-examples"></a>Proration – példák

A proráció számítása a napok számán vagy a hónapok számán alapulhat. A prorációszámításhoz **használt módszert az Ismétlődő szerződés számlázási paraméterei oldalon lehet** beállítani. A proration metódus azt befolyásolja, hogyan történik a számlázási ütemezések összegének kiszámítása a következő esetekben:

- Kezdeti létrehozás
- Eszkaláció vagy engedmény alkalmazása
- Befejezés
- El<a2/<a2
- Támogatás vagy megújítás kiegészítés

A proration módszer a havi ismétlődő bevétel (MRR) jelentés számításait is befolyásolja.

### <a name="example-1"></a>1. példa

A számlázási ütemezés éves összege nem $5,000. A kezdő dátum 2019. augusztus 12. és a záró dátum 2019. december 22. A számlázási gyakoriság éves. Attól függően, hogy használja-e a napi vagy havi számítási módszert, a program a következőképpen számítja ki a program a időkorrektált összeget:

- **Napi**

    - *Napok számaEndátum* = *·* – *Kezdő dátum* + 1 = 133 nap
    - *Napok száma az évben* = 2020. augusztus 11. – 2019. augusztus 12. + 1 = 366 nap
    - *Prorated összeg* = 5 000 &times; (133 &divide; 366) = 1816,94

- **Havi**

    - *Kezdő hónap része* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Középső hónap* = 3
    - *Záró hónap része* = 22 &divide; 31
    - Prorated összeg = 5 000 &divide; 12 &times;\[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1814,52

### <a name="example-2"></a>2. példa

A számlázási ütemezés éves összege nem $12,000. A kezdő dátum 2019. augusztus 1., záró dátum pedig 2019. december 31. A számlázási gyakoriság éves. A program a számítási módszertől függően a következőképpen számítja ki a program a nem megfelelő összegeket:

- **Napi**

    - *Napok számaEndátum* = *·* – *Kezdő dátum* + 1 = 153 nap
    - *Napok száma az évben* = 2020. július 31. – 2019. augusztus 1. + 1 = 366 nap
    - *Prorated összeg* = 12 000 &times; (153 &divide; 366) = 5016,39

- **Havi (teljes hónap)**

    - *Hónapok száma* = 5
    - *Összes hónap* = 12
    - *Prorated összeg* = (12 000 &times; 5) &divide; 12 = 5 000

## <a name="reversing-a-period-billing"></a>Időszaki számlázások megfordítása

Ebben a példában a számlázási ütemezésnek csak egy sora van:

- A számlázás havonta, januártól decemberig 12 hónapon keresztül történik.
- A számlák áprilisig minden időszakra létrejöttek.

Sztornírozni szeretné az áprilisi számlázási időszak számláját.

Ha az áprilisi számlázási időszakra még nem készült értékesítési számla, törölheti az értékesítési rendelést. Ebben az esetben a **részletek** számlázva állapota törlődik. Mivel azonban készült számla a számlázási időszakhoz, **a** részletek Számlázott állapota nem törlődhet. Ezért az áprilisi számlázás sztornírozához a sorhoz ellentételt kell létrehozni.

1. Hozzon létre **egy ütemezési sort** ugyanannak a cikknek a Minden számlázási ütemezés lapon.
2. A cikk **mennyiségértékének** módosítása az eredeti mennyiség negatív értékére.
3. A Számlázási **gyakoriság mező** beállítása egyszeres **.**
4. A kezdő és záró dátumok frissítése úgy, hogy megegyeznek annak a számlázási részletsornak a dátumokkal, amelyekhez jóváírást szeretne létrehozni. Ebben a példában állítsa a kezdő dátumot 2019. április 1-re, a záró dátumot pedig 2019. április 30-ra.
5. Mentse el a módosításokat.
6. Nyissa meg **a Számla létrehozása** lapot, és hozza létre azt az értékesítési rendelést, amely a jóváírást a megadott időszakra vonatkozóan könyveli.
7. Nem kötelező: A számla feladható.

Amikor áttekinti a számlázási ütemezés sorait, észreveszi, hogy az új sor a jóváírásra hivatkozik. Az eredeti sor továbbra is az eredeti áprilisi számlához lesz csatolva.

## <a name="split-item-group-examples"></a>Megosztott cikkcsoport – példák

Ehhez a példához a következő beállítások vannak érvényben:

- Az Ismétlődő szerződés **számlázási paraméterei** oldalon be **van** jelölve a Felosztás cikkcsoport szerint beállítás, **és az Egyedi ütemezéstípus** mező vevőre van **állítva**.
- Három cikkcsoport lett létrehozva: **ELŐTAG**, **DATAHUB** és **SPP**.
- A US-001 több számlázási ütemezést tartalmaz, ahol a cikkcsoport ELŐTAG vagy DATAHUB.
- A US-002 ütemezések több olyan számlázási ütemezéssel is rendelkezik, amelyekben a cikkcsoport előtag vagy SPP.

| Számlázási ütemezés száma | Vevő | Cikkcsoport |
|---|---|---|
| SCH001 | US-001 | ELŐTAG |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | ELŐTAG |
| SCH004 | US-002 | SPP |

A US-001 előtag cikkcsoporthoz tartozó megújítási cikket vásárol. Ez a tranzakció egy új értékesítési rendelés.

| Értékesítési rendelés # | Vevő | Fő cikk | Megújítási cikk | Megújítási cikkcsoport | Számlázási ütemezés száma |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | ELŐTAG | SCH001 |

Amikor meg történik az értékesítési rendelés számlájának feladása, a megújítási elem bekerül a vevő meglévő számlázási ütemezésébe (SCH001). Ez a számlázási ütemezés az ELŐTAG elemcsoportot használja. Az ugyanannak a cikkcsoportnak az összes újítási cikkét ugyanabban a számlázási ütemezésben veszi figyelembe a program.

**Fejléc**
 
| Számlázási ütemezés száma | Vevő | Cikkcsoport |
|---|---|---| 
| SCH001 | US-001 | ELŐTAG |

**Sor**

| Számlázási ütemezés száma | Vevő | Cikkcsoport |
|---|---|---|
| SCH001 | US-001 | D0002 |

A US-001 most olyan megújítási cikket vásárol, amely a SPP cikkcsoporthoz tartozik. Ez a tranzakció egy új értékesítési rendelés.

| Értékesítési rendelés # | Vevő | Fő cikk | Megújítási cikk | Megújítási cikkcsoport | Számlázási ütemezés száma |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

A vevői US-001 nem tartozik olyan számlázási ütemezés, amely az SPP cikkcsoportot használja. Ennek megfelelően létrejön egy új számlázási ütemezés.

**Fejléc**

| Számlázási ütemezés száma| Vevő | Cikkcsoport |
|---|---|---|
| SCH005 | US-001 | SPP |

**Sor**

| Számlázási ütemezés száma | Vevő | Cikkcsoport |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Több számlázási ütemezés ugyanannak a végfelhasználónak és vevőnek

Ehhez a példához a következő beállítások vannak érvényben:

- Az Ismétlődő szerződés számlázási paraméterei oldalon be **van** jelölve a Felosztás cikkcsoport szerint beállítás, **és az Egyedi ütemezéstípus** **mező beállítása Végfelhasználó**.**·**
- A Végfelhasználók **lapon** be van állítva a következő vevői és végfelhasználói kapcsolat.

    | Vevői számla | Végfelhasználói fiók |
    |---|---|
    | US-001 | US-221 |

Több számlázási ütemezés jön létre a vevő és a végfelhasználó kombinációjához. Mivel **a Cikkcsoport szerinti felosztás** van **kiválasztva** az Ismétlődő szerződés számlázási paraméterei lapon, több számlázási ütemezést lehet létrehozni ugyanannak a vevői és végfelhasználói kapcsolatnak.

| Számlázási ütemezés száma | Vevő | Végfelhasználói fiók | Fejléccikkcsoport |
|---|---|---|---|
| SCH005 | US-001 | US-221 | 1. IG |
| SCH006 | US-001 | US-221 | 2. IG |
| SCH007 | US-001 | US-221 | IG3 |

A Cikk beállítása **lapon** létrehozhatja a támogatási és megújítási cikkkapcsolatokat.

| Cikk kódja | Cikk-kapcsolat | Támogatási cikk | Megújítási cikk | Megújítási cikkcsoport |
|---|---|---|---|---|
| Táblázat | D001 | 27. CIKK | D007 | 1. IG |
| Táblázat | D002 | 28. CIKK | D005 | 2. IG |
| Táblázat | D003 | CIKK29 | D006 | IG3 |

Most értékesítési rendelést hoz létre az US-001 vevő számára. Az értékesítési rendelés cikkeket tartalmaz a Cikk beállítása **lapon**. Az értékesítési **rendelés** létrehozásakor nyissa meg a Támogatás és megújítás folyamatlapját, és állítsa be **a** Felhasználói fiók vége mezőt és a megújítási cikkhez szükséges egyéb adatokat.

Amikor létrejön és feladja a tranzakcióhoz tartozó számlát, különböző számlázási ütemezések jön létre a vevő/záró felhasználó és cikkcsoport kombinációhoz. Ugyanannak az értékesítési rendelésnek több sorát is hozzá lehet rendelni ugyanabba a számlázási ütemezésbe.

| Értékesítési rendelés # | Vevő | Végfelhasználói fiók | Fő cikk | Támogatási cikk | Megújítási cikk | Számlázási ütemezés száma |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | 27. CIKK | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | 28. CIKK | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | CIKK29 | D006 | SCH005 |
