---
title: Költségvetés által irányított beszerzési rendelés létrehozása
description: Ezzel az eljárással beszerzési rendelést lehet létrehozni, amelyet a rendszer költségvetés-ellenőrzésnek vet alá.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016188"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Költségvetés által irányított beszerzési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ezzel az eljárással beszerzési rendelést lehet létrehozni, amelyet a rendszer költségvetés-ellenőrzésnek vet alá.

## <a name="review-the-budget-control-configuration"></a>Költségvetés-ellenőrzési konfiguráció áttekintése

1. Menjen a Költségvetés-ellenőrzési **> > vagy > konfigurációhoz**.
1. Válassza a **Rendelkezésre álló költségvetési alapok lapot**.
1. Válassza a Dokumentumok **és naplók fület**.
1. Válassza a Költségvetés-ellenőrzési **szabályok megadása lapot**.
1. Válassza a Költségvetési **csoportok definiálja lapot**.
1. Zárja be a lapot.

## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a Beszerzés **és forrás > beszerzési > valamennyi beszerzési rendeléshez**.
1. Válassza az **Új** lehetőséget.
1. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.
1. Bontsa ki az **Általános** gyorslapot.
1. A Könyvelési **dátum mezőben** állítsa be a dátumot.
1. A **párbeszédpanel bezárásához és az új beszerzési rendelés megnyitásához kattintson az OK** gombra.
1. A Beszerzési **rendelés sorai** gyorspultban **válassza** a Sor hozzáadása lehetőséget az eszköztárban új sor hozzáadásához, majd az elem rendeléshez való hozzáadásához töltse ki a sort.
1. Válassza a Beszerzési **rendelés sorai** gyorsgombot az eszköztár **Pénzügyi adatok elosztása \> összegének kiválasztásához**.
1. A Főkönyvi **számla** mezőben adjon meg egy számlát.
1. Zárja be a lapot.

## <a name="perform-budget-checking"></a>Költségvetés ellenőrzése

1. Folytassa a munkát azzal a beszerzési rendeléssel, amelybe egy sort felvett.
1. A Beszerzési rendelés **sorai** gyorsgombok eszköztárán válassza **a Pénzügyek költségvetés-ellenőrzés \> végrehajtása lehetőséget**.
1. A Beszerzési rendelési **sorok** gyorsgombok eszköztárán válassza **a Pénzügyi költségvetés ellenőrzése \> hibát vagy figyelmeztetést**.
1. **Megjelenik a Költségvetés-ellenőrzés hibái vagy figyelmeztetései** párbeszédpanel. Ellenőrizze az ellenőrzés eredményeit, majd a párbeszédpanel **bezárásához** kattintson a Bezárás gombra.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]