---
title: Üzemi erőforrás létrehozása
description: Az üzemi erőforrás hajtja végre egy projekt vagy egy termelési folyamat tevékenységeit.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90535d3a6cf58fc10309cf035bc74143a96c2add
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576856"
---
# <a name="create-an-operations-resource"></a>Üzemi erőforrás létrehozása

[!include [banner](../../includes/banner.md)]

Az üzemi erőforrás hajtja végre egy projekt vagy egy termelési folyamat tevékenységeit. Ez az eljárás bemutatja, hogyan határozzon meg egy üzemi erőforrást. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.

1. Ugrás az Erőforrások parancsra.
2. Kattintson az Új lehetőségre.
3. Érték beírása az Erőforrás mezőbe.
4. A Leírás mezőben adjon meg egy értéket.

## <a name="define-capacity-and-consumption-parameters"></a>Határozza meg a kapacitás és a felhasználási paramétereit
1. Bontsa ki a Művelet szakaszt.
2. Adjon meg egy számot a Selejtszázalék mezőben.
3. A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg azt a költségkategóriát, amely meghatározza, hogyan számolhatja el a beállítás költségét.  
4. A Lefutásiidő-kategória mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg azt a költségkategóriát, amely meghatározza, hogyan számolhatja el a futtatási idő költségét.  
5. A Mennyiségkategória mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg azt a költségkategóriát, amely meghatározza, hogyan lehet a elszámolni a kimeneti mennyiségeken alapuló erőforrásköltséget.  
6. Egy lehetőség kiválasztása a Kapacitásegység mezőben.
    * Annak az egységnek a megadása, amelyben az üzemi erőforrás kapacitását kifejezik.  
7. Adjon meg egy számot a Kapacitás mezőben.
8. Adjon meg egy számot a Hatékonyság (százalék) mezőben.
    * Adja meg, hogy milyen hatékonyságot vár el az üzemi erőforrástól. A hatékonysági százalék beállítja az üzemi erőforrás teljesítményét és befolyásolja az erőforrás lefoglalt időt.  
9. A Műveletütemezés százalék mezőjében adjon meg egy számot.
    * Adja meg az üzemi erőforrások kapacitásának azt a maximális százalékát, amelyet a műveletek ütemezésében használni kíván.  
10. Válassza az Igen lehetőséget a Véges kapacitás mezőben.
    * Állítsa ezt a beállítást Igen-re, ha az üzemi erőforrást a ténylegesen elérhető kapacitás alapján kell ütemezni, és ha a meglévő kapacitásfoglalásokat figyelembe kell venni. Ha ebben a beállításban Nem szerepel, az üzemi erőforrás feltételezett kapacitása korlátlan, és előfordulhat, hogy az erőforrás túl van foglalva.  
11. Válassza az Igen lehetőséget a Szűk keresztmetszetű erőforrás mezőben.

## <a name="define-working-times"></a>Munkaidők meghatározása
1. Bontsa ki a Naptárak szakaszt.
2. Kattintson a Hozzáadás gombra.
3. A Naptárak mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg azt a munkaidőnaptárt, amely meghatározza az erőforrás kapacitását (órában).  
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="define-resource-capabilities"></a>Erőforrás-képességek meghatározása
1. Bontsa ki Képességek szakaszt.
2. Kattintson a Hozzáadás gombra.
    * A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására. Az ütemezési motor erőforrásokat utal ki azáltal, hogy összekapcsolja az egyes tevékenységek erőforrás-követelményeit az elérhető üzemi erőforrásokkal.  
3. A Képesség mezőben adjon meg vagy válasszon ki egy értéket.
4. Adjon meg egy számot a Szint mezőben.
    * Adja meg azt a szakértelemszintet, amellyel az erőforrás feldolgozza a képességet.  
5. Adjon meg egy számot a Prioritás mezőben.
    * Adja meg az üzemi erőforrás prioritását a képesség tekintetében. A prioritás szerint ütemezéskor a legmagasabb prioritású (legkisebb numerikus értékű) üzemi erőforrás lesz elsőként kijelölve.  

## <a name="assign-resource-to-resource-group"></a>Erőforrás hozzárendelése az erőforráscsoporthoz
1. Bontsa ki az Erőforráscsoportok szakaszt.
2. Kattintson a Hozzáadás gombra.
    * Az erőforráscsoport határozza meg a telephelyet, a termelési egységet és a raktárkörnyezetet az üzemi erőforrások számára. Az üzemi erőforrást csak akkor lehet ütemezni, ha hozzá van rendelve egy erőforráscsoporthoz, és csak azon a telephelyen, ahol az erőforráscsoport található.  
3. Az Erőforráscsoport mezőben adjon meg, vagy válasszon ki egy értéket.
4. A Bemeneti hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg annak a raktárnak az elhelyezkedését, ahonnan az üzemi erőforrás anyagot használ.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]