---
title: Könyvek száma naplónként
description: Ez a témakör ismerteti a naplók és az eszközkönyvek közötti viszonyt, amikor egy kötegelt feladat segítségével tárgyieszköz-beszerzési vagy értékcsökkenési javaslatot hoz létre. Megadhatja, hogy hány könyv szerepeljen az egyes beszerzéseknél és az értékcsökkenéseknél.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2dbd50963cf13f00e09b82e884cd8ebc0b67d424
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883329"
---
# <a name="number-of-books-per-journal"></a>Könyvek száma naplónként

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a naplók és az eszközkönyvek közötti viszonyt, amikor egy kötegelt feladat segítségével tárgyieszköz-beszerzési vagy értékcsökkenési javaslatot hoz létre. A **Tárgyi eszközök paraméterei** lap (**Tárgyi eszközök \> Beállítás \> Tárgyi eszközök paraméterei**) **Általános** fülön megadhatja az egyes beszerzéseknél és az értékcsökkenéseknél lévő **Naplónkénti könyvek száma**. Ezekkel a mezőkkel eloszthatók a tárgyi eszközkönyvek száma a beszerzési naplóban és az értékcsökkenési naplóban.

Egy beszerzési javaslat esetében az alapértelmezett érték legalább 10.000 könyv. Egy értékcsökkentési javaslat esetében az alapértelmezett érték legalább 2.000 könyv.

Ha például 4.000 tárgyi eszköz van, és az egyes eszközökhöz két könyv van társítva, akkor egy könyv jelenik meg az aktuális rétegben, és a program feladja a másik könyvet az adózási rétegbe. Ha kötegelt feldolgozással szerez 4.000 tárgyi eszközt, akkor az egy tárgyi eszközbeszerzési naplót létrehozó kötegelt feladat tartalmazni fog 4.000 eszközkönyveket.

> [!NOTE]
> A létrejövő naplót a program addig fogja használni, amíg a kötegelt feladat be nem fejeződik.
>
> A származtatott könyvek nem szerepelnek a naplókban szereplő könyvek maximális számában.

A kötegelt feldolgozással futtathatja az értékcsökkenést ugyanazon beszerzett eszközök készletéhez. Egy kötegelt feladat például két értékcsökkenési naplót hoz létre, amelyek mindegyike 2.000 eszközkönyvből áll. Az első napló az 1 és 2.000 közötti számozott tárgyi eszközökhöz kapcsolódó könyveket tartalmaz. A második napló 2.001 és 4.000 közötti számozott tárgyi eszközökhöz kapcsolódó könyveket tartalmaz.

A kötegelt feldolgozási feladat nem tartalmazza a lezárt könyveket. Egy értékcsökkenésre szánt kötegelt feladatban például az első 2.000 könyvből 10 le van zárva. Ebben az esetben az első napló az 1 és 2.011 közötti számozott tárgyi eszközökhöz kapcsolódó könyveket tartalmaz. A második napló 2.012 és 4.000 közötti számozott tárgyi eszközökhöz kapcsolódó könyveket tartalmaz.

> [!NOTE]
> Ha különböző elválasztókkal (például – vagy /) van eszközazonosítója, és kötegelt feldolgozások esetén tárgyieszköz-tranzakciókat hoz létre, minden elválasztó típushoz külön kötegelt feldolgozást kell futtatnia. A rendszer nem tudja feldolgozni a különböző elválasztókat ugyanazon kötegelt feldolgozáson belül.

A program a könyvek számának korlátját alkalmazza, ha nem létezik ismétlődő eszközazonosító ugyanabban a naplóban. Ha azonban az eszközazonosító megegyezik a könyvazonosítóval, akkor a naplónkénti könyvek száma túlléphető, hogy az eszközazonosító ugyanabban a naplóban maradjon.

Például 5.001 tárgyi eszközazonosító van, három könyv van társítva minden tárgyi eszközazonosítóhoz, és minden eszközkönyv ugyanarra a feladási rétegre kerül. Az értékcsökkenést három egymást követő hónapban futtatja összegzés nélkül.  Az értékcsökkenési napló kötegelt feladattal jön létre, a rendszer pedig hét naplót hoz létre, amelyek 667 tárgyi eszközazonosítóval és három könyvvel rendelkeznek minden tárgyi eszközazonosítóhoz. Az eredmény 2.001 könyv lesz. Ezért három hónapon belül 6.003 naplósor lesz ugyanazon eszközazonosítók fenntartásához ugyanabban a naplóban. A rendszer létrehoz egy naplót is, amely 332 tárgyi eszközazonosítóval és három könyvvel rendelkezik minden tárgyi eszközazonosítóhoz. Három hónap múlva 2.988 sor lesz.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
