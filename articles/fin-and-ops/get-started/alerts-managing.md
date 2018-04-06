---
title: "Figyelmeztetések kötegelt végrehajtása"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations figyelmeztetéseinek kötegelt feldolgozásáról nyújt információkat."
author: tjvass
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.translationtype: HT
ms.sourcegitcommit: 454368ab5a467002ebf973db97fd98e31885dfe0
ms.openlocfilehash: f4c874c148dc10ac658f659896009981962a5802
ms.contentlocale: hu-hu
ms.lasthandoff: 03/23/2018

---

# <a name="batch-processing-for-alerts"></a>Figyelmeztetések kötegelt feldolgozása
[!include[banner](../includes/banner.md)]

[!include[banner](../includes/pre-release.md)] 

A figyelmeztetéseket a Microsoft Dynamics 365 for Finance and Operations kötegfeldolgozó funkciója dolgozza fel. A figyelmeztetések elküldéséhez előbb kötegfeldolgozást kell beállítani.

A Finance and Operations kétféle típusú eseményt támogatja:

- Módosításalapú események által kiváltott események. Ezekre az eseményekre létrehozás/törlés, és frissítés eseményként is utalunk.
- Határidők által kiváltott események.

Kötegfeldolgozásokat minden ilyen típusú eseményre be lehet állítani.
        
## <a name="batch-processing-for-change-based-events"></a>Kötegelt feldolgozás módosításalapú események esetén
A Finance and Operations beolvassa a változásalapú eseményeket, amelyek a kötegelt feldolgozás utolsó futása óta történtek. A módosításon alapuló események közé tartozik a mezőfrissítés, a rekordok törlése és létrehozása. Ezek az események a figyelmeztetési szabályokban beállított feltételekkel vannak összehasonlítva. A kötegfeldolgozás figyelmeztetést generál, ha egy esemény teljesíti egy szabály feltételeit.

### <a name="frequency-for-change-based-events"></a>Módosításalapú események gyakorisága
A módosítás alapú eseményekhez beállíthat egy kötegfeladatot, amely kezdeményezi egy esemény feldolgozását nem sokkal azután, hogy a rendszer naplózta az eseményt. Ha a kötegelt feladat ismétlődését gyakrabbra állítja, felhasználók hamarabb megkapják a figyelmeztetéseket, ha változás történik. A kötegelt feldolgozás nagy gyakorisága azonban hátrányosan befolyásolhatja a rendszer teljesítményét.

Másrészről a ritkábban ismétlődő és alacsony rendszerterhelés idejére ütemezett kötegelt feladatok javíthatják a rendszer teljesítményét. A kötegfeldolgozás gyakoriságát alacsonyra állítva azonban lehet, hogy a felhasználók nem fognak időben megkapni figyelmeztetéseket.

Amikor tehát beállítja a módosítás alapú eseményekre vonatkozó kötegelt feldolgozást, akkor figyelembe kell vennie a figyelmeztetések gyorsaságát és a teljes rendszer teljesítményét, és ennek megfelelően kell kompromisszumot hoznia. Minél több olyan felhasználó van, aki figyelmeztetési szabályokat generál, annál fontosabb a fentiek megfontolása. A gyakoriság nem befolyásolja a feldolgozandó események számát. Ugyanakkor ha több felhasználó hoz létre szabályokat, több ellenőrzést kell végrehajtani. Az ilyen típusú adatcsere befolyásolhatja a rendszer teljesítményét.

#### <a name="the-risks-of-low-batch-frequency"></a>Az alacsony kötegfeldolgozási gyakoriság kockázata
Ha a módosításalapú kötegfeldolgozás gyakoriságát alacsonyra állítja, akkor előfordulhat, hogy a köteg feldolgozása előtt módosulnak azok az adatok, amelyek fontosak figyelmeztetési szabály feltételeihez. Emiatt a figyelmeztetések elveszhetnek.

Ha például egy figyelmeztetési szabály be van állítva figyelmeztetés megjelenítésére, ha az esemény **vevőkapcsolat módosul** és a feltétel **vevő = BB**. Más szóval, amikor a vevő BB ügyfélkapcsolata megváltozik, az esemény naplózásra kerül. Azonban a kötegelt feldolgozó rendszer úgy van beállítva, hogy a kötegelt feldolgozásra ritkábban kerüljön sor, mint adatbevitelre. Ha a vevő neve megváltozik **BB**-ről **AA**-ra az esemény feldolgozása előtt, az adatbázisban lévő adatok már nem felelnek meg meg a szabályban megadott feltételnek, miszerint **vevő = BB**. Ezért, amikor végül megtörténik az esemény feldolgozása, nem jön létre figyelmeztetés.

### <a name="set-up-processing-for-change-based-alerts"></a>Változáson alapuló figyelmeztetések feldolgozásának beállítása
1. Lépjen a **Rendszerfelügyelet** &gt; **Időszakos feladatok** &gt; **Figyelmeztetések** &gt; **Módosításalapú figyelmeztetések** elemre.
2. A **Módosításalapú figyelmeztetések** párbeszédpanelen írja be a megfelelő adatokat.

## <a name="batch-processing-for-due-date-events"></a>Kötegelt feldolgozás határidős események esetén
A Finance and Operations észlel minden, határidő által okozott eseményt, és ezeket az eseményeket összeveti a figyelmeztetési szabályokban beállított feltételekkel. A kötegfeldolgozás figyelmeztetést generál, ha egy esemény teljesíti egy szabály feltételeit.

### <a name="frequency-for-due-date-events"></a>Határidős események gyakorisága
A határidős eseményekre érdemes olyan kötegfeladatokat beállítani, amelyek az éjszaka vagy a nappal meghatározott időpontjaiban futnak le, és így a rendszer terhelését ki lehet egyenlíteni. Azt ajánljuk, hogy úgy állítsa be a kötegelt feladatot, hogy naponta legalább egyszer fusson. Ha a figyelmeztetéseket a lehető legkorábban kell elküldeni, állítsa be, hogy a kötegfeldolgozás közvetlenül a rendszerdátum-változások után megtörténjen. Ha olyan határidős eseményekről is szeretne figyelmeztetéseket generálni, amelyek azután történtek, hogy egy határidős köteg feldolgozta a figyelmeztetéseket, akkor a köteget újra futtathatja aznap.

Például egy kötegelt feladat futtatása történt egy adott napon. Ezután létrehoz egy beszerzési rendelést, amelynek a határidejének figyelmeztetést kell kiváltania ugyanazon a napon. Ahhoz, hogy megjelenjen a figyelmeztetés az adott napon, újra kell futtatni a kötegelt feladatot a beszerzési rendelés létrehozása után. Ha azonban nem futtatja le aznap még egyszer a kötegelt feladatot, akkor a másnapi kötegelt feladat érzékelni fogja az előző napok még fel nem dolgozott határidős eseményeit.

> [!NOTE]
> Még ha a kötegfeladat naponta többször le is fut, ugyanahhoz a határidős eseményhez és feltételhez nem jön létre több figyelmeztetés. A rendszer csak a lejárt határidőkhöz generál figyelmeztetéseket ha változás történt a rendszerben a köteg legutóbbi futtatása óta.

### <a name="batch-processing-window"></a>Kötegelt feldolgozás időkerete
A figyelmeztetési szabályok feldolgozását egy vállalatnál több okból is le lehet állítani. Az okok közé tartoznak például a szabadságok, a rendszerhibák vagy az egyéb problémák, amelyek bizonyos ideig megakadályozzák a kötegelt feladatok futtatását.

Azért, hogy a határidőn alapuló figyelmeztetések ne avuljanak el amiatt, mert a kötegelt feldolgozás nem futott néhány napig, ablak állítható be a kötegelt feldolgozáshoz. Kötegfeldolgozási ablak használható arra, hogy megakadályozza a kötegelt feladat bizonyos számú napig történő futtatását.

Ha kötegelt feldolgozáshoz időkeretet állít be, figyelmeztetés küldésére kerül sor a figyelmeztetési szabály feldolgozásakor még akkor is, ha a figyelmeztetés túl van a határidős feltételben megadott időkorláton. A figyelmeztetés mindaddig küldésre kerül, amíg az időhatár plusz a kötegelt feldolgozási ablak által meghatározott időtartam nincs túllépve. Azonban az időhatár plusz a kötegelt feldolgozási ablak által meghatározott időtartam túllépésekor többé nem kerül sor figyelmeztetés küldésére.

### <a name="set-up-processing-for-due-date-alerts"></a>Határidőn alapuló figyelmeztetések feldolgozásának beállítása
1. Lépjen a **Rendszerfelügyelet** &gt; **Időszakos feladatok** &gt; **Figyelmeztetések** &gt; **Határidőn alapuló figyelmeztetések** elemre.
2. A **Határidőn alapuló figyelmeztetések** párbeszédpanelen írja be a megfelelő adatokat.

