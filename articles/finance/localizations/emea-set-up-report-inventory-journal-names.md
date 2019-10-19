---
title: Készletnapló-jelentések
description: Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d051c8ab7f15f69dd06db0986c3151b61d595b6d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175769"
---
# <a name="inventory-journal-reports"></a>Készletnapló-jelentések

[!include [banner](../includes/banner.md)]

Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.

Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét. **Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat. További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.

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





