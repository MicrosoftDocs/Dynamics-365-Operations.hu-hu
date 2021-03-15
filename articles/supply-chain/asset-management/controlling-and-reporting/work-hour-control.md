---
title: Munkaóra-ellenőrzés
description: Ez a témakör az Eszközkezelés munkaóra-ellenőrzését ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc4382d72e032fdfad05f2077ffe8e41e64c6a55
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018471"
---
# <a name="work-hour-control"></a>Munkaóra-ellenőrzés

[!include [banner](../../includes/banner.md)]

 

Az eszközkezelésben kiszámíthatja az órákat, amelyekkel áttekintést kaphat a tényleges órákról a költségvetésben meghatározott órákkal szemben az eszközökön, munkavégzési helyszínekn vagy munkarendeléseken. A tényleges órák a feladott tranzakciókon alapulnak.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Munkaóra-ellenőrzés az eszközökhöz, a munkavégzési helyszínekhez és a munkarendelésekhez

Az eszközökre, munkavégzési helyszínekre és munkarendelésekre vonatkozó számítások szinte megegyeznek. Az egyetlen különbség az, hogy az eszközök és munkavégzési helyszínek esetén a számításban szerepelnek aleszközök és al-munkavégzési helyszínek is. A dátum a tranzakció dátuma, amikor a regisztráció rögzítése megtörtént.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközórák ellenőrzése** vagy **Munkavégzési helyszín óráinak ellenőrzése** elemre, vagy az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelések óráinak ellenőzése** elemre.

2. Az **Eszközórák ellenőrzése** párbeszédpanelen, .

3. Az **Eszközórák ellenőrzése** / **Munkavégzési helyszín óráinak ellenőrzése** / **Munkarendelés óráinak ellenőrzése** párbeszédpanelen válassza ki a számítási időszakot a **Nyitó dátum** és a **Záró dátum** mezőkben.

4. Szükség szerint válasszon egy **Pénzügyi dimenziókészlet** elemet, amit szerepeltetni szeretne a számításban.

5. Ha a nulla órát tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.

6. A **Szint** mezőben megadhatja, hogy az óraellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. 

    Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínek hierarchiájához, akkor a munkavégzési helyszínekhez tartozó óraellenőrzési sorok a legfelső szinten jelennek meg, így a sorban szereplő órák hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. 
    
    Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a óraellenőrzés minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

7. Ha az aleszközökhöz tartozó költségeket külön sorként szeretné megjeleníteni, állítsa az **Aleszközök szerepeltetése** beállítást „Igen” értékre.

8. Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket/munkavégzési helyszíneket/munkarendeléseket a **Szerepeltetni kívánt rekordok** gyorslapon.

9. Kattintson az **OK** gombra az számítás indításához.

10. Az **Eszközórák ellenőrzése** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

## <a name="example"></a>Példa

Az alábbi képernyőfotón az **Eszközórák ellenőrzése** számítás egyik példája látható.

- Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési órák láthatók. 
- A **Tényleges órák** mező a munkarendeléseken feladott órákat jeleníti meg. 
- A **Vállalt óraszám** mezőben az órák összes száma látható, amelyet a vállalat a munkarendelésekkel kapcsolatban vállalt.

![Példa a tárgyi eszköz óraellenőrzési számítására](media/04-controlling-and-reporting.png)

Az órák számításának másik módja az, ha többszörös kiválasztással kiválasztja az eszközöket az **Összes eszköz** vagy **Aktív eszközök** pontban. Ezután kattintson az **Óraellenőrzés** gombra az **Általános** gyorslapon. A rendszer automatikusan beilleszti a kiválasztott eszközöket az **Eszköz** mezőbe a **Szerepeltetni kívánt rekordok** gyorslapon. Kattintson az **OK** gombra az **Eszközórák ellenőrzése** párbeszédablakban, és megjelenik a kiválasztott eszközökre vonatkozó számítás. Ugyanez az eljárás hajtható végre az **Összes munkavégzési helyszín** vagy **Aktív munkavégzési helyszínek** pontban található munkavégzési helyszíneknél, valamint a munkarendeléseknél az **Összes munkarendelés** vagy **Aktív munkarendelések** pontban.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]