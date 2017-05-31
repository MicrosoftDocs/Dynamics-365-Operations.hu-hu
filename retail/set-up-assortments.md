---
title: "Szortiment beállítása"
description: "Ez a cikk leírja, hogy mi a szortiment, és elmagyarázza, hogyan kell beállítani a szortimenteket Microsoft Dynamics 365 for Operations - Retail programban."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ffa60ad4890a783c05bbde09aa00189fb30bd706
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-assortments"></a>Szortiment beállítása

[!include[banner](includes/banner.md)]


Ez a cikk leírja, hogy mi a szortiment, és elmagyarázza, hogyan kell beállítani a szortimenteket Microsoft Dynamics 365 for Operations - Retail programban.

A választék olyan kapcsolódó termékek gyűjteménye, amelyeket egy kiskereskedelmi csatornához hozzárendelnek, például egy fizikai üzlethez vagy egy online áruházhoz. A kiskereskedelmi áruházban rendelkezésre álló termékek azonosítása. Szortiment termékkategóriák is tartozhat. A kijelölt kategóriához rendelt összes termék szerepel a szortimentben. A vállalatfüggő termékek és termékek meghatározott változatok szortiment is tartalmazhatnak. Szortiment beállításával rendelhet termékek ezer a kiskereskedelmi csatornák egyidejűleg, bármilyen kombinációban az üzletben igénylő. Tetszőleges számú termék szortimentek van szüksége, be lehet állítani. Megadhat egy vagy több szortimentet, és minden termék egy vagy több szortimenthez rendelhető hozzá. Például megadhatja egy szortiment, amelyek a termékek alapvető készletét tartalmazza. Az összes üzlet a szortimentet kapja. Egy másik szortiment csak nagy sporteseményekre berendezések tartalmazó majd határozza meg. A nagyobb üzletek a szortimentet kapja. A következő ábra bemutatja, hogyan termékek rendelhetők szortimenteket a rendszerben, és hogyan kiskereskedelmi csatornák e szortimentek rendelhető. ![Szortiment terméksorai](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Előfeltételek
Szortiment beállítása, és rendelje hozzá a kiskereskedelmi csatorna, mielőtt a következő feladatokat kell elvégeznie.

| Feladat                              | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Csatornaprofil beállítása.          | A kiskereskedelmi csatornák közé tartoznak a tényleges áruházak, az online áruházak és az online piacterek. Állítsa be, ha legalább egy kiskereskedelmi csatorna kell, és adja meg a beállításokat az üzlet. Szortimentek azonosító, amely egy adott üzletre szállít üzletek vannak hozzárendelve.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Szervezeti hierarchia tervezése. | Miután beállította a kiskereskedelmi csatornák a szervezetben, konfigurálnia kell a kiskereskedelmi szervezeti hierarchia, amely tartalmazza a kiskereskedelmi csatornák szervezeti felépítését. A szervezeti hierarchia például szortimentekhez, feltöltéshez vagy jelentéshez használható. A kiskereskedelmi csatornák szervezeti hierarchia hozzáadásával szortimentek rendelhet üzletek csoportja. Nem rendeli a szortiment külön-külön az egyes üzletekhez, rendel a szortiment a szervezet legfelső szintű csomópont. Ezt követően a szervezet legfelső szintű csomópont hozzá van rendelve egy új kiskereskedelmi csatorna, amikor adott kiskereskedelmi csatorna automatikusan öröklik a magasabb szintű szervezeti csomópont rendelt minden szortimenteket a rendszerben. Csak a kiskereskedelmi csatornák hozzárendelt szervezeti hierarchiában szereplő hozzárendelheti a szortimenteket a rendszerben a **kiskereskedelmi szortiment** célját. |
| Termékek definiálása.                  | Mielőtt egy szortiment termékek adna hozzá kell adnia azokat a Microsoft Dynamics AX rendszerben. Termékek manuálisan is hozzá lehet adni, vagy a szállító importálhatja. Miután hozzáadta a termékeket, a jogi személyhez kell elengedése. Csak a jogi személynek számára kiadott termékek bocsáthatók rendelkezésre a kiskereskedelmi csatornák számára. Termékek, amelyek még nem még nincs kiadva jogi személy egy szortiment lehet hozzáadni, és a szortiment jóvá kell hagyni. Csak a jogi személynek számára kiadott termékek bocsáthatók rendelkezésre a kiskereskedelmi csatornák számára.                                                                                                                                                                                                                                                                                     |
| Kategóriahierarchia beállítása.      | A kiskereskedelmi termékek létrehozásakor csoportosíthatja, és kategorizálni őket funkciójával kategória hierarchia a Microsoft Dynamics 365 for Operations. Egy alapvető hierarchia csoportosítására és az összes termék, amelyet a kiskereskedelmi csatornák keresztül terjeszti kategorizálni lehet létrehozni. Létrehozhat külön, kiegészítő Kategóriahierarchiák vagy a csoport a termékek kategorizálása például előléptetés vagy szortimentek különleges célra is. Kategóriahierarchiák használatával egy adott kategóriára szereplő összes termék rendelhet egy szortiment. E terméket ad hozzá a kategóriát, amely a szortiment része automatikusan szerepelnek a készletben található. Ezt követően a kiskereskedelmi szortiment tervezés és ütemezés fut, amikor legközelebb ezeket a termékeket elérhetővé válnak a kiskereskedelmi csatornák, amely a szortiment hozzá van rendelve.                                            |

## <a name="setting-up-an-assortment"></a>Szortiment beállítása
Miután befejezte a Előfeltételek, hozzon létre egy szortiment, és rendelje hozzá a kiskereskedelmi csatornák. Egy online üzlet beállításához a következő feladatokat kell elvégeznie.

1.  Új támogatás létrehozása vagy meglévő rekord másolása ehhez.
2.  Válassza ki a kiskereskedelmi csatornák vagy a legfelső szintű csoportok a kiskereskedelmi csatornák, amely a szortiment vonatkozik.
3.  A szortiment termékkategóriák, az egyes termékek vagy termékváltozatok hozzáadása. Egy adott kategóriára az összes termék is felvehet, vagy egy kiválasztott termék kizárhatja a kategóriából, amely a szortiment szerepel.
4.  Közzéteszi a szortimentet. Szortiment közzétételekor automatikusan elindul a szortimentek ütemezése. Ez a folyamat hoz létre a termékek listája. Ez a folyamat befejezése után a termékek elérhetővé válnak, a kiskereskedelmi csatornák, amely a termék szortiment hozzá van rendelve. Ha módosításokat szortiment közzétett, illetve a kiskereskedelmi csatornák, amely a szortiment hozzá van rendelve, a szortiment frissíteni kell. A szortiment módosításakor frissítéséhez futtathatja a kiskereskedelmi szortiment tervezés és ütemezés kötegelt feladatként.





