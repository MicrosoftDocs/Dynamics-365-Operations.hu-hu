---
title: Költségvetés által irányított beszerzési rendelés létrehozása
description: Ezzel az eljárással beszerzési rendelést lehet létrehozni, amelyet a rendszer költségvetés-ellenőrzésnek vet alá.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a79b19ce4ff35ecc1f691edea1bdc5e30010b433
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821369"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Költségvetés által irányított beszerzési rendelés létrehozása

[!include [banner](../../includes/banner.md)]

Ezzel az eljárással beszerzési rendelést lehet létrehozni, amelyet a rendszer költségvetés-ellenőrzésnek vet alá. Ez a felvétel az USMF bemutató vállalati adatait használja.


## <a name="review-the-budget-control-configuration"></a>Költségvetés-ellenőrzési konfiguráció áttekintése
1. Lépjen a Költségvetés készítése > Beállítás > Költségvetés-ellenőrzés > Költségvetés-ellenőrzés konfigurációja lehetőségre.
2. Kattintson a Rendelkezésre álló költségvetési források lapra.
3. Kattintson a Dokumentumok és naplók lapra.
4. Kattintson a Költségvetés-ellenőrzési szabályok meghatározása lapra.
5. Kattintson a Költségvetés-ellenőrzési csoportok meghatározása lapra.
6. Zárja be a lapot.

## <a name="create-the-purchase-order-header"></a>Beszerzési rendelési fejléc létrehozása
1. Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.
2. Kattintson az Új lehetőségre.
3. A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.
4. Bontsa ki az Általános szakaszt.
5. A Könyvelési dátum mezőben állítsa a dátumot „2016-01-01” értékre.
6. Kattintson az OK gombra.

## <a name="add-a-purchase-order-line"></a>Beszerzési rendelési sor hozzáadása
1. A Beszerzési kategória mezőben adjon meg vagy válasszon ki egy értéket.
2. Állítsa a mennyiséget „2” értékre.
3. Az Egység mezőben adjon meg vagy válasszon ki egy értéket.
4. Állítsa az Egységárat „10000”-re.
5. Kattintson a Pénzügyre.
6. Kattintson az Összegek felosztása elemre.
7. A Főkönyvi számla mezőben adja meg a „601300-001-023--” értéket.
8. Zárja be a lapot.

## <a name="perform-budget-checking"></a>Költségvetés ellenőrzése
1. Kattintson a Pénzügyre.
2. Kattintson a Költségvetés ellenőrzése lehetőségre.
3. Kattintson a Pénzügyre.
4. Kattintson a Költségvetés ellenőrzésekor fellépő hibák vagy figyelmeztetések lehetőségre.
5. Kattintson a Bezárás gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]