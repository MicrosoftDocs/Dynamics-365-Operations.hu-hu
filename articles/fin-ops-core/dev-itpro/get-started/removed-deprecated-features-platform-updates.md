---
title: A platform eltávolított vagy elavult funkciói
description: Ez a témakör olyan funkciókat ír le, amelyek már el vannak távolítva, illetve a pénzügyi és műveleti alkalmazások platformfrissítései során tervezett eltávolításra vannak tervezve.
author: sericks007
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b2eec4dd71baef54877b4139a331288bf37f4960
ms.sourcegitcommit: e4b6521337dfff3515f70086b0125d4c23308c71
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/11/2022
ms.locfileid: "9262298"
---
# <a name="removed-or-deprecated-platform-features"></a>A platform eltávolított vagy elavult funkciói

[!include [banner](../includes/banner.md)]

Ez a témakör olyan funkciókat ír le, amelyek már el vannak távolítva, illetve a pénzügyi és műveleti alkalmazások platformfrissítései során tervezett eltávolításra vannak tervezve.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

A pénzügyi és műveletalkalmazások objektumaival kapcsolatos részletes információk a Műszaki hivatkozási [jelentésekben találhatók](/dynamics/s-e/global/axtechrefrep_61). Ezeknek a jelentéseknek a különböző verzióit össze lehet hasonlítani, hogy megismerjük azokat az objektumokat, amelyek megváltoztak vagy el vannak távolítva a pénzügyi és műveleti alkalmazások egyes verzióiban.

## <a name="feature-deprecation-effective-august-2022"></a>Funkciók eltávolításával kapcsolatos értesítés; 2022 augusztusától érvényes

### <a name="lifecycle-services-lcs-features-deprecated-in-august-2022"></a>A Lifecycle Services (LCS) 2022 augusztusában elavult szolgáltatásai

A One Dynamics One Platform [munkamunka](/dynamics365-release-plan/2022wave2/finance-operations/finance-operations-crossapp-capabilities/one-dynamics-one-platform) részeként a következő LCS-funkciók elavultak.

| Funkció neve | AX 2012-hez használatos? | Pénzügy- és műveletalkalmazásokkal használatos? | Felváltotta másik szolgáltatás? |
|--------------|--------------------|----------------------------------------|------------------------------|
| Bejelentések | Igen | Igen | Igen: Az egyes projekt- és környezeti lapok értesítési címeket tartalmaznak. |
| Konfigurációkezelő | Igen | Nem | Nem |
| Elemzés a rendszer össze- és kiírása között | Igen | Nem | Nem |
| Visszajelzés és programhibák | Igen | Igen | Nem |
| Saját előfizetés | Igen | Igen | Nem |
| Office 365 | Igen | Igen | Igen: Azure Active Directory vagy Microsoft admin portal. |
| Hatás analyis | Nem | Igen | Nem |
| A gazdasági hatás becslésének teljes összege | Nem | Igen | Nem |
| Szolgáltatási kérelmek | Nem | Igen | Igen: [Önkiszolgáló telepítések](../deployment/infrastructure-stack.md) |
| SharePoint-integráció | Igen | Igen | Nem |
| Konfiguráció- és adatkezelő | Nem | Igen | Nem |
| Folyamatadat-csomagok | Nem | Igen | Igen: Adatimport exportálási keretrendszer (DIXF) |
| Beékítés frissítése | Nem | Igen | Igen: [Egyverziós](../lifecycle-services/oneversion-overview.md) szolgáltatásfrissítések állnak rendelkezésre. |
| Infrastruktúrabecslő | Igen | Nem | Nem |
| Licenc méretezése | Igen | Nem | Nem |
| Használatiprofil-készítő | Igen | Nem | Nem |
| Testreszabás-elemzés | Igen | Nem | Nem |
| Rendszerdiagnosztika | Igen | Igen | Nem |
| Visio üzletifolyamat-modellező kezelése | Igen | Igen | Nem |
| AX 2012 -es felhőkörnyezet-kezelés | Igen | Nem | Nem |
| RDFE Azure-csatlakoztató | Igen | Igen | Nem |
| AX 2012-es verziók | Igen | Nem | Nem |
| LCS-tárolóban tárolt munkaelemek | Igen | Igen | Nem |
| Gyorsjavítás-kérelmek | Igen | Igen | Nem |


### <a name="transport-layer-security-tls-rsa-cipher-suites"></a>Átviteli réteg biztonsága (TLS) RSA-kódcsomagok

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A rendszer eltávolítja a következő kódokat, hogy megfeleljenek a jelenlegi biztonsági protokolloknak.<br><br>TLS_RSA_WITH_AES_256_GCM_SHA384<br>TLS_RSA_WITH_AES_128_GCM_SHA256<br>TLS_RSA_WITH_AES_256_CBC_SHA256<br>TLS_RSA_WITH_AES_128_CBC_SHA256<br>TLS_RSA_WITH_AES_256_CBC_SHA<br>TLS_RSA_WITH_AES_256_CBC_SHA  |
| **Felváltotta másik szolgáltatás?**   | 2022 [. november 30-án kezdődően az ügyfelek csak a szabványos kódos csomagokat használhatja](/power-platform/admin/server-cipher-tls-requirements). Ez a módosítás hatással van a kiszolgálóinkkal kommunikáló ügyfelekre és kiszolgálókra, és hatással lehet például a külső fél integrációjára, amelyek nem a szabványos kódcsomagokhoz vannak hatással. |
| **Érintett területek**         | Finance and Operations alkalmazások |
| **Telepítési beállítás**              | Felhőtelepítések |
| **Állapot**                         | Elavult. Az ügyfeleknek 2022. november 30. előtt frissíteniük kell a kiszolgálókat. A TLS Cipher Suite rendelés konfigurálásával kapcsolatos további tudnivalókat lásd [a Szállítási réteg biztonságának (TLS) kezelése.](/windows-server/security/tls/manage-tls)  |


## <a name="feature-deprecation-effective-june-2022"></a>Funkció értékcsökkenése 2022. júniusban

### <a name="finance-and-operations-dynamics-365-mobile-application-and-mobile-platform"></a>Pénzügy és műveletek (Dynamics 365) mobilalkalmazás és mobil platform 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A pénzügyek és műveletek (Dynamics 365) alkalmazás és platform leárazása egyetlen mobil platformra, Power Apps azaz egy mobil platformra való konszolidálás érdekében. |
| **Felváltotta másik szolgáltatás?**   | Igen, a pénzügyet és a műveleteket túli mobil tapasztalatok alkalmazásadatai integrációval is felépíthetőek Power Platform. További részleteket [a](https://cloudblogs.microsoft.com/dynamics365/it/2022/06/03/finance-and-operations-dynamics-365-mobile-app-to-be-deprecated/) post post és [Building mobil tapasztalatokkal](../power-platform/build-mobile-experiences.md) talál. |
| **Érintett területek**         | Finance and Operations alkalmazások |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult. A támogatás végének dátuma 2024. október. |


## <a name="platform-updates-for-version-10029-of-finance-and-operations-apps"></a>A Pénzügyi és üzemeltetési alkalmazások 10.0.29-es verziójának platformfrissítései

### <a name="panorama-tab-style"></a>Tabulátorlap stílusa

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A lapok vízszintes görgetése igazodik a dátumozott elrendezésmintákhoz, amelyek ismert használhatósági és kisegítő lehetőségekkel kapcsolatos problémákat tartalmaznak.  |
| **Felváltotta másik szolgáltatás?**   | Nem, de más tabulátorstílusok továbbra is elérhetők. |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult. |


## <a name="feature-deprecation-effective-april-2022"></a>A funkció értékcsökkenése 2022. április 20-án hatályos.

### <a name="xml-url-resolution-in-data-management"></a>XML URL-cím feloldása az Adatkezelésben 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az XML URL-címfeloldás támogatását megszüntetjük, mivel ezt a rendszer biztonsági résként azonosította. Ez azt jelenti, hogy az XML-fájlokhoz társított külső erőforrásokat a továbbiakban nem lehet feloldani.  |
| **Felváltotta másik szolgáltatás?**   | Nem. |
| **Érintett területek**         | Finance and Operations alkalmazások |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult. |

## <a name="feature-deprecation-effective-march-14-2022"></a>A funkció értékcsökkenése 2022. március 14-én hatályos.

### <a name="xslt-scripting-in-data-management"></a>XSLT-parancsfájlok az Adatkezelésben

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az XSLT parancsfájlok használata az Adatkezelésben elavult, így javítható a biztonság és az adatbiztonság a pénzügyi és műveleti alkalmazásokon belül.  |
| **Felváltotta másik szolgáltatás?**   | Nem. A vevőknek és az isV-knek érdemes megfontolni, hogy XSLT-parancsfájlok használata esetén az X++ nyelv alapján újra legyen edzve a megoldásuk. |
| **Érintett területek**         | Finance and Operations alkalmazások |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult <br><br>**Kivétel:** AZ XLST parancsfájlt jelenleg használó vevők. A verzió a 10.0.30-as vagy újabb verzióra való frissítésig továbbra is használható. Korábbi verziók esetén a kivétel 2023. január 31-én lejár. A kivétellel értesítő vevők értesítést kaptak az Microsoft 365 Adminisztrációs központban elérhető Üzenetközpontban. |

## <a name="feature-removal-effective-october-2021"></a>2021. októbertől hatályos funkcióeltávolítás

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Microsoft Azure SQL-jelentések a LifeCycle Services (LCS) szolgáltatásban

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Minden tevékenységet és megfigyelést belsőleg, a platformon keresztül, az automatizáláson keresztül hajt végre a rendszer. Ehhez nem szükséges kézi beavatkozás.|
| **Felváltotta másik szolgáltatás?**   | Igen, jelenleg egy automatizált rendszer van, amely ezeket a képességeket elavulttá teszi. |
| **Érintett területek**         | SQL-jelentések: jelenlegi DTU, aktuális DTU-részletek, Zárolási részletek lekérdezése, Aktuális csomagútmutató listája, Lekérdezésazonosítók listájának lekérdezése, SQL-lekérdezési csomag lekérése adott csomagazonosítóhoz, Lekérdezési csomagok és végrehajtási állapotok lekérdezése, Szabályozási konfiguráció lekérdezése, Várakozási statisztikák lekérése, Legdrágább lekérdezések listája |
| **Telepítési beállítás**              | Felhőtelepítés: a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Kivéve |

### <a name="azure-sql-actions-in-lcs"></a>Azure SQL-műveletek az LCS szolgáltatásban

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az LCS szolgáltatásban elavult néhány SQL-művelet. Minden tevékenységet és megfigyelést belsőleg, a platformon keresztül, az automatizáláson keresztül hajt végre a rendszer. Ehhez nem szükséges kézi beavatkozás. |
| **Felváltotta másik szolgáltatás?**   | Igen, jelenleg egy automatizált rendszer van, amely ezeket a képességeket elavulttá teszi. |
| **Érintett területek**         | SQL-műveletek: Csomagútmutató létrehozása a tervazonosító kényszerítésére, Csomagútmutató létrehozása táblatippek hozzáadásához, Csomagútmutató eltávolítása, Oldalzárolások letiltása/engedélyezése és eszkaláció zárolása, Tábla statisztikáinak frissítése, Index újjáépítése, Index létrehozása |
| **Telepítési beállítás**              | Felhőtelepítés: a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Kivéve |


## <a name="feature-deprecation-effective-october-2021"></a>Funkciók eltávolításával kapcsolatos értesítés; 2021 októberétől érvényes

### <a name="show-related-document-attachments-feature"></a>"Kapcsolódó dokumentummellékletek megjelenítése" funkció

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció nem várt eredményeket adott vissza. |
| **Felváltotta másik szolgáltatás?**   | Nem. A funkcióval kapcsolatos további tervek kommunikálását a szokásos kiadási hullám közzétételi folyamata fogja tartalmazni. |
| **Érintett területek**         | Webes ügyfél - Dokumentummelléklet-élmény |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások 10.0.23-as verziójának platformfrissítései

### <a name="ondbsynchronize-event"></a>OnDBSynchronize esemény

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az esemény végrehajtásához nincs vezérlő. |
| **Felváltotta másik szolgáltatás?**   | Igen, helyezze át **az OnDBSynchronize** esemény által előfizetett meglévő metódusokat egy SysSetup kiterjesztett osztályba. |
| **Érintett területek**         | Adatbázis szinkronizálása |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult. A tervezett eltávolítás dátuma: 2022. október. |


### <a name="systemnotificationsmanageraddnotification-api"></a>SystemNotificationsManager.AddNotification API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Microsoft további paramétereket kér az értesítések hozzáadásakor. |
| **Felváltotta másik szolgáltatás?**   | Igen, a **SystemNotificationsManager.AddSystemNotification()** API. Az API-hoz explicit módon be kell állítania a Létrehozott értesítésekhez az ExpirationDateTime és a RuleID értékeket. |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult. A tervezett eltávolítás dátuma: 2023. április. |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások 10.0.21-es verziójának platformfrissítései

### <a name="skype-for-business-online-support"></a>Skype for Business Online-támogatás

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Skype for Business Online szolgáltatás ki lett vezetve. A további tudnivalókat lásd: [A Skype for Business Online szolgáltatás ki lett vezetve](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601). |
| **Felváltotta másik szolgáltatás?**   | Jelenleg nem, bár előfordulhat, hogy a jövőben megfontoljuk a Teams jelenlét hozzáadását.|
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult. A10.0.21-es kiadásban már ki van kapcsolva a **Skype engedélyezve** beállítás. A beállítás eltávolítása 2022. áprilisára várható; A funkció azonban akkor áll le, amikor a Skype csapat lezárja a szolgáltatást. |
 
## <a name="feature-deprecation-effective-august-2021"></a>Funkciók eltávolításával kapcsolatos értesítés; 2021 augusztusától érvényes

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Microsoft Azure SQL-jelentések a LifeCycle Services (LCS) szolgáltatásban

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Minden tevékenységet és megfigyelést belsőleg, a platformon keresztül, az automatizáláson keresztül hajt végre a rendszer. Ehhez nem szükséges kézi beavatkozás.|
| **Felváltotta másik szolgáltatás?**   | Igen, jelenleg egy automatizált rendszer van, amely ezeket a képességeket elavulttá teszi. |
| **Érintett területek**         | SQL-jelentések: jelenlegi DTU, aktuális DTU-részletek, Zárolási részletek lekérdezése, Aktuális csomagútmutató listája, Lekérdezésazonosítók listájának lekérdezése, SQL-lekérdezési csomag lekérése adott csomagazonosítóhoz, Lekérdezési csomagok és végrehajtási állapotok lekérdezése, Szabályozási konfiguráció lekérdezése, Várakozási statisztikák lekérése, Legdrágább lekérdezések listája |
| **Telepítési beállítás**              | Felhőtelepítés: a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Elavult: A tervezett eltávolítási dátum 2021 októbere. |

### <a name="azure-sql-actions-in-lcs"></a>Azure SQL-műveletek az LCS szolgáltatásban

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az LCS szolgáltatásban elavult néhány SQL-művelet. Minden tevékenységet és megfigyelést belsőleg, a platformon keresztül, az automatizáláson keresztül hajt végre a rendszer. Ehhez nem szükséges kézi beavatkozás. |
| **Felváltotta másik szolgáltatás?**   | Igen, jelenleg egy automatizált rendszer van, amely ezeket a képességeket elavulttá teszi. |
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
| **Érintett területek**         | Finance and Operations alkalmazások|
| **Telepítési beállítás**              | Felhőtelepítés – a Microsoft által kezelt működési környezeteket és a 2.-tól az 5. szintig tartó tesztkörnyezeteket érinti. |
| **Állapot**                         | Ez a funkció el lett távolítva. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>A Pénzügyi és üzemeltetési alkalmazások 10.0.17-es verziójának platformfrissítései


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
| **Elavulás/eltávolítás oka** | A Dynamics AX 2012 Enterprise Portal (EP) metaadat-műtermékei elavultak, mert az EP soha nem volt támogatott a pénzügyi és műveleti alkalmazásokban. |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: Az összes EP-kód eltávolítása a 2021. októberi kiadásban van ütemezve. |

## <a name="deprecation-effective-december-2020"></a>Értékcsökkenés 2020. december 20-án hatályos

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Microsoft 2020 Internet Explorer . december 11-e óta támogatja minden Dynamics 365 termék és a Dynamics Lifecycle Services (LCS) használatát, Internet Explorer 2021. augusztus óta pedig 11 nem lesz támogatott.<br><br>Ez hatással lesz az ügyfelekre, akik a Dynamics 365 termékeket és az LCS-t Internet Explorer használják, és 11 felületet használnak. 2021 Internet Explorer . augusztus után 11 nem lesz támogatott az ilyen Dynamics 365 termékek és LCS esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Minden Dynamics 365 termék és LCS |
| **Telepítési beállítás**              | Minden|
| **Állapot**                         | Elavult: Az Internet Explorer 11 támogatása 2021. augusztusban megszűnik.|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>A Pénzügyi és műveleti alkalmazások 10.0.15-ös verziójának platformfrissítései

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Visual Studio-bővítmény a metaadatok gyorsjavításának alkalmazásához

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A metaadatok gyorsjavításai már nem támogatottak a [One Version](../../fin-ops/get-started/one-version.md) 8.1-es, 2018 júliusában bevezetett verziófrissítései esetében. |
| **Felváltotta másik szolgáltatás?**   | Nem érhetők el az egyes metaadatokhoz tartozó gyorsjavítások a támogatott verziókhoz. Ezek helyett halmozott minőségi frissítésekre kerül sor. |
| **Érintett területek**         | Visual Studio-bővítmények |
| **Telepítési beállítás**              | Fejlesztési virtuális gépek |
| **Állapot**                         | A 10.0.15-ös verziónál a bővítmény már nem szerepel a Visual Studio-eszközök között. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások 10.0.14-es verziójának platformfrissítései

### <a name="online-users-page"></a>Online felhasználók oldala 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez egy régebbi lap, amely a korábbi ügyfél-/kiszolgálóarchitektúrához készült. A lapon található adatok nem mindig pontosak, ami zavaró és félrevezető lehet. |
| **Felváltotta másik szolgáltatás?**   | Új oldalt fogunk biztosítani egy jövőbeli frissítésben.|
| **Érintett területek**         | Rendszerfelügyelet |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | 2021 októberétől ez a képernyő el lesz távolítva.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások 10.0.13-as verziójának platformfrissítései


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Az SSRS-jelentés tulajdonságai között definiált egyéni kód 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az egyéni kód általában korlátozott kedvezményeket biztosít, a támogatásához viszont jelentős erőforrások és számítás szükséges. Az egyéni kódokat elsősorban a jelentések készítői használják, hogy nyilvános metódusokat hívjanak egyéni kódszerelvényekből. A felhőben tárolt szolgáltatás azonban nem támogatja az SSRS-jelentésekhez az egyéni szerelvényekre mutató hivatkozásokat. |
| **Felváltotta másik szolgáltatás?**   | A jelentés szerzője dönthetnek úgy továbbra nyilvános .NET-API-kra hivatkoznak a szövegdobozban lévő kifejezésekből származó matematikai, konverziós és formátumműveletekhez. További információ: [Kód hozzáadása jelentéshez (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs).  |
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


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások 10.0.12-es verziójának platformfrissítései

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Érvénytelen mezők hivatkozásait tartalmazó rács vagy csoport vezérlő képernyő-kiterjesztések

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A rács vagy csoport vezérlőelem adatcsoport-tulajdonsága automatikusan megjeleníti a mezőcsoport összes mezőjét. A kiterjesztéssel hozzáadott rács vagy csoport tartalmazhat olyan mezőket, amelyek már nincsenek definiálva a mezőcsoportban, vagy hiányoznak azok a mezők, amelyek meg vannak határozva a mezőcsoportban. Ez inkonzisztens működést okozhat futásidőben. A pénzügyi és műveletalkalmazások 10.0.12-es verziójának platformfrissítései most fordítói figyelmeztetésként kategorizálják ezt a *problémát*. A hiba elhárításához nyissa meg a képernyő-kiterjesztést, és mentse.
| **Felváltotta másik szolgáltatás?**   | Ezt a fordítói figyelmeztetést egy jövőbeli frissítés fordítói hibára fog lecserélni. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Fordítói figyelmeztetés jelenik meg a pénzügyi és műveleti alkalmazások 10.0.12-es verziójának platformfrissítéseiben. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>A Pénzügyi és műveletalkalmazások 10.0.11-es verziójának platformfrissítései

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
| **Elavulás/eltávolítás oka** | A tábla metaadatok definíciójában található mezőcsoportok olyan mezőhivatkozásokat tartalmazhatnak, amelyek nem érvényesek. Ezen mezőcsoportok telepítése esetén hibákat okozhatnak futásidőben a Financial Reporting és a Microsoft SQL Server Reporting Services (SSRS) szolgálatásokban. A 23-as platformfrissítés bevezetett egy fordítási *figyelmeztetést*, amely a metaadat-problémák kezelését teszi lehetővé. A pénzügyi és műveletalkalmazások 10.0.11-es verziójának platformfrissítései fordítói hibaként kategorizálják ezt a *problémát*.<p>Ezen hiba javításához kövesse az alábbi lépéseket.</p><ol><li>Távolítsa el az érvénytelen mezőhivatkozást a tábla a mezőcsoport-definíciójából.</li><li>Végezzen újrafordítást.</li><li>Győződjön meg arról, hogy minden hiba orvosolva lett.</li></ol> |
| **Felváltotta másik szolgáltatás?**   | Ez a fordítóhiba véglegesen lecseréli a fordítói figyelmeztetését.  |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A fordító figyelmeztetés egy fordítói hiba a pénzügyi és műveleti alkalmazások 10.0.11-es verziójának platformfrissítései során. |

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
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Jelentés |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Ez a funkció aktívan el lesz távolítva a szolgáltatásból.<br><br>A korszerű ügyfél számos lehetőséget kínál olyan nézetek készítésére, amelyek automatikusan létrejövő hivatkozásokat is tartalmaznak, hogy segítsék a navigálást az alkalmazásban. A szolgáltatás által megjelenített, oldalszámmal ellátott dokumentumok olyan külső kommunikációhoz ajánlottak, amelyeket e-mailben elküldenek, archiválnak és kinyomtatnak címzetteknek. A dokumentumok közvetlenül a böngészőben történő előnézetének élményét a tapasztalatok alapján javítottuk amely közvetlen hozzáférést biztosít a helyi nyomtatókhoz. A további tudnivalókat lásd: [PDF-dokumentumok előnézete beágyazott megjelenítővel](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

