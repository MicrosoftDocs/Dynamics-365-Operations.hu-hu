---
title: A termék életciklusának állapotai és tranzakciói
description: Ez a témakör bemutatja, hogy ahogy egy mérnöki termék végighalad az életciklusán, hogyan tudja szabályozni, hogy az egyes életciklus-állapotokhoz melyik tranzakciók engedélyezettek.
author: t-benebo
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1e9b8a9f25edfa654a57e0ab4071cd93c8033d85
ms.sourcegitcommit: d375ef4138e898621416754c40770d8ccca4d271
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2022
ms.locfileid: "8322744"
---
# <a name="product-lifecycle-states-and-transactions"></a>A termék életciklusának állapotai és tranzakciói

[!include [banner](../includes/banner.md)]

Ahogy egy mérnöki termék végighalad az életciklusán, fontos, hogy tudja szabályozni, hogy az egyes életciklus-állapotokhoz melyik tranzakciók engedélyezettek. Például a még nem érett állapotban lévő termékeket nem szabad értékesítési rendelésre helyezni. Alternatív megoldásként, ha egy termék eléri az életciklus vége állapotát, érdemes lehet ellenőrizni az adott termék bejövő mennyiségét.

Egy mérnöki termék esetében az életciklus-állapot módosításai a termék mérnöki verzióihoz kapcsolódnak. Ezért a termék életciklus-állapota is csatlakoztatható a mérnöki verzióihoz. Ha a termék életciklusának állapota egy mérnöki verzióhoz csatlakozik, az életciklus-állapot segítségével szabályozhatja, hogy mely tranzakciók engedélyezettek a mérnöki verzióhoz.

## <a name="create-and-manage-product-lifecycle-states"></a>Termékéletciklus-állapotok létrehozása és kezelése

A termék életciklus-állapotaival való munkavégzéshez menjen a **Mérnöki módosítások kezelése \> Beállítás \> Termékéletciklus-állapot** lehetőségre. Majd tegye a következők egyikét.

- Új életciklus-állapot létrehozásához válassza az **Új** lehetőséget a Művelet ablakon, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő életciklus-állapot szerkesztéséhez jelölje ki azt a listaablaktáblán, válassza a Művelet ablak **Szerkesztés** parancsát, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő életciklus-állapot törléséhez jelölje ki azt a listapanelen, majd válassza a **Törlés** lehetőséget a Művelet panelen.

> [!NOTE]
> A mérnöki termékek ugyanazokat a termékéletciklus-állapotokat használják, mint a szabványos (nem mérnöki) termékek. A jelen témakörben ismertetett **Termék életciklus-állapota** lapot is megnyithatja a **Termékinformáció-kezelés \> Beállítás \> Termék életciklusának állapota** részben. A termék életciklus-állapotáról további információt a műszaki és a standard termékek esetében is a [Termék életciklus-állapotának áttekintése](../pim/product-lifecycle.md) című témakörben talál.

### <a name="header"></a>Fejléc

Állítsa be a következő mezőket egy termékéletciklus-állapot fejlécében.

| Mező | Leírás |
|---|---|
| Állami | Adjon egy nevet a termékéletciklus-állapotnak. |
| Leírás | Adjon egy leírást a termékéletciklus-állapotnak. |

### <a name="general-fasttab"></a>Általános gyorslap

Az **Általános** gyorslapon állítsa be a következő mezőket.

| Mező | Leírás |
|---|---|
| Alapértelmezett, ha jogi személynek adják ki | Szabványos termékek esetén állítsa ezt a beállítást *Igen* értékre, ha ezt az életciklus-állapotot alapértelmezés szerint az összes termékre alkalmazni kell az első kiadáskor. Állítsa *Nem* értékre, ha ezt az életciklus-állapotot később manuálisan alkalmazza.<p>Ez a beállítás nem vonatkozik a mérnöki termékekre. A mérnöki termékverzió életciklus-állapota a mérnöki vállalatnál való létrehozása után a mérnöki módosítási kategóriában van megadva. Amikor a terméket kiadják egy operatív vállalatnak, a program átmásolja a termék életciklus-állapotát. Más szóval, amikor egy mérnöki terméket kiadnak egy operatív vállalatnak, ugyanolyan életciklus-állapottal rendelkezik, mint a mérnöki vállalatnál. Az életciklus-állapot felülírható az operatív vállalatnál.</p> |
| Aktív a tervezéshez | Állítsa ezt a beállítást *Igen* értékre, ha az ebben az életciklus-állapotban lévő termékeket bele szeretné foglalni az alaptervezés és az anyagjegyzékszintek számításaiba. Állítsa *Nem* értékre, az ebben az életciklus-állapotban lévő termékek kizárásához a számításokból. |

### <a name="enabled-business-processes-fasttab"></a>Engedélyezett üzleti folyamatok gyorslap

Az **Engedélyezett üzleti folyamatok** gyorslapon szabályozhatja, hogy a rendelkezésre álló üzleti folyamatok közül melyek használhatók az aktuális életciklus-állapotban lévő termékekkel. A gyorslapon felsorolt folyamatok automatikusan a következőképpen találhatók meg:

- Amikor először ment egy új életciklus-állapotot, a lap betölti a jelenleg elérhető üzleti folyamatokat.
- Ha új üzleti folyamatokat ad hozzá a rendszerhez, a művelet panel **Frissítések keresése** parancsával frissítheti az **Engedélyezett üzleti folyamatok** gyorslapon található listát egy meglévő életciklus-állapot esetében.

A következő mezők érhetők el az **Engedélyezett üzleti folyamatok** gyorslapon felsorolt minden folyamathoz.

| Mező | Leírás |
|---|---|
| Feldolgozás | Ez az írásvédett mező egy meglévő üzleti folyamat nevét mutatja. |
| Folyamat területe | Ez az írásvédett mező egy meglévő folyamatterület nevét mutatja. |
| Házirend | Válasszon az alábbi értékek közül annak szabályozásához, hogy az aktuális folyamat engedélyezve legyen-e az ilyen életciklus-állapotú termékek esetében, és ha igen, hogyan:<ul><li>**Engedélyezett** – Az üzleti folyamat engedélyezett.</li><li>**Tiltott** – A folyamat nem engedélyezett. Ha egy felhasználó ilyen életciklus-állapotú terméken próbálja használni a folyamatot, a rendszer blokkolja a kísérletet, és helyette hibaüzenetet jelenít meg. Előfordulhat például, hogy letiltja az életciklus végén járó termékek vásárlását.</li><li>**Figyelmeztetéssel engedélyezve** – A folyamat engedélyezett, de figyelmeztetés jelenik meg. Előfordulhat például, hogy egy prototípus terméket szeretne elhelyezni egy termelési rendelésre, amelyet a Kutatási és Fejlesztési részleg hoz létre. Más szervezeti egységeknek azonban tisztában kell lenniük azzal, hogy még nem termelhetik a terméket.</li></ul> |

Ha további életciklusállapot-szabályokat ad hozzá testreszabásként, ezeket a szabályokat a felhasználói felületen (UI) tekintheti meg, ha a felső ablaktáblában a **Folyamatok frissítése** lehetőséget választja. A **Folyamatok frissítése** gomb csak rendszergazdák számára érhető el.

## <a name="lifecycle-states-for-released-products-and-product-variants"></a>A kiadott termékek és termékváltozatok életciklus-állapotai

Egy olyan termék esetében, amelynek változatai (alaptermék és változatai) vannak, a termék (alaptermék) életciklus-állapottal rendelkezik, és mindegyik változat eltérő életciklus-állapotú lehet.

Bizonyos folyamatok esetében, ha a változat vagy a termék blokkolva van, akkor a folyamat is blokkolva lesz. Pontosabban annak meghatározására, hogy egy folyamat blokkolva van-e, a rendszer a következő ellenőrzéseket hajtja végre:

- Mérnöki vezérlésű termékek esetében:
  - Ha az aktuális mérnöki verzió blokkolva van, akkor blokkolja a folyamatot.
  - Ha a változat blokkolva van, akkor blokkolja a folyamatot.
  - Ha a kiadott termék blokkolva van, akkor blokkolja a folyamatot.
- Standard termékek esetében:
  - Ha a változat blokkolva van, akkor blokkolja a folyamatot.
  - Ha a kiadott termék blokkolva van, akkor blokkolja a folyamatot.

Tegyük fel például, hogy csak egy adott termék (póló) egy változatát (pirosát) szeretné eladni, és egyelőre blokkolni szeretné az összes többi változat értékesítését. Ezt a következő beállítással valósíthatja meg:

- Rendelje hozzá a terméket egy életciklus-állapothoz, amely lehetővé teszi a folyamatot. Például rendelje hozzá a pólóterméket az *Értékesíthető* életciklus-állapothoz, amely lehetővé teszi az *Értékesítési rendelés* üzleti folyamatot.
- Rendelje hozzá az értékesíthető változatot egy életciklus-állapothoz, amely lehetővé teszi a folyamatot. Például rendelje hozzá a piros változatot is az *Értékesíthető* életciklus állapothoz.
- Az összes többi változathoz egy másik életciklus-állapotot kell hozzárendelni, ahol a folyamat blokkolva van. Például rendelje hozzá a fehér változatot (és az összes többi változatot) a *Nem értékesíthető* életciklus állapothoz, ami blokkolja az *Értékesítési rendelés* üzleti folyamatát.

## <a name="default-product-lifecycle-states"></a>A termékek életciklusának alapértelmezett állama

A műszaki verziók alapértelmezett életciklus-állapotát a műszaki kategória adja meg. Új mérnöki verzió létrehozása esetén az állam lesz az alapérték, az új termék első verziójával együtt.

Új termék vagy mérnöki termék létrehozása esetén az alapértelmezett életciklusállapotot is be lehet állítani, ha a sablonban megadhatja a termékhez rendelt kiadási irányelvből kiadott terméket.

Ebben az esetben új mérnöki termék létrehozása esetén a termék életciklusa a verziótól eltérő állapotban lehet.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
