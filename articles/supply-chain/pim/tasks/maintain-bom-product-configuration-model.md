---
title: Termékkonfigurációs modell anyagjegyzékének karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921317"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Termékkonfigurációs modell anyagjegyzékének karbantartása

[!include [banner](../../includes/banner.md)]

Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre. Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva készült.

## <a name="add-a-bom-line"></a>Anyagjegyzéksor hozzáadása

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a Felső kategóriás hangszóró lehetőséget ehhez az eljáráshoz.  
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Bontsa ki az **Anyagjegyzéksorok** szakaszt.
1. Válassza a **Hozzáadás** lehetőséget.
1. Írjon be egy értéket a **Név** mezőbe.
1. Írjon egy értéket a **Leírás** mezőbe.
1. Válassza a **Mentés** lehetőséget.

## <a name="add-bom-line-details"></a>Anyagjegyzéksor-részletek hozzáadása

1. Válassza ki az **Anyagjegyzéksor részletei** lehetőséget.
2. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.
    * Használhatja például az M0055 cikket.  
    * Minden anyagjegyzéksor-tulajdonság esetében ki lehet választani, hogy rögzített értéke legyen vagy egy attribútum legyen hozzárendelve.  
3. Jelölje be a **Beállít** jelölőnégyzetet.
4. Válassza ki az *Igen* lehetőséget a **Számítás** mezőben.
    * A **Számítás** tulajdonság beállítása *Igen* értékre biztosítja, hogy az Anyagjegyzéksor szereplejen a költségszámításokban.  
5. Válassza ki a **Beállítás** fület.
6. Jelölje be a **Beállít** jelölőnégyzetet.
7. Adjon meg egy számot a **Mennyiség** mezőben.
    * A mennyiség mező határozza meg, hogy az adott cikkből mennyi szereplejen az anyagjegyzékben. Ez egy nyilvánvaló jelölt lehet attribútum-hozzárendeléshez.  
8. Válassza ki a **Dimenzió** fület.
    * Győződjön meg róla, hogy aktív-e valamelyik termékdimenzió és ezért szükséges beállítani egy értéket vagy hozzárendelni egy attribútumot.  
9. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]