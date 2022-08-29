---
title: Készletláthatósággal kapcsolatos tanácsok
description: Ez a témakör néhány olyan tippeket tartalmaz, amelyekre érdemes megfontolni a készlet láthatósági bővítményének beállítása és használata esetén.
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
ms.openlocfilehash: 3bdd161815a15d5c39b3c0afc176a288c8d9055a
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306085"
---
# <a name="inventory-visibility-tips"></a>Készletláthatósággal kapcsolatos tanácsok

[!include [banner](../includes/banner.md)]

Íme néhány olyan tipp, amit érdemes figyelembe venni a készlet láthatósági bővítményének beállítása és használata esetén:

- A Készlet láthatósági bővítménye Microsoft Dataverse Microsoft Dynamics jelenleg csak olyan környezeteket támogat, amelyek a Lifecycle Services (LCS) használatával létrejöttek. Ha a Dataverse környezet valamilyen más módon lett létrehozva (Power Apps például a rendszergazdai központ használatával), Dynamics 365 Supply Chain Management és ez kapcsolódik a környezethez, először meg kell kérje a készlet láthatósági termékcsoportját a megfeleltetési probléma kijavítása érdekében. A csoporttal a következő inventvisibilitysupp@microsoft.com [...](mailto:inventvisibilitysupp@microsoft.com). A csoport tudni fogja, hogy mikor áll készen a környezet a készlet láthatóságának telepítésére.
- Ha több LCS-környezete van, mindegyik Azure Active Directory környezethez hozzon létre egy másik (Azure AD) alkalmazást. Ha ugyanazt az alkalmazásazonosítót és bérlőazonosítót használja a készlet láthatósági bővítményének különböző környezetekben való telepítéséhez, jogkivonat-probléma fog előfordulni a régebbi környezetekben. Csak a telepített készlet láthatósági bővítményének utolsó példánya lesz érvényes.
- A készlet láthatósága jelenleg nem támogatott a felhőben tárolt környezetekben. Csak a Tier-2+ környezetekben támogatott.
- Az alkalmazásprogramozási felület (API) jelenleg legfeljebb 100 különálló cikk érték alapján történő lekérdezését `ProductID` támogatja. Az `SiteID` egyes `LocationID` lekérdezések több és több értéket is meg lehet adni. A maximális korlát a következőként van meghatározva:`NumOf(SiteID) * NumOf(LocationID) <= 100`
- A tömeges API legfeljebb 512 rekordot ad vissza minden kéréshez.
- Az `fno` adatforrás le van foglalva az Ellátásilánc-kezeléshez. Ha a készlet láthatósági bővítménye integrálva van egy ellátásilánc-kezelési környezettel, javasoljuk, `fno` hogy ne törölje az adatforráshoz kapcsolódó [konfigurációkat](inventory-visibility-configuration.md#data-source-configuration).
- A készlet láthatósága nem módosíthatja az adatforrás adatait `fno`. Az adatforgalom egy egy mód, ami azt jelenti, `fno` hogy az adatforrás mennyiségi változásainak az Ellátásilánc-kezelés környezetből kell erednie. Ennek megfelelően nem használhatja az API-t az adatforráshoz szükséges módosítási vagy foglalási kérések elküldre `fno`.
- Ha egy vagy több új intézkedéseket ad hozzá az ellátásilánc-kezelési környezethez, akkor azokat a készlet láthatósága érdekében is hozzá kell adni. Az új intézkedések mennyiségi változásainak ugyanakkor az Ellátásilánc-kezelés környezetből kell jönniük.
- A [partíciókonfiguráció](inventory-visibility-configuration.md#partition-configuration) jelenleg két alapdimenzióból (és `SiteId`) áll,`LocationId` amelyek az adatok elosztását jelzik. Az ugyanazon a partíción található műveletek magasabb teljesítményt és alacsonyabb költségű műveleteket is tudnak szállítani. A megoldás alapértelmezés szerint tartalmazza ezt a partíciókonfigurációt. Nem kell *tehát saját magának meghatároznia*. Ne szabja testre az alapértelmezett partíciókonfigurációt. Ha törli vagy módosítja, akkor valószínűleg váratlan hibát fog okozhatni.
- A partíciókonfigurációban definiált alapdimenziókat nem szabad definiálni a termékindex-hierarchia [konfigurációjában](inventory-visibility-configuration.md#index-configuration).
- A [termékindex-hierarchia](inventory-visibility-configuration.md#index-configuration) konfigurációjának tartalmaznia kell legalább egy indexhierarchiát (`Empty` például az alapdimenziót tartalmazó), különben a lekérdezések nem fognak sikerülni a "Nincs indexhierarchia beállítva" hibával.
- Az adatforrás `@iv` egy előre definiált adatforrás `@iv``@`, és az előtaggal meghatározott fizikai intézkedések előre meghatározottak. Ezek a intézkedések a felosztási funkció előre definiált konfigurációi, ezért ezeket ne módosítsa vagy törölje, vagy a felosztási funkció használata során váratlan hibákat fog látni.
- Az előre meghatározott számított mértékhez `@iv.@available_to_allocate` új fizikai mértékeket lehet hozzáadni, de a nevét nem szabad megváltoztatni.
- Ha visszaállít egy Ellátásilánc-kezelés adatbázist, akkor előfordulhat, hogy a visszaállított adatbázis olyan adatokat tartalmaz, amelyek már nem egyeztethetők a Készlet visibility funkcióval korábban szinkronizált adatokkal Dataverse. Az adatok inkonzisztenciája rendszerhibákat és más problémákat okozhat. Emiatt fontos, hogy minden Dataverse kapcsolódó készlet-láthatósági adatot kitisztítson az ellátásilánc-kezelési adatbázis visszaállítása előtt. A részleteket lásd [a Készlet láthatósági adatainak Dataverse tisztítása az Ellátásilánc-kezelés adatbázis visszaállítása előtt](inventory-visibility-setup.md#restore-environment-database).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
