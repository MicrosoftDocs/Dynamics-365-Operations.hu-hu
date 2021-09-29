---
title: Eltávolított vagy elavult Platform-funkciók
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.
author: sericks007
ms.date: 09/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 8910fc338f822e6b6b59acb0e6ee7a90db2b5007
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500109"
---
# <a name="removed-or-deprecated-platform-features"></a>Eltávolított vagy elavult Platform-funkciók

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](/dynamics/s-e/global/axtechrefrep_61) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="feature-deprecation-effective-august-2021"></a>Funkciók eltávolításával kapcsolatos értesítés; 2021 augusztusától érvényes

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Microsoft Azure SQL-jelentések a LifeCycle Services (LCS) szolgáltatásban

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** |   Minden tevékenységet és megfigyelést belsőleg, a platformon keresztül, az automatizáláson keresztül hajt végre a rendszer. Ehhez nem szükséges kézi beavatkozás.|
| **Felváltotta másik szolgáltatás?**   | Nincs |
| **Érintett területek**         | SQL-jelentések: jelenlegi DTU, aktuális DTU-részletek, Zárolási részletek lekérdezése, Aktuális csomagútmutató listája, Lekérdezésazonosítók listájának lekérdezése, SQL-lekérdezési csomag lekérése adott csomagazonosítóhoz, Lekérdezési csomagok és végrehajtási állapotok lekérdezése, Szabályozási konfiguráció lekérdezése, Várakozási statisztikák lekérése, Legdrágább lekérdezések listája |
| **Telepítési beállítás**              | Felhőtelepítés: a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Elavult: A tervezett eltávolítási dátum 2021 októbere. |

### <a name="azure-sql-actions-in-lcs"></a>Azure SQL-műveletek az LCS szolgáltatásban

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az LCS szolgáltatásban elavult néhány SQL-művelet.  |
| **Felváltotta másik szolgáltatás?**   | Nincs |
| **Érintett területek**         | SQL-műveletek: Csomagútmutató létrehozása a tervazonosító kényszerítésére, Csomagútmutató létrehozása táblatippek hozzáadásához, Csomagútmutató eltávolítása, Oldalzárolások letiltása/engedélyezése és eszkaláció zárolása, Tábla statisztikáinak frissítése, Index újjáépítése, Index létrehozása |
| **Telepítési beállítás**              | Felhőtelepítés: a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Elavult: A tervezett eltávolítási dátum 2021 októbere. |

## <a name="feature-deprecation-effective-may-2021"></a>Funkciók elavulásával kapcsolatos értesítés; 2021 májusától érvényes

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>A Lifecycle Services (LCS) globalizációs portálja

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az LCS globalizációs portálja elavult, mert ezt a funkciót már más LCS-alapú szolgáltatások biztosítják. |
| **Felváltotta másik szolgáltatás?**   | Igen, ennek a funkciónak az LCS [Megoldáskereső](../lifecycle-services/issue-search-lcs.md) és [a Dynamics szabályozó figyelmeztetések külésére szolgáló szolgáltatása](../lcs-solutions/submit-localization-alerts.md) lépett a helyére. |
| **Érintett területek**         | Az LCS globalizációs portálja|
| **Telepítési beállítás**              | Felhőbeli telepítés |
| **Állapot**                         | Elavult: A tervezett eltávolítási dátum 2022 májusa. |


## <a name="feature-removed-effective-january-28-2021"></a>A funkció eltávolítva 2021. január 28-án

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Kötegelt feladat az SQL-index töredezettségmentesítésének kezeléséhez

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A szolgáltatás el lett távolítva, hogy csökkentse indexkezelés vevők általi üzemeltetéséből, figyeléséből és fenntartásából származó járulékos költségeket. |
| **Felváltotta másik szolgáltatás?**   | A továbbiakban az index karbantartását a Microsoft szolgáltatásai végzik. Ez a folyamat folyamatosan, a felhasználói terhelések befolyásolása nélkül történik. |
| **Érintett területek**         | Finance and Operations-alkalmazásoknak|
| **Telepítési beállítás**              | Felhőtelepítés – a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Ez a funkció el lett távolítva. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.17 verziójához


### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Visual Studio legújabb verzióinak támogatásához néhány módosítást be tenni az X++ Visual Studio kiterjesztések esetében. Ezek a változtatások nem kompatibilisek a Visual Studio 2015 megoldással. |
| **Felváltotta másik szolgáltatás?**   | A Visual Studio 2017 váltja a Visual Studio 2015 verziót a telepített és szükséges verzióként. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: Frissítéskor a korábbi X++-eszközök törlődnek a Visual Studio 2015-ből, és a frissített eszközöket nem telepíti a rendszer a Visual Studio 2015-ön. Ez nincs hatással a tárolt buildekre. Buildelt virtuális gépek esetében a buildelési folyamatot (builddefiníciót) manuálisan kell frissíteni, hogy a függőség az MSBuild 14.0 (Visual Studio 2015) verzióról az MSBuild 15.0 (Visual Studio 2017) módosuljon, lásd: [Örökölt folyamat frissítése az Azure Pipelines szolgáltatásban](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Felhasználó 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A navigációs sáv jobb oldalán látható felhasználó beolvasása a Dynamics 365 fejlécvezérlőben található API használatával történt, amely már elavult. |
| **Felváltotta másik szolgáltatás?**   | A felhasználók a kezdőbetűiket ehelyett a navigációs sáv egy körében látják. Ugyanez a vizualizáció jelenleg fejlesztési gépeken is használatos. |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Eltávolítva a 10.0.17 verziójától kezdve |

### <a name="enterprise-portal-ep-deprecation"></a>Enterprise Portal (EP) elavulása  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics 2012 AX Enterprise Portal (EP) alkalmazással összefüggő metaadat-műtermékei elavultak, mert az EP soha nem volt támogatott a Finance and Operations alkalmazásokban. |
| **Felváltotta másik szolgáltatás?**   | Nincs |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: Az összes EP-kód eltávolítása a 2021. októberi kiadásban van ütemezve. |

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.15 verziójához

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2020 decemberétől hatályos Microsoft Internet Explorer 11 támogatás az összes Dynamics 365 termékre elavulttá válik, ezért az Internet Explorer 11 nem lesz támogatott 2021. augusztus után.<br><br>Ez hatással lesz azokra, akik Dynamics 365 termékeket használnak, amelyeket a Internet Explorer 11 interfészen való használatra terveztek. 2021. augusztus után az Internet Explorer 11 nem lesz támogatott az ilyen Dynamics 365 termékek esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Az összes Dynamics 365 termék |
| **Telepítési beállítás**              | Összes|
| **Állapot**                         | Elavult: Az Internet Explorer 11 támogatása 2021. augusztusban megszűnik.|


### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Visual Studio-bővítmény a metaadatok gyorsjavításának alkalmazásához

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A metaadatok gyorsjavításai már nem támogatottak a [One Version](../../fin-ops/get-started/one-version.md) 8.1-es, 2018 júliusában bevezetett verziófrissítései esetében. |
| **Felváltotta másik szolgáltatás?**   | Nem érhetők el az egyes metaadatokhoz tartozó gyorsjavítások a támogatott verziókhoz. Ezek helyett halmozott minőségi frissítésekre kerül sor. |
| **Érintett területek**         | Visual Studio-bővítmények |
| **Telepítési beállítás**              | Fejlesztési virtuális gépek |
| **Állapot**                         | A 10.0.15-ös verziónál a bővítmény már nem szerepel a Visual Studio-eszközök között. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.14 verziójához

### <a name="online-users-page"></a>Online felhasználók oldala 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez egy régebbi lap, amely a korábbi ügyfél-/kiszolgálóarchitektúrához készült. A lapon található adatok nem mindig pontosak, ami zavaró és félrevezető lehet. |
| **Felváltotta másik szolgáltatás?**   | Új oldalt fogunk biztosítani egy jövőbeli frissítésben.|
| **Érintett területek**         | Rendszerfelügyelet |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | 2021 októberétől ez a képernyő el lesz távolítva.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.13 verziójához


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Az SSRS-jelentés tulajdonságai között definiált egyéni kód 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az egyéni kód általában korlátozott kedvezményeket biztosít, a támogatásához viszont jelentős erőforrások és számítás szükséges. Az egyéni kódokat elsősorban a jelentések készítői használják, hogy nyilvános metódusokat hívjanak egyéni kódszerelvényekből. A felhőben tárolt szolgáltatás azonban nem támogatja az SSRS-jelentésekhez az egyéni szerelvényekre mutató hivatkozásokat. |
| **Felváltotta másik szolgáltatás?**   | A jelentés szerzője dönthetnek úgy továbbra nyilvános .NET-API-kra hivatkoznak a szövegdobozban lévő kifejezésekből származó matematikai, konverziós és formátumműveletekhez. További információ: [Kód hozzáadása jelentéshez (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Érintett területek**         | Egyéni kódot tartalmazó, RDL-jelentésben alkalmazásjelentési megoldások csoportjai. |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A 10.0.13-as verzióban a fordító figyelmeztetést küld az olyan példányok esetében, ahol egyéni kódokat észlel egy SSRS-jelentésdefinícióban. A hiba elhárításához nyissa meg a jelentéstervezési definíciót, és távolítsa el az összes egyéni kódot használó megoldás. Ezt a figyelmeztetést egy jövőbeli frissítés fordítói hibára fog lecserélni.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Három jQuery-összetevő programkönyvtárának frissítése 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A program három jQuery- összetevőfüggvénytárat frissít biztonsági javítások és a pénznem karbantartása céljából.   
| **Felváltotta másik szolgáltatás?**   | Az a következő könyvtárakat érinti: jQuery (3.5.0 és 2.1.4 verzió között ), jQuery UI (1.12.1 és 1.11.4 verzió között), jQuery qTip (3.0.3 és 2.2.1 verzió között). Áttelepítési útmutatót a jQuery online formában biztosítja.  |
| **Érintett területek**         | Kiterjeszthető vezérlőelemek, egyéni JavaScript-kód kifejezetten az elavult vagy törölt API-khoz |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A10.0.13-as verzió / 37-es platformfrissítéssel, a vevők tetszés szerint mozoghatnak a legújabb könyvtárakban, ha engedélyezik a „három jQuery összetevő-függvénytár frissítése” funkciót. Az új könyvtárakra történő áttérés kötelező lesz a 2021 áprilisi kiadásban, ez időt ad az érintett API-k áttelepítéséhez.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Meglévő rácsvezérlő/forceLegacyGrid() API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A meglévő rácsvezérlőt az új rácsvezérlő helyettesíti. |
| **Felváltotta másik szolgáltatás?**   | Az [új rácsvezérlő](../..//fin-ops/get-started/grid-capabilities.md) |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A 10.0.13 verzióban az új rácsvezérlő általánosan elérhető, és a vevők tetszés szerint be tudják kapcsolni ezt a funkciót. Az új rácsvezérlő alapértelmezés szerint a 2021. októberi kiadással lesz bekapcsolva,és a jelenleg célok szerint kötelező lesz 2022. áprilisban. Amikor az új rácsvezérlő használata kötelezővé válik, a **forceLegacyGrid()** API többé nem lesz figyelembe véve. |

### <a name="personalization-without-saved-views"></a>Mentett nézetek nélküli személyre szabás 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A személyre szabási alrendszer ki lett egészítve a mentett nézetek funkcióval, így nagyobb a teljesítménye, és további képességeket kínál. |
| **Felváltotta másik szolgáltatás?**   | Mentett nézetek |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A 10.0.13 vezió/Platform update 37, a mentett nézetek funkció általánosan elérhető, és a vevők tetszés szerint be tudják kapcsolni ezt a funkciót. A mentett nézetek funkció használata kötelezővé válik a 2021 októberi kiadástól. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.12 verziójához

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Érvénytelen mezők hivatkozásait tartalmazó rács vagy csoport vezérlő képernyő-kiterjesztések

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A rács vagy csoport vezérlőelem adatcsoport-tulajdonsága automatikusan megjeleníti a mezőcsoport összes mezőjét. A kiterjesztéssel hozzáadott rács vagy csoport tartalmazhat olyan mezőket, amelyek már nincsenek definiálva a mezőcsoportban, vagy hiányoznak azok a mezők, amelyek meg vannak határozva a mezőcsoportban. Ez inkonzisztens működést okozhat futásidőben. A Finance and Operations alkalmazások 10.0.12 verzióihoz tartozó platformfrissítések most már fordítási *figyelmeztetésként* kategorizálják ezt a problémát. A hiba elhárításához nyissa meg a képernyő-kiterjesztést, és mentse.
| **Felváltotta másik szolgáltatás?**   | Ezt a fordítói figyelmeztetést egy jövőbeli frissítés fordítói hibára fog lecserélni. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Egy fordítói figyelmeztetés került bevezetésre a Finance and Operations alkalmazások 10.0.12 verziójának platformfrissítéseiben. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.11 verziójához

### <a name="explicit-safe-lists-for-self-service-environments"></a>Explicit biztonságos lista az önkiszolgáló környezetek számára

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Módosult az a folyamat, amely az IP-cím biztonságos listákba történő helyezésére vonatkozik. Az önkiszolgáló megoldás már nem támogatja az IP biztonságos listák használatát. |
| **Felváltotta másik szolgáltatás?**   | További információ: [Azure Active Directory feltételez hozzáférés konfigurálása](/appcenter/general/configuring-aad-conditional-access).|
| **Érintett területek**         | Biztonság |
| **Telepítési beállítás**              | Felhőbeli |
| **Állapot**                         | Elavult: Ez a funkció teljes mértékben elavult az önkiszolgáló telepítések esetében. |

### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Visual Studio legújabb verzióinak támogatásához néhány módosítást be tenni az X++ Visual Studio kiterjesztések esetében. Ezek a változtatások nem kompatibilisek a Visual Studio 2015 megoldással. |
| **Felváltotta másik szolgáltatás?**   | A Visual Studio 2017 váltja a Visual Studio 2015 verziót a telepített és szükséges verzióként. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A 10.0.13-as verzió (37-es platformfrissítés) vagy újabb verzióra telepített virtuális gépek a Visual Studio 2017-et tartalmazzák. A 10.0.16-os verzió (40-es platformfrissítés) a Visual Studio 2015-ös támogatással rendelkező végleges kiadás. A csak Visual Studio 2015-tel rendelkező virtuális gépek nem tudnak frissíteni a 10.0.17-es verzióra (41-es platformfrissítés). |

### <a name="field-groups-containing-invalid-field-references"></a>Érvénytelen mező hivatkozásokat tartalmazó mezőcsoportok

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A tábla metaadatok definíciójában található mezőcsoportok olyan mezőhivatkozásokat tartalmazhatnak, amelyek nem érvényesek. Ezen mezőcsoportok telepítése esetén hibákat okozhatnak futásidőben a Financial Reporting és a Microsoft SQL Server Reporting Services (SSRS) szolgálatásokban. A 23-as platformfrissítés bevezetett egy fordítási *figyelmeztetést*, amely a metaadat-problémák kezelését teszi lehetővé. A Finance and Operations alkalmazások 10.0.11 verzióihoz tartozó platformfrissítések fordítási *hibaként* kategorizálják ezt a problémát.<p>Ezen hiba javításához kövesse az alábbi lépéseket.</p><ol><li>Távolítsa el az érvénytelen mezőhivatkozást a tábla a mezőcsoport-definíciójából.</li><li>Végezzen újrafordítást.</li><li>Győződjön meg arról, hogy minden hiba orvosolva lett.</li></ol> |
| **Felváltotta másik szolgáltatás?**   | Ez a fordítóhiba véglegesen lecseréli a fordítói figyelmeztetését.  |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A fordítói figyelmeztetés fordítói hiba a Finance and Operations-alkalmazások 10.0.11 verziójának platformfrissítéseiben. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Az SHA1 kivonatolási algoritmussal létrehozott ISV-licencek

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A független szoftvergyártói (ISV) licencek létrehozási folyamata módosult. További tájékoztatás: [Független szoftvergyártói (ISV) licencek](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Felváltotta másik szolgáltatás?**   | Igen. Licencek létrehozása a Windows PowerShell használatával. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: Az SHA1 kivonatolási algoritmussal létrehozott ISV-licencek. Ez az algoritmus a MakeCert segédprogrammal létrehozott tanúsítványokra épített, és ez a segédprogram elavult.<br><br>Elavult: Az SHA1 használata biztonsági vagy kivonatolási célokra. Az SHA1 2021 elejétől nem működik majd. Ezért a továbbiakban nem használható.<br><br>Eltávolítva : A Transport Layer Security (TLS) 1.0 és TLS 1.1 támogatása a bejövő vagy kimenő kérésekhez. |

## <a name="platform-update-32"></a>Platform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez biztonsági hiba volt, mert a módosítási kérelmet nem szándékolt felhasználó számára is lehetett elküldeni. Ez egy használhatósági probléma is volt, mivel a felhasználó rá volt kényszerítve, hogy meghatározza, hogy ki volt a kezdeményező, és manuálisan ki kellet jelölnie.  |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Munkafolyamat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A felhasználó kiválasztása legördülő lista el lett távolítva a 32-es platformfrissítésben. A módosítási kérelmeket a program automatikusan elküldi a létrehozónak, a szándéknak megfelelően. A funkciókkal kapcsolatos további tudnivalókat lásd: [Munkafolyamat-jóváhagyási folyamatok műveletei](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>A beágyazott részletező hivatkozások már nem támogatottak a felhőalapú szolgáltatások által megjelenített oldalszámmal ellátott dokumentumok esetében 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A szolgáltatás által megjelenített, dokumentumokba ágyazott navigációs URL-címek bizalmas üzleti adatokat is tartalmazhatnak. Biztonsági óvintézkedésként megszüntetjük a dokumentumok beágyazott részletező hivatkozásainak támogatását a vevők adatainak további védelme érdekében. A felhasználók számára is előnyös a jobb teljesítményt, miközben interaktívan állítanak elő dokumentumokat a módosítás eredményeképpen.  |
| **Felváltotta másik szolgáltatás?**   | Nincs |
| **Érintett területek**         | Jelentés |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Ez a funkció aktívan el lesz távolítva a szolgáltatásból.<br><br>A korszerű ügyfél számos lehetőséget kínál olyan nézetek készítésére, amelyek automatikusan létrejövő hivatkozásokat is tartalmaznak, hogy segítsék a navigálást az alkalmazásban. A szolgáltatás által megjelenített, oldalszámmal ellátott dokumentumok olyan külső kommunikációhoz ajánlottak, amelyeket e-mailben elküldenek, archiválnak és kinyomtatnak címzetteknek. A dokumentumok közvetlenül a böngészőben történő előnézetének élményét a tapasztalatok alapján javítottuk amely közvetlen hozzáférést biztosít a helyi nyomtatókhoz. A további tudnivalókat lásd: [PDF-dokumentumok előnézete beágyazott megjelenítővel](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
