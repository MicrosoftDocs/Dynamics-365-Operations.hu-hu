---
title: Kötegalapú kiigazítás
description: Ez a témakör leírja a tételalapú kiigazítás folyamatát.
author: johanhoffmann
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8c1f52239b2050425c37a8130507e689b29205a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966555"
---
# <a name="batch-balancing"></a>Kötegalapú kiigazítás

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a tételalapú kiigazítás folyamatának támogatási módját.

További tájékoztatásért tekintse meg a [tételalapú kiigazítással kapcsolatos videót](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be).

A tételalapú kiigazítás folyamatban a termelési kötegben használt összetevők mennyiségét számoljuk ki a kiválasztott termékkötegekben levő hatóanyagok koncentrációjából.

## <a name="products-that-have-an-active-ingredient"></a>Hatóanyaggal rendelkező termékek

A terméket egy hatóanyag koncentrációjával határozható meg. A termék hatóanyagát egy termékspecifikus kötegattribútummal modellezzük, amelynek van minimális értéke, maximális értéke és célszintje.

A kötegattribútum célszintje a hatóanyag becsült százalékát jeleníti meg a termékben. A minimális és maximális értékek képviselik a célszinttől elfogadott eltérést. Használható például a kötegek elfogadott tűréshatáraként a termék bevételezésénél.

Egy terméknek csak egy hatóanyaga lehet. A termék hatóanyagának meghatározásához először definiálni kell egy termékspecifikus kötegattribútumot. Az attribútum ezután a termék alapattribútumaként társítható.

A termék szintjén meg kell adni a termékköteg hatóanyagszintje rögzítésének módját is: a beszerzési bevételezési folyamat részeként, vagy a minőségi rendelési folyamat részeként.

Az alapattribútum társításához termékkel, a következőket kell beállítani:

- A terméknek kötegvezéreltnek kell lennie. Ahhoz, hogy a termék kötegvezéreltté váljon, nyomon követési dimenziócsoportot kell rendelnie a termékhez, amelynek egy aktív kötegdimenziója van.

- Az attribútumot, amely jelzi az összetevőszinteket, a termék termékspecifikus kötegattribútumaként kell megadni.

Köteg hatóanyagának tényleges értékének megkereséséhez és szerkesztéséhez:
1. Ugrás a **Készletgazdálkodás \> Lekérdezések és jelentések \> Nyomon követési dimenziók \> Cikk-követés** menüpontba.
1. Kötegszám kiválasztása a rácsból.
1. A Művelet ablakban nyissa meg a **Nézet** lapot, és válassza a **Készlet kötegattribútumai** elemet.

## <a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Összetevőtípusok és az együttműködésük a tételalapú kiigazítási folyamatban

A létrehozott receptúrasor következő összetevőtípusok egyike lehet:

- Nincs
- Aktív
- Kompenzálás
- Kitöltő neve

A szakasz többi része példákkal mutatja be, hogyan működik minden egyes összetevőtípus. A példák alapja a következő receptúra, amelynek a teljes kötegmérete 100 liter.

| Összetevő típusa | Cikkszám | Receptúrasor mennyisége | Egység |
|---|---|---|---|
| Nincs | A | 20 | Liter |
| Aktív | milliárd | 30 | Liter |
| Kompenzálás | K | 10 | Liter |
| Kitöltő neve | T | 40 | Liter |

Az alábbi táblázat áttekintést nyújt az egyes példaeredményekről.

| Cikkszám | Összetevő típusa | Becsült mennyiség | Kiegyensúlyozott mennyiség | Aktív mennyiség | Egység | Alapérték |
|---|---|---|---|---|---|---|
| A | Nincs | 20 | 20 | | liter | |
| h | Aktív | 30 | 25,71 | 9:00 | Liter | 30.00 |
| K | Kompenzálás | 10 | 14.72 | | Liter | |
| T | Kitöltő neve | 40 | 39.57 | | Liter | |

### <a name="active-ingredients"></a>Hatóanyag

Amikor egy olyan terméket, amelynek van alapattribútuma, hozzáadunk a receptúrasorhoz, ezt nevezik a receptúra *hatóanyagának*. A tételalapú kiigazítási folyamathoz a hatóanyagot tartalmazó receptúrákkal rendelkező kötegrendelések használható. A receptúrában szereplő minden egyes összetevőnél a tételalapú kiigazítási folyamat megbecsüli a termék előállításához szükséges mennyiséget. A mennyiségek becslése a kijelölt kötegbeli hatóanyag-koncentráció alapján történik.

#### <a name="active-ingredient-example"></a>Példa hatóanyagra

A B összetevő alapattribútuma X, a célszintje 30, és egy olyan receptúrában szerepel, amely a termék minden 100 literéhez a B összetevőből 30 litert igényel. Kötegrendelést hoznak létre, amelynek a kötegmérete 100 liter. A kötegrendelés elindult, és a tételalapú kiigazítási folyamat során a felhasználó kiválaszt a B összetevőből egy köteget, amelynek 35 szintű a tartalma. Mivel a tartalom szerinti 35-ös szint mértéke magasabb, mint a 30-as célszint, a B összetevő kiegyenlített mennyiségét csökkentjük azzal, hogy a tartalom szerinti érték és a köteg célszintjének hányadosát használjuk, megszorozva a becsült mennyiséggel. A kiegyenlített mennyiség számítása a következő lesz:

(30 ÷ 35) x 30 liter = 25,71 liter

### <a name="none-ingredients"></a>Összetevők nélkül

A tételalapú kiigazítás folyamat alkalmazásakor, ha az **Összetevő típusa** *Nincs*, a receptúrasor becsült mennyisége és kiegyenlített mennyisége a kötegrendelésben megegyezik.

#### <a name="none-ingredient-example"></a>Példa arra, ha a hatóanyag típusa nincs

Az A összetevő hozzá van rendelve egy *Nincs* típusú összetevőhöz, és hozzá van adva egy receptúrához egy készterméknél. A receptúra 10 litert igényel az A összetevőből a késztermék minden 100 literjéhez. Amikor egy kötegrendelés 200 litert igényel, az A összetevő becsült mennyiségét és kiegyenlített mennyiségét 20 liternek számoljuk ki.

### <a name="compensating-ingredients"></a>Kompenzációs összetevők

A kompenzációs összetevő ellentételezheti vagy kiegészítheti a hatóanyag hatását a termékben. Ezért a felhasznált kompenzációs összetevő mennyisége a termék tartalmától függ:

- **Ellentétes hatás** – Ha a hatóanyag mennyisége több a vártnál, kevesebbet kell hozzáadnia a kompenzációs összetevőből.

- **Kiegészítő hatás** – Ha a hatóanyag mennyisége kevesebb a vártnál, többet kell hozzáadnia a kompenzációs összetevőből.

Egy hatóanyag és a kiegészítő összetevő közötti kapcsolatot a **Kompenzációs elv** oldalon lehet beállítani.

Az összetevők közötti kapcsolatok beállításához tegye a következőket.

1. Válassza a **Termékinformációk kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** menüpontot.
1. Nyisson meg egy receptúrasort, majd válassza ki az **Összetevők** lehetőséget a **Kompenzációs elv** lap megnyitásához.
1. Válassza ki a kompenzációs elvet jelölő sort, és válassza ki a kompenzálandó hatóanyagot.

A kompenzációs elvben meg kell adni egy pozitív vagy negatív kompenzációs tényezőt is annak a meghatározásához, hogy mennyi a kompenzáció, és hogy ellentételező vagy kiegészítő. A pozitív tényező kiegészítő hatást, a negatív tényező ellentételező hatást jelez.

#### <a name="compensating-ingredient-example"></a>Kompenzációs összetevők példája

B összetevő egy hatóanyag, amelynek az alapattribútuma X, a célszintje 30. Egy olyan receptúra része, amely 30 litert igényel a B összetevőből a késztermék minden 100 literjéhez. A C összetevő egy kompenzációs összetevő, és az ugyanabban a receptúrában szereplő mennyisége 10. A kompenzációs elvhez beállított kompenzációs tényező 1,10. Emiatt a kompenzációs összetevő kiegyenlített mennyisége csökkentve lesz a hatóanyag kiegyenlített mennyisége és a becsült szükséges mennyiség különbségével, megszorozva 1,1-del.

A példában a *hatóanyag* esetében a szükséges hatóanyag kiegyenlített mennyisége 25,71 volt, a becsült szükséges mennyiséget pedig 30-ra számítottuk ki. Ebben az esetben a kompenzációs összetevő kiegyenlített mennyiségét a következő módon számoljuk ki:

1. Meghatározzuk a becsült és a kiegyenlített mennyiség különbségét:  
    25,71 – 30 = –4,29

1. Az eredményt ezután megszorozzuk a kompenzációs tényezővel.  
    4,29 × 1,10 = –4,72

1. A becsült kompenzációs mennyiség csökkentve lesz –4,72-dal kompenzációs kiegyenlített mennyiség meghatározásához:  
    10 – (–4,72) = 14,72

Mivel az 1,10 pozitív kompenzációs tényező, a kompenzációs elv hatása kiegészítő. Ebben az esetben a hatóanyag a vártnál hatékonyabb. Emiatt a kompenzációs összetevőből többre van szükség.

### <a name="filler-ingredients"></a>Töltőanyagok

A *töltőanyag* semleges összetevő, amelynek a használatával elérhető a késztermék kívánt kimeneti mennyisége. A töltőanyag kiigazítási mennyiségének számítása a hatóanyag és a kompenzációs összetevő eltéréseinek alapján történik, a szokásos mennyiséggel összehasonlítva.

#### <a name="filler-ingredient-example"></a>Példa töltőanyagra

Olyan termék receptúráját alkotta meg, amely A, B, C és D összetevőket tartalmazza, a receptúra mérete pedig 100 liter. A minden összetevőtípus kiegyenlített mennyiségét kiszámította a *Töltőanyag* összetevőtípus kivételével, amely egy sorban használt.
A töltőanyag kiegyenlített mennyisége 100 liter kötegméretének és az A, B és C összetevők összegének különbsége:

100 – (20 + 25,71 + 14,72) = 39,57

## <a name="the-batch-balancing-process"></a>A tételalapú kiigazítás folyamata

A tételalapú kiigazítás folyamatot a **Tételalapú kiigazítás** oldalról kell végrehajtani.
Válassza ki a **Költségkezelés \> Kötegelt rendelések** elemet, majd a **Folyamat** lapon válassza ki a **Tételalapú kiigazítás** elemet. A tételalapú kiigazítás azokhoz kötegrendelésekhez érhető el, amelyeknek az állapota **Elindítva**.

Általánosságban a tételalapú kiigazítás akkor alkalmazható a kötegrendelésekhez, ha a formulának van legalább egy formulasora, ahol az **Összetevő típusa** *Aktív*. (A szabály alóli kivételekhez lásd a „Kötegelt rendelések, amelyek nem alkalmazhatók a tételalapú kiigazításhoz” című részt, a témakör későbbi részében.)

A tételalapú kiigazítás folyamatot két alfolyamatra lehet osztani:

1. Összetevők kötegalapú kiigazítása
1. Erősítse meg és adja ki a receptúrát

### <a name="balance-batch-ingredients"></a>Összetevők kötegalapú kiigazítása

Az egyenleg tételalapú kiigazítás alfolyamatban a termelési kötegben használt összetevők mennyiségét a hatóanyagot tartalmazó kiválasztott kötetek alapján számoljuk ki. A szabály szerint a számítás csak akkor hajtható végre, ha teljes fedezete van minden összetevőnek. A kötegnek csak egy részét, amelyet a kötegrendelés állított be gyártásra, nem lehet kiigazítani.

> [!NOTE]
> Nem lehet menteni a számítást, majd befejezni a tételalapú kiigazítási folyamatot később. Ha bezárja a **Tételalapú kiigazítás** lapot, meg kell ismételnie a számítást a folyamat befejezéséhez.

### <a name="confirm-and-release-the-formula"></a>Erősítse meg és adja ki a receptúrát

Az összetevő-mennyiségek kiszámítása után megerősítheti és kiadhatja a képletet. A kiadási folyamat eltér attól függően, hogy engedélyezve vannak-e a termékeket a raktárkezelési folyamatokhoz:

- Ha egy termék engedélyezve van a raktárkezelési folyamatokhoz, a receptúrasor kiadása a raktárba a raktárkezelési folyamatok elvei szerint történik. A receptúrasor kiadása a kiegyensúlyozott mennyiségeknek megfelelő mennyiségben történik, és a hatóanyagokhoz kiválasztott konkrét kötegekhez van kiadva.

    > [!NOTE]
    > A receptúrasorokat csak a tételalapú kiigazítás folyamat részeként lehet kiadni a raktárba. Bár egyéb lehetőségek is vannak az anyagok kiadására a raktárba a termeléshez, ezek a beállítások nem használhatók a receptúrasorokhoz.

- Ha egy termék nem engedélyezett a raktárkezelési folyamatokhoz, a termelési kitárolási lista akkor jön létre a termékhez, ha megerősítette és kiadta a receptúrát.

Egyetlen receptúrában kombinálhatók azok a termékek, amely engedélyezve vannak a raktárkezelési folyamatokhoz, és a raktárkezelési folyamatokhoz nem engedélyezett termékek. Ha a kétféle típusú termék egy formulában szerepel, a raktárkezelési folyamatokhoz engedélyezett a termékek kiadása megtörténik a raktárba. A raktárkezelési folyamatokhoz nem engedélyezett termékekhez termelési kitárolási lista jön létre, ha megerősítette és kiadta a receptúrát.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Kötegelt rendelések, amelyek nem alkalmazhatók a tételalapú kiigazításhoz

Két kivétel van az alól a szabály alól, hogy a tételalapú kiigazítás akkor alkalmazható a kötegrendelésekhez, ha a formulának van legalább egy formulasora, ahol az **Összetevő típusa** *Aktív*.

1. Ha egy formula tartalmaz egy hatóanyagot egy olyan termékhez, amely a raktárkezelési folyamatokhoz engedélyezve van, de a kötegszám a hely alatt van a foglalási hierarchiában, a kötegrendelés nem alkalmazható a tételalapú kiigazításhoz.
1. Ha a receptúra mértékegysége eltér a hatóanyagkészlet mértékegységtől, akkor a kötegrendelés nem alkalmazható kötegelt kiigazításra.

Azok a kötegelt rendelések, amelyek nem alkalmazhatók a tételalapú kiigazításhoz, a kötegrendelések rendes folyamatciklusán mennek keresztül.
