---
title: Szolgáltatásiobjektum-kapcsolat létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet szolgáltatásiobjektum-kapcsolatokat létrehozni egy szolgáltatási szerződéshez és egy szervizrendeléshez.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4d9424b5678a6f37d46203e5d4e359b020fda7a
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016970"
---
# <a name="create-service-object-relations"></a>Szolgáltatásiobjektum-kapcsolat létrehozása 

[!include [banner](../includes/banner.md)]


Ez a témakör azt ismerteti, hogyan lehet szolgáltatásiobjektum-kapcsolatokat létrehozni egy szolgáltatási szerződéshez és egy szervizrendeléshez. Egy szolgáltatásitárgy-kapcsolat létrehozásakor a szolgáltatási tárgyat egy szolgáltatási szerződéshez vagy egy szervizrendeléshez társítja. Ha egy vevő szolgáltatást igényel egy olyan cikkhez, ami egy szolgáltatási tárgy, a szolgáltatási tárgyat kiválaszthatja a szolgáltatásitárgy-kapcsolatok listájáról.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>Hozzon létre szolgáltatásitárgy-kapcsolatot egy szolgáltatási szerződéshez

Kövesse az alábbi lépéseket egy szolgáltatási szerződéshez tartozó szolgáltatásitárgy-kapcsolat létrehozásához:

1.  Kattintson a **Szolgáltatáskezelés** \> **szolgáltatási szerződések szolgáltatási** \> **szerződései hivatkozásra**.

2.  A **Szolgáltatási szerződések** listából válasszon ki egy létező szolgáltatási szerződést, vagy kattintson az **Új** lehetőségre egy új szolgáltatási szerződés létrehozásához.

3.  A **Műveleti ablaktáblán**, a **Szolgáltatási szerződések** képernyőn, a **Szolgáltatási szerződés** fülön, a **Kapcsolatok** csoportban kattintson a **Szolgáltatási tárgyak** lehetőségre.

4.  Válassza ki a szolgáltatási megállapodáshoz tartozó szolgáltatási tárgyat a **Szolgáltatási tárgyak** képernyőn található **Új** parancsra kattintva.

5.  Ha csatolni szeretne egy anyagjegyzék-sablont a szolgáltatási szerződéshez, kattintson a **Funkciók** menüpontra, és kattintson a **Sablonanyagjegyzék csatolása** lehetőségre. A **Sablon AJ kiválasztása** ablakban található **Sablon AJ** mezőben válassza ki a megfelelő sablont. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>Hozzon létre szolgáltatásitárgy-kapcsolatot egy szervizrendeléshez

Kövesse az alábbi lépéseket egy szervizrendeléshez tartozó szolgáltatásitárgy-kapcsolat létrehozásához:

1.  Kattintson a **Szolgáltatáskezelés szervizrendelések** \> **szervizrendelések** \> **lehetőségre**.

2.  Válasszon ki egy meglévő szervizrendelést a **Szervizrendelések** listáról, vagy hozzon létre egy új szervizrendelést.

3.  A **Műveleti ablaktáblán**, a **Szervizrendelések** képernyőn, a **Szervizrendelés** fülön, a **Kapcsolatok** csoportban kattintson a **Szolgáltatási tárgyak** lehetőségre.

4.  Válassza ki a szervizrendeléshez tartozó szolgáltatási tárgyat a **Szolgáltatási tárgyak** képernyőn található **Új** parancsra kattintva.

5.  Ha csatolni szeretne egy AJ-sablont a szolgáltatási szerződéshez, kattintson a **Funkciók** menüpontra, és kattintson a **Sablonanyagjegyzék csatolása** lehetőségre. A **Sablon AJ kiválasztása** ablakban található **Sablon AJ** mezőben válassza ki a megfelelő sablont. 


## <a name="see-also"></a>Lásd még

[Szolgáltatási tárgyak áttekintése](service-objects.md)

[A szolgáltatás tárgyának kapcsolatai](service-object-relations.md)

[Sablonanyagjegyzékek](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]