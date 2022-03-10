---
title: Szervizrendelések automatikus létrehozása
description: Szervizrendeléseket lehet létrehozni egy vagy több szolgáltatási szerződéshez.
author: kamaybac
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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fc63a720dd06c85be17ca61de1fe7c25f1cf3f7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571545"
---
# <a name="create-service-orders-automatically"></a>Szervizrendelések automatikus létrehozása    

[!include [banner](../includes/banner.md)]


Szervizrendeléseket lehet létrehozni egy vagy több szolgáltatási szerződéshez. A létrehozásuk után a szervizrendeléseket a **Szervizrendelések** képernyőn lehet megtekinteni.

A szervizrendelések csak a szolgáltatási szerződésben érvényes időszakra vonatkozóan jönnek létre. Ha a **Szervizrendelések létrehozása** képernyőn megadott intervallum a szolgáltatási szerződés kezdő dátuma elé vagy záró dátuma utánra esik, akkor a szervizrendelések csak az intervallum azon részéhez jönnek létre, amely a szolgáltatási szerződés időszakára esik.

Ha manuálisan vagy automatikusan szervizrendeléseket hoz létre a szolgáltatásiszerződés-sorból, akkor a szervizrendelésnek a sor kezdő és záró dátuma által meghatározott időintervallumban kell lennie, kivéve ha a sorban nincs megadva záró dátum.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Szervizrendelések automatikus létrehozása a szolgáltatási szerződésekhez

1.  Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.

2.  Válasszon ki egy szolgáltatási szerződést.

3.  Kattintson a **Szállítása** fülre, majd a **Tervezett szervizrendelések** lehetőségre.

4.  A **Kezdő dátum** és a **Záró dátum** mező értékeinek a beállításával határozza meg a szolgáltatás időszakát.

5.  Jelölje be az **Információs napló megjelenítése** jelölőnégyzetet a létrehozott szervizrendelések listájának a megjelenítése érdekében.

6.  Válassza ki a tranzakciótípusokat a **Tranzakciótípusok szerepeltetése** mezőcsoportban. A tranzakciótípusok a szolgáltatási szerződésben létrehozott soroknak felelnek meg, és minden kiválasztott tranzakciótípus több szervizrendelést hoz létre, a szolgáltatási megállapodás sorában beállított szolgáltatási intervallumtól függően.

7.  Jelölje be a **Folytonos** jelölőnégyzetet, ha minden olyan szervizrendelést létre szeretne hozni, amely hiányzik a szervizrendelések egy folytonos sorozatából.

8.  Kattintson az **OK** gombra.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Szervizrendelések automatikus létrehozása több szolgáltatási megállapodáshoz

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Rendszeres** \> **Szervizrendelések** \> **Szervizrendelések létrehozása**.

2.  Kattintson a **Kiválasztás** lehetőségre ahhoz, hogy a szervizrendelések létrehozásához használt kritériumokat adjon hozzá vagy távolítson el.

3.  Kattintson az **OK** gombra.

## <a name="see-also"></a>Lásd még

[Szervizrendelések](service-orders.md)

[Szervizrendelések automatikus létrehozása](auto-create-service-orders.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]