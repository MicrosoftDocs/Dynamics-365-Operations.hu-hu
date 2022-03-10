---
title: Szervizrendelések automatikus létrehozása
description: A szervizrendelések a szolgáltatási szerződések alapján hozhatók létre a szolgáltatási szerződés érvényességi időtartamán belül.
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
ms.openlocfilehash: 1acf4620556fe7ec5ae40f0a98b0a23602e2524a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565137"
---
# <a name="automatically-create-service-orders"></a>Szervizrendelések automatikus létrehozása 

[!include [banner](../includes/banner.md)]


A szervizrendelések a szolgáltatási szerződések alapján hozhatók létre a szolgáltatási szerződés érvényességi időtartamán belül.

A szolgáltatási szerződésből előállított szervizrendelések a szolgáltatási szerződéshez vannak csatolva.

A szervizrendelések a következő beállításokból generálhatók automatikusan:

  - A szolgáltatási szerződés intervalluma, amely a szolgáltatási szerződés soraiban állítható be. A szolgáltatási szerződés intervalluma a szervizrendelés-sorok létrehozásának gyakoriságát jelzi. További információkkal kapcsolatban lásd: [Szolgáltatási intervallumok](service-intervals.md).

  - A szervizintervallumot meghatározó időszak, amely a **Szervizrendelések létrehozása** képernyő **Kezdő dátum** és **Befejezési dátum** mezőjében van megadva. További információkkal kapcsolatban lásd: [Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md).

  - A **Szervizrendelések kombinálása** beállítás a szolgáltatási szerződés fejlécében. Ez az opció azt határozza meg, hogy a szolgáltatási szerződés alapján létrehozott szervizrendelési sorok kombinálják-e a szervizrendeléseket a következőknek megfelelően: munkavállaló, szolgáltatási feladat, szolgáltatási tárgy vagy szolgáltatási szerződés. További információkkal kapcsolatban lásd: [Szervizrendelések kombinálása](combine-service-orders.md).

  - Az **Időablak** beállítás a szolgáltatási szerződési soron. Az időablak meghatározza, hogy milyen távol kerülhetnek a szervizrendeléssorok a számított dátumukhoz képest. További információkkal kapcsolatban lásd: [Időablakok](time-windows.md).


> [!NOTE]
> <P>Ha a szervizrendelés számára megadott nap nincs megnyitva a naptárban, amelyet a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyőn kiválasztott, akkor egy üzenetet kap, amely jelzi a dátumok ütközését. Az üzenetet nyugodtan figyelmen kívül hagyhatja; a szervizrendelés akkor is létrejön, ha a nap le van zárva a naptárban.</P>

## <a name="example-1"></a>1. példa

A szolgáltatási szerződés 2012. január 1-től 2012. december 31-ig tart. Ha a **Szervizrendelések létrehozása** képernyőn létrehozott szolgáltatási időszak 2012. november 1-től 2013 február 1-ig tart, a szervizrendelések 2012. november 1-től 2012. december 31-ig jönnek létre.

## <a name="example-2"></a>2. példa

A szolgáltatási szerződés 2012. január 1-től 2012. december 31-ig tart. A szolgáltatási szerződéshez két szolgáltatásiszerződés-sor kapcsolódik. Az első szolgáltatásiszerződés-sor kezdési dátuma 2012. január 2. és a záró dátuma 2012. március 1. A második szolgáltatásiszerződés-sor kezdési dátuma 2012. április 1. és a záró dátuma 2012. december 31. Megadhatja az időszakot a **Szervizrendelések létrehozása** képernyőn, amely 2012. október 1-től 2012. december 31-ig tart. Ennek megfelelően a szervizrendelések csak a második szolgáltatásiszerződés-sorhoz jönnek létre, mert az első szolgáltatásiszerződés-sor kezdési és a befejezési dátuma a szervizrendeléshez megadott időszak előtt van.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]