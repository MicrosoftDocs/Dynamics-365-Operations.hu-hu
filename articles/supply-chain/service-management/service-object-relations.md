---
title: A szolgáltatás tárgyának kapcsolatai
description: A szolgáltatásitárgy-kapcsolatokat egy szolgáltatási tárgy és egy szolgáltatási szerződés vagy szervizrendelés között lehet létrehozni.
author: ShylaThompson
manager: tfehr
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 913b3c30bf972de7cc3dde73280e4f2f2be38507
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974335"
---
# <a name="service-object-relations"></a>A szolgáltatás tárgyának kapcsolatai 

[!include [banner](../includes/banner.md)]

A szolgáltatásitárgy-kapcsolatokat egy szolgáltatási tárgy és egy szolgáltatási szerződés vagy szervizrendelés között lehet létrehozni. Ehhez a kapcsolat létrehozásakor csatolni kell a szolgáltatási tárgyat a szolgáltatási szerződéshez vagy a szervizrendeléshez.

Amikor létrejött a kapcsolat, csatolhatja a szolgáltatási tárgyat a szolgáltatási szerződés vagy a szervizrendelés bármelyik sorához.

## <a name="template-boms"></a>Sablonanyagjegyzékek

A tárgykapcsolathoz sablonanyagjegyzék is megadható. A sablonanyagjegyzék annak a tárgynak az anyagjegyzéke, amelyen a szolgáltatást végzik. Ha egy szervizlátogatás alkalmával kicseréli egy szolgáltatási tárgy egy alkatrészét, akkor ez a módosítás A szolgáltatás tárgyai képernyő segítségével regisztrálható a szolgáltatási anyagjegyzékben.

## <a name="example"></a>Példa

Létrehoz egy szolgáltatási szerződést, amelynek értelmében Ön szervizel két liftet egy vevő telephelyén.
A szolgáltatás szerződés azonosítója ID SAL-001.

A lifteket létrehozta tárgyként A szolgáltatás tárgyai képernyőn, az EL-S/1000 és az EL-L/1000 kóddal.

A tárgyakat (EL-S/1000 és EL-L/1000) csatolta a szolgáltatási szerződéshez.

Módosításokat kíván regisztrálni a szolgáltatási tárgy anyagjegyzékében, ugyanis kicserélték a tárgy egyes alkatrészeit. Ezért egy szolgáltatási anyagjegyzéket csatol a szolgáltatásitárgy-kapcsolathoz, amint azt a következő táblázat ismerteti.

| A szolgáltatás tárgya | Kapcsolat – szolgáltatási szerződés | Szolgáltatási anyagjegyzék   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

A szerződésnek vannak szolgáltatásitárgy-kapcsolatai, ezért létrehozhatók az ezeket a tárgyakat tartalmazó szolgáltatásiszerződés-sorok, amint a következő táblázatban megjelenik.

| Tranzakció típusa | Kategória           | A szolgáltatás tárgya |
|------------------|--------------------|----------------|
| Óra             | Vizsgálat         | EL-S/1000      |
| Óra             | Fogaskerekek tisztítása  | EL-S/1000      |
| Cikk             | Tisztítóanyagok | EL-S/1000      |
| Óra             | Vizsgálat         | EL-L/1000      |
| Óra             | Fogaskerekek tisztítása   | EL-L/1000      |
| Cikk             | Tisztítóanyagok | EL-L/1000      |

Egy szervizlátogatás alkalmával ki kell cserélni az EL-S/1000 kódú lift fogaskerekeit. Ha ki kell cserélnie a tárgy egy alkatrészét, megnyithatja az Anyagjegyzék-tervezőt az aktuális szolgáltatási szerződés szolgáltatásitárgy-kapcsolata segítségével.

Az Anyagjegyzék-tervező megnyitása egy szolgáltatásitárgy-kapcsolat segítségével.

1. Szolgáltatási szerződések
2. Kattintson duplán egy szolgáltatási szerződésre, vagy kattintson a Szolgáltatási szerződés lehetőségre új szolgáltatási szerződés létrehozásához.
3. Kattintson a Beállítás fülre.
4. Ha csatolni szeretne egy sablonanyagjegyzéket a szolgáltatási szerződéshez, kattintson A szolgáltatás tárgyai elemre.
5. A szolgáltatás tárgyai képernyőn kattintson a Tervező lehetőségre a Tervező megnyitásához a sablon anyagjegyzék módosításához.

## <a name="automatically-created-service-orders"></a>Automatikusan létrehozott szervizrendelések

Ha automatikusan hoz létre szervizrendeléseket egy szolgáltatási szerződéshez, a szerződés szolgáltatásitárgy-kapcsolatai átkerülnek a létrehozott szervizrendelésekbe is.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]