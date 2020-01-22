---
title: Többcsatornás termékajánlások demóadatok
description: A dokumentum célja, hogy útmutatást adjon a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872326"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Többcsatornás termékajánlások demóadatok

A dokumentum célja, hogy útmutatást adjon a többcsatornás termékajánlásoknak az 1.szintű egyablakos környezetekben történő kihasználásához előre kitöltött, testreszabható demóadatok felhasználásával.

A többcsatornás termékajánlások termékek szerkesztők által karbantartott vagy program által generált rendezett listájának készletét adják. Ezek a listák több esetben is használhatók, attól függően, hogy milyen üzleti szükséglet van. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése.](../commerce/product-recommendations.md)

A 2. és magasabb szintű Dynamics környezetekben a termékajánlások automatikusan, a vevői adatok alapján kerülnek kiszámításra.
A termékajánlások demóadatainak használata nem tiltja le a környezetben már kiépített ajánlási megoldásokat, illetve a vonatkozó használati költségeket.

Az 1. szintű környezetekben a termékajánlások csak a CSV-fájlban tárolt statikus demóadatokon alapulnak.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>A termékajánlások demóadatainak engedélyezése egy környezetben

A **Dynamics 365 Commerce Preview Demo Extension** kiterjesztést a megfelelő környezetre kell telepíteni, ami automatikusan engedélyezi a termékajánlások demóadatait.

## <a name="default-demo-data"></a>Alapértelmezett demóadatok
Minden Onebox típusú környezet rendelkezik egy előre betöltött termékajánlás-demóadat készlettel a vesszővel elválasztott **‘reco_demo_data.csv’** fájlban, amely ugyanabban a mappában található, mint ez a dokumentuma Retail Server kiszolgálón.

Ezek az adatok a következő oszlopok mentén strukturáltak.

| Oszlop neve         | Kötelező          | Leírás                                                                                                                                 | Lehetséges értékek                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | A konkrét termékajánlási listatípust, amelyre a demóadatok mutatnak, létre kell hozni.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Az a meghatározott üzemiegység-szám, amelyekben a termékajánlásoknak meg kell jelenniük.                                        |                                                                              |
| Kategória            |                    |    Az a kategória, amelyhez a megadott lista visszaadandó. Ha nincs megadva kategória, akkor a lista csak a navigációs hierarchia elejére kerül.    |                                                                              |
| SeedItemId          |                    |    A kiindulást igénylő listáknál (RecoPeopleAlsoBuy és RecoCart) a terméknél a listán további termékeket kell megjeleníteni.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Egy vagy több termék, amelyet eredményként kell visszaküldeni, elválasztva a következővel **";"**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Demóadatok testreszabása
A felhasználók szerkeszthetik az alapértelmezett demóadatokat bármilyen termék- és kategóriainformációval, amelyet a HQ konfigurál. A CSV-fájl frissítését követően a vevőknek visszaküldött termékajánlásokban azonnal megjelennek a módosítások.

A kiterjesztés tartalmaz egy RecoMockDataset.csv nevű adatfájlt, amely lehetővé teszi, hogy a vevő vezérelje azt az adathalmazt, amely a szimulált ajánlások eredményeinek alkalmazására használt. A fájlnév a kiterjesztéskonfigurációt használva vezérelhető a **ext.Recommendations.DemoFilePath** DemoFilePath beállítás használatával. Ez lehetővé teszi a vevők számára, hogy több adatkészlettel rendelkezzenek, amelyek között a konfiguráció használatával könnyen lehet váltani.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>További erőforrások

[Termékajánlások áttekintése](../commerce/product-recommendations.md)

[Környezet tervezése](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
