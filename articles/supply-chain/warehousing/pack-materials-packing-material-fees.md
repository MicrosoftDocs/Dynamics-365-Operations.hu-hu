---
title: Csomagolóanyagok és díjak
description: A csomagolóanyag-díjakat meghatározott időközönként kell kifizetni egy feldolgozó vállalatnak. Súlyegységenként egy bizonyos összeget kell kifizetni a csomagolási egységet alkotó minden egyes anyag után. A program a csomagolóanyag-díjakat kiszámítja és jelentést is készít róluk, viszont – mivel nem számít a hatóságoknak fizetendő adónak – nem ad fel főkönyvi tranzakciót a díjjal kapcsolatban.
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c188651fe8ba3fe3f9678f36ab11ae886ef6f1cf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "312301"
---
# <a name="packing-materials-and-fees"></a>Csomagolóanyagok és díjak

[!include [banner](../includes/banner.md)]

A csomagolóanyag-díjakat meghatározott időközönként kell kifizetni egy feldolgozó vállalatnak. Súlyegységenként egy bizonyos összeget kell kifizetni a csomagolási egységet alkotó minden egyes anyag után. A program a csomagolóanyag-díjakat kiszámítja és jelentést is készít róluk, viszont – mivel nem számít a hatóságoknak fizetendő adónak – nem ad fel főkönyvi tranzakciót a díjjal kapcsolatban.

A csomagolóanyag-súlyokat és -díjakat az értékesítési rendeléssoroknál és a beszerzési rendeléssoroknál a program számolja ki.

Megadhat egy vagy több csomagolási egységet egy cikkhez, egy vagy az összes cikk csomagoló csoportjához. A csomagolási egység különféle csomagolóanyagokat tartalmaz, azok súlyából és a csomagolási egységbetartozó cikkek számából áll. A Csomagolóanyag-kód a meghatározott csomagolóanyag minden egyes típusához hozzá van rendelve. A csomagolóanyag-kódon alapul, megadhatja az árat egy adott időszakra. A csomagolóanyag-díj ezen információ alapján számítják ki.

| **Megjegyzés**                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Még akkor is, ha a vállalat nem fizeti ki a csomagolási díjakat, használhatja a funkciót a csomagolási anyagok súlyával kapcsolatos statisztikák kiszámításához. |

## <a name="setup-requirements-for-packing-material-fees"></a>A csomagolóanyag-díjak előfeltételeinek beállítása
A csomagolóanyag-súlyok/-díjak vagy mindkettő kiszámítása előtt létre kell hoznia a következő alapadatokat:

-   Csomagoló csoportok: - Hozza létre a cikkekhez társítandó csomagolócsoportokat.
-   Csomagolóanyag-kódok – Hozza létre a csomagolóanyag-kódokat a csomagoló anyagok minden egyes meghatározott típusához.
-   Csomagoló egységek - Határozza meg egy csomagoló egységet egy cikkhez, egy csomagolócsoporthoz vagy az összes cikkhez. Az egyes csomagolási egységeknél határozza meg, mely csomagolóanyagokat tartalmazzon, milyen súlyokat rendeljen hozzá, és a Csomagolási egység szorzótényező mezőben adja meg az átváltási tényezőt a készletegységből.
-   Csomagolási anyag díjak - Határozza meg csomagolóanyag-kódonként a csomagolóanyag-díjakat. Minden anyagtípushoz adja meg az érvényességi időszakot, az anyagonkénti árat, a pénznemet és az egységet.

## <a name="packing-units-on-sales-order-lines"></a>Az értékesítési rendelési sorokon lévő csomagolási egységek
Értékesítésirendelés-sorok létrehozása esetén a program ellenőrzi, hogy a csomagolási egységeket meg vannak-e határozva a cikkhez. Ha meg vannak határozva a csomagolási egységek, a rendszer frissíti a meghatározott csomagolási egységgel és csomagolási egység mennyiséggel rendelkező rendelkező értékesítési rendelési sort. A csomagolási egység mennyisége a a kiválasztott csomagolási egységben lévő elemek számával elosztott rendelt mennyiségen alapul. Ha nincs megadva csomagolási egység, akkor manuálisan is be lehet írni a csomagolási egységet és a csomagolási egység mennyiségét az értékesítésirendelés-sorba. Az értékesítésirendelés-sor feladása során módosítani lehet a csomagolási egységet és a csomagolási egység mennyiségét. Ez akkor lehet fontos, ha az értékesítésirendelés-sor szállítása vagy számlázása csak részben készül el. Az értékesítési rendelés számlázásakor, csomagolóanyag-tranzakciók jönnek létre. A csomagolóanyag-tranzakciók tartalmazzák az értékesítés sorhoz tartozó csomagolóanyag súlyát. Módosíthatja a tranzakciókat azok számlázását követően, majd új tranzakciókat hozhat létre.

## <a name="packing-units-on-purchase-order-lines"></a>A beszerzési rendelési sorokon lévő csomagolási egységek
Nem hoz létre a rendszer a beszerzési rendelés sorokhoz csomagolási anyag tranzakciókat. Tranzakciókat hoz létre manuálisan a számlázott beszerzési rendelési sorhoz a **Csomagolóanyag-tranzakciók** oldalon.

## <a name="set-up-customer-packaging-material-fee-license-numbers"></a>Vevő csomagolóanyag-díjakhoz való licencszámának beállítása
Ha a vevő fizeti a csomagolóanyag-díjakat, határozza meg a vevő csomagolási anyag díjához való licencszámokat a **Vevők** oldalon. Ha társított licencszámot a vevőhöz, akkor a program értékesítési rendelések számlázása során automatikusan kiszámítja a csomagolóanyag-díjakat. Számlázás után a **Díj kiszámítása** jelölőnégyzet törlődik a **Csomagoló anyag tranzakciók** oldalon, mert nem szükséges a kiszámítása és a jelentés nyomtatása. A csomagolóanyag súlyadatait rá lehet nyomtatni a számlára, és tájékoztatni lehet a vevőt arról, hogy ő fizeti a díjakat. 

Ha a vállalat fizeti a csomagolóanyag-díjakat, ne adja meg a vevő licencszámát. Számlázás után a **Díjak kiszámítása** jelölőnégyzet be van jelölve a **Csomagolóanyag-tranzakciók** oldalon. Ez azt jelzi, hogy egy jelentés létrejöttekor a díjak kiszámítása megtörtént. A súlyadatokat rá lehet nyomtatni a számlára, és jelezni lehet, hogy a vállalat fizeti a díjakat.

## <a name="print-packaging-material-weights-on-invoices"></a>Csomagolóanyag súlyadatainak nyomtatása a számlákra
A számlákra rá lehet nyomtatni a csomagolóanyag súlyadatait, és jelezni lehet, hogy ki fizeti a számlán szereplő csomagolóanyag-díjakat. A súlyok összegzése a csomagolóanyag-kód alapján történik.





