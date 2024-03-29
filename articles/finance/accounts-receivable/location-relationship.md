---
title: Helyhez és felekhez tartozó kapcsolattípusok hozzáadása
description: Ez a cikk bemutatja, hogyan lehet új helyet és félkapcsolat-típust hozzáadni.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2aaf16fac658d26dc2d2a389fd5c1dbb9cbb7649
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874754"
---
# <a name="add-location-and-party-relationship-types"></a>Helyhez és felekhez tartozó kapcsolattípusok hozzáadása 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Hely szerepköreinek hozzáadása

Két módszer áll rendelkezésre új helyszerepkör hozzáadására a cím és kapcsolattartási adatokhoz:

-  Hozzáadás **A cím és a kapcsolattartási adatok célja** oldalon. Az új szerepkör mentésére a **LogisticsLocationRole** táblában kerül sor (típus= 0), ami azt jelzi, hogy a szerepkör nem a rendszer által meghatározott szerepkör a **LogisticsLocationRoleType** felsorolásban és a bővítményeiben. A felhasználó akkor tudja használni ezt a szerepkört, amikor címet vagy kapcsolattartási adatokat létrehozásakor hoz létre.

    ![Cím- és tartalomadatok típusa.](media/Address-Contact.PNG)

-  Adja hozzá a **LogisticsLocationRoleType** felsorolás kiterjesztéséhez, és hagyja, hogy az adatbázis feltöltődjön a szinkronizálási folyamat során.

    1.  Hozzon létre kiterjesztést a **LogisticsLocationRoleType** felsoroláshoz, és adja meg az új szerepkör a kiterjesztésben. 
  
        ![A LogisticsLocationRoleType felsorolás bővítménye.](media/Logistics.PNG)

    2. Hozzon létre egy új erőforrásfájlt az új szerepkörhöz, majd rendeljen hozzá egy értéket a tulajdonságaihoz.
     
     ![Új erőforrás-fájl.](media/Resource.PNG)
        
    3.  Hozzon létre egy adatfeltöltési osztályt, és adjon meg egy kezelési módszert az új szerepkör feltöltéséhez. 

        ![Adatfeltöltés.](media/Dirdata.PNG)

    4.  Az új helyszerepkör feltöltésének teszteléséhez létrehozhat egy futtatható osztályt, és hívja elő ezt: DirDataPopulation::insertLogisticsLocationRoles() a Fő() menüben. Miután ez a folyamat befejeződött, látnia kell a feltöltött új szerepkört a **LogisticsLocationRole** táblában, melynek típusa \>0. Az új szerepkör megjelenik a **Cím- és kapcsolattartási adatok célja** oldalon.

        ![Új hely beszúrása.](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Fél-kapcsolattípus hozzáadása 

Új kapcsolattípust kétféleképpen lehet hozzáadni:

-   Hozzáadás a **kapcsolattípusok** oldalon keresztül. Az új kapcsolat mentésére itt kerül sor: **DirRelationshipTypeTable**, systemtype = 0.

    ![Kapcsolattípusok.](media/Relationship.PNG)

-  Adja hozzá a **DirSystemRelationshipType** felsorolás kiterjesztéséhez, és hagyja, hogy az adatbázis feltöltődjön a szinkronizálási folyamat során.

    1.  Hozzon létre kiterjesztést a **DirSystemRelationshipType** felsoroláshoz, majd adja meg az új kapcsolat típusát.

    2. Hozzon létre egy inicializálót ehhez az új típushoz. Számos példa található a fő kódra, az egyikük **DirRelationshipTypeChildInitialize**. Ez az egy inicializáló-osztály a "Gyermek" kapcsolattípusú félhez. A inicializálót ennek a kódnak a másolásával és beillesztésével, majd frissítse a kijelölt területeket.
    
    ![DirRelationshipChild inicializálója.](media/DirRelationship.PNG)

    3.  Az új kapcsolattípus feltöltésének teszteléséhez létrehozhat egy futtaható osztályt, és hívja elő ezt: DirDataPopulation::insertDirRelationshipTypes() a Fő() menüben. Az új kapcsolattípus megjelenik a **DirRelationshipTypeTable** táblában, és az új kapcsolattípus elérhető lesz a **Kapcsolattípusok** lapon.

        ![Futtatható osztály.](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
