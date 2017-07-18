---
title: "Számsorozatok áttekintése"
description: "A Microsoft Dynamics 365 for Finance and Operations rendszerben a számsorozatok az alapadat-rekordok és tranzakciórekordok egyéni, olvasható azonosítójának létrehozásához szükségesek, abban az esetben, ha szükséges hozzájuk azonosító. Az azonosítókat igénylő alapadatokrekordokat és tranzakciós bejegyzéseket <em>hivatkozásnak</em> nevezik."
author: MargoC
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: d260f460bf0da072eb46909d8c28d18041ecaa78
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="number-sequence-overview"></a>Számsorozatok áttekintése

[!include[banner](../includes/banner.md)]


A Microsoft Dynamics 365 for Finance and Operations rendszerben a számsorozatok az alapadat-rekordok és tranzakciórekordok egyéni, olvasható azonosítójának létrehozásához szükségesek, abban az esetben, ha szükséges hozzájuk azonosító. Az azonosítókat igénylő alapadatokrekordokat és tranzakciós bejegyzéseket <em>hivatkozásnak</em> nevezik.

Mielőtt egy hivatkozáshoz új rekordokat hozhat létre a Microsoft Dynamics 365 for Finance and Operations rendszerben, be kell állítania egy számsorozatot és a hivatkozáshoz társítani. Javasoljuk, hogy a **Szervezeti adminisztráció** űrlapon belül található lapokat használja a számsorozatok beállításakor. Ha modulspecifikus beállításokat kell megadni, akkor használhatja a paraméterek lapot a modulban, hogy meghatározza az abban a modulban található hivatkozásokhoz tartozó számsorozatokat. Például a **Kinnlevőségek** és **Kötelezettségek** modulokban beállíthat számsorozat csoportokat, hogy meghatározott számsorozatokat meghatározott vevőkhöz vagy szállítókhoz rendeljen. Számsorozat beállításakor mindig meg kell adnia egy hatókört, ami megadja, mely szervezet használja a számsorozatot. A hatókör lehet **megosztott**, **vállalat**, **jogi személy**, vagy **operációs egység**. A **jogi személy** és **vállalat** hatókörök összevonhatóak a **pénzügyi naptári időszak** modullal, hogy még több meghatározott számsorozatot hozzon létre. A számsorozatok formátumai szegmensekből állnak. Az olyan számsorozatok, amelyek hatóköre nem **megosztott** tartalmazhatnak olyan szegmenseket, amelyek megfelelnek a hatókörnek. Például egy számsorozat a **jogi személy** hatókörrel tartalmazhat egy jogi személy szegmenst. Ha hatókör-szegmenst is felvesz a számsorozat-formátumba, akkor már a szám alapján beazonosíthatja egy adott rekord hatókörét. A hatóköröket jelölő szegmenseken kívül a számsorozat-formátumok tartalmazhatnak **állandó** és **alfanumerikus szegmens** értékeket. Az **állandó** szegmens olyan betűket, számokat vagy szimbólumokat tartalmaz, amelyek nem változnak. Az **alfanumerikus** szegmens olyan betűhalmazt vagy számot is tartalmazhat, amely a szám minden új használatakor nő. A kettős kereszt (\#) használatával jelezheti a növekvő számokat, az (&) jellel pedig a növekvő betűket. Például a \#\#\#\#\#\_2017 formátum a 00001\_2017, 00002\_2017 és így tovább sorozatot hozza létre.
Példák a számsorozatokra
------------------------

A következő példák bemutatják, hogyan hozhat létre számsorozat-formátumokat szegmensekből. A példákban azt is láthatja, milyen hatása van a hatókörszegmenseknek.
### <a name="expense-report-numbers"></a>Költségjelentésszámok

A következő példában költségjelentésszámokat állítunk be egy **CS** nevű jogi személyhez. **Terület:** Utazás és költségek **Hivatkozás:** A költségjelentés száma **Hatókör:** Jogi személy **Jogi személy:** CS
| Szegmensek  | Szegmens típusa | Érték     |
|-----------|--------------|-----------|
| 1. szegmens | Jogi személy | CS        |
| 2. Szegmens | Állandó     | -KIADAS- |
| 3. szegmens | Alfanumerikus | \#\#\#\#  |

**Példa a formázott számra**: CS-EXPENSE-0039 Beállíthat egy hasonló számsorozat-formátumot a többi jogi személyhez. Így például az **RW** nevű jogi személynél, ha csak a jogi személyre vonatkozó szegmenst változtatja meg, a formázott szám RW-KIADAS-0039 lesz. De más jogi személyekre vonatkozóan akár a teljes számsorozat-formátumot megváltoztathatja. Így például kihagyhatja a jogi személyre vonatkozó hatókör szegmensét, így a szám lehet például Kiad-0001.

### <a name="sales-order-numbers"></a>Értékesítési rendelések számai

A következő példában szereplő értékesítésirendelés-számokat a **CEU** vállalatazonosítóhoz hoztuk létre. **Terület:** Értékesítés **Hivatkozás:** Értékesítési rendelés **Hatókör:** Vállalat **Vállalat** CEU
| Szegmensek  | Szegmens típusa | Érték    |
|-----------|--------------|----------|
| 1. szegmens | Állandó     | SO-      |
| 2. Szegmens | Alfanumerikus | \#\#\#\# |

**Példa a formázott számra**: SO-0029 Bár a formátum nem tartalmazza a hatókörszegmenst, a formázás minden vállalatazonosítónál újrakezdődik. Ha minden cégazonosítónál ugyanazt a formátumot használja, akkor minden vállalatnál ugyanazokat a számokat kapja. Így például a huszonkilencedik értékesítési rendelés száma minden cégnél SO-0029 lesz. Más vállalatazonosítókhoz azonban akár a teljes számsorozat formátumát megváltoztathatja.

### <a name="purchase-requisition-numbers"></a>Beszerzési igénylések számai

A következő példában szereplő beszerzésiigénylés-számok a teljes szervezeti szintre vonatkoznak. **Terület:** beszerzés **Hivatkozás:** beszerzési igénylés **Hatókör:** megosztott
| Szegmensek  | Szegmens típusa | Érték    |
|-----------|--------------|----------|
| 1. szegmens | Állandó     | Besz      |
| 2. Szegmens | Alfanumerikus | \#\#\#\# |

**Példa a formázott számra**: Req0052, mivel a hatókör **megosztott**, a számsorozat-formátum az egész szervezetben használatos. Nem állíthat be a szervezet különböző részei számára más-más számsorozat-formátumot. Teljesítménnyel kapcsolatos megfontolások a számsorozatok létrehozásánál
-----------------------------------------------

A számsorozatok beállítása előtt figyelembe kell venni, hogy a számsorozatok konfigurációja hogyan befolyásolhatja a rendszerteljesítményt.
### <a name="continuous-and-non-continuous-number-sequences"></a>Folyamatos és nem folyamatos számsorozatok

Egy számsorozat lehet folyamatos vagy nem folyamatos. A folyamatos számsor nem hagy ki egyetlen számot sem, de nem feltétlenül sorrendben használja a számokat. A nem folyamatos számsorozatok ugyan sorban haladnak, de a sorozat időnként ugorhat egy számot. Így például ha egy felhasználó megszakít egy tranzakciót, akkor a rendszer számot generál hozzá, de nem használja azt. A folyamatos számsorozat ezzel később újra felhasználja ezt a számot. Nem folyamatos számsorozatnál a rendszer nem használja többé ezt a számot. A folyamatos számsorozatok általában külső dokumentumoknál hasznosak, mint amilyen a beszerzési rendelés, az értékesítési rendelés, illetve a számlák. Azonban a folyamatos számsorozatokok lelassíthatják a rendszer válaszidejét, mert a rendszernek minden alkalommal új számot kell kérnie az adatbázisból, valahányszor új dokumentmot vagy rekordot hoznak létre. Nem folytonos számsor használatakor engedélyezheti az **előzetes lefoglalást** a **teljesítmény** gyorslapon, amelyet a **számsorozatok** lapon talál. Ha egy adott mennyiségű számot előre lefoglal, akkor a rendszer ezeket kiválasztja és eltárolja a memóriában. Ezek után csak akkor igényel új számokat az adatbázisból, ha az előre lefoglaltakat már felhasználta. Hacsak nem törvényi előírás a folyamatos számsorozatok használata, akkor a rendszerteljesítmény javítása érdekében érdemesebb a nem folyamatos számozást választani.

### <a name="automatic-cleanup-of-number-sequences"></a>Számsorozatok automatikus tisztítása

Áramszünet, szoftverhiba vagy egyéb váratlan probléma esetén a rendszer nem tudja automatikusan újrahasznosítani a folyamatos számsorozatok korábbi számait. Ezért ezen elveszett sorszámok rendbetételéhez manuállis vagy automatikus tisztítási folyamatot futtathat. A tisztítási folyamat betervezésekor vegye figyelembe, hogy milyen használati terhelés alatt van éppen a szerver. Javasolt a tisztítás kötegelt feladatként történő futtatása a csúcsidőn kívüli órákban.






