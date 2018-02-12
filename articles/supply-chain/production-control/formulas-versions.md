---
title: "Receptúrák és receptúraverziók"
description: "Ez a témakör receptúrákkal és receptúraverziókkal kapcsolatban tartalmaz tájékoztatást. A receptúra határozza meg az anyagokat, az összetevőket és egy adott folyamat eredményeit a folyamatszerű gyártás során. Receptúrák segítségével tervezhet és állíthat elő termékeket a folyamatszerű gyártásban."
author: cvocph
manager: AnnBe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4475695b1a00213ab7e3b5060fd38cc71883d2bd
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="formulas-and-formula-versions"></a>Receptúrák és receptúraverziók

[!include[banner](../includes/banner.md)]

A receptúra határozza meg az anyagokat, az összetevőket és egy adott folyamat eredményeit a folyamatszerű gyártás során. A megfelelő útvonallal együtt a receptúra a teljes folyamatot meghatározza a folyamatszerű gyártásban. Receptúrák segítségével tervezhet és állíthat elő termékeket a folyamatszerű gyártásban.

A receptúra az összetevőkből és a mennyiségekből áll, amelyek a receptúrás cikk adott mennyiségének létrehozásához szükségesek. Az elvégzett feladattól függően a receptúra funkció a Készlet- és raktárkezelésből vagy a Termékinformációk kezeléséből érhető el.

## <a name="formulas-and-formula-lines"></a>Receptúrák és receptúrasorok
A receptúra egy vagy több receptúrasorból áll, amelyek azonosítják a receptúrát alkotó összetevőket vagy elemeket. A receptúrasor anyagjegyzék- (AJ) cikkeket, receptúrás cikkeket, tényleges súlyú cikkeket, beszerzett cikkeket, társtermékeket vagy melléktermékeket is tartalmazhat. Mivel több cikk több termékben is használatos, a cikkek cikk több receptúrában is használhatók.

A receptúra egyik példája csokoládélapka-süti receptúrája. A receptúra összetevői, például a liszt, cukor, tojás, vaj és csokoládélapka többsorosak. A csokoládélapka-süti receptúrája valószínűleg más receptúréjban us használt összetevőket tartalmaz. Csokoládélapka-sütik készítése során létrejöhetnek maradékok, például morzsalékok, illetve egyes sütik túlsülhetnek vagy nyersek maradhatnak. Ezek a cikkek beállíthatók társtermékekként vagy melléktermékekként a termelési műveletektől függően.

Receptúrasor létrehozásakor a sortípus segítségével adható meg, hogy a rendszer hogyan kezelje a sort az alaptervezés futtatása és kötegrendelések előállítása során. Minden sortípus eltérő eredményt ad. A következő táblázat leírja a sortípusokat, amelyekből választani lehet. 

| Sor típusa     | Leírás  |
|---------------|--------------|
| Tétel          | Válassza a **Cikk** típust, amikor a cikk készletből kiadott nyersanyag vagy félkész áru, illetve amikor a cikk szolgáltatás. |
| Látszólagos       | Válassza a **Látszólagos** típust, amikor a receptúrasorokban szereplő alacsonyabb szintű receptúrás cikkeket akarja bontani. Ha a kötegrendelés becslését végzi, és a receptúrás cikkek bontva vannak, az sszetevő cikkek receptúrasorokként jelennek meg a kötegrendelésen. Ezenkívül a megfelelő útvonalak hozzáadódnak a termelési útvonalhoz. A receptúrás cikkek alábontása az aktuális konfiguráció használatával történik. A **Látszólagos** sortípus használata esetén kezelhetők a különböző receptúraszinteken megjelenő termelési és mérési konfigurációk. Ha egy termékhez a **Látszólagos** lehetőséget választja a **Mérnök** gyorslapon a **Kiadott termék részletei** oldalon, és ezután ezt a terméket felhasználja a receptúrában, a receptúrasor sortípusa **Látszólagos** értékre változik. A **Látszólagos** nem választható ki tényleges súllyal rendelkező cikkekhez, sem olyan cikkekhez, amelyeknél a termelés típusa **Társtermék**, **Melléktermék** vagy **Tervezési cikk**. |
| Rögzített készletek | A receptúrasorban található összetevőhöz kötegrendelés, termelési rendelés, kanban, átmozgatási rendelés vagy beszerzési rendelés létrehozásához válassza a **Rögzített készletek** elemet. A kapcsolódó rendelés meghatározása az alapértelmezett rendelési beállítások és az összetevő termelési típusa alapján történik, és a kötegrendelés becslésekor jön létre. A szükséges összetevőmennyiségeket a program automatikusan lefoglalja a kötegrendeléshez. |
| Szállító        | Válassza a **Szállító** lehetőséget, ha a termelési folyamat alvállalkozót használ, és az alvállalkozóhoz résztermelést vagy beszerzési rendelést szeretne létrehozni. Az alvállalkozó által végzett szolgáltatást vagy munkát receptúrás cikk vagy szolgáltatási tétel formájában kell létrehozni. Az elem a szülőcikkhez receptúrasorként csatolható. Az útvonalnak tartalmaznia kell egy az alvállalkozó műveleti erőforrásához hozzárendelt műveletet. A művelet a receptúrasorhoz a **Műveletszám** használatával kapcsolódik. mezőben történik). |

## <a name="formula-versions"></a>Receptúraverziók
Új receptúra létrehozása esetén egy receptúraverziót kell létrehoznia, mielőtt hozzáadná a receptúra-sortételeket és ezek konkrét jellemzőit. Minden receptúrának legalább egy verzióval kell rendelkeznie. A **Jóváhagyva** gomb a receptúraverzióban csak azt követően válik elérhetővé, hogy a verzió rekordjának mentése sikeresen megtörtént. Minden egyes receptúraverzió-rekordhoz tartozik egy vagy több társ- és melléktermék, amelyek a végtermék előállítása során állhatnak elő. Számos termék állhat azonos összetevőkből különböző kötegméretben, többszörösen vagy különböző hozamok segítségével. Szükség szerint tetszőleges számú receptúraverziót létrehozhat.

Több aktív receptúraverzió kezeléséhez használhat érvényes dátumtartományokat vagy „kezdő” mennyiségmezőket. Több aktív receptúraverzió csak akkor létezhet, ha a dátumtartomány és a „kezdő” mennyiség nem fedik át egymást.

Ellentétben az anyagjegyzékekkel, ha ahol egy anyagjegyzék gyakran sok anyagjegyzék-verzióval van társítva, receptúránként rendszerint csak egy receptúraverzió létezik. Ne feledje, hogy csak egy receptúraverzió aktiválható a fedezeti dimenziókhoz és a mennyiséghez egy adott termék esetén. Azonban sok receptúraverzió létezhet egyéb okból, és manuálisan kiválaszthatja őket kötegrendelés létrehozásakor.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Receptúrák és receptúraverziók jóváhagyása és aktiválása
A receptúrákat és receptúraverziókat jóvá kell hagyni a tervezési és termelési felhasználhatóságuk előtt. A receptúrákat általában aktiválni kell a használatuk előtt. Termelés során választhat olyan receptúraverziót, amely jóvá van hagyva, de nincs aktiválva.

A receptúra vagy receptúraverzió biztonsága érdekében be lehet állítani a **Szerkesztés zárolása** és a **Jóváhagyás eltávolításának zárolása** paramétereket a **Gyártásvezérlési paraméterek** lapon.

Ha bejelöli a **Szerkesztés zárolása** lehetőséget, és a képlet jóvá van hagyva, a Receptúrasorok mezői nem törölhetők és nem szerkeszthetők. Azonban ha törli a receptúra jóváhagyását, akkor törölheti és módosíthatja a receptúrasorokat. Létrehozhat új receptúrákat és az új receptúraverziókat is.

Ha bejelöli a **Jóváhagyás eltávolításának zárolása** lehetőséget, a jóváhagyott receptúra vagy receptúraverzió jóváhagyása nem távolítható el. Azonban új receptúrák és új receptúraverziók létrehozhatók, és eltávolíthatja a receptúraverzió aktiválását.

Az elektronikus aláírási funkciók használatával további vezérlési szintek is hozzáadhatók. Ha egy felhasználó úgy van beállítva, hogy a receptúra jóváhagyásához elektronikus aláírás szükséges, egy **Aláírás** lap jelenik meg a receptúra aktiválásakor. A felhasználónak engedéllyel kell rendelkeznie az elektronikus aláíráshoz, és a tanúsítványt sikeresen érvényesíteni kell a módosítás alkalmazása előtt. Ha az aláírást nem lehet hitelesíteni, a jóváhagyást vagy a jóváhagyás eltávolítását a rendszer megtagadja, és a jóváhagyást vagy a jóváhagyás eltávolítását kezdeményező módosítás visszakerül az eredeti állapotába.

## <a name="use-the-scalable-feature"></a>A skálázható funkció használata
A skálázható funkció akkor használható, csak ha a receptúrában az összes cikkösszetevő **Változó felhasználás** értékre van állítva. A szolgáltatás nem érhető el, ha a cikkösszetevők **Rögzített felhasználás** vagy **Fokozatos felhasználás** értékre vannak állítva. A skálázható funkció használata esetén a receptúra összetevőin végzett módosítások a többi kiválasztott összetevő mennyiségét is módosítják. A receptúra mérete is módosul. Hasonlóképpen ha módosítja a receptúra méretét, az összes skálázható összetevő mennyisége is módosul. A funkció célja kifejezetten a receptúra létrehozása és karbantartása. Nem jelenti azt, hogy az összetevő mennyiségét a program felfelé vagy lefelé skálázza kötegrendelésnél.

## <a name="use-step-consumption"></a>Fokozatos felhasználás felhasználása
A fokozatos felhasználással nem kell az összetevőknél mennyiséget megadni a **Receptúrasor** lapon. A fokozatos felhasználás ehelyett úgy van beállítva, hogy van egy **Kezdő sorozat** értéke és egy **Mennyiség** értéke. A rendszer a Fokozatos felhasználás sorozatonként rekordból azt az adatot választja ki, amely megfelel a kötegrendelés mennyiségének. A fokozatos felhasználás akkor hasznos, ha a felhasználási ráta nem lineáris a köterrendelés méretéhez képest, és csak konkrét mennyiségi küszöbérték elérése esetén növeli a követelményt. A funkció engedélyezéséhez új receptúrához a **Felhasználás számítása** csoportban módosítsa az érintett összetevőnél a receptúra beállítását **Normál** értékről **Lépés** értékre. A felhasználási módszer a **Beállítás** lapon adható meg a **Receptúrasor** oldalon.

