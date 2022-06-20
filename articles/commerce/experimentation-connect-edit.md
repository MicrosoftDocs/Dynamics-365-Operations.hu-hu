---
title: Kísérlet csatlakoztatása és változatok szerkesztése
description: Ez a témakör azt ismerteti, hogyan Dynamics 365 Commerce lehet egy harmadik fél szolgáltatásában történő kísérlethez csatlakozni, és szerkeszteni a kísérletek variációit.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942822"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Kísérlet csatlakoztatása és változatok szerkesztése

Ez a témakör azt írja le, hogyan lehet összekapcsolni a Commerce rendszerbeli kísérleteket, és módosításokat kell eszközlni a variációkban, hogy azok igazodnak a szöveghez. 

A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön cikkekbe tartoznak.

[![Kísérletezés felhasználói interakciósorozata – Csatlakoztatás és szerkesztés.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Miután a [kísérletet beállította](experimentation-setup.md) egy harmadik fél szolgáltatásban, csatlakoztathatja a kísérletet a Dynamics 365 Commerce rendszerben, és szerkesztheti a kísérlet változatait.

## <a name="connect-your-experiment"></a>A kísérlet csatlakoztatása
A kísérlet csatlakoztatásához a **Kísérlet csatlakoztatása** varázslót indítsa el. A varázsló végigvezeti a kísérlet csatlakoztatásához szükséges lépéseken. Amikor a varázsló végére ér, a kísérlet csatlakoztatottá válik, és a változatok jönnek létre, amelyek készen állnak a szerkesztésre.

A Commerce webhelykészítőben a kísérlethez történő csatlakozás elkezdéséhez hajtsa végre az alábbi lépéseket.

1. A **Kísérlet csatlakoztatása** varázsló indításához válassza a bal oldali navigációs panel **Kísérletek** elemét, majd a **Csatlakozás** lehetőséget. Azt is megteheti, hogy a varázslót az oldal vagy a töredék szerkesztőjéből nyitja meg úgy, hogy szerkeszti, és kiválasztja a **Kísérlet csatlakoztatása** elemet a parancssorból.

    > [!NOTE]
    > - Egy oldal egyszerre csak egy kísérlethez kapcsolható. Ha egy másik kísérlethez szeretne egy oldalt csatlakoztatni, először törölje azt a kísérletet, amelyhez az oldal aktuálisan kapcsolódik.
    > - A lapokon csak egyéni elrendezéssel lehet kísérletezni. Ha a lapnak van előre beállított elrendezése, először konvertálja egyéni elrendezésre. Ehhez a lapra kell váltania, **és a parancssávon a Konvertálás** egyéni elrendezésre gombra kell választania. Az elrendezésekkel kapcsolatos további tudnivalókat lásd [: Előre beállított és egyéni elrendezések](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Ha a bal oldali navigációs **ablak Beszúrás** lapján egy kísérlethez kapcsolódik, válassza ki a kísérlet nevét a megjelenő listáról.
1. Válassza ki azt a lapot vagy részletet, amelyről le szeretné futtatni a kísérletét.
1. A varázsló utolsó lépésében válassza ki a **Változatok létrehozása és kilépés a varázslóból**. A kísérlethez változatok jönnek létre. 

> [!NOTE]
> Ha szeretné beütemezni, hogy kísérlete mikor kerüljön ki az élő webhelyre, akkor ellenőrizze, hogy a kísérlethez társítani kívánt tartalom elérhető-e egy közzétételi csoportban, még *mielőtt* csatlakoztatná a kísérletet. A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).

## <a name="edit-your-variations"></a>A változatok szerkesztése

Amikor kilép a **Connect varázslóból**, létrejönnek a változatok. Az alábbi lépések szerint szerkessze a variációkat, hogy tükrözzék a kísérlet közben ellenőriznie kell a beállításokat.

1. A szerkesztő nézetben a parancssor alatt található változatok legördülő menü segítségével szerkessze az egyes változatokat az eredeti hipotézisének megfelelően. Egy ellenőrző- vagy alapváltozatot is létre lehet hozni úgy, hogy a változatok valamelyikét változatlanul hagyja.
1. Válassza ki azt a modult, amelyen a kísérletet el szeretné végezni, aztán a kipontozást (...) és a **Kísérlet hozzáadása** elemet válassza ki.

> [!NOTE]
> Fontolja meg ellenőrzés vagy alap variáció létrehozásának az egyik variáció változatlanul hagyása mellett.

## <a name="previous-step"></a>Előző lépés
[Kísérlet beállítása](experimentation-setup.md) 


## <a name="next-step"></a>Következő lépés
[Kísérlet előnézetének megtekintése és közzététele](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
