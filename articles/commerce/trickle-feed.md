---
title: A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi áruház tranzakcióihoz
description: Ez a témakör bemutatja az áruházi tranzakciók folyamatos, apránkénti rendelés-létrehozási folyamatát a Microsoft Dynamics 365 Commerce alkalmazásban.
author: analpert
ms.date: 12/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3a7fd8698d7123403cf9092a4a4bf810595d795b
ms.sourcegitcommit: f82372b1e9bf67d055fd265b68ee6d0d2f10d533
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7921245"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi áruház tranzakcióihoz

[!include [banner](includes/banner.md)]

Javasoljuk, hogy a Microsoft Dynamics 365 Commerce 10.0.5-ös és újabb verziókban minden kimutatásfeladási folyamatot a kimutatások apránkénti feladása folyamatokba vigyen át. Jelentős teljesítmény- és üzleti előnyök társulnak az apránkénti funkcionalitáshoz. Az értékesítési tranzakciók feldolgozása a nap folyamán történik. A fizetőeszköz- és készpénzkezelési tranzakciókat a nap végén kell feldolgozni a pénzügyi kimutatásban. Az apránkénti feldolgozás funkció az értékesítési rendelések, számlák és kifizetések folyamatos feldolgozását teszi lehetővé. Ebből következően a készlet, bevétel és kifizetések közel valós időben frissíthetők és ismerhetőek fel.

## <a name="use-trickle-feed-based-posting"></a>A folyamatos, apránkénti feladás használata

> [!IMPORTANT]
> Mielőtt engedélyezné a folyamatos apránkéti feladást, gondoskodnia kell arról, hogy ne legyennek számított és fel nem adott kimutatások. A funkció engedélyezése előtt minden kimutatást adjon fel. A nyitott kimutatásokat az **Üzlet pénzügyi adatai** munkaterületén ellenőrizheti.

Ha engedélyezni szeretné a kiskereskedelmi tranzakciók folyamatos, apránkénti feladását, engedélyezze a **Kiskereskedelmi kimutatások – folyamatos, apránkénti feldolgozás** funkciót a **Funkciókezelés** munkaterületen. A kimutatások két típusra lesznek felosztva: tranzakciós kimutatásokra és pénzügyi kimutatásokra.

### <a name="transactional-statements"></a>Tranzakciós kimutatások

A tranzakciós kimutatásoknak sűrű gyakorisággal kell futniuk a nap során, így a bizonylatok létrehozása akkor történik, amikor a tranzakciókat a rendszer felölti a Commerce központba. A **P-feladat** futtatásakor a tranzakciók az üzletekből a Commerce központba töltődnek fel. Az **Üzleti tranzakciók ellenőrzése** feladatot is futtatnia kell a tranzakciók ellenőrzéséhez, hogy a tranzakciós kimutatás felvegye azokat.

A következő feladatokat nagy gyakorisággal való futtatására ütemezze:

- A tranzakciós kimutatás kiszámításához futtassa a **Tranzakciós kimutatások kötegelt kiszámítása** feladatot (**Retail és Commerce \> Retail és Commerce IT \> Pénztárfeladás \> Tranzakciós kimutatások kötegelt kiszámítása**). Ez a feladat felveszi az összes fel nem adott és ellenőrzött tranzakciót, és hozzáadja azokat egy új tranzakciós kimutatáshoz.
- A tranzakciós kimutatások kötegelt feladásához futtassa a **Tranzakciós kimutatások kötegelt feladása** feladatot (**Retail és Commerce \> Retail és Commerce IT \> Pénztárfeladás \> Tranzakciós kimutatások kötegelt feladása**). Ez a feladat futtatja a feladási folyamatot, és a hibákat nem tartalmazó, feladatlan kimutatásokhoz értékesítési rendeléseket, értékesítési számlákat, fizetési naplókat, engedménynaplókat és bevétel-költség tranzakciókat hoz létre. 

### <a name="financial-statements"></a>Pénzügyi kimutatások

A pénzügyi kimutatás feldolgozása nap végi folyamatként esedékes. Az ilyen típusú kimutatásfeldolgozás csak a **Műszak** zárása módot támogatja, és csak lezárt műszakokat vesz fel. A kimutatások csak a pénzügyi egyeztetésre korlátozódnak. Csak a különböző fizetőeszközök számított összege és tranzakciós összege közti összegeltérésekről készít naplókat, valamint a további készpénzkezelési tranzakciók naplóit hozza létre.

A következő pénzügyi kimutatási feladatok kezdő és záró időpontjának ütemezése a nap várható vége alapján:

- A pénzügyi kimutatás kiszámításához futtassa a **Pénzügyi kimutatások kötegelt kiszámítása** feladatot (**Retail és Commerce \> Retail és Commerce IT \> Pénztárfeladás \> Pénzügyi kimutatások kötegelt kiszámítása**). Ez a feladat összegyűjti az összes fel nem adott pénzügyi tranzakciót, és hozzáadja azokat egy új pénzügyi kimutatáshoz.
- A pénzügyi kimutatások kötegelt feladásához futtassa a **Pénzügyi kimutatások kötegelt feladása** feladatot (**Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Pénztárfeladás \> Pénzügyi kimutatások kötegelt feladása**).

### <a name="manually-create-statements"></a>Kimutatások manuális létrehozása

Manuálisan is létre lehet hozni a tranzakciós és pénzügyi kimutatástípusokat. 

1. Nyissa meg a **Kiskereskedelem és kereskedelem \> Csatornák \> Áruházak** pontot, és kattintson a **Kimutatások** lehetőségre. 
2. Válassza az **Új** lehetőséget, majd válassza ki a létrehozni kívánt kimutatás típusát. A **Kimutatások** oldalon a kiválasztott kimutatástípus szempontjából releváns adatok jelennek meg és a **Kimutatáscsoport** alatt pedig a kapcsolódó műveletek jelennek meg.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
