---
title: Visszárura vonatkozó számlafrissítés végrehajtása
description: A rendszernek ezek a funkciói támogatják a szervezet azon üzleti folyamatait, amelyek során ugyanaz a személy egyszerre számlázza a visszárurendeléseket és az értékesítési rendeléseket.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32a108694c11a2ebd922a71d5c82691584bbb397
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014749"
---
# <a name="perform-invoice-updates-for-returns"></a>Visszárura vonatkozó számlafrissítés végrehajtása 

[!include [banner](../includes/banner.md)]


A visszárurendelés olyan értékesítési rendeléstípus, amelynek cikkei visszárurendelésként vannak megjelölve. Emiatt a **Minden értékesítési rendelés** listaoldalt használja a rendszer a visszárurendelések számláinak létrehozásához a **Visszárurendelések** képernyő helyett. A rendszernek ezek a funkciói támogatják a szervezet azon üzleti folyamatait, amelyek során ugyanaz a személy egyszerre számlázza a visszárurendeléseket és az értékesítési rendeléseket.

Mivel a visszaküldött cikk számlája negatív összeg, ezt jóváírásnak nevezik.

Ha kötegelten végzi a számlafrissítést, akkor a **Visszárurendelés** típusú értékesítési rendelés visszárusorának **Bevételezve** állapotban kell lennie, ami azt jelzi, hogy a rendelés csomagjegyzékét frissítették.

## <a name="post-an-invoice-for-a-return-order"></a>Számla feladása egy visszárurendeléshez

1.  Kattintson a **Kinnlevőségek –** \> **Rendelések** \> **minden értékesítési rendelés lehetőségre**.

2.  Válasszon egy olyan értékesítési rendelést, amelyhez **Visszaküldött rendelés** jelenik meg a **Rendelés típusa** mezőben.

3.  A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban kattintson a **Számla** elemre.

4.  A **Paraméterek** lapon jelölje be a **Feladás** jelölőnégyzetet.

5.  Ellenőrizze a képernyőn lévő információkat, és végezze el a szükséges változtatásokat.

6.  Kattintson az **OK** gombra. A jóváírás feladásra került.

## <a name="see-also"></a>Lásd még

[Visszárura vonatkozó csomagjegyzék-frissítés](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]