---
title: "Szolgáltatásiobjektum-kapcsolat létrehozása"
description: "Ez a témakör a szolgáltatási szerződésekhez és a szervizrendelésekhez alkalmazható szolgáltatásitárgy-kapcsolatok létrehozását mutatja be."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
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
ms.openlocfilehash: c27070436139f784af690900a3f1ab108a809d03
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-object-relations"></a>Szolgáltatásiobjektum-kapcsolat létrehozása 

[!include [banner](../includes/banner.md)]


Ez a témakör a szolgáltatási szerződésekhez és a szervizrendelésekhez alkalmazható szolgáltatásitárgy-kapcsolatok létrehozását mutatja be. Egy szolgáltatásitárgy-kapcsolat létrehozásakor a szolgáltatási tárgyat egy szolgáltatási szerződéshez vagy egy szervizrendeléshez társítja. Ha egy vevő szolgáltatást igényel egy olyan cikkhez, ami egy szolgáltatási tárgy, a szolgáltatási tárgyat kiválaszthatja a szolgáltatásitárgy-kapcsolatok listájáról.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>Hozzon létre szolgáltatásitárgy-kapcsolatot egy szolgáltatási szerződéshez

Kövesse az alábbi lépéseket egy szolgáltatási szerződéshez tartozó szolgáltatásitárgy-kapcsolat létrehozásához:

1.  Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.

2.  A **Szolgáltatási szerződések** listából válasszon ki egy létező szolgáltatási szerződést, vagy kattintson az **Új** lehetőségre egy új szolgáltatási szerződés létrehozásához.

3.  A **Műveleti ablaktáblán**, a **Szolgáltatási szerződések** képernyőn, a **Szolgáltatási szerződés** fülön, a **Kapcsolatok** csoportban kattintson a **Szolgáltatási tárgyak** lehetőségre.

4.  Válassza ki a szolgáltatási megállapodáshoz tartozó szolgáltatási tárgyat a **Szolgáltatási tárgyak** képernyőn található **Új** parancsra kattintva.

5.  Ha csatolni szeretne egy anyagjegyzék-sablont a szolgáltatási szerződéshez, kattintson a **Funkciók** menüpontra, és kattintson a **Sablonanyagjegyzék csatolása** lehetőségre. A **Sablon AJ kiválasztása** ablakban található **Sablon AJ** mezőben válassza ki a megfelelő sablont. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>Hozzon létre szolgáltatásitárgy-kapcsolatot egy szervizrendeléshez

Kövesse az alábbi lépéseket egy szervizrendeléshez tartozó szolgáltatásitárgy-kapcsolat létrehozásához:

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Válasszon ki egy meglévő szervizrendelést a **Szervizrendelések** listáról, vagy hozzon létre egy új szervizrendelést.

3.  A **Műveleti ablaktáblán**, a **Szervizrendelések** képernyőn, a **Szervizrendelés** fülön, a **Kapcsolatok** csoportban kattintson a **Szolgáltatási tárgyak** lehetőségre.

4.  Válassza ki a szervizrendeléshez tartozó szolgáltatási tárgyat a **Szolgáltatási tárgyak** képernyőn található **Új** parancsra kattintva.

5.  Ha csatolni szeretne egy AJ-sablont a szolgáltatási szerződéshez, kattintson a **Funkciók** menüpontra, és kattintson a **Sablonanyagjegyzék csatolása** lehetőségre. A **Sablon AJ kiválasztása** ablakban található **Sablon AJ** mezőben válassza ki a megfelelő sablont. 


## <a name="see-also"></a>Lásd még

[A szolgáltatás tárgyai](service-objects.md)

[A szolgáltatás tárgyának kapcsolatai](service-object-relations.md)

[Sablonanyagjegyzékek](template-boms.md)

  



