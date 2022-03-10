---
title: Készletnapló-jelentések
description: Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.
author: anasyash
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: kfend
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: anasyash
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c2e1f8c534cf63ee65d29ccaa797c8a5a339a87b
ms.sourcegitcommit: 49f29aaa553eb105ddd5d9b42529f15b8e64007e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2021
ms.locfileid: "7592462"
---
# <a name="inventory-journal-reports"></a>Készletnapló-jelentések

[!include [banner](../includes/banner.md)]

Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.

Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét. **Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat. További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.

| Ország/régió            |    Jelentés leírása               | Napló típusa     |    Formátum-hozzárendelés neve                  |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| Litvánia, Magyarország | Készletkimutatás-jelentés          | Számlálás         | Készletkimutatás (HU, LT)            |
| Lettország, Lengyelország     | Készletátsorolási bizonylat | Átvitel         | InventoryReclassificationDocument\_PLLV |
| Észtország            | Készletátsorolási bizonylat | Átvitel         | InventoryReclassificationDocument\_EE   |
| Lengyelország             | Belső PW/RW                      | Mozgás         | InventJournalLinesDocPL                 |
| Lettország             |  Készletmozgási bizonylat         | Mozgás         | Mozgás\_LV                            |
| Lettország             | Készletleírási bizonylat       | Korrekció       | InventJournalLines\_LV                  |
| Lettország             | Szállítás - szállítólevél              | Átvitel         | InternalTransferDeliveryNote\_LV        |
| Lettország             | Leltáribizonylat-jelentés            | Számlálás         | CountedDocument\_LV                     |
| Lettország             | Leltárlista-jelentés                | Számlálás         | Leltárlista                           |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
