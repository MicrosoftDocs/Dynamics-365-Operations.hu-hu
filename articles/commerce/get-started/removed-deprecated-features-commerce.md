---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban
description: Ez a témakör olyan funkciókat ismertet, amelyek már el vannak távolítva, illetve amelyek eltávolítása tervezett Dynamics 365 Commerce.
author: josaw1
ms.date: 08/23/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 59ffcc00d67f6538980dec8965f894eb51f7230d
ms.sourcegitcommit: 649f1db26da8f20602f11180fc565b7c59eaf545
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337596"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör olyan funkciókat ismertet, amelyek már el vannak távolítva, illetve amelyek eltávolítása tervezett Dynamics 365 Commerce.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Egy *elavult* funkció nincs aktív fejlesztésben, és a későbbi frissítésben már valószínűleg nem fog törlődni.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A pénzügyi és műveletalkalmazások objektumaival kapcsolatos részletes információk a Műszaki hivatkozási [jelentésekben találhatók](/dynamics/s-e/). Ezeknek a jelentéseknek a különböző verzióit össze lehet hasonlítani, hogy megismerjük azokat az objektumokat, amelyek megváltoztak vagy el vannak távolítva a pénzügyi és műveleti alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-commerce-10029-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.29 kiadásában

### <a name="commerce-parameters-setting---allow-price-adjustments-to-increase-product-price"></a>Kereskedelmi paraméterek beállítása - Az árkorrekciók engedélyezése a termék árának növeléséhez

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezzel a beállítással szabályozható, hogy az árkorrekciós funkció lehetővé teszi-e a termékár növelését. Ha ez a paraméter ki van kapcsolva, az árkorrekciós funkció szervezetei csak az alapárnál és a kereskedelmi szerződés eladási árnál alacsonyabb egységárat állíthatnak be. Ezt a beállítást elavultuk, mert az árkorrekciós funkció frissült, hogy a mezőből kivehető a kétes visszaigazítás (csökkentés vagy csökkentés). |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Árképzés és engedmények |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: Ez a beállítás alapértelmezés szerint be van kapcsolva a Commerce 10.0.29-es verziója óta, és 2023 októberében törlődik. |

### <a name="commerce-parameters-setting---enable-price-report-for-retail-store"></a>Kereskedelmi paraméterek beállítása - Árjelentés engedélyezése a kiskereskedelmi áruházhoz

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezzel a beállítással szabályozható, hogy az árjelentés funkció használható-e az üzlet konfigurációs űrlapja segítségével. Ezt a beállítást elavultuk, mert az üzlet konfigurációs képernyője frissült, hogy mindig az árjelentési funkciót alapértelmezett funkcióként működtetse. |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Árképzés és engedmények |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: Ez a beállítás 2023 októberében törlődik. |

### <a name="commerce-parameters-setting---use-todays-date-to-calculate-prices"></a>Kereskedelmi paraméterek beállítása – az árak kiszámítása a mai dátum alapján

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az ellátásilánc-kezelési (SCM) árképzési motor támogatja az árképzési számítást a kért szállítási dátum vagy a kért kézhezvételi dátum alapján, a mai dátummal együtt. ACommerce árképzési motor csak a mai dátumon alapuló árképzési számítást támogatja. Az SCM- és a Commerce-funkciókat is használni képes vevők esetében ezt a beállítást meg lehet adni, **és** javasolt, hogy a vevők mindig Igen beállítást adjanak meg, hogy a két árképzési motor együtt működjön. A beállítás elavult, mivel nem módosítja a számítás viselkedését, és ezek redundánsak. |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Árképzés és engedmények |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | Elavult: Ez a beállítás alapértelmezés szerint be van kapcsolva a Commerce 10.0.29-es verziója óta, és 2023 októberében törlődik. |

## <a name="feature-deprecation-effective-july-2022"></a>Funkció értékcsökkenése 2022. július 2-án

### <a name="commerce-analytics-preview"></a>Commerce elemzések (Előzetes verzió)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics 365 Commerce csoport elemezte a Commerce Analytics (Előnézet) szolgáltatás használatát és felvételét, és úgy döntöttek, hogy a továbbiakban nem hozzák előre a funkciót az általános elérhetőségnek.   |
| **Felváltotta másik szolgáltatás?**   | Jelenleg a Commerce Analytics (Preview) szolgáltatást nem cseréli le egy másik funkció vagy megoldás. A nyers tranzakciók és alapadatok pénzügyi és műveleti alkalmazásokból történő exportálása továbbra is elérhető lesz az Azure-adatügyletekbe, [mint azt a Pénzügyi és műveleti alkalmazások Adatexportakciókba exportálása is folytatja](../../fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake.md). A partnerek és a vevők ezt az adatfolyamot az üzleti igénynek megfelelő, bármilyen tervezett elemzési jelentés szerzője számára biztosítják.
| **Érintett területek**         | Commerce elemzések (Előzetes verzió) |
| **Telepítési beállítás**              | Minden |
| **Állapot**                         | A funkció letiltásának 2022. augusztus 30-ig kell lennie.  Ettől a dátumtól már nem történik frissítés a Power BI Commerce analitikában (Előnézet) által biztosított aktuális jelentésekben.     |

## <a name="features-removed-or-deprecated-in-the-commerce-10021-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.21 kiadásában

[!include [banner](../includes/preview-banner.md)]

### <a name="overlapping-discounts-handling-setting-in-commerce-parameters"></a>Átfedő engedménykezelés beállítása a Commerce paramétereiben

A Commerce rendszer 10.0.21-es verziójában elavult a **Commerce paraméterek** oldalon az **Átfedő kedvezmények kezelése** beállítás. A Commerce árképzési motor innentől egyetlen algoritmust használ az átfedő engedmények optimális kombinációjának meghatározására.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | <p>A Commerce paraméterek **Átfedő engedmények kezelése** beállítása határozza meg, hogy hogyan keresi meg a Commerce árképzési motor az átfedő engedményeket, és határozza meg az átfedő engedmények optimális kombinációját. Jelenleg három lehetőség áll rendelkezésre:<p><ul><li> **Legjobb teljesítmény** – Ez a beállítás speciális heurisztikus algoritmust és a [marginálisérték-rangsorolás](../optimal-combination-overlapping-discounts.md) módszerét használja a prioritás meghatározására, értékelésére és a legjobb engedménykombináció gyors meghatározására.</li><li>**Kiegyensúlyozott számítás** – az aktuális kódbázisban ez a beállítás a **Legjobb teljesítmény** beállításhoz hasonló módon működik. Emiatt gyakorlatilag egy ismétlődő beállításról van szó.</li><li>**Teljes számítás** – Ez a beállítás egy régi algoritmust használ, amely az árszámítás során minden lehetséges engedménykombináción végig megy. Nagy sorokat és mennyiségeket eredményező rendelések esetén ez a beállítás teljesítménybeli problémákat okozhat.</li></ul><p>A konfigurálás egyszerűsítése, a teljesítmény javítása és a régi algoritmus által okozott események csökkentése érdekében teljesen eltávolítjuk az átfedő engedmények kezelési beállítását, **és** frissítjük a Commerce árképzési motor belső logikáját, hogy most csak a speciális algoritmust használja (**vagyis** a legjobb teljesítménybeállítást elát csökkentő algoritmust).</p> |
| **Felváltotta másik szolgáltatás?**   | Nem. A funkció eltávolítása előtt ajánlott a **Kiegyensúlyozott számítás** vagy a **Teljes számítása** beállítást kapcsolót **Legjobb teljesítmény** értékre állítani. |
| **Érintett területek**         | Árképzés és engedmények |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A 10.0.21-es kiadástól az **Átfedő engedmények kezelése** beállítás törlődik a Commerce rendszer 2022. októberi paramétereiből. |

### <a name="retail-sdk-distributed-by-using-lifecycle-services"></a>Kiskereskedelmi SDK a Lifecycle Services használatával

A kiskereskedelmi SDK-t a Lifecycle Services (LCS) csomagban szállítjuk. Ez a terjesztési mód a 10.0.21-es kiadásban elavult. A jövőben a kiskereskedelmi SDK referenciacsomagokat, könyvtárakat és mintákat a GitHub nyilvános tárolóiban teszik közzé.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A kiskereskedelmi SDK az LCS-ben kerül szállításra. Az LCS-folyamat néhány órát vesz igénybe, és a folyamatot minden frissítésnél meg kell ismételni. A jövőben a kiskereskedelmi SDK referenciacsomagokat, könyvtárakat és mintákat a GitHub nyilvános tárolóiban teszik közzé. A kiterjesztett minták és referenciacsomagok könnyen fogyaszthatók, és a frissítések néhány perc alatt befejeződnek. |
| **Felváltotta másik szolgáltatás?**   |  [Töltse le a kiskereskedelmi SDK mintákat és referenciacsomagokat a GitHubról és innen: NuGet](../dev-itpro/retail-sdk/sdk-github.md) |
| **Érintett területek**         | Retail SDK |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Megszűnt: A 10.0.21-es kiadástól kezdve az LCS VM-eken keresztül szállított SDK 2023 októberében eltávolításra kerül. |

### <a name="retail-deployable-package-and-combined-pos-hardware-station-and-cloud-scale-unit-installers"></a>Kiskereskedelmi telepíthető csomag és kombinált POS, hardverállomás és Cloud Scale egység telepítői

A kiskereskedelmi SDK MSBuild segítségével létrehozott kiskereskedelmi telepíthető csomagok a 10.0.21-es verzióban elavulttá váltak. A jövőben használja a Cloud Scale Unit (CSU) csomagot a Cloud Scale unit bővítményekhez (Commerce Runtime, csatorna adatbázis, Headless commerce API-k, Fizetések és Cloud Point of Sale (POS)). Használja a csak bővítményt tartalmazó telepítőket a POS, a hardverállomás és a felhőskála önállóan üzemeltetett egységéhez.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A kiskereskedelmi telepíthető csomag egy olyan kombinált csomag, amely a bővítőcsomagok és telepítők teljes készletét tartalmazza. Ez a kombinált csomag összetetté teszi a telepítést, mivel a CSU-bővítmények a Cloud scale egységbe kerülnek, a telepítők pedig az üzletekben kerülnek telepítésre. A telepítők tartalmazzák a bővítményt és az alapterméket, ami megnehezíti a frissítéseket. Minden frissítéskor kódegyesítésre és csomaggenerálásra van szükség. A folyamat egyszerűsítése érdekében a bővítménycsomagok mostantól komponensekre vannak bontva a könnyebb telepítés és kezelés érdekében. Az új megközelítéssel a bővítmények és az alaptermék telepítői elkülönülnek, és egymástól függetlenül, kódegyesítés vagy újracsomagolás nélkül karbantarthatók és frissíthetők.|
| **Felváltotta másik szolgáltatás?**   | CSU-bővítések, POS-bővítések telepítői, hardverállomás-bővítések telepítői |
| **Érintett területek**         | Dynamics 365 Commerce bővítés és telepítés |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Megszűnt: A 10.0.21-es kiadástól kezdve a RetailDeployablePackage LCS-ben történő telepítésének támogatása 2022 októberében megszűnik. |

További tájékoztatás:

+ [Külön csomag létrehozása a kereskedelmi felhőskála egységhez (CSU)](../dev-itpro/retail-sdk/retail-sdk-packaging.md#generate-a-separate-package-for-commerce-cloud-scale-unit-csu)
+ [Modern POS-bővítménycsomag létrehozása](../dev-itpro/pos-extension/mpos-extension-packaging.md)
+ [A POS integrálása egy új hardvereszközzel](../dev-itpro/hardware-device-extension.md)
+ Kódminták
    + [Cloud Scale egység](https://github.com/microsoft/Dynamics365Commerce.ScaleUnit)
    + [POS, CSU és hardverállomás](https://github.com/microsoft/Dynamics365Commerce.InStore)

### <a name="modernpossln-and-cloudpossln-in-the-retail-sdk"></a>ModernPos.Sln és CloudPos.sln a Retail SDK készletben

POS-bővítmény fejlesztés a ModernPos.sln, CloudPos.sln, POS használatával. Az Extension.csproj és a POS mappa elavult a 10.0.21-es kiadásban. A jövőben használja a POS-független csomagolási SDK-t a POS-bővítésekhez.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A kiskereskedelmi SDK korábbi verzióiban, ha vannak POS-bővítmények, a POS legújabb verziójára való frissítéshez kódegyesítésre és újracsomagolásra van szükség. A kódegyesítés időigényes frissítési folyamat volt, és a teljes Retail SDK-t fenn kellett tartania a tárolóban. A POS.App projektet is le kellett fordítania. A független csomagolási modell használatával csak a kiterjesztést kell karbantartania. A POS-bővítmények legújabb verziójára való frissítés olyan egyszerű, mint a NuGet csomag verziójának frissítése, amelyet a projekt fogyaszt. A kiterjesztések önállóan is telepíthetők, a szolgáltatások pedig a kiterjesztések telepítőit használják. Az alap POS külön telepíthető és karbantartható, és nincs szükség kódegyesítésre vagy újracsomagolásra az alap telepítővel vagy kóddal. |
| **Felváltotta másik szolgáltatás?**   | [POS-független csomagolási SDK](../dev-itpro/pos-extension/pos-extension-getting-started.md) |
| **Érintett területek**         | Dynamics 365 Commerce POS bővítés és telepítés |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Megszűnt: A 10.0.21-es kiadástól kezdve a ModernPos.Sln, CloudPOs.sln és POS.Extensons.csproj csomagok és bővítmények kombinált POS csomagok és bővítmény modelljének támogatása a Retail SDK-ban 2023 októberében megszűnik. |

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.17 kiadásában

### <a name="full-dataset-generation-interval-is-deprecated"></a>A teljes adatkészlet-generálás intervalluma elavult

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezzel a kiadással kezdődően a Dynamics 365 központi felületén a **Commerce ütemezés paraméterei** űrlapjában a **Teljes adatkészlet-generálás intervalluma napokban** mező elavult lesz. A kiadás elkezdődhet is, vizuálisan el lesz távolítva a mező, így az értéket nem lehet szerkeszteni. Ez **0** érték marad. |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Dynamics 365 Commerce |
| **Telepítési beállítás**              | Minden|
| **Állapot**                         | Elavult. Ne használja ezt a mezőt, vagy ne módosítsa az értékét.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.15 kiadásában

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2020 decemberétől hatályos Microsoft Internet Explorer 11 támogatás az összes Dynamics 365 termékre elavulttá válik, ezért az Internet Explorer 11 nem lesz támogatott 2021. augusztus után.<br><br>Ez hatással lesz azokra, akik Dynamics 365 termékeket használnak, amelyeket a Internet Explorer 11 interfészen való használatra terveztek. 2021. augusztus után az Internet Explorer 11 nem lesz támogatott az ilyen Dynamics 365 termékek esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Az összes Dynamics 365 termék |
| **Telepítési beállítás**              | Összes|
| **Állapot**                         | Elavult. Az Internet Explorer 11 támogatottsága 2021. augusztus után megszűnik.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.11 kiadásában
### <a name="data-action-hooks"></a>Adatművelet-horgok
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az adatművelet-horgok funkció a teljesítménnyel kapcsolatos problémák miatt elavult. |
| **Felváltotta másik szolgáltatás?**   | Javasolt az [adatművelet felülbírálások](../e-commerce-extensibility/data-action-overrides.md) használata az üzleti logika módosításához az adatműveleti rétegben.|
| **Érintett területek**         | e-kereskedelmi bővíthetőségi adatműveletek |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult a 10.0.11 kiadás óta |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Retail SDK-támogatás Visual Studio 2015-höz, msbuild 14.0 és Retail SDK\Reference könyvtárakhoz és eszközökhöz
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Visual Studio 2015 kiskereskedelmi SDK-támogatás elavult és frissítve lett 2017, msbuild 15.0 támogatásához és az összes hivatkozási függvénytár és kiskereskedelmi proxy-generator eszköz a RetailSDK\References mappából át lett helyezve, és így NuGet-csomagokba, így egyszerűbbé válik a bővítési modell és az SDK frissítési folyamata.|
| **Felváltotta másik szolgáltatás?**   | Javasoljuk, hogy kövesse [A Retail szoftverfejlesztői készlet (SDK) áttelepítése a Visual Studio 2015 szolgáltatásból a Visual Studio 2017 szolgáltatásba](../dev-itpro/retail-sdk/migrate-sdk.md) információit a rendszere frissítéséhez. |
| **Érintett területek**         | Kiskereskedelmi SDK-bővítmények |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult a 10.0.11 kiadás óta |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Retail Server Extension IEdmModelExtender és CommerceController használatával
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Retail Server Extension az IEdmModelExtender és a CommerceController használatával elavult egyszerűbb bővítési modell érdekében. Az új implementációnak csak vezérlőosztálya lesz további IEdmModelExtender-osztályvégrehajtás nélkül. Ezzel elkerülhető a függőség egy adott OData-verzióval (ha a OData verzió frissül, akkor a bővítmények meghibásodhatnak.) |
| **Felváltotta másik szolgáltatás?**   |  Javasoljuk, hogy a IController Class Extension modellt használja a NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts) csomag importálásával. |
| **Érintett területek**         | Retail-kiszolgáló bővítményei |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult a 10.0.11 kiadás óta |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Hardverállomás-bővítmény az IHardwareStationController használatával
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A hardverállomás-bővítmény az IHardwareStationController használatával elavult a leegyszerűsített bővítménymodell alkalmazása érdekében. Az új implementáció csak a IController osztályt fogja tartalmazni a további osztályimplementáció nélkül, és a függőség elkerüléséhez az alapszintű hardverállomás-könyvtárakkal, a korábbi bővítmények több könyvtárra kell utalnia.) |
| **Felváltotta másik szolgáltatás?**   | Az IController NuGet osztálykiterjesztési modellt ajánlott a (Microsoft.Dynamics.Commerce.Hosting.Contracts) csomag importálásával használni. |
| **Érintett területek**         | Hardverállomás bővítményei |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult a 10.0.11 kiadás óta |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.10 kiadásában
### <a name="pos-operation-803---picking-and-receiving"></a>803-as pénztári művelet – Kitárolás és bevételezés
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A kitárolási és bevételezési műveletek új művelet-újratervezés miatt elavulnak. |
| **Felváltotta másik szolgáltatás?**   | Igen. Két új POS-művelet helyettesíti, a bejövő művelet (804) és a kimenő művelet (805).|
| **Érintett területek**         | Pénztár (POS) alkalmazás |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 10.0.10 kiadástól kezdve a kitárolási és bevételezési művelet már nem fog új szolgáltatási frissítéseket kapni. Csak a kritikus hibajavítások lesznek végrehajtva ehhez a művelethez a későbbi kiadásokban. Minden ügyfelünket arra bíztatjuk, hogy álljanak át új [Bejövő műveletek](../pos-inbound-inventory-operation.md) és [Kimenő műveletekre](../pos-outbound-inventory-operation.md) lehetőségekre, amelyek továbbra is a hosszú távú termékfejlesztési program részei. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.7 kiadásában
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Commerce GetProductAvabilities és GetAvailableInventoryNearby API-k
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új, optimalizált API-k lettek létrehozva, ezek váltják le a GetProductAvailabilities és GetAvailableInventoryNearby API-kat. |
| **Felváltotta másik szolgáltatás?**   | Igen: a getEstizedAvailability és a GetEstizededProductWareraktározásAvailability API-k helyettesítik. |
| **Érintett területek**         | e-Commerce alkalmazás SDK |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 10.0.7-es kiadástól a továbbiakban nem fordítunk figyelmet a GetProductAvailabilities és GetAvailableInventoryNearby fejlesztésére. Azok a szervezetek, amelyek ezeket az API-kat használják az e-Commerce telepítések során, át kell álljanak az új GetEstimatedAvailability és GetEstimatedProductWarehouseAvailability API-k használatára, és engedélyezniük kell az [Optimalizált termékelérhetőség-számítás funkciót](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

