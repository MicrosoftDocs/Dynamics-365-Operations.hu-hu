---
title: Szolgáltatás intervallumai
description: A szerviz intervalluma azt a gyakoriságot jelzi, amellyel a szervizrendeléssorok létrejönnek a szervizrendelések automatikus létrehozása esetén.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5766d8ce1fa382f3f014e160d311b2dfab2bf774
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216275"
---
# <a name="service-intervals"></a>Szolgáltatás intervallumai

[!include [banner](../includes/banner.md)]

A szolgáltatási szerződés intervalluma azt a gyakoriságot jelzi, amellyel a szervizrendeléssorok létrejönnek a szervizrendelések automatikus létrehozása esetén.

Ha automatikusan hoz létre szervizrendeléseket, akkor a rendelés sorai a szerződéssor kezdő dátumától kezdve a szolgáltatási szerződés sorára meghatározott időközönként jönnek létre.

Ha az **Intervallum** mező üres a **Szolgáltatási szerződések** lap valamelyik szerződéssorában, akkor az adott sor egyszeri eseményt jelöl, amely nem vesz részt a szervizrendelések ismételt létrehozásában.

## <a name="example"></a>Példa

Ez a példa azt mutatja be, hogy miként befolyásolja a szerviz intervalluma a szolgáltatási szerződés sorait és a szervizrendeléssorokat egy szervizrendelésnél.

### <a name="create-a-service-agreement"></a>Szolgáltatási szerződés létrehozása

Először hozzon létre egy szolgáltatási szerződést, és állítsa a **Szervizrendelések kombinálása** beállítást **Szolgáltatási szerződés szerint** értékre.

1. Kattintson a **Szolgáltatási szerződések** pontra
2. A **Műveleti ablaktáblán**, a **Szolgáltatási szerződés** lapon, az **Új** csoportban, kattintson a **Szolgáltatási szerződés** lehetőségre egy új szolgáltatási szerződés létrehozásához.
3. Adjon meg egy leírást, válasszon ki egy projektet a **Projektazonosító** mezőben, és adjon meg egy dátumot a **Kezdő dátum** mezőben.
4. A **Szervizrendelések kombinálása** mezőben válassza ki a **Szolgáltatási szerződés szerint** lehetőséget.

Ezzel létrehozta a következő szolgáltatási szerződést:

| Project      | Kezdő dátum                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Saját projekt | A projektnél megadott dátum. Ebben a példában az aktuális dátumot használjuk. |

### <a name="create-a-service-agreement-line"></a>Szolgáltatásiszerződés-sor létrehozása

A következő lépésben hozzon létre egy szolgáltatásiszerződés-sort, amelynek tranzakciótípusa **Óra**.

A példa jelen részének végrehajtásához létre kell hoznia egy 10 napos szolgáltatás-intervallumot a **Szolgáltatás-intervallum** lapon. 

1. Válassza ki az imént létrehozott szolgáltatási szerződést. 
2. A **Sorok** gyorslapon kattintson a **Hozzáadás** gombra egy új sor létrehozásához a **Szolgáltatási szerződések** lapon.
3. Válassza ki az **Óra** lehetőséget a **Tranzakció típusa** mezőben.
4. A **Dolgozó** mezőben válassza ki azt a dolgozót, aki elvégzi a szolgáltatást.
5. A **Szolgáltatás intervalluma** mezőben válassza ki a 10 napos intervallumot.

Ezzel létrehozta a szolgáltatásiszerződés-sort a következő adatokkal:

| Tranzakció típusa | Kezdő dátum                               | Szolgáltatás intervalluma |
|------------------|------------------------------------------|------------------|
| Óra             | Az aktuális dátum.                        | 10 naponta    |
| Dolgozó           | A szolgáltatást végző dolgozó. |                  |

Nincs megadott időszak a sornál. 

### <a name="create-planned-service-orders"></a>Tervezett szervizrendelések létrehozása

Ekkor létrehozhatja a tervezett szervizrendeléseket és azok sorait a következő hónapra.

1. A **Szolgáltatási szerződések** lap **műveleti ablaktábláján**, a **Szállítás** lapon kattintson a **Tervezett szervizrendelések** lehetőségre.
2. A **Szervizrendelések létrehozása** lapon adja meg az aktuális dátumot a **Kezdő dátum** mezőben, illetve az aktuális dátum után egy hónappal lévő dátumot a **Záró dátum** mezőben.
3. Állítsa az **Óra** csúszkát **Igen** értékre. 
4. Kattintson az **OK** gombra.

Mivel a szervizrendelésen nincs csoportosítás (amit a **Szolgáltatási szerződés szerint** lehetőség jelez a **Szervizrendelések kombinálása** beállításban), ezért szervizrendelésenként egy szervizrendeléssor jön létre.

### <a name="service-orders-created"></a>A létrehozott szervizrendelések

Az ebben a példányban létrehozott három szervizrendeléssor a **Szervizrendelések létrehozása** párbeszédpanelen beállított időkeretbe esik. A szervizrendeléseket a **Szolgáltatási szerződések** lapon tekintheti meg (**Műveleti ablaktábla** \> **Szállítás** lap \>**Megjelenítés** gomb).

## <a name="related-topics"></a>Kapcsolódó témakörök

[Szolgáltatás intervallumainak beállítása](set-up-service-intervals.md)  

