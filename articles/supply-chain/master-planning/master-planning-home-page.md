---
title: Alaptervezés kezdőlap
description: Az Alaptervezés lehetővé teszi a vállalat számára, hogy meghatározza a jövőbeli szükséges nyersanyag- és kapacitásigényt a vállalati célok teljesítéséhez.
author: ShylaThompson
manager: tfehr
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20ef016f254f8cc9adafb4b18f0d1db3cfc0e2b2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005127"
---
# <a name="master-planning-home-page"></a>Alaptervezés kezdőlap

[!include [banner](../includes/banner.md)]

Lényegét tekintve az Alaptervezés lehetővé teszi a vállalat számára, hogy meghatározza a jövőbeli szükséges nyersanyag- és kapacitásigényt a vállalati célok teljesítéséhez. Az Alaptervezés értékeli a következőket: 

-  Milyen nyersanyagok és kapacitások érhetők el most? 
-  Milyen nyersanyagok és kapacitások szükségesek a termelés végrehajtásához? Például mit kell előállítani, beszerezni, átmozgatni vagy biztonsági készletként fenntartani, mielőtt teljesíthető lenne a termelés.

Az Alaptervezés az információk alapján kiszámítja a követelményeket és létrehozza a tervezett megrendeléseket.

A három fő tervezési folyamat a következő:

-  **Alaptervezés** – az alapterv kiszámítja a nettó követelményeket. Tényleges aktuális rendeléseken alapul, és lehetővé teszi a vállalatoknak a készlet feltöltésének szabályozását rövid távú, napi alapon. Egy másik kifejezés ugyanerre a *Nettó szükségleti terv*. További informáciért lásd: [Alaptervek áttekintése](master-plans.md). 

-  **Előrejelzési tervezés** – az előrejelzési ütemezés a bruttó követelményeket számítja ki. Jövőbeli projekciókon (vagy előrejelzéseken) alapul, és lehetővé teszi a vállalatoknak az anyagok és a kapacitás hosszú távú tervezését. A további tudnivalókat lásd: [Igény-előrejelzés áttekintése](introduction-demand-forecasting.md). 

-  **Vállalatközi alaptervezés** – a vállalatközi alapterv kiszámítja a nettó követelményeket a jogi személyeket lefedve. Az igényeket és az ellátást köti össze a vállalatok között, és nem csak a rövid távú, megerősített igényt és ellátást, hanem a hosszú távú, tervezett (még meg nem erősítése) igényt és ellátást is. További tudnivalókért lásd: [Vállalatközi alaptervezés](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (CustomerSource-fiókot igényel). 

A vállalatok módosíthatják a terv eredményét. Futtathatják az újragenerálást, a nettó változtatást vagy mindkettőt. Az újragenerálási tervek valamennyi követelményt frissítik, miközben a nettó változási tervek csak az olyan új követelményekkel rendelkező cikkek tervét frissítik, amelyek az utolsó ütemezés futtatása óta érkeztek.

Az alapütemezési tervek általában rövid távúak, az időtartamuk egy hét és hat hónap közötti. Az Alaptervezés modul határozza meg az ellátási (anyagok) és kapacitási (erőforrások) szükségleteket, amelyek megfelelnek az aktuális igénynek (a nettó követelményeknek). A legtöbb vállalatnál ez ki van bővítve, hogy a lehető leghosszabb összesített átfutási időt tartalmazza a leszállítandó termékek között.

## <a name="learning-map"></a>Tanulási térkép

A következő tanulási térkép fontos fogalmakat és feladatokat mutat be, amelyek az Alaptervezés modul keretét alkotják. Kattintson a hivatkozásra a [Gyorshivatkozások](#quick-links) szakaszban a modul használatának elsajátításához.

[![Az alaptervezés tanulási térképe](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Gyorshivatkozások

- [Alaptervek áttekintése](master-plans.md)  
- [Korlátozott terv létrehozása](./tasks/constrained-plan.md)
- [Társtermékek anyagfelhasználási tervének létrehozása](./tasks/create-material-plan-co-products.md)
- [Az alaptervezés és a többhelyes funkció áttekintése](master-plan-multisite-functionality.md)
- [Vállalatközi terv létrehozása](./tasks/create-intercompany-plan.md)
- [Igény-előrejelzés áttekintése](introduction-demand-forecasting.md)
- [Előrejelzés csökkentési kulcsok](reduction-keys.md)
                                  
## <a name="additional-resources"></a>További erőforrások

### <a name="roadmaps"></a>Ütemtervek
Keresse fel a [Microsoft Dynamics365 ütemterv](https://roadmap.dynamics.com/) oldalt a már kiadott új funkciók és a kidolgozás alatt álló új szolgáltatások megtekintése érdekében.

### <a name="blogs"></a>Blogok
A [Dynamics AX Manufacturing kutatás-fejlesztési csapatának blogjában](https://blogs.msdn.microsoft.com/axmfg) és a [Supply Chain Management in Dynamics AX kutatás-fejlesztési csapatának blogjában](https://blogs.msdn.microsoft.com/dynamicsaxscm) számos vélemény, hír és egyéb információ található az alaptervezésről és az egyéb megoldásokról.

### <a name="task-guides"></a>Feladat-útmutatók
További súgó áll rendelkezésére feladat útmutatókon belül. A feladat-útmutatók eléréséhez kattintson bármelyik lapon a **Súgó** gombra.

### <a name="webinars"></a>Webináriumok
[Azure gépi tanulás használata az igény-előrejelzéshez](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)

### <a name="tech-conference-recordings"></a>Technikaikonferencia-felvételek
-  [Az igény-előrejelzési funkció kiterjesztése](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
-  [Alaptervezés – tippek és trükkök a hibajavítási teljesítményért](https://youtu.be/7v8BPmEs9Dg)
-  [Segítség! Lassú az MPR!](https://youtu.be/RLXybx20B5o)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]