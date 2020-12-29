---
title: Látszólagos cikkek
description: Ez a témakör részletesen leírja, hogyan használható a Látszólagos sortípus egy anyagjegyzék (BOM) sorainál, illetve egy képletben Dynamics 365 Supply Chain Management rendszerben.
author: ShylaThompson
manager: tfehr
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: kamaybac
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b14bebadd7088c9bbcfb6b1c5df1fe1a3c98694d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429702"
---
# <a name="phantom-items"></a>Látszólagos cikkek

[!include [banner](../includes/banner.md)]

Ez a témakör részletesen leírja, hogyan használható a Látszólagos sortípus egy anyagjegyzék (BOM) sorainál, illetve egy képletben. A következő példában (a) a H termék és F, valamint G rész anyagjegyzéke, míg (b) a H termék és F rész útvonallapja.

![H termék és F rész](media/product-H-part-F.png)


Ez az ábra egy anyagjegyzék-struktúra példáját mutatja be két szinten. A H késztermék egy gépösszszerelés termékét jelöli. A gép két részből áll: egy elektromos egységből (F), amelynek két összetevője van (A és B) és csomagolóanyagok csoportjából (G), amelynek szintén két összetevője van (C és D). Egy másik anyagot (E) is felhasználnak a gép általános összeszerelése során.

![H termék és F rész](media/product-H-part-B.png)

Az előző ábra mutatja be a H termék Műszaki anyagjegyzékét. Ez a szerkezet jó áttekintést biztosít a teljes gépösszeszerelés részeiről és összetevőiről. Azonban annak ellenére, hogy a terméktervezők valószínűleg így szeretnék látni az anyagjegyzéket, előfordulhat, hogy ez a szerkezet nem jelöli megfelelően a gép üzemben történő összeszerelését. 

Az iménti Műszaki anyagjegyzék például azt jelzi, hogy az F elektromos egység külön kerül összeszerelésre egy külön munkarendelés keretében. Azonban az üzemben előfordulhat, hogy optimálisabb lenne az elektromos egység összeszerelését a teljes gépösszeszerelés részeként értelmezni egy külön munkarendelés helyett.

Ez a Műszaki anyagjegyzék azt is jelzi, hogy a G egy külön rész. Ugyanakkor ebben a struktúrában a G rész nem fizikai részte utal, hanem csomagolóanyagok egy gyűjteményére. 

Ebből következően annak ellenére, hogy egy Műszaki anyagjegyzék rendkívül értékes egy termék tervezése és a terv karbantartása során, lehet, hogy nem a leglogikusabb a termék gyártásának végrehajtásához. Ezzel szemben a Gyártási anyagjegyzék egy termék előállítására szolgáló legjobb módszernek felel meg.

Az alábbi ábra bemutatja, hogy miként változik át az előző Műszaki anyagjegyzék egy Gyártási anyagjegyzékké. Ezen az ábrán az (a) a H termékhez tartozó anyagjegyzék, a b pedig a H termék útvonallapja.

Ebben a szerkezetben láthatja, hogy nem értelmezhetők az F és G részek, és az anyagok, amelyekből ezek a részek állnak, kiemelésre kerültek az anyagjegyzék következő szintjére. 

A Műszaki anyagjegyzék két műveletlapot is tartalmazott, ellentétben a Gyártási anyagjegyzékkel, amelynek csak egy műveletlapja van. A G részhez kapcsolt csomagolási műveletet szintén kiemelte a rendszer, és az most a H termék műveleti lapjának részévé vált. Az első művelet az elektromos egység összeszerelése. Ez a rendelés jónak tűnik, mert ezt az egységet használja a rendszer a következő műveletben, amely a gépösszeszerelés. Az utolsó művelet a csomagolási művelet, amely két csomagolóanyagot (C és D) használ fel.

Az átmenet a műszaki anyagjegyzék és a gyártási anyagjegyzék közötti a Phantom anyagjegyzék sortípuson keresztül engedélyezhető. Amint arra a „látszólagos” kifejezés is utal, az F és G részek eltűntek a két anyagjegyzéktípus közötti átmenet során. Ebben a példában a Látszólagos sortípust alkalmazza a rendszer az F és G részekre a Műszaki anyagjegyzékben. Amikor létrejön egy termelési vagy kötegrendelés, a rendszer a Műszaki anyagjegyzéket bemásolja a termelési vagy kötegrendelésbe. Ezután, a rendelés becslésekor, végbemegy az átmenet a Műszaki anyagjegyzékből a Gyártási anyagjegyzékbe, ahogyan azt az előző ábrákon láthatta. A második ábra műveleti lapjáról a C és D csomagolóanyagok meg vannak adva a művelethez. 

## <a name="multilevel-phantom-bom-structures"></a>Többszintű látszólagos anyagjegyzék-struktúrák
A Látszólagos sortípus többszintű anyagjegyzék-struktúráknál is használható, a következő ábrán látható módon. Ebben a példában (a) a G termék anyagjegyzéke, míg (b) az E és F rész, valamint a G termék útvonallapja. 

![G termék és F rész útvonallapokkal](media/product-G-route-sheet-G.png)


A következő ábrán az eredményként jelentkező gyártási anyagjegyzék és útvonallap látható, amennyiben az E és F részek anyagjegyzéksorai úgy vannak konfigurálva, hogy a sortípus a Látszólagos. Ezen az ábrán az (a) a G termékhez tartozó anyagjegyzék, a (b) pedig a G termék útvonallapja.

![G termék](media/product-G.png)


## <a name="phantom-and-route-network"></a>Látszólagos anyagjegyzék és útvonalhálózat
A látszólagos anyagjegyzékek olyan anyagjegyzéknél is használhatók, amely rendelkezik útvonalhálózattal. Az útvonalhálózatoknál egy vagy több művelet párhuzamosan futhat. A következő ábra bemutat egy példát egy olyan útvonalhálózatról, amelyet többszintű anyagjegyzékben használnak. Ebben a példában az (a) a G termék és F rész anyagjegyzéke, a (b) a G termék és F rész az útvonallapja, ahol szerepel útvonalhálózat.

![G termék és F rész](media/product-G-part-F.png)


A következő példában (a) a G termék és F rész anyagjegyzéke, míg (b) a G termék és F rész útvonallapja.

![G termék és F rész útvonallapokkal](media/product-G-part-F-with-route-sheet.png)
