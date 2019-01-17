---
title: "A Retail Modern POS (MPOS) és a Cloud POS közötti választás"
description: "Ez a témakör bemutatja a Retail Modern POS és a Cloud POS közötti alapvető eltéréseket. Emellett azokat a különböző tényezőket is ismerteti, amelyeket a Microsoft Dynamics 365 for Retail megoldást telepítő kiskereskedőknek figyelembe kell venniük, hogy a legjobban választhassák meg a követelményeket."
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 0b137a21a610a8bffc10b03067b429995e8e0662
ms.contentlocale: hu-hu
ms.lasthandoff: 01/04/2019

---

# <a name="choose-between-retail-modern-pos-mpos-and-cloud-pos"></a>A Retail Modern POS (MPOS) és a Cloud POS közötti választás

[!include [banner](includes/banner.md)]

Ez a témakör további háttérinformációkat, tippeket és útmutatást ad az alkalmazás telepítőinek azokkal a tényezőkkel kapcsolatban, amelyeket figyelembe kell venni a Microsoft Dynamics 365 for Retail üzembe helyezésekor. Az útmutató áttekintésével és követésével a telepítés részeként a bevezetők elkerülhetik azokat a problémákat, amelyek hatással lehetnek a felhasználói élményre vagy a teljesítményre.

## <a name="insights"></a>Fontos információk

A Retail számos telepítési és topológialehetőséget kínál. Emiatt a kiskereskedők kiválaszthatják az üzleti és technológia követelményeiket legjobban teljesítő összetevőket és konfigurációkat. A bevezetés egyik körültekintő figyelmet igénylő kérdése a pénztárösszetevő (POS) platformjának és helyigényének kiválasztása.

### <a name="pos-platform-and-form-factor-considerations"></a>Pénztár platformot és helyigényt érintő szempontjai

A Retail a következő pénztárlehetőségeket támogatja:

- Retail Modern POS (MPOS) a Microsoft Windows rendszerhez
- MPOS a Microsoft Windows Phone rendszerhez
- MPOS Apple iPad vagy Google Android táblagépekhez
- Cloud POS (CPOS), amely a Microsoft Edge, az Internet Explorer és Google Chrome böngészőket támogatja

Minden esetben a pénztár (MPOS és CPOS) azonos alapvető alkalmazáskóddal rendelkezik. Ez pont a következő okok miatt fontos:

- A felhasználói felület a platformtól és a helyigénytől függetlenül egységes.
- A funkciók többsége ugyanaz, függetlenül a platformtól és a helyigénytől. Vannak azonban fontos eltérések. Ezek a különbségek ebben a témakörben találhatók.
- Egy adott áruházban a pénztárváltozatok kombinálhatók és egyidejűleg futtathatók. Például a főpénztárgépek esetében a kiskereskedő Windowst futtató számítógépeken használhatja az MPOS-t. A kiskereskedő azonban böngészőalapú terminálokkal vagy mobileszközökkel is kiegészítheti ezeket a pénztárgépeket.
- A testreszabások és a bővítések könnyen használhatók mindegyik platform és helyigény esetében. Mivel az alapvető alkalmazáskód ugyanaz, a legtöbb testreszabás egy menetben hajtható végre, több szakasz helyett.

### <a name="mpos-vs-cpos"></a>MPOS és CPOS

Annak ellenére, hogy az MPOS és a CPOS nagyjából azonos, vannak fontos eltérések, amelyekkel pontosan tisztában kell lenni.

#### <a name="mpos"></a>MPOS

Windows, iOS vagy Android eszköz esetében az MPOS alkalmazás, amelynek a csomagolása, telepítése és karbantartása az eszközön történik.

- **Windows** – Az MPOS for Windows alkalmazás tartalmazza a teljes alkalmazáskódot és a beágyazott kiskereskedelmi futtatókörnyezetet (CRT). 
- **iOS/Android** – Ezeken a rendszereken az alkalmazás a CPOS-alkalmazáskód üzemeltetőjeként viselkedik. Ez azt jelenti, hogy az alkalmazáskód a CPOS-kiszolgálóról származik a Microsoft Azure vagy a Retail Store Scale Unit (RSSU) használatával. További tudnivalókért lásd: [Retail Store Scale Unit áttekintése](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>CPOS

Mivel a CPOS a böngészőben fut, az alkalmazás nincs telepítve az eszközön. Ehelyett a böngésző a CPOS-kiszolgálóról éri el az alkalmazás kódját. Ezért CPOS nem éri el közvetlenül a pénztárhardvert, és nem működik offline állapotban.

### <a name="store-deployment-considerations"></a>Üzletbeli telepítéssel kapcsolatos szempontok

A platform és a helyigény mellett a kiskereskedőnek ki kell választania egy rendszerbe állítási lehetőséget is. Az alábbi táblázat ismerteti a választható konfigurációkat az egyes pénztárra vonatkozó választási lehetőségekhez.

| Pénztáralkalmazás         | Retail Server | Offline elérhető. |
|-------------------------|---------------|-------------------|
| MPOS for Windows        | Felhő vagy RSSU | Igen               |
| MPOS iOS vagy Android rendszerhez | Felhő vagy RSSU | Nincs                |
| Felhő POS               | Felhő vagy RSSU | Nincs                |

#### <a name="retail-server"></a>Retail Server

A Retail Server összetevő a CRT-t tárolja. A CRT tartalmazza a pénztár által használt összes üzleti logikát, és hozzáférést biztosít a csatorna-adatbázishoz. Amíg online állapotban vannak, az üzlet minden pénztárügyfele a Retail Servert használja. A Retail Server telepíthető a felhőben vagy az üzletben (RSSU).

#### <a name="offline-mode"></a>Offline mód

Az MPOS for Windows támogatja a kapcsolat nélküli módot. Kapcsolat nélküli módban a pénztár továbbra is képes az eladások feldolgozására, még akkor is, ha megszakadt a kapcsolata a Retail Serverrel. A kapcsolat visszaállításakor szinkronizálható a csatorna-adatbázissal. Az MPOS a saját beágyazott CRT-példányát, valamint ideiglenesen saját helyi adatforrását (offline SQL Server adatbázis) használja. Az offline funkciókkal kapcsolatban további tudnivalókat lásd: [A POS pénztár kapcsolat nélküli üzemelése](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>Pénztár: periféria/hardver szempontok

A kiskereskedőknek azt is figyelembe kell venniük, hogyan fér hozzá a pénztár az olyan eszközökhöz és perifériákhoz, mint a nyomtatók, a pénztárfiókok és a fizetési terminálok. Csak az MPOS for Windows támogatja a közvetlen kommunikációt ezekkel az eszközökkel. Az MPOS for Windows Phone, iOS és Android, valamint a Cloud POS hardverállomást igényel ezeknek az eszközöknek az eléréséhez. A hardverállomás hozzárendelhető egy pénztárgéphez, de az üzletben található pénztárgépek közösen is osztozhatnak rajta. A hardverállomásokkal kapcsolatos további tudnivalókért lásd: [Kiskereskedelmi hardverállomás konfigurálása és telepítése](https://docs.microsoft.com/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Kivitelezési szempontok

A kiskereskedelmi üzletekben való pénztártelepítés tervezésekor vegye figyelembe a következőket:

- **Funkcionális követelmények** – Az alapvető üzleti folyamatok és képességek ugyanazok, függetlenül a platformtól, a helyigénytől vagy a telepítési topológiától. Emiatt a legtöbb kiskereskedőnek nem kell figyelembe vennie a funkcionális követelményeket a telepítés tervezésekor.
- **Kapcsolat** – A hálózati elérhetőség (nagykiterjedésű hálózat \[WAN\] és helyi hálózat \[LAN\]) gondos figyelmet igénylő jelentős tényező. A nulla helyigényű, felhő által szolgáltatott megoldások által kínált költségmegtakarítási és egyszerűsítési előnyök elvesznek, ha a rendszer nem érhető el a kritikus üzleti folyamatokhoz.

    Azokat az eseteket kivéve, amikor az adott eszköz kapcsolata nagyon megbízható és rugalmas, vagy amikor bizonyos mennyiségű leállást elfogadható a kiskereskedő számára, a következő lehetőségek valamelyikét ajánljuk:

    - Windows-alapú MPOS használata, és az offline mód engedélyezése.
    - Helyszíni RSSU telepítése.

    Ez a két lehetőség nem zárja ki kölcsönösen egymást. A legmegbízhatóbb topológia érdekében a kiskereskedők telepíthetnek egy helyi RSSU-t az internetkapcsolat vagy az Azure rendelkezésre állásától való függőség csökkentése érdekében, továbbá telepíthetnek olyan pénztárgépeket, amelyeken engedélyezve van a kapcsolat nélküli mód arra az esetre, ha probléma lépne fel a helyi kiszolgálóval vagy a hálózattal.

- **Hardvereszközök/perifériák** – A Retail POS rendszer egyik fontos szempontja az, hogy képes pénztárperifériák, például nyomtatók, pénztárfiókok és fizetési terminálok használatára. Annak ellenére, hogy a rendelkezésre álló pénztáropciók mindegyike képes perifériák használatára, csak az MPOS for Windows támogatja őket közvetlenül. A többi alkalmazáshoz egy vagy több hardverállomás szükség. Annak ellenére, hogy ez a megközelítés rugalmasságot nyújt, további összetevőket kell telepíteni, konfigurálni és karbantartani.
- **Rendszerkövetelmények** – A pénztáralkalmazás rendszerkövetelményei eltérőek lehetnek. Ügyeljen a legfrissebb információk ellenőrzésére a kiválasztás elvégzése előtt. Például: a CPOS böngészőben fut, ezért operációs rendszerek szélesebb körét támogatja. A rendszerkövetelményekkel kapcsolatos további tudnivalókat lásd: [Felhőtelepítések rendszerkövetelményei](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Telepítés és karbantartás** – A telepítési és karbantartási követelmények összetettsége változhat az alkalmazással és a telepítéssel kapcsolatos döntésektől függően. Például a felhő által szolgáltatott CPOS telepítéshez nem kell minden eszközön telepítést és frissítést végezni. Ezért ez a megközelítés jelentősen csökkenti a bonyolultságot és a költséget. Azonban ha telepíti az MPOS-t minden pénztárgépre, engedélyezi a kapcsolat nélküli módot, valamint megosztott hardverállomásokat is telepít, nagy mértékben növeli a kezelendő végpontok számát.

