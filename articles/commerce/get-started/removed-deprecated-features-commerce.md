---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Commerce alkalmazásban.
author: josaw
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: f80d1509c7c363e93b83cb47c1b93ab00bf67180
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193468"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Commerce alkalmazásban.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](/dynamics/s-e/) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.17 kiadásában

### <a name="full-dataset-generation-interval-is-deprecated"></a>A teljes adatkészlet-generálás intervalluma elavult

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezzel a kiadással kezdődően a Dynamics 365 központi felületén a **Commerce ütemezés paraméterei** űrlapjában a **Teljes adatkészlet-generálás intervalluma napokban** mező elavult lesz. Ezzel a kiadással kezdődően a mezőt vizuálisan is eltávolítjuk, így az értéket nem lehet szerkeszteni. Ez **0** érték marad. |
| **Felváltotta másik szolgáltatás?**   | Nincs |
| **Érintett területek**         | Dynamics 365 Commerce |
| **Telepítési beállítás**              | Összes|
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
| **Felváltotta másik szolgáltatás?**   | Javasoljuk, hogy a IController Class Extension modellt használja a NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts) csomag importálásával. |
| **Érintett területek**         | Hardverállomás bővítményei |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult a 10.0.11 kiadás óta |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.10 kiadásában
### <a name="pos-operation-803---picking-and-receiving"></a>803-as pénztári művelet – Kitárolás és bevételezés
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A kitárolási és bevételezési műveletek új művelet-újratervezés miatt elavulnak. |
| **Felváltotta másik szolgáltatás?**   | Igen. A két új pénztári-művelet helyettesíti: bejövő művelet (804) és kimenő művelet (805).|
| **Érintett területek**         | Pénztár (POS) alkalmazás |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 10.0.10 kiadástól kezdve a kitárolási és bevételezési művelet már nem fog új szolgáltatási frissítéseket kapni. Csak a kritikus hibajavítások lesznek végrehajtva ehhez a művelethez a későbbi kiadásokban. Minden ügyfelünket arra bíztatjuk, hogy álljanak át új [Bejövő műveletek](../pos-inbound-inventory-operation.md) és [Kimenő műveletekre](../pos-outbound-inventory-operation.md) lehetőségekre, amelyek továbbra is a hosszú távú termékfejlesztési program részei. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.7 kiadásában
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Commerce GetProductAvailabilities és GetAvailableInventoryNearby API-k
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új, optimalizált API-k lettek létrehozva, ezek váltják le a GetProductAvailabilities és GetAvailableInventoryNearby API-kat. |
| **Felváltotta másik szolgáltatás?**   | Igen: Leváltották a GetEstimatedAvailability és a GetEstimatedProductWarehouseAvailability API-k. |
| **Érintett területek**         | e-Commerce alkalmazás SDK |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 10.0.7-es kiadástól a továbbiakban nem fordítunk figyelmet a GetProductAvailabilities és GetAvailableInventoryNearby fejlesztésére. Azok a szervezetek, amelyek ezeket az API-kat használják az e-Commerce telepítések során, át kell álljanak az új GetEstimatedAvailability és GetEstimatedProductWarehouseAvailability API-k használatára, és engedélyezniük kell az [Optimalizált termékelérhetőség-számítás funkciót](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]