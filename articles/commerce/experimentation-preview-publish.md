---
title: Kísérlet előnézetének megtekintése és közzététele
description: Ez a témakör azt mutatja be, hogyan tekinthető meg és tehető közzé egy kísérlet a Dynamics 365 Commerce rendszerből.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 32115378be00df771c6ff658da0c090446edf8b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009945"
---
# <a name="preview-and-publish-an-experiment"></a>Kísérlet előnézetének megtekintése és közzététele

Ez a témakör azt mutatja be, hogyan tekinthető meg és tehető közzé egy kísérlet a Dynamics 365 Commerce rendszerből, miután [csatlakoztatta a kísérletet és szerkesztette a változatokat](experimentation-connect-edit.md). A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön témákban szerepelnek.

[ ![Kísérletezés felhasználói interakciósorozata – Előnézet és közzététel](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>A kísérletek változatainak előnézete
Megtekintheti a változatokat, és folytathatja a szerkesztést egészen addig, amíg azok el nem nyerik a tetszőleges állapotot.

A Commerce webhelykészítőben a kísérlet változatai előnézetének megtekintéséhez hajtsa végre az alábbi lépéseket.

1. A parancssáv alatti változatok legördülő menü segítségével kiválaszthatja az előnézetben megtekinteni kívánt tartalmat. 
1. Válassza a parancssáv **Előnézet** elemét. Annak az előnézete, hogy hogyan fog festeni a tartalom a közzététel utáni megjelenítéskor.
1. A különböző változatok előnézetéhez válassza ki az adott elemet a változatok legördülő menüből, majd újból válassza ki az **Előnézet** elemet.

## <a name="publish-your-experiment"></a>A kísérlet közzététele
Ha nem használ közzétételi csoportot annak ütemezéséhez, hogy mikor lépjen életbe a kísérlet, és azonnali közzétételt szeretne végezni, akkor a **Közzététel** parancsot válassza ki a parancssorban. A program az összes, a kísérlethez tartozó változatot közzéteszi.
    
> [!IMPORTANT]
> Ha az oldal nem közzétett URL-címmel rendelkezik, akkor először közzé kell tennie az URL-címet, ellenkező esetben nem lesz látható a webhely felhasználói számára. A részletekért lásd: [Oldal mentése, előnézete és közzététele](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>A közzétételi csoportokat annak ütemezéséhez használhatja, hogy mikor lépjen életbe a kísérlet.
A webhelykészítőben létrehozott változatok közzététele egy közzétételi csoport segítségével ütemezhető be. A közzétételi csoporton belül a bal oldali navigációs ablak **Kísérletek** elemét kiválasztva egy oldalt vagy egy töredéket is csatlakoztathat a kísérlethez. Ezt úgy is megteheti, hogy kiválasztja az **Oldalak** vagy **Töredékek** elemet, és követi az útmutatót a [Kísérlet csatlakoztatása és változatok szerkesztése](experimentation-connect-edit.md) részben. A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).

Ha a kísérletekhez közzétételi csoportokat használ, akkor figyelembe kell vennie néhány fontos szempontot.
- Amikor olyan oldalt vagy töredéket ad hozzá egy közzétételi csoporthoz, amelyen egy kísérlet fut, a kísérletet eltávolítja a program a közzétételi csoportban lévő oldalról vagy töredékből.
- Az élő webhely oldalaihoz kapcsolódó kísérletek nem érhetők el a közzétételi csoportokon belüli oldalakhoz, és fordítva. Hasonlóképpen az élő webhelyen futó kísérleteket tartalmazó oldalak nem érhetők el a közzétételi csoportok egyéb kísérleteihez, és fordítva.
- Közzétételi csoport közzététele vagy ütemezése során a közzétételi csoport minden tartalmát közzéteszi a program, függetlenül attól, hogy van-e a közzétételi csoporthoz kapcsolt kísérlet.
- Mivel a közzétételi csoport azt követően is létezik, hogy élő webhelyen közzétették, a közzétételi csoport kísérletei is megmaradnak. Emiatt más kísérleteket nem lehet ugyanazzal az oldalhoz vagy töredékhez társítani. E korlátozás elkerülése érdekében törölje a megmaradó kísérletekkel rendelkező közzétételi csoportokat. Hasonlóképpen, ha törölni szeretne egy olyan kísérletet egy élő webhelyről, amely a közzétételi csoportban is szerepel, akkor először törölje azt a közzétételi csoportból.

## <a name="previous-step"></a>Előző lépés
[Kísérlet csatlakoztatása és szerkesztése](experimentation-connect-edit.md)

## <a name="next-step"></a>Következő lépés
[Kísérlet futtatása és nyomon követése](experimentation-run-monitor.md)
