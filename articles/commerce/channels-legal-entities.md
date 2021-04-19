---
title: Jogi személyek létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet jogi személyeket létrehozni a Microsoft Dynamics 365 Commerce szolgáltatásban, amelyet a csatornák létrehozása előtt létre kell hozni és be kell állítani.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 225fd6a07fee29414ac30a4602b4dfccdc4d742b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800615"
---
# <a name="create-legal-entities"></a>Jogi személyek létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet jogi személyeket létrehozni a Microsoft Dynamics 365 Commerce szolgáltatásban, amelyet a csatornák létrehozása előtt létre kell hozni és be kell állítani.

A jogi személy olyan szervezet, amely bejegyzett vagy törvényben szabályozott jogi struktúrával rendelkezik. A jogi személyek törvényes szerződéseket köthetnek, teljesítményükről pedig tájékoztató beszámolókat kell készíteniük.

A vállalat is jogi személy. Jelenleg a vállalatok az egyetlen típusú jogi személy, amelyet létrehozhat, és minden jogi személyhez tartozik egy vállalati azonosító. Erre a társításra azért van szükség, mert a program egyes funkcionális területeinek modelljei vállalat azonosítót vagy *DataAreaId*-t használnak. Ezeken a funkcionális területeken a vállalatokat határként használják az adatbiztonsághoz. A felhasználók csak annak a vállalatnak a részére férhetnek hozzá adatokhoz, amelyen éppen bejelentkeznek. 

Csatorna létrehozásakor meg kell adnia, hogy melyik jogi személy tartozik a csatornához.

## <a name="create-a-new-legal-entity"></a>Új jogi személy létrehozása

Új jogi személy létrehozásához a Dynamics 365 Commerce szolgáltatásban kövesse az alábbi lépéseket.

1. A navigációs ablakban nyissa meg a **Modulok \> központi telepítése \> jogi személyek** elemet.
1. A műveleti ablaktáblán kattintson az **Új** elemre. A jobb oldalon megjelenik az **Új jogi személy** ablaktábla.
1. A **Név** mezőben adjon meg egy értéket.
1. A **Vállalat** mezőben adjon meg egy értéket.
1. Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza ki az **OK** lehetőséget. 

   ![Jogi személy létrehozása](media/legal-entities.png)

1. Az **Általános** szakaszban adja meg a következő általános információkat a jogi személyről: 
   1. Szükség esetén írja be a keresési nevet. A keresési név olyan másodlagos név, amelynek használatával elvégezheti a keresést a jogi személyre vonatkozóan. 
   1. Adja meg, hogy ez a jogi személy konszolidációs vállalatként használatos-e.
   1. Adja meg, hogy ez a jogi személy eltávolítási vállalatként használatos-e. 
   1. Jelölje ki az **alapértelmezett nyelvet** az entitáshoz. 
   1. Válassza ki az entitás **időzónáját**.
1. A **Címek** szakaszban kattintson a **Szerkesztés** lehetőségre, és adja meg a cím adatait, mint például az utca nevet és a számot, az irányítószámot és a várost.
1. A **Kapcsolattartási adatok** szakaszban adja meg a kommunikációs módszerekkel kapcsolatos adatokat, például a e-mail címeket, az URL-címeket és a telefonszámokat.
1. A **Kötelezően előírt jelentéskészítés** szakaszban adja meg a kötelező jelentési célokra használt nyilvántartási számokat.
1. A **Regisztrációs számok** szakaszban adja meg a jogi személy által igényelt információkat.
1. A **Bankszámla adatok** szakaszban adja meg a bankszámlaákat és a regisztrációs azonosítót a jogi személyre vonatkozóan.
1. A **Külföldi kereskedelem és logisztika** szakaszban adja meg a szállítási adatokat a jogi személyre vonatkozóan.
1. A **Számsorozat** gyorslapon megtekintheti a jogi személyhez kapcsolódó számsorozatokat. Ez a mező üresen marad eredetileg.
1. Az **Irányítópult képei** szakaszban tekintse meg vagy módosítsa a jogi személyhez társított emblémát és/vagy irányítópultot.
1. Az **Adóregisztráció** szakaszban adja meg az adóhatóságnál tett jelentéshez használt nyilvántartási számokat.
1. Az **Adó - 1099** szakaszban adja meg a 1099-es adatokat a jogi személyre vonatkozóan.
1. Az **Adózási adatok** szakaszban adja meg az adózási adatokat a jogi személyre vonatkozóan.
1. Válassza a **Mentés** lehetőséget.

A következő kép egy példa jogi személy részleteit mutatja.

![Jogi személy általános szakasza](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>További erőforrások

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchia megtervezése](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchiák](channels-org-hierarchies.md)

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
