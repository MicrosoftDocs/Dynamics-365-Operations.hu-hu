---
title: Termékajánlatok beszerzése bemutatóadatok használatával
description: A dokumentum útmutatást ad a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: af8a30e69d9ed143e045950efdcece207f6da14c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697934"
---
# <a name="get-product-recommendations-using-demo-data"></a>Termékajánlatok beszerzése bemutatóadatok használatával
A dokumentum útmutatást ad a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.

A többcsatornás termékajánlások termékek szerkesztők által karbantartott vagy program által generált listájának készletét adják. Ezek a listák több esetben is használhatók, attól függően, hogy milyen üzleti szükséglet van. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

A 2. és magasabb szintű Dynamics 365 környezetekben a termékajánlások automatikusan, a vevői adatok alapján kerülnek kiszámításra. A termékajánlások demóadatainak használata nem tiltja le a környezetben már kiépített ajánlási megoldásokat, illetve a vonatkozó használati költségeket.

Az 1. szintű környezetekben a termékajánlások csak a .csv-fájlban tárolt statikus demóadatokon alapulnak.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>A termékajánlások demóadatainak engedélyezése egy környezetben
A Dynamics 365 Commerce Preview Demo Extension kiterjesztést a megfelelő környezetre kell telepíteni, hogy automatikusan engedélyezze a termékajánlások demóadatait. Így automatikusan engedélyezve lesznek a temékjavaslatok demóadatai.

## <a name="default-demo-data"></a>Alapértelmezett demóadatok
Minden Onebox típusú környezet rendelkezik egy előre betöltött termékajánlás-demóadat készlettel a vesszővel elválasztott „reco_demo_data.csv” fájlban, amely ugyanabban a mappában található, mint ez a dokumentuma Retail Server kiszolgálón.

Ezek az adatok a következő oszlopok mentén strukturáltak.

| Oszlop neve         | Kötelező          | Leírás                                                                                                                                 | Lehetséges értékek                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | A konkrét termékajánlási listatípust, amelyre a demóadatok mutatnak, létre kell hozni.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Az a meghatározott üzemiegység-szám, amelyekben a termékajánlásoknak meg kell jelenniük.                                        |                                                                              |
| Kategória            |                    |    Az a kategória, amelyhez a megadott lista visszaadandó. Ha nincs megadva kategória, akkor a lista csak a navigációs hierarchia elejére kerül.    |                                                                              |
| SeedItemId          |                    |    A kiindulást igénylő listáknál (RecoPeopleAlsoBuy és RecoCart) a terméknél a listán további termékeket kell megjeleníteni.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Egy vagy több termék, amelyet eredményként kell visszaküldeni, elválasztva a következővel „;”.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Demóadatok testreszabása
Szerkesztheti az alapértelmezett demóadatokat bármilyen termék- és kategóriainformációval, amelyet a HQ konfigurál. A CSV-fájl frissítését követően a vevőknek visszaküldött termékjavaslatokban azonnal megjelennek a módosítások.

A kiterjesztés tartalmaz egy „RecoMockDataset.csv” nevű adatfájlt, amely lehetővé teszi, hogy a vevő vezérelje azt az adathalmazt, amely a szimulált ajánlások eredményeinek alkalmazására használt. A fájlnév a kiterjesztéskonfigurációt használva vezérelhető a **ext.Recommendations.DemoFilePath** DemoFilePath beállítás használatával. Ez lehetővé teszi a Önnek, hogy több adatkészlettel rendelkezzen, amelyek között a konfiguráció használatával könnyen lehet váltani.


```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Környezet tervezése](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)