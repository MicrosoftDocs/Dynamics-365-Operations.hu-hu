---
title: Optimalizálási tanácsadó – áttekintés
description: Ez a témakör azt írja le, hogy hogyan használható a optimalizálási művelet a pénzügyek és műveletek optimális konfigurációjának biztosítása érdekében.
author: kamaybac
ms.date: 07/23/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.author: kamaybac
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.assetid: ''
ms.search.industry: ''
ms.search.form: SelfHealingWorkspace
ms.openlocfilehash: f24e8dfecb04f928994bb5a197d32a7279022512
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281355"
---
# <a name="optimization-advisor-overview"></a>Optimalizálási tanácsadó – áttekintés

[!include [banner](../includes/banner.md)]

Ez a témakör azt írja le, hogy hogyan használható a optimalizálási művelet a pénzügyek és műveletek optimális konfigurációjának biztosítása érdekében.

## <a name="overview"></a>Áttekintés

A modul helytelen konfigurálása és beállítása hátrányosan befolyásolhatja az alkalmazás funkcióinak elérhetőségét, a rendszer teljesítményét és az üzleti folyamatok zavartalan működését. Az üzleti adatok minősége (például a helyesség, teljesség és az adatok tisztasága) is befolyásolja a rendszer teljesítményét, és egy szervezet döntéshozatali képességét, a termelékenységet és így tovább.

Az **Optimalizálási tanácsadó** munkaterület egy olyan eszköz, amely a kiemelt felhasználók, az üzleti elemzők, a funkcionális tanácsadók és az informatikai funkciók számára teszi lehetővé a problémák azonosítását a modulkonfigurációkban és az üzleti adatokban. Az optimalizálási tanácsadó javaslatot tesz a modulok konfigurációjának legjobb gyakorlatára, és azonosítja az elavult vagy helytelen üzleti adatokat.

Az optimalizálási tanácsadó rendszeres időközönként lefuttatja az ajánlott eljárás szabályait. Rendelkezésre áll egy alapértelmezett szabálykészlet, a felhasználók azonban olyan szabályokat is létrehozhatnak, amelyek egyediek a saját testreszabásaikra, független szoftverszállítók (ISV) megoldásaira és üzleti adatokra. További információ a szabályok létrehozásáról: [Szabályok létrehozása az Optimalizálási tanácsadóhoz](./create-rules-optimization-advisor.md).

Egy szabály megsértésének észlelésekor optimalizálási lehetőséget jön létre és jelenik meg az **Optimalizálási tanácsadó** munkaterületen. A felhasználó közvetlenül az **Optimalizálási tanácsadó** munkaterületről végezheti el a megfelelő javító intézkedéseket.

A lehetőségek lehetnek vállalatspecifikusak vagy vállalatközi jellegűek, attól függően, hogy milyen típusú beállításokat és adatokat érvényesít. A több vállalatot érintő lehetőségek minden vállalatnál megtekinthetők. A lehetőségek megtekintéséhez egy adott vállalat esetében először ki kell választania a vállalatot.

Szabványos biztonsági házirendek vonatkoznak az optimalizálási lehetőségekre. Például a **Raktárkezelés** modul konfigurációjához kapcsolódó optimalizálási lehetőségek csak olyan felhasználók számára láthatók, akik hozzáférnek a Raktárkezeléshez, és megváltoztathatják a beállításait.

Amikor műveletet hajt végre az optimalizálási lehetőségeken, a rendszer kiszámítja a lehetőség hatását az üzleti folyamatok futásidő-csökkentésének szempontjából. Sajnos ez a funkció nem használható az összes optimalizálási lehetőséghez.

Ha további tudnivalókat szeretne tudni az optimalizálásról, nézze meg [a rövid optimalizálási összefoglalót a Dynamics 365 Pénzügyi videofelvételen](https://www.youtube.com/watch?v=MRsAzgFCUSQ).

## <a name="optimization-rules"></a>Optimalizálási szabályok

Az Optimalizálási tanácsadó szabályok teljes listájának megtekintéséhez, és annak a megtekintéséhez, hogy milyen gyakran történik meg a szabályok kiértékelése, ugorjon a **Rendszerfelügyelet** &gt; **Időszakos feladatok** &gt; **Diagnosztikai érvényesítési szabály karbantartása** elemre. Csak az **Aktív** állapotú szabályok értékelésére kerül sor. Az értékelési gyakoriság beállítása lehet **Napi**, **Heti**, **Havi** vagy **Nem ütemezett**.

A nem ütemezett szabályok értékelésének kiváltására, vagy az időszakos szabályok megadott ütemezéstől eltérő felülvizsgálatára indítsa el a következőt: **Rendszerfelügyelet** &gt; **Időszakos feladatok** &gt; **Diagnosztikai ellenőrzési szabály ütemezése**. Ezután a **Diagnosztikai szabály ellenőrzése** párbeszédpanelen jelölje ki az értékelési gyakoriságot. Minden megadott gyakorisággal rendelkező szabály újraértékelésre kerül.

Az optimalizálási szabályok aktuális készletét a következő kategóriákba lehet osztani.

### <a name="module-configuration-and-setup"></a>Modulkonfiguráció és -beállítás

A Raktárkezelés beállítása bonyolult folyamat. A folyamat könnyebbé tételére egyes szabályokat a beállítások helyességének ellenőrzése érdekében vezettek be. Például egy szabály érvényesíti a raktári helyekre vonatkozó irányelveket rögzített termékváltozat-helyekre értékesítési rendelések és átmozgatási rendelések esetén.

Ezenkívül néhány szabály ellenőrzi, hogy a funkciók, amelyek engedélyezve vannak, ténylegesen használatban vannak-e. Például egy szabály határozza meg, hogy az **Alaptervezés** modult használja-e. Ha a szabály azt állapítja meg, hogy nem használja a modult, létrejön egy optimalizálási lehetőség, amely azt javasolja hogy kapcsolja ki a tervezési folyamatokat.

### <a name="system-configuration"></a>Rendszerkonfiguráció

Ha egy adott konfigurációs kulccsal vezérelhető funkció nincs használatban, optimalizálási lehetőség jön létre, és javasolja, hogy kapcsolja ki a konfigurációs kulcsot. Néhány példa a konfigurációs kulcsokra: **Tényleges súly**, **Költségvetés-tervezés**, **Projekt** és **Engedélyezett szállítók listája**.

### <a name="business-data-consistency-and-cleanup"></a>Üzleti adatok összefüggései és tisztítása

Ha az alapadatok nem megfelelők (például mértékegység-átváltások történnek olyan egységeknél, amelyek még nem lettek meghatározva, vagy mértékegység-átváltásoknál 0-val \[nullával\] osztás jelentkezik), optimalizálási lehetőség jön létre. amely javasolja, hogy helyesbítse az adatokat. 

Ha túl sok kötegeltfeladat-előzménybejegyzéssel, elavult cikkekkel, lezárt készleten lévő tételekkel raktárkezelésre engedélyezett cikkekhez stb. rendelkezik, vagy ha ezek a bejegyzések és cikkek túl régiek, akkor optimalizálási lehetőségek jönnek létre, amelyek javasolják az adatok megtisztítását. Az adatok tisztán tartásával javíthatja a rendszer általános teljesítményét.

### <a name="best-practices"></a>Gyakorlati tanácsok

Ha bizonyos üzleti folyamatokat nem a legjobb gyakorlatoknak megfelelően futtat (például ha a készlet-előzárást futtat, a készlet lezárása előtt, vagy ha az ütemezett köteget használ analitikus napló bejegyzéseinek kötegelt átviteléhez), az optimalizálási lehetőségek tájékoztatják Önt a legjobb gyakorlatról, és felkérik, hogy kövesse azt.

## <a name="optimization-opportunities"></a>Optimalizálási lehetőségek

Az optimalizálási szabályok értékelése során létrejövő optimalizálási lehetőségek megtekintéséhez nyissa meg az **Optimalizálási tanácsadó** munkaterületet.

Ezen a munkaterületen a lehetőséggel kapcsolatos további információkat a **További információ** kiválasztásával tekintheti meg. Ha azt szeretné, hogy a rendszer lépjen és javítsa a beállításokat, tisztítsa meg az adatokat stb., hogy Önnek ne magának kelljen megnyitnia a megfelelő lapokat, jelölje be a **Művelet végrehajtása** lehetőséget.

Nincs munkafolyamat az optimalizálási lehetőségekhez. Miután kiválasztotta a **Művelet végrehajtása** elemet használt egy a **További információt** párbeszédpanelen található navigációs útvonalat, az optimalizálási lehetőség eltűnik a listából. Ha a javító intézkedés nem oldja meg teljes mértékben a problémát, akkor a szabály következő értékelésénél újból létrejön a lehetőség.

Ha egy lehetőség nem vonatkozik az Ön szerepére, válassza az **Elrejtés a saját listából** lehetőséget. Még akkor is, ha a lehetőség mögött meghúzódó szabály később újra kiváltásra kerül, nem fogja látni a lehetőséget a listán.

Adott szabályok kiértékelésének inaktiválásához válassza a szabály által létrehozott lehetőséget, majd válassza az **Elemzés inaktiválása** elemet.

## <a name="additional-resources"></a>További erőforrások

[Optimalizálási tanácsadó szabályainak létrehozása](./create-rules-optimization-advisor.md)

[Optimalizálás a Dynamics 365 Pénzügyben (Video)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
