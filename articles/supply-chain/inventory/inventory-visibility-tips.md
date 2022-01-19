---
title: Készletláthatósággal kapcsolatos tanácsok
description: Ez a témakör néhány olyan tippet tartalmaz, amelyekre érdemes megfontolni a készlet láthatósági bővítményének beállítása és használata esetén.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1f6ade36ac184a3c8bf790fc0d899ea01d90c8d2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952415"
---
# <a name="inventory-visibility-tips"></a>Készletláthatósággal kapcsolatos tanácsok

[!include [banner](../includes/banner.md)]

Íme néhány olyan tipp, amit érdemes figyelembe venni a készlet láthatósági bővítményének beállítása és használata esetén:

- A Készlet láthatósági bővítménye jelenleg csak olyan környezeteket támogat, amelyek a Microsoft Dataverse Microsoft Dynamics Lifecycle Services (LCS) használatával létrejöttek. Ha a környezet valamilyen más módon lett létrehozva (például a rendszergazdai központ használatával), és ez kapcsolódik a környezethez, először meg kell kérje a készlet láthatósági termékcsoportját a megfeleltetési probléma Dataverse Power AppsDynamics 365 Supply Chain Management kijavítása érdekében. A csoporttal a [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). A csoport tudni fogja, hogy mikor áll készen a környezet a készlet láthatóságának telepítésére.
- Ha több LCS-környezete van, mindegyik környezethez hozzon létre egy Azure Active Directory Azure AD másik () alkalmazást. Ha ugyanazt az alkalmazásazonosítót és bérlőazonosítót használja a készlet láthatósági bővítményének különböző környezetekben való telepítéséhez, jogkivonat-probléma fog előfordulni a régebbi környezetekben. Csak a telepített készlet láthatósági bővítményének utolsó példánya lesz érvényes.
- A készlet láthatósága jelenleg nem támogatott a felhőben tárolt környezetekben. Csak a Tier-2+ környezetekben támogatott.
- Az alkalmazásprogramozási felület (API) jelenleg legfeljebb 100 különálló cikk érték alapján történő lekérdezését `ProductID` támogatja. Az `SiteID` egyes `LocationID` lekérdezések több és több értéket is meg lehet adni. A maximális korlát a következőként van meghatározva:`NumOf(SiteID) * NumOf(LocationID) <= 100`
- A tömeges API legfeljebb 512 rekordot ad vissza minden kéréshez.
- Az `fno` adatforrás le van foglalva az Ellátásilánc-kezeléshez. Ha a készlet láthatósági bővítménye integrálva van egy ellátásilánc-kezelési környezettel, javasoljuk, hogy ne törölje az adatforráshoz kapcsolódó `fno`[konfigurációkat](inventory-visibility-configuration.md#data-source-configuration).
- A készlet láthatósága nem módosíthatja az adatforrás `fno` adatait. Az adatforgalom egy egy mód, ami azt jelenti, hogy az adatforrás mennyiségi változásainak az Ellátásilánc-kezelés `fno` környezetből kell erednie. Ennek megfelelően nem használhatja az API-t az adatforráshoz szükséges módosítási vagy foglalási kérések `fno` elküldre.
- Ha egy vagy több új intézkedéseket ad hozzá az ellátásilánc-kezelési környezethez, akkor azokat a készlet láthatósága érdekében is hozzá kell adni. Az új intézkedések mennyiségi változásainak ugyanakkor az Ellátásilánc-kezelés környezetből kell jönniük.
- A [partíciókonfiguráció](inventory-visibility-configuration.md#partition-configuration) jelenleg két alapdimenzióból (és ) áll, amelyek az adatok `SiteId``LocationId` elosztását jelzik. Az ugyanazon a partíción található műveletek magasabb teljesítményt és alacsonyabb költségű műveleteket is tudnak szállítani. A megoldás alapértelmezés szerint tartalmazza ezt a partíciókonfigurációt. Nem *kell tehát saját határozzák* meg. Ne szabja testre az alapértelmezett partíciókonfigurációt. Ha törli vagy módosítja, akkor valószínűleg váratlan hibát fog okozhatni.
- A partíciókonfigurációban definiált alapdimenziókat nem szabad definiálni a [termékindex-hierarchia](inventory-visibility-configuration.md#index-configuration) konfigurációjában.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
