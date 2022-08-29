---
title: Az Azure Data Lake Storage engedélyezése Dynamics 365 Commerce környezetben
description: Ez a témakör azt is bemutatja, hogyan Azure Data Lake Storage lehet gen 2 megoldást csatlakoztatni a Dynamics 365 Commerce környezet entitástárhoz. Ez a termékajánlások engedélyezése előtti szükséges lépés.
author: bebeale
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: d7995e826a838796f714ced2f30220201a157f93
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284745"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Az Azure Data Lake Storage engedélyezése Dynamics 365 Commerce környezetben

[!include [banner](includes/banner.md)]

Ez a témakör azt is bemutatja, hogyan Azure Data Lake Storage lehet Gen2-megoldást csatlakoztatni a Dynamics 365 Commerce környezet entitástárhoz. Ez a termékajánlások engedélyezése előtti szükséges lépés.

A Dynamics 365 Commerce megoldásban az ajánlások, termékek és tranzakciók kiszámításához szükséges adatokat a rendszer a környezet entitástárában összesíti. Ha az adatokat elérhetővé szeretné tenni a Dynamics 365 más szolgáltatásaihoz (például az adatelemzéshez, az üzleti intelligenciához és a személyre szabott ajánlásokhoz), akkor a környezetet egy vevő által birtokolt Azure Data Lake Storage Gen2 megoldáshoz kell csatlakoztatni.

A fenti lépések befejezése után a környezet entitástárolójában található összes vevőadat automatikusan a vevő Azure Data Lake Storage Gen 2 megoldásában tükröződik. Ha a Commerce központ Funkciókezelési munkaterületén keresztül engedélyezi az ajánlások funkcióit, akkor az ajánlások vermében ugyanaz a Azure Data Lake Storage Gen2 megoldás lesz hozzáférhető.

A teljes folyamat során a vevők adatai védve és ellenőrzésük alatt maradnak.

## <a name="prerequisites"></a>Előfeltételek

A Dynamics 365 Commerce környezet entitástárát egy Azure Data Lake Gen Storage Gen2 fiókhoz és a kapcsolódó szolgáltatásokhoz kell csatlakoztatni.

Az Azure Data Lake Storage Gen2-vel és beállításával kapcsolatos további tudnivalókért lásd: [Azure Data Lake Storage Gen 2 hivatalos dokumentációja](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Konfigurációs lépések

Ez a szakasz azokat a konfigurációs lépéseket ismerteti, amelyek szükségesek ahhoz, hogy az Azure Data Lake Storage Gen2 engedélyezve legyen egy környezetben, mivel a termékajánlásokhoz kapcsolódik.
Az Azure Data Lake Storage Gen2 engedélyezéséhez szükséges lépésekről a további tudnivalókat lásd: [Entitástár elérhetővé tétele Data Lake alkalmazásként](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Azure Data Lake Storage engedélyezése a környezetben

1. Jelentkezzen be a környezet back office portáljára.
1. Keresse meg a **Rendszerparamétereket**, és navigáljon az **Adatkapcsolatok** lapra. 
1. Állíts az **Data Lake-integráció engedélyezése** elemet **Igen** értékre.
1. Adja meg a következő kötelező adatokat:
    1. **Alkalmazásazonosító** // **Alkalmazástitok** // **DNS-név** – Az Azure Data Lake Storage titok tárolására szolgáló KeyVaulthoz való csatlakozáshoz szükséges.
    1. **Titok neve** – A KeyVaultban tárolt titkos név, amely az Azure Data Lake Storage-dzsel történő hitelesítéshez használatos.
1. Mentse a módosításokat a lap bal felső sarkában.

A következő kép egy példát mutat az Azure Data Lake Storage-konfigurációra.

![Minta Azure Data Lake Storage-konfiguráció.](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Azure Data Lake Storage-kapcsolat ellenőrzése

1. Ellenőrizze a kapcsolatot a kulcstárolóval az **Azure Key Vault tesztelése** link segítségével.
1. Ellenőrizze a kapcsolatot az Azure Data Lake Storage-dzsel az **Azure Storage tesztelése** link segítségével.

> [!NOTE]
> Ha a fenti tesztek bármelyike sikertelen, erősítse meg, hogy a fentiekben hozzáadott összes KeyVault-információ helyes-e, majd próbálkozzon újra.

A csatlakozási tesztek sikeres végrehajtása után engedélyeznie kell az Entitás tároló automatikus frissítését.

Az Entitás tároló automatikus frissítésének engedélyezéséhez hajtsa végre az alábbi lépéseket.

1. Az **Entitás tároló** keresése.
1. A bal oldali listában navigáljon a **RetailSales** bejegyzéshez, majd válassza a **Szerkesztés** parancsot.
1. Győződjön meg arról, hogy **Az automatikus frissítés engedélyezve van** beállítása **Igen**, válassza a **Frissítés** elemet, majd válassza a **Mentés** parancsot.

A következő kép egy példát mutat be az Entitás tárra az automatikus frissítés engedélyezve beállítással.

![Példa az automatikus frissítést engedélyező Entitás tárra.](./media/exampleADLSConfig2.png)

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
