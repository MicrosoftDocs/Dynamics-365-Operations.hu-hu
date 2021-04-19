---
title: Terméktulajdonosok
description: Ez a témakör a terméktulajdonosokkal kapcsolatban tartalmaz tájékoztatást. A terméktulajdonos olyan felhasználók csoportja, akik bizonyos termékekért felelősek. Csak a csoport tagjai adhatják ki ezeket a termékeket. A terméktulajdonos használható a jóváhagyási munkafolyamatban is.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 679712b2397f220e263da3df07ecd03c99bebf3f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842032"
---
# <a name="product-owners"></a>Terméktulajdonosok

[!include [banner](../includes/banner.md)]

A terméktulajdonos olyan felhasználók csoportja, akik bizonyos termékekért felelősek. Ha egy terméktulajdonos egy termékhez van hozzárendelve, akkor csak a csoport tagjai adhatják ki a terméket. A terméktulajdonos használható a jóváhagyási munkafolyamatban is a mérnöki változáskezelésben.

A terméktulajdonosok globális beállítások. Ennélfogva valamennyi jogi személy számára elérhetők.

## <a name="create-a-product-owner-group"></a>Terméktulajdonos csoport létrehozása

A következő lépések végrehajtásával létrehozhatja a terméktulajdonos csoportját, és tagokat adhat hozzá.

1. Lépjen a **Mérnöki változtatások kezelése – \> Beállítás \> Terméktulajdonosok** lehetőségre.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **terméktulajdonos** mezőbe írja a csoport nevét.
4. A **Név** mezőbe írja be a csoport rövid leírását.
5. A **Tagok** gyorslapon adja meg azokat a dolgozókat, akik tagjai a csoportnak.

## <a name="assign-a-product-owner-to-a-product"></a>Terméktulajdonos hozzárendelése termékhez

A terméktulajdonos hozzárendeléséhez egy termékhez, kövesse az alábbi lépéseket.

1. Nyissa meg a megfelelő termék vagy alaptermék **Termékadatok** oldalát.
1. Az **Általános** gyorslapon állítsa a **Terméktulajdonos** mezőt a megfelelő terméktulajdonosi csoport nevére.

Noha a terméktulajdonos egy termékhez van hozzárendelve, csak a terméktulajdonosi csoport tagjai módosíthatják a **Terméktulajdonos** beállítását.

A terméktulajdonos a **Kiadott termékek** oldalon is látható.

## <a name="product-owners-and-product-releases"></a>A termék tulajdonosai és a termék kiadásai

Az adott terméket csak a termék terméktulajdonosi csoportjához tartozó felhasználók adhatják ki. Azonban van egy kivétel, amikor a termék alárendelt elem, és a fölérendelt elemet a fölérendelt elem tulajdonosa adja ki. Más szóval, ha a termék egy másik termék anyagjegyzékének része, a rendszer nem ellenőrzi az anyagjegyzékben szereplő minden egyes cikk terméktulajdonosát. Csak a fölérendelt cikk terméktulajdonosát ellenőrzi.

Az X termék például a *Design kabinetek* terméktulajdonosi csoportjához vannak hozzárendelve. Az X termék az Y termék AJ része is, amely a *Design hangszórók* terméktulajdonosi csoportjához van hozzárendelve. Ha egy felhasználó a *Design hangszórók* terméktulajdonosi csoporttól kiadja az Y terméket és annak anyagjegyzékét, akkor az X termék az Y termékkel együtt fog megjelenni.

## <a name="product-owners-and-approvals"></a>Terméktulajdonosok és jóváhagyások

Mivel a terméktulajdonosok tudják, hogy az egyes mérnöki módosítások előnyösek-e termékeik számára, gyakran érdemes ezeket belefoglalni a mérnöki változáskezelés modul jóváhagyási folyamatának részeként. Ezt a módszert úgy hajthatja végre, hogy a termék tulajdonosait a mérnöki változtatások kezeléséhez használt munkafolyamatokban résztvevő szolgáltatókként állítja be. A rendszer ezután a munkafolyamatokban hozzárendeli a jóváhagyási feladatokat a mérnöki módosítási kérelmekben és a mérnöki módosítási rendelésekben szereplő termékek alapján. További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]