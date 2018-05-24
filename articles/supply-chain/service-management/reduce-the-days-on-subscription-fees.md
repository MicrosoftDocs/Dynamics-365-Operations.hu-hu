---
title: "Előfizetési díjak napjainak csökkentése"
description: "Ha egy meglévő előfizetési díjnál csökkenteni szeretné a napok számát, létrehozhat egy új tranzakciót, amelyben eltávolítja azt az időtartamot, amelynek már nem kell szerepelnie az előfizetési intervallumban."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c70e393c125eecef85e8711d1635250f5ff408d9
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---


# <a name="reduce-the-days-on-subscription-fees"></a>Előfizetési díjak napjainak csökkentése 

[!include [banner](../includes/banner.md)]


Ha egy meglévő előfizetési díjnál csökkenteni szeretné a napok számát, létrehozhat egy új tranzakciót, amelyben eltávolítja azt az időtartamot, amelynek már nem kell szerepelnie az előfizetési intervallumban.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Előfizetési díj napjainak csökkentése

1.  Kattintson a következőkre: **Szolgáltatáskezelés**\>**Közös**\>**Szolgáltatási előfizetések**\>**Minden szolgáltatási előfizetés**. Jelölje ki a szolgáltatási előfizetést, majd a műveleti ablaktáblán kattintson az **Előfizetési díjak** elemre.

2.  Az **Előfizetés típusa** mezőben válassza ki a **Csökkentési napok** lehetőséget.

3.  A **Kezdő dátum** és a **Záró dátum** mezőkkel adja meg az előfizetéses időszakból eltávolítani kívánt előfizetési díj dátumintervallumát, majd kattintson az **OK** gombra.

A létrehozott tranzakció megtekintéséhez kattintson az **Előfizetés** képernyőn a **Díjtranzakciók** elemre.

## <a name="example"></a>Példa

Ha egy előfizetési tranzakció időszaka január 1-től január 31-ig tart, és az időtartamot 10 nappal csökkenteni szeretné, hozzon létre új tranzakciót, amelynél a csökkentési időszak január 1-től január 10-ig tart. (A csökkentési időszak ugyanúgy tarthat január 5-től január 15-ig vagy lehet bármely más tíz napos időszak.)

Továbbá ha a csökkentési időszaknál a **Kezdő dátum** értéke január 21. (31-ből 10), a **Záró dátum** értékét január 31-e utáni bármilyen dátumra beállíthatja, akkor is 10 nappal lesz kevesebb az előfizetéses tranzakció tartama.

## <a name="see-also"></a>Lásd még

[Csökkentési napok – Példa](reduction-days-example.md)

  



