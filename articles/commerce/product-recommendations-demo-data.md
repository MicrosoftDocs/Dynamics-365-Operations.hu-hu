---
title: Ajánlások létrehozása bemutató adatokkal
description: Ez a cikk útmutatást ad arról, hogyan lehet alkalmazni az egykulcsos környezetekben a csatorna-ajánlásokat az 1. szintű környezetben, előre kitöltve, testreszabható bemutatóadatok használatával.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7e3df414b3c16c28b6f5ca04f765d91c1312ada4
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9459968"
---
# <a name="create-recommendations-with-demo-data"></a>Ajánlások létrehozása bemutató adatokkal

[!include [banner](includes/banner.md)]

Ez a cikk útmutatást ad arról, hogyan lehet alkalmazni az egykulcsos környezetekben a csatorna-ajánlásokat az 1. szintű környezetben, előre kitöltve, testreszabható bemutatóadatok használatával.

A többcsatornás termékajánlások termékek szerkesztők által karbantartott vagy program által generált listájának készletét adják. Ezek a listák több esetben is használhatók, attól függően, hogy milyen üzleti szükséglet van. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

A 2. és magasabb szintű Dynamics 365 környezetekben a termékajánlások automatikusan, a vevői adatok alapján kerülnek kiszámításra. A termékajánlások demóadatainak használata nem tiltja le a környezetben már kiépített ajánlási megoldásokat, illetve a vonatkozó használati költségeket.

Az 1. szintű környezetekben a termékajánlások csak a .csv-fájlban tárolt statikus demóadatokon alapulnak.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>A termékajánlások demóadatainak engedélyezése egy környezetben
A Dynamics 365 Commerce Preview Demo Extension kiterjesztést a megfelelő környezetre kell telepíteni, hogy automatikusan engedélyezze a termékajánlások demóadatait. Így automatikusan engedélyezve lesznek a temékjavaslatok demóadatai.

## <a name="default-demo-data"></a>Alapértelmezett demóadatok
Minden OneBox típusú környezet rendelkezik egy előre betöltött termékajánlás-demóadat készlettel a vesszővel elválasztott „reco_demo_data.csv” fájlban, amely ugyanabban a mappában található, mint ez a dokumentum a Commerce Scale Unit kiszolgálón.

Ezek az adatok a következő oszlopok mentén strukturáltak.

| Oszlop neve         | Kötelező          | Leírás                                                                                                                                 | Lehetséges értékek                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | A konkrét termékajánlási listatípust, amelyre a demóadatok mutatnak, létre kell hozni.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li><li>RecoPicks</li><li>RecoSuallarVisual</li><li>RecoSuallarTextual</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Az a meghatározott üzemiegység-szám, amelyekben a termékajánlásoknak meg kell jelenniük.                                        |                                                                              |
| Kategória            |                    |    Az a kategória, amelyhez a megadott lista visszaadandó. Ha nincs megadva kategória, akkor a lista csak a navigációs hierarchia elejére kerül.    |                                                                              |
| SeedItemId          |                    |    A kiindulást igénylő listáknál (RecoPeopleAlsoBuy és RecoCart) a terméknél a listán további termékeket kell megjeleníteni.            |                                                                              |
| CustomerId          |                    |    A vevőazonosítót (RecoPicks) igénylő listákhoz.  Az alapértelmezett „0” érték minden vevőre vonatkozik.          |                                                                              |
| ItemIds             | :heavy_check_mark: | Egy vagy több termék, amelyet eredményként kell visszaküldeni, elválasztva a következővel „;”.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Demóadatok testreszabása
Szerkesztheti az alapértelmezett demóadatokat bármilyen termék- és kategóriainformációval, amelyet a HQ konfigurál. A CSV-fájl frissítését követően a vevőknek visszaküldött termékjavaslatokban azonnal megjelennek a módosítások.

A kiterjesztés tartalmaz egy „RecoMockDataset.csv” nevű adatfájlt, amely lehetővé teszi, hogy a vevő vezérelje azt az adathalmazt, amely a szimulált ajánlások eredményeinek alkalmazására használt. A fájlnév a kiterjesztéskonfigurációt használva vezérelhető a **ext.Recommendations.DemoFilePath** DemoFilePath beállítás használatával. Ez lehetővé teszi a Önnek, hogy több adatkészlettel rendelkezzen, amelyek között a konfiguráció használatával könnyen lehet váltani.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Termékajánlatok hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
