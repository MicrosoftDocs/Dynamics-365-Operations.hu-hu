---
title: TDS-számítás a számlákon
description: Ez a témakör olyan tranzakciókra hivatkozik, amelyeknél a Forrásnál levont adót (TDS) a számla szintjén számítják ki.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 496e87e3028025f738d2f0a697d91c18b77ad1c9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023302"
---
# <a name="tds-calculation-on-invoices"></a>TDS-számítás a számlákon

[!include [banner](../includes/banner.md)]

Ez a témakör olyan tranzakciókra hivatkozik, amelyeknél a Forrásnál levont adót (TDS) a számla szintjén számítják ki.

| Sorozatszám | Tranzakció típusa                                 | Tranzakció összege | Oldal neve és kijelölési útvonala                                 | Számla típusa és ellenszámla típusa                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Szállítótól történő vásárlás / költségek nyilvántartása   | Terhelés vagy jóváírás  | Főkönyvi naplók oldal (Főkönyvi > Naplóbejegyzések > Általános naplók), Számlajóváhagyási napló lap (Kötelezettségek > Számlák > Számla jóváhagyása), Számlanapló oldal (Kötelezettségek > Számlák > Számlanapló) | Főkönyv (Dr.), Szállító (Cr.).  Az adóelőleget csak akkor számítják ki a Szállító-Főkönyvi kombinációra, ha a Főkönyvi számlán a könyvelés típusa: **Vásárlás** **készpénz**. |
| 2.            | Ügyféltől történő vásárlás / költségek nyilvántartása | Terhelés vagy jóváírás  | Általános naplók oldal (Főkönyvi > Naplóbejegyzések > Általános naplók), Számlanapló oldal (Kintlévőségek > Számlák > Számlanapló) | Főkönyv (Dr.), Ügyfél (Cr.)                                 |
| 3.            | Tárgyi eszköz beszerzése a szállítótól              | Terhelés vagy jóváírás  | Főkönyvi naplók oldal (Főkönyvi > Naplóbejegyzések > Általános naplók), Számlajegyzék napló lap (Kötelezettségek > Számlák > Számla jegyzék), Számlanapló oldal (Kötelezettségek > Számlák > Számlanapló) | Tárgyi eszközök (Dr.) Szállító (Cr.)                             |
| 4.            | Tárgyi eszköz beszerzése a ügyféltől            | Terhelés vagy jóváírás  | Általános naplók oldal (Főkönyvi > Naplóbejegyzések > Általános naplók), Számlanapló oldal (Kintlévőségek > Számlák > Számlanapló) | Tárgyi eszközök (Dr.) Ügyfél (Cr.)                           |
| 5.            | Beszerzési számla (TDS fizetendő)                  |                    | Beszerzési rendelés lap (Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés) |                                                              |
| 6.            | Értékesítési számla (TDS visszaigényelhető)                  |                    | Értékesítési rendelés oldal (Kintlévőségek > Megrendelések > Összes értékesítési rendelés), Szabadszöveges számla oldal (Kintlévőségek > Számlák > Összes szabadszöveges számla) |                                                              |
