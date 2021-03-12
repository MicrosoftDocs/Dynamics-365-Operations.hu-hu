---
title: A szolgáltatás tárgyainak csoportjai
description: Az objektumcsoportok jól használhatók az objektumadatok rendezésére és szűrésére a jelentéseknél és a statisztikáknál.
author: ShylaThompson
manager: tfehr
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a8e050afb44787072f78e2c971394956cb1026f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977588"
---
# <a name="service-object-groups"></a>A szolgáltatás tárgyainak csoportjai 

[!include [banner](../includes/banner.md)]

Az objektumcsoportok jól használhatók az objektumadatok rendezésére és szűrésére a jelentéseknél és a statisztikáknál. Csoportosíthatja például a tárgyakat földrajzi hely vagy típus szerint.

## <a name="group-by-geographical-location"></a>Csoportosítás földrajzi elhelyezkedés szerint

Ezzel a csoportosítással megjelenítheti, hogy hol helyezkednek el a vállalat által szervizelt különböző tárgyak. Az objektumok földrajzi elhelyezkedés szerinti csoportosítása hasznos lehet akkor is, ha például egy adott országban vagy területen kell meghatároznia, hogy milyen tárgyakat szervizeltek már.

## <a name="example"></a>Példa

Egy Belgiumban lévő ügyfél felhívja szervizközpontját, és szolgáltatási szerződést szeretne kötni az ABC tárgyra. Hozzárendelt egy tárgycsoportot a Belgium földrajzi helyhez minden olyan tárgy esetében, amelyeknek szervizelése Belgiumban történik. Ha ezt a csoportot használja szűrőként, akkor gyorsan keresést végezhet, és megtekintheti, hogy rendelkezik-e már rekorddal az ABC tárgyhoz a programban, vagy új tárgyat kell beállítania. 

## <a name="group-by-type"></a>Csoportosítás típus szerint

Ezzel a csoportosítási móddal kimutathatja, hogy milyen tárgytípusokon végez szolgáltatást a vállalat. Az objektumok típus szerinti csoportosítása hasznos lehet például akkor is, ha a meglévő hasonló objektumok alapján egy új objektumot szeretne létrehozni a programban.

## <a name="example"></a>Példa

Egy ügyfél telefonál, és be szeretne állítani egy szervizszerződést a HIJ légkondícionálóról. Nincs már rekordja ennél a készüléknél. Beállított azonban egy Légkondícionálók tárgycsoportot, és hozzárendelte ezt a csoportot az összes légkondícionálóhoz. Így gyorsan kikeresheti és azonosíthatja az összes többi légkondícionálót, és ezen tárgyak sablonadataiból szolgáltatásiszerződés-sorokat hozhat létre a HIJ számára. Ha oly módon használja a tárgycsoportokat, akkor gyorsan beállíthatja az új tárgyakat, illetve meghatározhatja a szervizfeladatokat, amelyeket el kell végezni rajtuk. 

## <a name="create-service-object-groups"></a>Szolgáltatás tárgyának csoportjai – Létrehozás

Hozzon létre csoportokat, amelyekhez szolgáltatási objektumokat rendelhet. A szolgáltatási objektumok olyan készletcikkek és egyéb termékek, amelyekhez szolgáltatást nyújtanak. A szolgáltatási objektumok csoportosításával létrehozhat jelentéseket a hasonló és a kapcsolódó szolgáltatási objektumokhoz. Például egy szolgáltatási objektumcsoport állhat két szolgáltatásobjektumból: egy szolgáltatási objektum a csomag, a másik pedig a csomag telepítését magába foglaló szolgáltatás.

Szolgáltatási objektumcsoportok létrehozásához tegye a következőket:

1. Kattintson a **Szolgáltatáskezelés > Beállítás > A szolgáltatás tárgyai > A szolgáltatás tárgyai lehetőségre**.

2. Kattintson az **Új** lehetőségre egy új szolgáltatási objektumcsoport létrehozásához.

3. Írjon be egy egyedi nevet a szolgáltatási objektumcsoport számára, illetve igény szerint adjon meg hozzá leírást.

A **Szolgáltatásobjektumok** képernyő használatával rendelhet szolgáltatási objektumokat a csoporthoz. 

## <a name="see-also"></a>Lásd még

[Szolgáltatási objektumok létrehozása](create-service-objects.md)


