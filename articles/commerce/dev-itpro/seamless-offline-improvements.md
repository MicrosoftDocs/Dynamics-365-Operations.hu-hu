---
title: Zökkenőmentes offline kapcsoló ajándékutalvány- és jóváírási műveletek esetén
description: Ez a témakör áttekintést nyújt azokról a fejlesztésekről, amelyek egy zökkenőmentes offline kapcsolót biztosítanak bizonyos fizetéstípusokhoz.
author: rubendel
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: a8eda003e4cd4cf0d43bb07c93bd8d68a2fb9e57
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792957"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Zökkenőmentes offline kapcsoló ajándékutalvány- és jóváírási műveletek esetén

[!include [banner](../includes/banner.md)]

Ha egy pénztári(POS) eszköz elveszíti a csatlakozását a csatorna-adatbázishoz, akkor a legtöbb pénztári művelet és a folyamatban lévő tranzakció végebe mehet, miután a pénztáros figyelmeztető üzenetet kap a kapcsolat elvesztésével kapcsolatban. Bizonyos esetekben azonban a tranzakciók olyan elemekkel rendelkeznek, amelyek a valós idejű szolgáltatáson alapulnak, és a pénztár offline állapotában nem támogatottak ezek az elemek. Ez a témakör bemutatja azokat a funkciókat, amelyek segítségével csökkenthető az elvesztett kapcsolatok hatása ezekben az esetekben.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Ajándékutalvány-tranzakciók lebonyolítása offline módban

A belső ajándékutalványok a valós idejű szolgáltatástól függenek, mivel az ajándékutalványok egyenlegét központilag kell karbantartani a Microsoft Dynamics 365 Commerce központban. A csalás vagy más szinkronizálási problémák megelőzése érdekében a program zárolja az ajándékutalványokat, mihelyt azok egy tranzakcióhoz hozzá van rendelve. A zárolási funkció biztosítja, hogy egyszerre több terminálon ne legyen felhasználható egy ajándékutalvány. A tranzakció befejeztével a rendszer automatikusan frissíti és feloldja az ajándékutalványt.

Ha azonban a pénztár elveszíti a kapcsolatot, miután egy ajándékutalványt hozzáadtak egy tranzakcióhoz, akkor az ajándékutalvány használhatatlanná válhat. Ennek a helyzetnek a megelőzése érdekében a Dynamics 365 Commerce egy olyan paraméterrel rendelkezik, amely lehetővé teszi az ajándékutalványt tartalmazó tranzakciók végrehajtását, ha a pénztár offline állapotban van. Ha ez a paraméter be van kapcsolva, az offline állapotba kényszerített ajándékutalvány-tranzakciókat az offline tranzakciókkal együtt menti el, és szinkronizálja őket a Commerce Headquarters modulba az offline tranzakciók szinkronizálásakor. A szinkronizálás feloldja az ajándékutalvány zárolását is, így egy az egy másik terminálon is felhasználható.

Ha szeretné bekapcsolni a funkciót, hogy offline állapotban is el lehessen végezni azajándékutalvány-tranzakciókat, nyissa meg a **Feladás** lapot a **Commerce Paraméterek** lapon. Az lapon keresse meg az **Ajándékutalvány** gyorslapot, és az **Ajándékutalvány-tranzakciók lebonyolításának engedélyezése offline módban** elemet állítsa **Igen** értékre.

![Offline ajándékutalvány-beállítás](../media/gift.png)

A Commerce paraméterek általában a gyorsítótárazva vannak. Ennek megfelelően a paraméter beállításának frissítése után a program a módosítást a csatornára történő szinkronizálás céljából kezdeményezi, és a módosítás akár 24 óráig is eltarthat. A módosítás azonnali érvénybe lépéséhez állítsa alaphelyzetbe a Microsoft Internet Information Services (IIS) szolgáltatást.

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Jóváírási-tranzakciók lebonyolítása offline módban

A belső ajándékutalványokhoz hasonlóan a jóváírások is központilag a Commerce Headquarters modulban vannak karbantartva. A Commerce rendelkezik egy paraméterrel, amely engedélyezi a jóváírási tranzakciók végrehajtását, amikor a pénztár offline állapotban van. Ez a paraméter ugyanúgy működik, mint az előző szakaszban említett ajándékutalvány-paraméter. Ha a paraméter be van kapcsolva, a program az offline állapotba kényszerített jóváírási tranzakciókat visszaszinkronizálja a csatorna-adatbázisba,a többi tranzakcióval együtt, amelyek végre lettek hajtva a pénztár offline állapotában.

Ha szeretné bekapcsolni a funkciót, hogy offline állapotban is el lehessen végezni a jóváírási-tranzakciókat, nyissa meg a **Feladás** lapot a **Commerce Paraméterek** lapon. Az lapon keresse meg a **Jóváírás** gyorslapot, és az **Jóváírási-tranzakciók lebonyolításának engedélyezése offline módban** elemet állítsa **Igen** értékre.

![Offline jóváírás beállítása](../media/creditmemo.png)

A Commerce paraméterek általában a gyorsítótárazva vannak. Ennek megfelelően a paraméter beállításának frissítése után a program a módosítást a csatornára történő szinkronizálás céljából kezdeményezi, és a módosítás akár 24 óráig is eltarthat. A módosítások azonnali érvénybe léptetéséhez állítsa vissza az IIS-t.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Offline pénztárfunkció (POS)](https://docs.microsoft.com/dynamics365/retail/pos-offline-functionality)
- [Online és offline pénztár (POS) műveletek](https://docs.microsoft.com/dynamics365/retail/pos-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]