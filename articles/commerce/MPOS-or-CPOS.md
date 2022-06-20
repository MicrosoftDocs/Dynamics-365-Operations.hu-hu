---
title: A Store Commerce és a Cloud POS közötti választás
description: Ez a cikk bemutatja a Store Commerce és a Cloud POS rendszer közötti alapvető különbségeket, és leírja azokat a tényezőket, Dynamics 365 Commerce amelyek közül a kiskereskedőknek érdemes megfontolni, hogy a lehető legjobb választást tárolják követelményeket.
author: jblucher
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 26f6e94b13b3058ac42c4c7b83dcf7179bae18e3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854006"
---
# <a name="choose-between-store-commerce-and-cloud-pos"></a>A Store Commerce és a Cloud POS közötti választás

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja a Store Commerce és a Cloud POS rendszer közötti alapvető különbségeket, és leírja azokat a tényezőket, Dynamics 365 Commerce amelyek közül a kiskereskedőknek érdemes megfontolni, hogy a lehető legjobb választást tárolják követelményeket. Ezenkívül további háttér-, tippeket és útmutatást ad a megvalósító eszközöknek, és útmutatást ad az olyan tényezőkkel kapcsolatban, amelyek a telepítéskor figyelembe kell venni őket Dynamics 365 Commerce. Az útmutató áttekintésével és követésével a telepítés részeként a bevezetők elkerülhetik azokat a problémákat, amelyek hatással lehetnek a felhasználói élményre vagy a teljesítményre.

## <a name="insights"></a>Információk

A Commerce számos telepítési és topológialehetőséget kínál. Emiatt a kiskereskedők kiválaszthatják az üzleti és technológia követelményeiket legjobban teljesítő összetevőket és konfigurációkat. A bevezetés egyik körültekintő figyelmet igénylő kérdése a pénztárösszetevő (POS) platformjának és helyigényének kiválasztása.

### <a name="pos-platform-and-form-factor-considerations"></a>Pénztár platformot és helyigényt érintő szempontjai

A Commerce a következő pénztárlehetőségeket támogatja:

- Commerce Áruház – Microsoft Windows
- Store Commerce for iOS és Android
- A Cloud POS (CPOS) szolgáltatás, amely a Microsoft Edge és a Króm böngészőket támogatja.
- A Modern POS (MPOS) for Microsoft Windows (MPOS 2023 októberében lesz elavult.) 

A POS (Store Commerce és CPOS) minden esetben ugyanazt az alapvető alkalmazáskódot használja. Ez pont a következő okok miatt fontos:

- A felhasználói felület a platformtól és a helyigénytől függetlenül egységes.
- A funkciók többsége ugyanaz, függetlenül a platformtól és a helyigénytől. Vannak azonban fontos eltérések. Ezeket a különbségeket a cikk jegyezte fel.
- Az egyes áruházakban a POS-változatok kombinálhatók, és párhuzamosan is futtathatók. Például egy kiskereskedő a fő pénztárgépein a Windows rendszert futtató számítógépeken használhatja a Store Commerce rendszert. A kiskereskedő azonban böngészőalapú terminálokkal vagy mobileszközökkel is kiegészítheti ezeket a pénztárgépeket.
- A testreszabások és a bővítések könnyen használhatók mindegyik platform és helyigény esetében. Mivel az alapvető alkalmazáskód ugyanaz, a legtöbb testreszabás egy menetben hajtható végre, több szakasz helyett.

### <a name="store-commerce-vs-cpos"></a>Store Commerce és CPOS

Bár a Store Commerce és a CPOS ugyanazok, néhány fontos eltérést meg kell érteni.

#### <a name="store-commerce"></a>Store Commerce

A Store Commerce egy asztali alkalmazás, amely telepítve van és szervizelt egy eszközön.

- **Windows** – a Store Commerce for Windows alkalmazás tartalmazza az összes alkalmazáskódot Commerce Runtime (CRT) és a hardverállomást (HWS).
- **iOS/Android** – Ezeken a rendszereken az alkalmazás a CPOS-alkalmazáskód üzemeltetőjeként viselkedik. Más szóval az alkalmazáskód abból a CPOS-kiszolgálóról származik, amely a Commerce Scale Unit kiszolgálón található. További tudnivalókért lásd: [Commerce Scale Unit áttekintése](dev-itpro/retail-store-system-begin.md).

#### <a name="cpos"></a>CPOS

Mivel a CPOS a böngészőben fut, az alkalmazás nincs telepítve az eszközön. Ehelyett a böngésző a CPOS-kiszolgálóról éri el az alkalmazás kódját. Ezért CPOS nem éri el közvetlenül a pénztárhardvert, és nem működik offline állapotban.

### <a name="store-deployment-considerations"></a>Üzletbeli telepítéssel kapcsolatos szempontok

A platform és a helyigény mellett a kiskereskedőnek ki kell választania egy rendszerbe állítási lehetőséget is. Az alábbi táblázat ismerteti a választható konfigurációkat az egyes pénztárra vonatkozó választási lehetőségekhez.

| Pénztáralkalmazás            | Commerce Scale Unit | Offline elérhető. | Helyi HWS-támogatás |
|----------------------------|---------------------|-------------------|-------------------|
| Commerce Áruház – Windows | Felhő vagy RSSU       | Igen               | Igen               |
| Commerce Áruház – Android | Felhő vagy RSSU       | Nem                | Igen               |
| Commerce áruház iOS-hez     | Felhő vagy RSSU       | Nem                | Nem                |
| Felhő pénztár                  | Felhő vagy RSSU       | Nem                | Nem                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

A Commerce Scale Unit egy olyan összetevő, amely a CRT-t tárolja. A CRT tartalmazza a pénztár által használt összes üzleti logikát, és hozzáférést biztosít a csatorna-adatbázishoz. Amíg online állapotban vannak, az üzlet minden pénztárügyfele a Commerce Scale Unitot használja. A Commerce Scale Unit telepíthető a felhőben vagy az üzletben.

#### <a name="offline-mode"></a>Offline mód

A Store Commerce for Windows támogatja az offline módot. Kapcsolat nélküli módban a pénztár továbbra is képes az eladások feldolgozására, még akkor is, ha megszakadt a kapcsolata a Commerce Scale Unittal. A kapcsolat visszaállításakor szinkronizálható a csatorna-adatbázissal. A Store Commerce a saját beágyazott CRT példányát használja, és ideiglenesen saját helyi adatforrását (offline SQL Server-adatbázist) használja. Az offline funkciókkal kapcsolatban további tudnivalókat lásd: [A POS pénztár kapcsolat nélküli üzemelése](pos-offline-functionality.md).

### <a name="pos-peripheralhardware-considerations"></a>Pénztár: periféria/hardver szempontok

A kiskereskedőknek azt is figyelembe kell venniük, hogyan fér hozzá a pénztár az olyan eszközökhöz és perifériákhoz, mint a nyomtatók, a pénztárfiókok és a fizetési terminálok. A hardverállomás hozzárendelhető egy pénztárgéphez, de az üzletben található pénztárgépek közösen is osztozhatnak rajta.

| Pénztáralkalmazás            | Helyi HWS OPOS | Hálózati perifériák | Megosztott HWS-támogatás |
|----------------------------|----------------|---------------------|--------------------|
| Commerce Áruház – Windows | Igen            | Igen                 | Igen                |
| Commerce Áruház – Android | Nem             | Igen                 | Igen                |
| Commerce áruház iOS-hez     | Nem             | Nem                  | Igen                |
| Felhő pénztár                  | Nem             | Nem                  | Igen                |

A hardverállomásokkal kapcsolatos további tudnivalókért lásd: [Kiskereskedelmi hardverállomás konfigurálása és telepítése](retail-hardware-station-configuration-installation.md).

## <a name="implementation-considerations"></a>Kivitelezési szempontok

Az üzletekben való pénztártelepítés tervezésekor vegye figyelembe a következőket:

- **Funkcionális követelmények** – Az alapvető üzleti folyamatok és képességek ugyanazok, függetlenül a platformtól, a helyigénytől vagy a telepítési topológiától. Emiatt a legtöbb kiskereskedőnek nem kell figyelembe vennie a funkcionális követelményeket a telepítés tervezésekor.
- **Kapcsolat** – A hálózati elérhetőség (nagykiterjedésű hálózat \[WAN\] és helyi hálózat \[LAN\]) gondos figyelmet igénylő jelentős tényező. A nulla helyigényű, felhő által szolgáltatott megoldások által kínált költségmegtakarítási és egyszerűsítési előnyök elvesznek, ha a rendszer nem érhető el a kritikus üzleti folyamatokhoz.

    Azokat az eseteket kivéve, amikor az adott eszköz kapcsolata nagyon megbízható és rugalmas, vagy amikor bizonyos mennyiségű leállást elfogadható a kiskereskedő számára, a következő lehetőségek valamelyikét ajánljuk:

    - Használja a Store Commerce rendszert a Windows rendszerben, és engedélyezze az offline módot.
    - Helyszíni Commerce Scale Unit bevezetése.

    Ez a két lehetőség nem zárja ki kölcsönösen egymást. A legmegbízhatóbb topológia érdekében a kiskereskedők telepíthetnek egy helyi RSSU-t az internetkapcsolat vagy az Azure rendelkezésre állásától való függőség csökkentése érdekében, továbbá telepíthetnek olyan pénztárgépeket, amelyeken engedélyezve van a kapcsolat nélküli mód arra az esetre, ha probléma lépne fel a helyi kiszolgálóval vagy a hálózattal.

- **Hardvereszközök/perifériák** – A Retail POS rendszer egyik fontos szempontja az, hogy képes pénztárperifériák, például nyomtatók, pénztárfiókok és fizetési terminálok használatára. Bár minden rendelkezésre álló POS-beállítás használhat perifériás eszközöket, csak a Store Commerce for Windows támogatja őket közvetlenül. A többi alkalmazáshoz egy vagy több hardverállomás szükség. Annak ellenére, hogy ez a megközelítés rugalmasságot nyújt, további összetevőket kell telepíteni, konfigurálni és karbantartani.
- **Rendszerkövetelmények** – A pénztáralkalmazás rendszerkövetelményei eltérőek lehetnek. Ügyeljen a legfrissebb információk ellenőrzésére a kiválasztás elvégzése előtt. Például: a CPOS böngészőben fut, ezért operációs rendszerek szélesebb körét támogatja. A rendszerkövetelményekkel kapcsolatos további tudnivalókat lásd: [Felhőtelepítések rendszerkövetelményei](../fin-ops-core/fin-ops/get-started/system-requirements.md).
- **Telepítés és karbantartás** – A telepítési és karbantartási követelmények összetettsége változhat az alkalmazással és a telepítéssel kapcsolatos döntésektől függően. Például a felhő által szolgáltatott CPOS telepítéshez nem kell minden eszközön telepítést és frissítést végezni. Ezért ez a megközelítés jelentősen csökkenti a bonyolultságot és a költséget. Ha azonban a Store Commerce minden pénztárgépre telepít, és engedélyezi az offline módot, és megosztott hardvereszközöket is telepít, nagy mértékben megnöveli a kezelhető végpontok számát.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
