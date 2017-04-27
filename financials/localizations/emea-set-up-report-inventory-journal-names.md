---
title: "Készletnapló-jelentések"
description: "Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között."
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

# <a name="inventory-journal-reports"></a>Készletnapló-jelentések

[!include[banner](../includes/banner.md)]


Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.

Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét. **Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat. További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.
|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| **Ország**        | **Jelentés leírása**              | **Napló típusa** | **Formátum-hozzárendelés neve**                 |
| Litvánia, Magyarország | Készletkimutatás-jelentés          | Számlálás         | Készletkimutatás (HU, LT)            |
| Lettország, Lengyelország     | Készletátsorolási bizonylat | Átvitel         | InventoryReclassificationDocument\_PLLV |
| Észtország            | Készletátsorolási bizonylat | Átvitel         | InventoryReclassificationDocument\_EE   |
| Lengyelország             | Belső PW/RW                      | Mozgás         | InventJournalLinesDocPL                 |
| Lettország             |  Készletmozgási bizonylat         | Mozgás         | Mozgás\_LV                            |
| Lettország             | Készletleírási bizonylat       | Korrekció       | InventJournalLines\_LV                  |
| Lettország             | Szállítás - szállítólevél              | Átvitel         | InternalTransferDeliveryNote\_LV        |
| Lettország             | Leltáribizonylat-jelentés            | Számlálás         | CountedDocument\_LV                     |
| Lettország             | Leltárlista-jelentés                | Számlálás         | Leltárlista                           |






