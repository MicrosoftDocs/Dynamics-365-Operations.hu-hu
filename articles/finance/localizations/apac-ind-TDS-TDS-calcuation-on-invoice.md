---
title: TDS-számítás a számlákon
description: Ez a témakör olyan tranzakciókra hivatkozik, amelyeknél a Forrásnál levont adót (TDS) a számla szintjén számítják ki.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5a4c3e13eba76db2fae1f66560a2fea68d9a3c5f
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407947"
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
