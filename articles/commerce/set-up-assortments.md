---
title: Szortiment beállítása
description: Ez a cikk leírja, hogy mi a szortiment, és elmagyarázza, hogyan kell beállítani a szortimenteket a Dynamics 365 Commerce programban.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bbe7749e6c8293ded933611d6f1084b89223302c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790982"
---
# <a name="set-up-assortments"></a>Szortimentek beállítása

[!include [banner](includes/banner.md)]

Ez a cikk leírja, hogy mi a szortiment, és elmagyarázza, hogyan kell beállítani a szortimenteket a Dynamics 365 Commerce programban.

A választék olyan kapcsolódó termékek gyűjteménye, amelyeket egy kereskedelmi csatornához hozzárendelnek, például egy fizikai üzlethez vagy egy online áruházhoz. A kiskereskedelmi áruházban rendelkezésre álló termékek azonosítása. Szortiment termékkategóriák is tartozhat. A kijelölt kategóriához rendelt összes termék szerepel a szortimentben. A vállalatfüggő termékek és termékek meghatározott változatok szortiment is tartalmazhatnak. Szortiment beállításával rendelhet egyidejűleg több ezer terméket a kereskedelmi csatornáihoz, bármilyen kombinációban, amelyet az üzlet igényel. Tetszőleges számú termék szortimentek van szüksége, be lehet állítani. Megadhat egy vagy több szortimentet, és minden termék egy vagy több csatornához rendelhető hozzá. Például megadhatja egy szortiment, amelyek a termékek alapvető készletét tartalmazza. Az összes üzlet a szortimentet kapja. Egy másik szortiment csak nagy sporteseményekre berendezések tartalmazó majd határozza meg. A nagyobb üzletek a szortimentet kapja. A következő ábra bemutatja, hogyan rendelhetők a termékek szortimentekhez, és azok hogyan rendelhetők kereskedelmi csatornákhoz.

![Szortiment terméksorai](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Előfeltételek

Szortiment beállítása és kereskedelmi csatornához való hozzárendelése előtt, a következő feladatokat kell elvégeznie.

| Feladat                              | Leírás |
|-----------------------------------|-------------|
| Állítson be egy csatornát.          | A kereskedelmi csatornák közé tartoznak a tényleges áruházak, az online áruházak és az online piacterek. Állítson be legalább egy csatornát, és adja meg a beállításokat az üzlethez. Szortimentek azonosító, amely egy adott üzletre szállít üzletek vannak hozzárendelve. |
| Szervezeti hierarchia tervezése. | Miután beállította a kereskedelmi csatornát a szervezethez, konfigurálnia kell a szervezeti hierarchiát, amely tartalmazza a csatornák szervezeti felépítését. A szervezeti hierarchia például szortimentekhez, feltöltéshez vagy jelentéshez használható. A kereskedelmi csatornák szervezeti hierarchiához való hozzáadásával szortimenteket rendelhet üzletek csoportjához. Nem rendeli a szortiment külön-külön az egyes üzletekhez, rendel a szortiment a szervezet legfelső szintű csomópont. Ezt követően bármikor hozzá van rendelve egy új kereskedelmi csatorna egy legfelső szintű szervezeti csomóponthoz, az adott csatorna automatikusan örökli a magasabb szintű szervezeti csomóponthoz rendelt összes szortimentet a rendszerben. Csak azokhoz a csatornákhoz rendelhet hozzá szortimenteket, amelyek szerepelnek egy olyan szervezeti hierarchiában, amely hozzárendelt **Commerce szortiment** céllal rendelkezik. |
| Termékek definiálása.                  | Mielőtt egy szortimenthez termékeket adna, hozzá kell adnia azokat a Commerce szolgáltatásban. Termékek manuálisan is hozzá lehet adni, vagy a szállító importálhatja. Miután hozzáadta a termékeket, a jogi személyhez kell elengedése. Csak a jogi személy számára kiadott termékek bocsáthatók rendelkezésre az Ön csatornái számára. Termékek, amelyek még nem még nincs kiadva jogi személy egy szortiment lehet hozzáadni, és a szortiment jóvá kell hagyni. Ugyanakkor amíg a termékek egy jogi személy számára vannak kibocsátva, nem bocsáthatók rendelkezésre a csatornák számára. |
| Kategóriahierarchia beállítása.      | A kereskedelmi termékek létrehozásakor csoportosíthatja és kategorizálhatja őket a kategóriahierarchia funkcióval. Létrehozhat egy alapvető hierarchiát a csoportosításra, és az összes terméket kategorizálhatja, amelyeket a csatornákon keresztül terjeszt. Létrehozhat külön, kiegészítő Kategóriahierarchiák vagy a csoport a termékek kategorizálása például előléptetés vagy szortimentek különleges célra is. Kategóriahierarchiák használatával egy adott kategóriára szereplő összes termék rendelhet egy szortiment. E terméket ad hozzá a kategóriát, amely a szortiment része automatikusan szerepelnek a készletben található. Ezt követően, amikor legközelebb a kereskedelmi szortiment ütemezés fut, ezek a termékek elérhetővé válnak azon csatornák számára, amelyekhez a szortiment hozzá van rendelve. |

## <a name="setting-up-an-assortment"></a>Szortiment beállítása

Miután befejezte a előfeltételeket, hozzon létre egy szortimentet, és rendelje hozzá a csatornáihoz. Egy online üzlet beállításához a következő feladatokat kell elvégeznie.

1. Új támogatás létrehozása vagy meglévő rekord másolása ehhez.
2. Válassza ki a csatornákat vagy azon legfelső szintű csatornacsoportokat, amelyekre a szortiment vonatkozik.
3. A szortiment termékkategóriák, az egyes termékek vagy termékváltozatok hozzáadása. Egy adott kategóriára az összes termék is felvehet, vagy egy kiválasztott termék kizárhatja a kategóriából, amely a szortiment szerepel.
4. Közzéteszi a szortimentet. Szortiment közzétételekor automatikusan elindul a szortimentek ütemezése. Ez a folyamat hoz létre a termékek listája. A folyamat befejezése után a termékek elérhetővé válnak azon csatornák számára, amelyhez a termékszortiment hozzá van rendelve. Ha a módosítások egy közzétett szortimentet érintenek, vagy olyan csatornákat, amelyekhez a szortiment hozzá van rendelve, akkor a szortimentet frissíteni kell. A szortiment módosításkor történő frissítése érdekében futtathatja a szortimentütemezőt kötegelt feladatként.


[!INCLUDE[footer-include](../includes/footer-banner.md)]