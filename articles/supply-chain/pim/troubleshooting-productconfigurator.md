---
title: A termékkonfiguráló hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a termékkonfiguráció használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f09ca4e69ca4bd3e87ee425c483b7a338045a0f28312a92b154fa07eb125927a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772496"
---
# <a name="troubleshoot-the-product-configurator"></a>A termékkonfiguráló hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani a termékkonfiguráció használata során felmerülő problémákat.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>A cikk szövege felülíródik, amikor egy terméket konfigurálok egy értékesítési rendeléssorban.

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordul elő, ha egy konfigurálható cikkhez értékesítési rendeléssort hoz létre, majd módosítja a cikk szövegét. Amikor konfigurálja az elemet, majd az **OK** lehetőséget választja, a program felülírja a szöveget a szabványos szöveggel.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a viselkedés várható. A szövegmező tartalmazza a változat nevét, amelyet csak a sor konfigurálása után tölt ki a program. Ezért a szöveget a sor konfigurálása után kell módosítania, nem korábban.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Az egész szám attribútumok helytelenül kerekítve jelennek meg a termékkonfigurációs modellek számításakor.

### <a name="issue-description"></a>Probléma leírása

Ez a probléma a következő műveletek végrehajtásakor fordulhat elő:

1. Állítsa be a következő attribútumokat egy termelési konfigurációs modellen:

    - Bemenet (egész szám)
    - Százalék (tizedesérték)
    - Eredmény (egész szám)

2. Hozzon létre egy kalkulációt, amelynek kifejezései a következők:

    *Eredmény* = *Bevitel* × *Százalék* ÷ 100

Ebben az esetben az egész szám eredmény nem mindig megfelelően van kerekítve. Például a bemenet 1000, és a százalék 2,40. Ezért az egész szám eredmény 24 lesz, mert az 1000 2,40 százaléka 24 (vagy 24,00 tizedesértékben megadva). Ehelyett az eredmény 23-ként jelenik meg. Ha azonban a százalék 2,39, akkor a kalkuláció 24-re lesz kerekítve 23 helyett. Ha a százalék 2,50, akkor a kalkuláció a vártnak megfelelően 25 lesz.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a probléma amiatt fordul elő, mert a Microsoft Solver Foundation számokat a törtszámokkal, belső használatra jeleníti meg. Az előző példában a számítás eredménye, ahol a százalék 2,40 volt, így jelenik meg: 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Amikor a .NET egész számként adja meg ezt az értéket, 23-ra fog visszatérni.

Ez a viselkedés nem változik, mert más forgatókönyvek függnek tőle. Az előző példában a problémát egy további tizedes attribútum és egy kalkuláció bevezetésével oldhatja meg.

Például beállíthatja a következő attribútumokat egy termelési konfigurációs modellen:

- Bemenet (egész szám)
- Százalék (tizedesérték)
- EredményTizedesérték (tizedesérték)
- EredményEgészszám (egész szám)

A következő kalkulációkat adhatja hozzá ezután:

- *EredményTizedesérték* = *Bemeneti* × *Százalék* ÷ 100
- *EredményEgészszám* = *EredményTizedesérték*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]