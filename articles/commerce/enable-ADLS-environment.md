---
title: ADLS engedélyezése a Dynamics 365 Commerce környezetben
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage (ADLS) megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 553e1512ba72559923403eef741ce08222172a09
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127767"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a>ADLS engedélyezése a Dynamics 365 Commerce környezetben

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage (ADLS) megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce megoldásban minden termék- és tranzakciós adatot nyomon követése megtörténik a környezet Entitás tárában. Ha az adatokat elérhetővé szeretné tenni a Dynamics 365 más szolgáltatásaihoz (például az adatelemzéshez, az üzleti intelligenciához és a személyre szabott ajánlásokhoz), akkor a környezetet egy vevő által birtokolt Azure Data Lake Storage Gen 2 (ADLS) megoldáshoz kell csatlakoztatni.

Mivel az ADLS egy környezetben konfigurálható, az összes szükséges adatot tükrözni kell az Entitás tárból, miközben továbbra is védve vannak, az ügyfél felügyelete alatt.

Ha a termékajánlások vagy a személyre szabott javaslatok is engedélyezve vannak a környezetben, akkor a termékajánlások készlete hozzáférési jogosultságot kap az ADLS dedikált mappájához, hogy beolvassa a vevő adatait, és kiszámítsa a javaslatokat ez alapján.

## <a name="prerequisites"></a>Előfeltételek

A vevőknek a saját Azure-előfizetésben kell konfigurálniuk az ADLS-t. Ez a témakör nem terjed ki egy Azure-előfizetés vagy egy ADLS-alapú tárolási fiók beállításainak beszerzésére.

Az ADLS-sel kapcsolatos további tudnivalókért lásd: [ADLS hivatalos dokumentációja](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Konfigurációs lépések

Ez a szakasz azokat a konfigurációs lépéseket ismerteti, amelyek szükségesek az ADLS-nek egy környezetben történő engedélyezéséhez.

### <a name="enable-adls-in-the-environment"></a>ADLS engedélyezése a környezetben

1. Jelentkezzen be a környezet back office portáljára.
1. Keresse meg a **Rendszerparamétereket**, és navigáljon az **Adatkapcsolatok** lapra. 
1. Állíts az **Data Lake-integráció engedélyezése** elemet **Igen** értékre.
1. Állíts a **Data Lake folyamatos frissítése** elemet **Igen** értékre.
1. Adja meg a következő kötelező adatokat:
    1. **Alkalmazásazonosító** // **Alkalmazástitok** // **DNS-név** – Az ADLS titok tárolására szolgáló KeyVaulthoz való csatlakozáshoz szükséges.
    1. **Titok neve** – A KeyVaultban tárolt titkos név, amely az ADLS-sel történő hitelesítéshez használatos.
1. Mentse a módosításokat a lap bal felső sarkában.

A következő kép egy példát mutat az ADLS-konfigurációra.

![Minta ADLS-konfiguráció](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a>ADLS-kapcsolat ellenőrzése

1. Ellenőrizze a kapcsolatot a kulcstárolóval az **Azure Key Vault tesztelése** link segítségével.
1. Ellenőrizze a kapcsolatot az ADLS-lel az **Azure Storage tesztelése** link segítségével.

> [!NOTE]
> Ha a tesztek sikertelenek, ellenőrizze, hogy a fentiekben hozzáadott összes KeyVault-információ helyes-e, majd próbálkozzon újra.

A csatlakozási tesztek sikeres végrehajtása után engedélyeznie kell az Entitás tároló automatikus frissítését.

Az Entitás tároló automatikus frissítésének engedélyezéséhez hajtsa végre az alábbi lépéseket.

1. Az **Entitás tároló**keresése.
1. A bal oldali listában navigáljon a **RetailSales** bejegyzéshez, majd válassza a **Szerkesztés** parancsot.
1. Győződjön meg arról, hogy **Az automatikus frissítés engedélyezve van** beállítása **Igen**, válassza a **Frissítés** elemet, majd válassza a **Mentés** parancsot.

A következő kép egy példát mutat be az Entitás tárra az automatikus frissítés engedélyezve beállítással.

![Példa az automatikus frissítést engedélyező Entitás tárra](./media/exampleADLSConfig2.png)

Az ADLS most be van állítva a környezethez. 

Ha nem fejeződött be, akkor kövesse a [termékajánlások és a környezet személyre szabásának](enable-product-recommendations.md) engedélyezésének lépéseit.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez](add-reco-list-to-page.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


