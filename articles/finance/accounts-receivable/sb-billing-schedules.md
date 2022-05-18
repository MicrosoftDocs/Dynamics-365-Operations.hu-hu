---
title: Számlázási ütemezések létrehozása
description: Ez a témakör bemutatja a számlázási ütemezések létrehozásához, törléséhez és szerkesztéséhez szükséges beállításokat.
author: JodiChristiansen
ms.date: 02/09/2022
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
ms.openlocfilehash: ed31dd96b0115610cfb74aed69f1acc1055bfe56
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690445"
---
# <a name="create-billing-schedules"></a>Számlázási ütemezések létrehozása

[!include [banner](../includes/banner.md)]

A Számlázási **ütemezés** lapon lehet számlázási ütemezéseket létrehozni, törölni vagy szerkeszteni. A számlázási ütemezések listáját is áttekintheti. Számlázási ütemezés létrehozásakor annak alapértelmezett értékeit a társított számlázási csoport határozza meg. További információk az Ismétlődő szerződés számlázási paraméterei **oldalon vannak beállítva**.

## <a name="create-a-billing-schedule"></a>Számlázási ütemezés létrehozása

Számlázási ütemezés létrehozásához kövesse az alábbi lépéseket.

1. A Számlázás **ütemezése** lapon válassza az Új **lehetőséget**.
2. A Számlázási **ütemezés létrehozása** párbeszédpanel **Számlázási** ütemezés csoport mezőjében válasszon ki egy számlázási ütemezési csoportot.
3. A Vevőszámla **mezőben** válasszon ki egy vevői számlát.
4. A Kezdő **dátum mezőben** válassza ki a kezdő dátumot, **majd** az Időszakok száma mezőbe írja be az időszakok számát. A **Záró dátum** mező a beírott időszakok száma alapján frissül. Ha frissíti a Számlázás **záró dátuma mezőt**, **·** **az Időszakok száma mezőben a program nullára (0)** frissíti az értéket.
5. Válassza ki az **OK** lehetőséget.
6. A Számlázás **ütemezése** lap **Általános** lapjának **Leírás** mezőjébe írja be a számlázási ütemezés leírását.
7. A Mérföldkő **sablon mezőben** válassza ki a mérföldkő-számlázási **sablont**.

A program a **vevőtől származó** **adatokkal** frissíti az olyan mezőket, mint a Számlaszámla és a Pénznemkód.

A **számlázási gyakoriság és** a **Számlázási intervallum** mezők beállítása automatikusan történik a kiválasztott számlázási ütemezési csoport alapján.

8. Külön számlák létrehozásához állítsa a Számla külön **beállítása** Igen **beállításra**.
9. Ha automatikusan meg szeretne újítani egy számlázási ütemezést a végleges számlázási időszak után, **·** **állítsa** Az automatikus megújítás lehetőséget Igen beállításra, **majd** állítsa be a Megújításonkénti hozzáadás mezőben a Sorok adatokat.

A **Paraméterek** mezők beállítása automatikusan történik az Ismétlődő szerződés számlázási paraméterei lapon **található értékek** alapján.

10. A számlázási ütemezések összegének újraosztásához állítsa **a** Részleges időszakok át ütemezése lehetőséget Igen **beállításra**.
11. Ha a számlázási ütemezés részletsorait a hónap végi dátumhoz igazítja, **állítsa Az Igazítás a hónaphoz beállítást Igen beállításra** **.**
12. Adja meg **a** **szerződés** kezdő és záró dátumát a Szerződés kezdő és záró dátuma mezőben. Ezek a dátumok csak tájékoztatásra valók.

A **Fizetés** mezőben a vevőtől származó fizetési adatok megjelenik. Ha egy sortétel felfüggesztve van vagy el lett határodva, a fizetési adatok nem módosíthatók.

> [!NOTE]
> Amikor cikk szerint vonja össze a számlákat, **meg kell egyeznie a Fizetési feltételek**, **·** **Metódus és Számlázási ütemezés mezők értékével.** Ellenkező esetben nem lehet konszolidálni a számlákat.

13. A Cím **lapon** áttekintheti **·** **és frissítheti a Szállítási cím és a Számlázási cím mezőit.**
14. A Kapcsolattartási **adatok** lapon lehet társítani egy végfelhasználót a számlázási ütemezéshez.
15. A Kapcsolattartó **adatai mezőben** megadhatja a kapcsolattartót, az e-mail címet és az internetcímet.
16. A partner jutalékinformációinak nyomon követéséhez állítsa be **a Partnerszámla** **és partner jutalékaránya mezőket**. Ezek a mezők csak tájékoztatásra valók.
17. Az Összesen **lapon** megtekintheti a számlázási ütemezéshez kiszámított különféle végösszegeket.
18. A Hold **lapon** megtekintheti, hogy mikor történt a számlázási ütemezés a hold eltávolításakor.
19. A Felmondás **lapon** megtekintheti a számlázási ütemezésben alkalmazott vagy abból eltávolított felmondások előzményeit.
20. Válassza a **Mentés** lehetőséget.
21. A Számlázási ütemezés **sorai** gyorséta csoportban válassza a Sor **hozzáadása lehetőséget**.
22. A Cikkszám **mezőben** válassza ki a cikkszámot. Ha a hozzáadott cikk szülőcikk a bevétel felosztásában, a sorok automatikusan frissülnek a gyermekcikkekkel. Csak a szülőcikket szerkesztheti a bevétel felosztása esetén. A program ezután az összes gyermekelemet ennek megfelelően frissíti.
23. A Cikktípus **mezőben** válassza ki a cikk típusát.
24. A kezdő és záró dátumok frissítése.
25. A számlák létrehozása előtt módosítani lehet a számlázási gyakoriságot a Számlázási **gyakoriság mező frissítésével**. Miután létrejött a számlázási ütemezés első számlája, nem lehet módosítani a számlázási gyakoriságot.
26. Az Egység **mezőben** válassza ki a cikk mértékegységét.
27. Az Árképzési **módszer mezőben** válassza ki a cikk árképzési módját.

Az **Egységár mező** automatikusan be van állítva a készletből. Frissítheti azonban, ha az **árképzési módszert Flat módra módosítja**.

## <a name="remove-a-line-item"></a>Sortétel eltávolítása

A következő lépések szerint távolíthatja el a kívánt elemet a számlázási ütemezésből.

1. A Számlázás **ütemezése** lapon, az **Ütemezés száma** mezőben válassza ki a szerkeszteni kívánt számlázási ütemezés számát.
2. Válassza ki **a törölni kívánt** sort a Számlázási ütemezés sorai gyorsgombra, majd válassza az Eltávolítás **lehetőséget**.
3. Válassza a **Mentés** lehetőséget.

A témakör hátralévő része a **Számlázási** ütemezés sorai gyorsabban a sorokhoz elérhető műveleteket és részleteket írja le.

## <a name="billing-schedule-line-actions"></a>Számlázási ütemezés sorműveletei

A Számlázási ütemezés sorai **gyorsábra** gombjaival műveleteket lehet alkalmazni az egyes sorokban.

| Gomb | Leírás |
|--------|-------------|
| Sor hozzáadása | Sor hozzáadása a számlázási ütemezéshez. |
| Hozzáadás cikklistából | Ha több elemet szeretne hozzáadni egy számlázási ütemezéshez, jelölje ki őket a listából. |
| Eltávolítás | <p>A kijelölt sor eltávolítása a számlázási ütemezésből.</p><p>Bevétel felosztásának részét képezi cikkek esetén csak a szülő cikket távolíthatja el. A rendszer ezután automatikusan eltávolítja az összes társított gyermekelemet.</p> |
| Számlázási adatok megtekintése | A számlázási adatok megtekintése. |
| Felmondás | <p>A kijelölt sorok megszüntetése. Ez a gomb csak akkor érhető el, ha a kiválasztott sorok állapota **Aktív**.</p><p>A bevétel felosztásában részt adó cikkek esetén csak a szülő cikk felmondása lehet.</p> |
| Felmondás eltávolítása | <p>A felmondás eltávolítása a kijelölt sorokból. Ez a gomb csak akkor érhető el, ha a **kiválasztott sorok állapota Megszakítva**.</p><p>Bevétel felosztásának részét képezi cikkek esetén a felmondás csak a szülő cikkből távolítható el.</p> |
| Várakoztatásba helyezés | <p>Részletes információk kiválasztása a kijelölt sor feleső sorának felesőről.</p><p>Bevétel felosztásának részét képezi cikkek esetén csak a szülő cikket lehet függesni.</p> |
| Várakoztatás eltávolítása | <p>A hold eltávolítása a kijelölt sorból</p><p>Bevétel felosztásának részét képezi cikkek esetén csak a szülő cikkből lehet törölni a visszatartott tételt.</p> |
| Eszkaláció és engedmény | Ez a gomb nem érhető el olyan cikkekhez, amelyek bevételfelosztás része, **kivéve azokat a szülő cikkeket, amelyeknél a bevétel felosztása a Nulla összegű felosztási** módszert használja. |
| Halasztások | <p>Adja meg a kiválasztott sor halasztásának beállításait.</p><p>Ez a gomb nem érhető el a bevétel felosztása után szülő cikkekhez.</p> |
| Mérföldkő felosztás | <p>A kijelölt sor mérföldkőhöz tartozó felosztási információinak áttekintése és frissítése.</p><p>Ez a gomb csak akkor érhető el, ha a számlázási ütemezési sortétel mérföldkőelem.</p> |
| Támogatás és megújítás | <p>A kiválasztott sor támogatási és megújítási információinak áttekintése és frissítése.</p><p>Ez a gomb csak akkor érhető el, ha a számlázási ütemezés sortétele támogatás vagy megújítási elem.</p> |
| Dimenziók megjelenítése | A Számlázási ütemezés sorai rácsban megjelenő dimenzióoszlopok **megjelenítése vagy** elrejtése |
| Egységár számítása | <p>A cikk egységárának kiszámítása, hogy a vevő részletfizetéssel (például napi, havi, negyedéves, féléves vagy éves) részletfizetéssel fizetheti a szerződés összegét. Kiválaszthatja a szerződés árát és az ár gyakoriságát.</p><p>A változások könyvvizsgálati ellenőrzése megtekinthető: a régi szerződési ár és gyakoriság, az új szerződési ár és gyakoriság, a módosítást el végező felhasználó, valamint a módosítás dátuma és időpontja.</p> |
| Igazítás dátuma | <p>Adja meg a megújítási cikkek igazításának dátumát.</p><p>Ha cikkcsoportot választ a **Cikkcsoport** mezőben, minden cikk a számlázási ütemezésben a cikkcsoport első cikkének igazítási dátumát használja. Ha a **Cikkcsoport mező** üres, minden cikkhez megadhat egy igazítási dátumot.</p><p>Ez a gomb csak akkor érhető el, ha **a Számlázási gyakoriság** mező beállítása **Éves**.</p> |
| Számlázatlan bevétel | <p>A cikk beállítása a nemszámlázatlan bevétel funkció használatára. Ezt követően megadhatja a cikk nem számlázandó bevételi és nem számlázatlan engedményszámláit.</p><p>Ez a gomb csak akkor érhető el, ha a Cikktípus **mező beállítása Normál** **.** Ez nem érhető el meglévő számlázási ütemezések, illetve olyan számlázási ütemezéssorok esetén, amelyekhez már létrejött a számla.</p> |
| Alárendelt bevételelosztás hozzáadása | <p>Válassza ki az értékesítési rendeléshez hozzáadni kívánt gyermek cikket.</p><p>Ez a gomb csak a bevétel felosztása esetén használható szülő cikkeknél.</p> |
| Speciális árképzési beállítások | A cikk árképzési beállításainak szerkesztése. |

## <a name="billing-schedule-line-details"></a>Számlázási ütemezés sorának részletei

Ha kiválaszt egy sort **a** Számlázási ütemezés sorai gyorsábra, megtekintheti a sor részletes adatait. Ezek a részletek különböző lapokra vannak felosztva.

### <a name="general-tab"></a>Általános fül

Az Általános lapon az alábbi információk **érhetők** el.

| Mező vagy szakasz | Leírás |
|------------------|-------------|
| Használat | <p>Ez a szakasz a cikkek használatáról nyújt tájékoztatást. A következő mezőket tartalmazza:</p><ul><li>**Használati azonosító** – a mérő vagy használati cikk azonosítója.</li><li>**Leolvasási beállítás** – a használati olvasási beállítás: **olvasás vagy** **felhasználás**.</li><li>**Becsült felhasználás** – adja meg a becsült felhasználást egy olyan használati cikkhez, amely olyan időszakokat is tartalmazza, amelyekhez nem készült számla. A Számlázás **részletei** lapon áttekintheti a becsült felhasználás számlázási részleteinek sorait.</li></ul> |
| Külső hivatkozások\* | Ez a szakasz a Külső **és** **Sor** száma mezőket tartalmazza, amelyeken külső hivatkozási adatokat lehet megadni. |
| Mérföldkő | <p>Ez a szakasz a mérföldkőelemekről nyújt tájékoztatást. A Becsült befejezési **dátum mezőt** tartalmazza, amely a cikk befejezésének dátumát tartalmazza.</li></ul> |
| Szöveg | A sorhoz fűző megjegyzés. A program a vevő vagy jogi személy alapértelmezett nyelvére fordítja le a szöveget. |
| Cikkcsoport | A sorcikk cikkcsoportja. |
| Igazítás dátuma | A számlázási ütemezés igazításának dátuma. |

\* Amikor cikk szerint vonja össze a számlákat a Számla **létrehozása lapon,** a külső hivatkozási mezőknek **meg kell** egyezniük. Ha akár egy karakter is különbözik, akkor a cikkek konszolidálása nem történik meg a számlán. A Külső hivatkozás **szakasz** egyik mezőjében sem történik ellenőrzés, **és** a Sor száma mező értékének pozitív egész számnak kell lennie.

### <a name="address-tab"></a>Cím lap

A Cím lapon az alábbi **információk érhetők** el.

| Mező | Leírás |
|-------|-------------|
| Szállítási cím | <p>A sorcikk szállítási címének kiválasztása. Az alapértelmezett szállítási cím a Cím gyorsábra **elsődleges** szállítási címe.</p><p>A cím módosításakor a következő címbeállítások közül választhat:</p><ul><li>**Címek** – az aktuális vevő címének kiválasztása.</li><li>**Használatban** – válasszon ki egy címet, amely jelenleg az aktuális vevőhöz van használatban.</li><li>**Egyéb cím** – a vevőrekordok címének kiválasztása.</li></ul><p>Bevétel-felosztást felhasználó cikkek esetén csak a szülőcikk címe szerkeszthető. A gyermekelemek címe megegyezik a szülő címével, és külön nem szerkeszthető.</p> |
| Számlázási cím | <p>Válassza ki a sorcikkhez a számlázási címet. Az alapértelmezett szállítási cím a Cím gyorsábra **elsődleges** szállítási címe. A cím szükség szerint megváltoztatható az elérhető címek célja alapján:</p><ul><li>Ha egyik címnek sincs Számla a **célja**, akkor a vevőnek a céltól függetlenül az alapértelmezett számlázási cím lesz az elsődleges címe.</li><li>Ha egy vagy több címnek Számla a **célja**, akkor az alapértelmezett számlázási cím az a cím, amely legutóbb be lett állítva.</li><li>Ha egy vagy több címnek Számla a **célja**, és az egyik számlázási cím van beállítva elsődleges címként, az alapértelmezett számlázási cím az a **cím**, amely a számla célját szolgálja, és elsődleges címként van beállítva.</li><li>Bevétel-felosztást felhasználó cikkek esetén csak a szülőcikk címe szerkeszthető. A gyermekelemek címe megegyezik a szülő címével, és külön nem szerkeszthető.</li></ul> |

### <a name="product-tab"></a>Termék lap

Az alábbi információk a Termék lapon **érhetők** el.

| Mező vagy szakasz | Leírás |
|------------------|-------------|
| Tárolási dimenziók | <p>Ez a szakasz a cikk tárolási adatait mutatja be. A sorozatszám mezőt **tartalmazza**, amely a cikk sorozatszámát tartalmazza.</p><p>A sorozatszámot a rendszer a kezdeti értékesítési rendelésből másolja át a támogatási és megújítási folyamat során. A bevétel felosztását használó cikkeknél a szülőcikk sorozatszámát az összes gyermekcikkbe másolja a rendszer. A sorozatszámot akkor másolja a rendszer, **·** **·** **ha** az Ismétlődő szerződés számlázási paraméterei lapon a Sorozatszám másolása beállítás Igen beállítás van megállítva.</li></ul> |
| Termékdimenziók | A cikk termékadatok és az értékek automatikusan frissülnek a **számlázási** ütemezés sorához kiválasztott Változatszám érték alapján. |

### <a name="account-tab"></a>Számla lap

A Számla lapon az alábbi **információk érhetők** el.

| Mező | Leírás |
|-------|-------------|
| Fő számla | Az értékesítési sorban létrehozott fő számla. Az alapértelmezett érték az értékesítési rendelésből van. A mező üresen is lehet. |
| Cikk pénzügyi dimenziói | <p>A vevő- és cikkrekordon alapuló alapértelmezett pénzügyi dimenzióértékek.</p><p>Bevétel-felosztást felhasználó cikkek esetén a gyermekcikkek a vevő- és cikkrekordok pénzügyi dimenzióértékeit használják a korábban ismertetett módon. Ha frissítenie kell a gyermekelemek pénzügyi dimenzióértékét, importálhatja az adatentitást.</p> |

### <a name="renewals-tab"></a>Megújítások lap

A következő információk a Megújítások lapon **érhetők** el.

| Mező | Leírás |
|-------|-------------|
| Megújítás automatikusan | <p>Ez az érték jelzi, hogy a számlázási ütemezési sor automatikusan meg újul-e a következő számlázási időszakban:</p><ul><li>**Igen** – a számlázási ütemezési sor automatikusan meg újul a következő számlázási időszakra számla létrehozásakor.</li><li>**Nem** – a számlázási ütemezés sorát nem újítja meg automatikusan a rendszer. Manuálisan kell újítania a számlázási ütemezést.</li></ul> |
| Hozzáadandó sorok megújításonként | A számlázási ütemezés megújításához hozzáadható sorok száma |

Ezenkívül a Következő gombok érhetők el a **Megújítások** lapon.

| Gomb | Leírás |
|--------|-------------|
| Nem számlázott bevételnapló-bejegyzésének auditálása | A nemszámlázandó bevétel szolgáltatást használt cikkek minden módosításának megtekintése. |
| Megújítási időszak hozzáadása | A cikk megújítási időtartamának hozzáadása. Az új megújítási időszak kezdő dátuma az előző időszak záró dátuma utáni következő dátum. A **megújítás záró dátuma**, **a halasztás kezdő** dátuma, **a halasztás záró dátuma**, **a Cikkmennyiség** **és az Egységár** mező frissíthető. |
| Megújítási időszak módosítása | <p>Megújítási időszak módosítása Az első kifejezéshez a kezdő naplóbejegyzés létrehozása előtt módosíthatja a halasztás kezdő és záró dátumát. A következő feltételek szerint a kezdő dátum nem módosítható. Ez mindig az előző időszak vége utáni következő dátum.</p><p>Ha a módosítási időszak után létezik megújítási időszak, akkor a kifejezés dátumai nem módosíthatók. Ebben az esetben csak a **megújítási** **cikk** Mennyiség és Egységár mezői frissíthetők.</p><p>Például három feltétel létezik. <ul><li>Az első kifejezés nem módosítható, mert már elkezdődött.</li><li>Második fogalomként csak a mennyiség és az egységár módosítható.</li><li>Harmadik fogalomként a kezdő dátum kivételével minden érték módosítható. Ezenkívül az Ütemezés **sablonból** beállítással olyan halasztás-ütemezést lehet létrehozni, amely a nem kiszámlázatlan bevételi cikk sablonja alapján jött létre. Ha ez a beállítás **Igen**, válassza **ki** a halasztássablont a Sablon mezőben, és módosítsa a halasztás kezdő és záró dátumát, ahogy az szükséges. Az ezt követő megújítási feltételek ugyanazt a halasztássablont használják. A halasztássablon azonban módosítható.</p></li></ul> |

### <a name="termination-tab"></a>Felmondás lap

A Felmondás lapon az alábbi **információk érhetők** el.

| Mező | Leírás |
|-------|-------------|
| Munkaviszony megszűnésének dátuma | Az a dátum, amikor a számlázási ütemezési sor megszűnik. Az alapértelmezett érték a fejléc **Felmondási dátum** mezőjéből van beállítva. Az érték szükség szerint megváltoztatható. |
| Felmondás típusa | A felmondás típusa. Az alapértelmezett érték a fejléc **Felmondás típusa** mezőjéből van beállítva. |

### <a name="hold-tab"></a>Visszatartott lap

Bevételi és kiadási halasztások használata **esetén a Hold** lapon a halasztás dátuma látható.

### <a name="escalation-and-discount-tab"></a>Eszkaláció és engedmény lap

Az Eszkaláció és **engedmény lapon az alábbi információk érhetők** el.

| Mező | Leírás |
|-------|-------------|
| Eszkaláció | <p>Adja meg, hogy engedélyezettek-e eszkalációk a számlázási ütemezés sorában. A számlázási ütemezési sor létrehozásakor a fejlécben található eszkalációs sorokat alkalmazza a rendszer.</p><ul><li>**Igen** – a sorra eszkalációk alkalmazhatók. Ha ez a beállítás be van jelölve, **a számlázási ütemezési sorokhoz az Eszkaláció és engedmény oldalon állíthatja be az eszkalációkat**.</li><li>**Nem** – a sorra nem lehet eszkalációkat alkalmazni.</li></ul><p>Az alapértelmezett beállítás a kiválasztott számlázási ütemezéscsoporton **alapul**.</p> |

### <a name="price-changes-tab"></a>Árváltozások lap

Az Árváltozások **lapon a Normál** **·** **ár** értékről a Normál ár beállításra módosított sorok rácsa a következő oszlopokat tartalmazza:

- Dátum módosítása
- Felhasználó által megváltoztatva
- Normál ár
- Lakás ár
- Ár frissítése
