---
title: "Készlet napló jelentések"
description: "Konfigurálható nyilvántartási jelentések elektronikus jelentés alapján használatakor szüksége egy adott jelentés és a napló típusa közötti kapcsolat beállítása."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalName
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265144
ms.assetid: 0f07f62f-1053-46e9-b235-a7b38cbda409
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: eed3398651612743958722814ec5594ec34e4e5e
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-journal-reports"></a>Készlet napló jelentések

Konfigurálható nyilvántartási jelentések elektronikus jelentés alapján használatakor szüksége egy adott jelentés és a napló típusa közötti kapcsolat beállítása.

Egy adott jelentés és a napló típusa közötti kapcsolat beállítása a a **Készlet-napló neve** lap (**Inventory management**&gt;**a telepítő**&gt;**Naplónevek**&gt;**készlet**), adja meg a jelentés nevét. **Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat. További tudnivalókért lásd: [letöltés elektronikus jelentési szolgáltatások életciklus konfigurációk](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Példák a támogatott konfigurációk Európában a nyilvántartási jelentések az alábbi táblázatban szerepelnek.
|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| **Country**        | **Jelentés leírása**              | **Journal type** | **Formátum leképezésnév**                 |
| Litvánia, Magyarország | Jelentés          | Számlálás         | Készletkimutatás (HU, LT)            |
| Lettország, Lengyelország     | Készletátsorolási bizonylat | Átvitel         | InventoryReclassificationDocument\_PLLV |
| Észtország            | Készletátsorolási bizonylat | Átvitel         | InventoryReclassificationDocument\_EE   |
| Lengyelország             | Belső PW/RW                      | Mozgás         | InventJournalLinesDocPL                 |
| Lettország             |  Készletmozgási bizonylat         | Mozgás         | Mozgás\_LV                            |
| Lettország             | Leírás árukészlet-bizonylat       | Korrekció       | InventJournalLines\_LV                  |
| Lettország             | Szállítás - szállítólevél              | Átvitel         | InternalTransferDeliveryNote\_LV        |
| Lettország             | Leltári bizonylat jelentés            | Számlálás         | CountedDocument\_LV                     |
| Lettország             | Leltárlista-jelentés                | Számlálás         | Leltárlista                           |




