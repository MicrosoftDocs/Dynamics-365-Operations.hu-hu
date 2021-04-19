---
title: Az Azure Data Lake Storage engedélyezése Dynamics 365 Commerce környezetben
description: Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.
author: bebeale
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 61f96dae0643e3383afd91864e4c145f3b5c04c8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792607"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Az Azure Data Lake Storage engedélyezése Dynamics 365 Commerce környezetben

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet engedélyezni és tesztelni az Azure Data Lake Storage megoldást egy Dynamics 365 Commerce környezet számára, amely előfeltétele a termékajánlások engedélyezésének.

A Dynamics 365 Commerce megoldásban minden termék- és tranzakciós adatot nyomon követése megtörténik a környezet Entitás tárában. Ha az adatokat elérhetővé szeretné tenni a Dynamics 365 más szolgáltatásaihoz (például az adatelemzéshez, az üzleti intelligenciához és a személyre szabott ajánlásokhoz), akkor a környezetet egy vevő által birtokolt Azure Data Lake Storage Gen 2 megoldáshoz kell csatlakoztatni.

Mivel az Azure Data Lake Storage egy környezetben konfigurálható, az összes szükséges adatot tükrözni kell az Entitás tárból, miközben továbbra is védve vannak, az ügyfél felügyelete alatt.

Ha a termékajánlások vagy a személyre szabott javaslatok is engedélyezve vannak a környezetben, akkor a termékajánlások készlete hozzáférési jogosultságot kap az Azure Data Lake Storage dedikált mappájához, hogy beolvassa a vevő adatait, és kiszámítsa a javaslatokat ez alapján.

## <a name="prerequisites"></a>Előfeltételek

A vevőknek a saját Azure-előfizetésben kell konfigurálniuk az Azure Data Lake Storage-t. Ez a témakör nem terjed ki egy Azure-előfizetés vagy egy Azure Data Lake Storage-alapú tárolási fiók beállításainak beszerzésére.

Az Azure Data Lake Storage-dzsel kapcsolatos további tudnivalókért lásd: [Azure Data Lake Storage Gen 2hivatalos dokumentációja](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Konfigurációs lépések

Ez a szakasz azokat a konfigurációs lépéseket ismerteti, amelyek szükségesek ahhoz, hogy az Azure Data Lake Storage engedélyezve legyen egy környezetben, mivel a termékajánlásokhoz kapcsolódik.
Az Azure Data Lake Storage engedélyezéséhez szükséges lépésekről a további tudnivalókat lásd: [Entitástár elérhetővé tétele Data Lake alkalmazásként](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Azure Data Lake Storage engedélyezése a környezetben

1. Jelentkezzen be a környezet back office portáljára.
1. Keresse meg a **Rendszerparamétereket**, és navigáljon az **Adatkapcsolatok** lapra. 
1. Állíts az **Data Lake-integráció engedélyezése** elemet **Igen** értékre.
1. Állíts a **Data Lake folyamatos frissítése** elemet **Igen** értékre.
1. Adja meg a következő kötelező adatokat:
    1. **Alkalmazásazonosító** // **Alkalmazástitok** // **DNS-név** – Az Azure Data Lake Storage titok tárolására szolgáló KeyVaulthoz való csatlakozáshoz szükséges.
    1. **Titok neve** – A KeyVaultban tárolt titkos név, amely az Azure Data Lake Storage-dzsel történő hitelesítéshez használatos.
1. Mentse a módosításokat a lap bal felső sarkában.

A következő kép egy példát mutat az Azure Data Lake Storage-konfigurációra.

![Minta Azure Data Lake Storage-konfiguráció](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Azure Data Lake Storage-kapcsolat ellenőrzése

1. Ellenőrizze a kapcsolatot a kulcstárolóval az **Azure Key Vault tesztelése** link segítségével.
1. Ellenőrizze a kapcsolatot az Azure Data Lake Storage-dzsel az **Azure Storage tesztelése** link segítségével.

> [!NOTE]
> Ha a tesztek sikertelenek, ellenőrizze, hogy a fentiekben hozzáadott összes KeyVault-információ helyes-e, majd próbálkozzon újra.

A csatlakozási tesztek sikeres végrehajtása után engedélyeznie kell az Entitás tároló automatikus frissítését.

Az Entitás tároló automatikus frissítésének engedélyezéséhez hajtsa végre az alábbi lépéseket.

1. Az **Entitás tároló** keresése.
1. A bal oldali listában navigáljon a **RetailSales** bejegyzéshez, majd válassza a **Szerkesztés** parancsot.
1. Győződjön meg arról, hogy **Az automatikus frissítés engedélyezve van** beállítása **Igen**, válassza a **Frissítés** elemet, majd válassza a **Mentés** parancsot.

A következő kép egy példát mutat be az Entitás tárra az automatikus frissítés engedélyezve beállítással.

![Példa az automatikus frissítést engedélyező Entitás tárra](./media/exampleADLSConfig2.png)

Az Azure Data Lake Storage most be van állítva a környezethez. 

Ha nem fejeződött be, akkor kövesse a [termékajánlások és a környezet személyre szabásának](enable-product-recommendations.md) engedélyezésének lépéseit.

## <a name="additional-resources"></a>További erőforrások

[Entitástár elérhetővé tétele data lake alkalmazásként](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Termékajánlatok áttekintése](product-recommendations.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Termékajánlatok hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
