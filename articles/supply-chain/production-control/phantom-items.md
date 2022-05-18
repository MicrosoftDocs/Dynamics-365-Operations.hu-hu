---
title: Látszólagos cikkek
description: Ez a témakör azt ismerteti, hogyan használható a Látszólagos sortípus az anyagjegyzék sorainál és a receptúráknál Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 05/05/2022
ms.topic: article
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-05-05
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5c9768381d35709611e4bec3d2b7793a4d896b34
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713246"
---
# <a name="phantom-items"></a>Látszólagos cikkek

[!include [banner](../includes/banner.md)]

Ez a témakör részletesen leírja, hogyan használható a Látszólagos sortípus egy anyagjegyzék (BOM) sorainál, illetve egy képletben.

Az 1., (a) ábra a H termék és az F és G termék anyagjegyzéke, és (b) a H és az F rész termék útvonallapja.

![1. ábra: Műszaki anyagjegyzék.](media/product-H-part-F.png)
*1. ábra: Műszaki anyagjegyzék*

Az 1. ábra két szinten mutatja be az anyagjegyzék-szerkezet egy példáját. A H késztermék egy gépösszszerelés termékét jelöli. A gép két részből áll: egy elektromos egységből (F), amelynek két összetevője van (A és B) és csomagolóanyagok csoportjából (G), amelynek szintén két összetevője van (C és D). Egy másik anyagot (E) is felhasználnak a gép általános összeszerelése során.

Az 1. ábra a H termék műszaki anyagjegyzékét jelöli. Ez a szerkezet jó áttekintést nyújt a teljes gépszerelés részeiről és összetevőiről. Azonban annak ellenére, hogy a terméktervezők valószínűleg így szeretnék látni az anyagjegyzéket, előfordulhat, hogy ez a szerkezet nem jelöli megfelelően a gép üzemben történő összeszerelését.

Például az 1-es számban található műszaki anyagjegyzék azt jelzi, hogy az F elektromos egység különálló alkatrészként áll össze egy külön munkarendelésen. Azonban az üzemben előfordulhat, hogy optimálisabb lenne az elektromos egység összeszerelését a teljes gépösszeszerelés részeként értelmezni egy külön munkarendelés helyett.

Ez a Műszaki anyagjegyzék azt is jelzi, hogy a G egy külön rész. Ugyanakkor ebben a struktúrában a G rész nem fizikai részte utal, hanem csomagolóanyagok egy gyűjteményére.

Ebből következően annak ellenére, hogy egy Műszaki anyagjegyzék rendkívül értékes egy termék tervezése és a terv karbantartása során, lehet, hogy nem a leglogikusabb a termék gyártásának végrehajtásához. Ezzel szemben a Gyártási anyagjegyzék egy termék előállítására szolgáló legjobb módszernek felel meg.

A 2. ábra azt mutatja be, hogyan megjelenik az előző műszaki anyagjegyzék egy gyártási anyagjegyzékbe. A 2. ábra (a) a H termék anyagjegyzéke, a b pedig a H termék útvonallapja.

![2. ábra: gyártási anyagjegyzék.](media/product-H-part-B.png)
*2. ábra: gyártási anyagjegyzék*

Ebben a szerkezetben láthatja, hogy nem értelmezhetők az F és G részek, és az anyagok, amelyekből ezek a részek állnak, kiemelésre kerültek az anyagjegyzék következő szintjére.

A Műszaki anyagjegyzék két műveletlapot is tartalmazott, ellentétben a Gyártási anyagjegyzékkel, amelynek csak egy műveletlapja van. A G részhez kapcsolt csomagolási műveletet szintén kiemelte a rendszer, és az most a H termék műveleti lapjának részévé vált. Az első művelet az elektromos egység összeszerelése. Ez a rendelés jónak tűnik, mert ezt az egységet használja a rendszer a következő műveletben, amely a gépösszeszerelés. Az utolsó művelet a csomagolási művelet, amely két csomagolóanyagot (C és D) használ fel.

Az átmenet a műszaki anyagjegyzék és a gyártási anyagjegyzék közötti a Phantom anyagjegyzék sortípuson keresztül engedélyezhető. Amint arra a „látszólagos” kifejezés is utal, az F és G részek eltűntek a két anyagjegyzéktípus közötti átmenet során. Ebben a példában a Látszólagos sortípust alkalmazza a rendszer az F és G részekre a Műszaki anyagjegyzékben. Amikor létrejön egy termelési vagy kötegrendelés, a rendszer a Műszaki anyagjegyzéket bemásolja a termelési vagy kötegrendelésbe. Ezután a rendelés becslésekor megtörténik a műszaki anyagjegyzék és a gyártási anyagjegyzék közötti váltás, amint azt a 2. ábra mutatja. A 2. ábrán található műveletlapon a C és A csomagolóanyag-adatok bevitele a művelethez.

## <a name="multilevel-phantom-bom-structures"></a>Többszintű látszólagos anyagjegyzék-struktúrák

A Látszólagos sortípus többszintű anyagjegyzék-szerkezetben használható, a 3. ábrán látható módon. A 3., (a) ábra a G termék anyagjegyzéke, és (b) az E és F alkatrészek, illetve a G termék útvonallapja.

![3. ábra: Műszaki anyagjegyzék-rész G.](media/product-G.png)
*3. ábra: Műszaki anyagjegyzék-rész G*

A 4. ábra a kapott gyártási anyagjegyzéket és útvonallapot jeleníti meg, ha az E és F alkatrészek anyagjegyzéksorai látszólagos típusúak. A 4., (a) ábra a G termék anyagjegyzéke, és (b) a G termék útvonallapja.

![4. ábra: Gyártási anyagjegyzék-rész G.](media/product-G-route-sheet-G.png)
*4. ábra: Gyártási AJ-rész G*

## <a name="phantom-and-route-network"></a>Látszólagos anyagjegyzék és útvonalhálózat

A látszólagos anyagjegyzékek olyan anyagjegyzéknél is használhatók, amely rendelkezik útvonalhálózattal. Az útvonalhálózatoknál egy vagy több művelet párhuzamosan futhat. Az 5. ábra a többszintű anyagjegyzékben használt útvonalhálózatra példát mutat. Az 5., (a) ábra a G termék és az F rész anyagjegyzéke, és (b) a G termék és az F rész útvonalhálózattal rendelkezik útvonallapja.

![5. ábra: G anyagjegyzék-rész, útvonalhálózat. ](media/product-G-part-F.png)
*5. ábra: G anyagjegyzék-rész, útvonalhálózat*

A 6. ábra (a) a G termék és az F rész anyagjegyzéke, és (b) a G termék és az F rész útvonallapja.

![6. ábra: Gyártási AJ-rész G, útvonalhálózat. ](media/product-G-part-F-with-route-sheet.png)
*6. ábra: Gyártási anyagjegyzék-rész G, útvonalhálózat*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]