--- 
title: "Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között"
description: "Ez a témakör bemutatja, hogy hogyan állíthat be és futtathat több jogi személynél értékcsökkenés folyamatot."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között

[!include [task guide banner](../../includes/task-guide-banner.md)]

Tárgyi eszköz értékcsökkenése egyetlen lépésben futtatható jogi személyek között. Ez a témakör bemutatja, hogy hogyan állíthatja be és futtathatja több jogi személynél a folyamatot. A könyvelői szerepkört használja.  

Ez a felvétel az USMF bemutatócéget használja.


Lépések (16) alfeladat: Vállalatközi vállalati értékcsökkenés-futtatási naplók beállítása. 

1. Először be kell állítania a naplókat a több vállalatot érintő értékcsökkenés futtatásához valamennyi jogi személynél. Ugorjon a Tárgyi eszközök > Beállítás > Tárgyi eszköz paraméterek pontra. 
2. Bontsa ki a tárgyieszköz-javaslatok szakaszt. 
3. Hozzon létre rekordot azzal a naplónévvel, amely a jogi személy egyes feladási rétegekeinél lesz használatban. Ha a könyvek nem adják fel az adatokat a főkönyvbe, akkor a Nincs feladási réteget lehetőséget kell kiválasztania a társított naplóval. Kattintson a Hozzáadás gombra. 
4. A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket. 
5. A Napló neve mezőben adjon meg vagy válasszon ki egy értéket. 
6. Ismételje meg a napló beállítását a tárgyi eszköz paraméterei lapon az egyes jogi személyekhez. 

Alfeladat: Értékcsökkenés kiszámítása

1. Az Értékcsökkenési javaslat létrehozása lap használatával indítsa el az értékcsökkenés futtatását a jogi személyek között. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása pontra. 
2. A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket. 
3. A napló neve alapértelmezésben a tárgyi eszköz paramétereiből jön. Itt módosítható az aktuális jogi személyhez. 
4. Adja meg a dátumot a „Záró dátum” mezőben. 
5. Válassza ki az értékcsökkenés futtatásába felvenni kívánt jogi személyeket. A listában csak a tárgyieszköz-javaslatokhoz a tárgyi eszköz paraméterei lapon beállított naplókkal rendelkező jogi személyek fognak megjelenni. 
6. Ha engedélyezve van, a naplók feladása beállítás automatikusan feladja az értékcsökkenési naplókat a létrehozásukkor. Ha nincs bejelölve, a naplók létre lesznek hozva, de nem lesznek feladva, így a feladás előtt megtekintheti a részleteket. Válassza ki az Igen lehetőséget a Naplók feladása mezőben. 
7. A szűrőmezőkbe beletartozik az összes tárgyi eszköz, a csoportok és a könyvek az értékcsökkenési futtatáshoz kiválasztott a jogi személyekhez. 
8. A kötegelt feldolgozási beállítás alapértelmezés szerint engedélyezve van. Ha ez a beállítás engedélyezve van, az értékcsökkenési napló létrehozása és feladása a háttérben fog futni. 
9. Kattintson a Napló létrehozása lehetőségre. 
10. Az egyes jogi személyeknél létrehozott értékcsökkenési naplókat meg kell tekinteni. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.

