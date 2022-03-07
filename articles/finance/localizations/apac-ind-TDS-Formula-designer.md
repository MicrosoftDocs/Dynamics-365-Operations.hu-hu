---
title: Képlettervező TDS-számításokhoz
description: Ez a témakör egy példát mutat arra, hogy a Forrásnál levont adót (TDS) hogyan számítják ki a tranzakcióhoz csatolt TDS-csoport minden egyes TDS-adókódjára meghatározott képlet alapján.
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
ms.openlocfilehash: e9c97982233b1f3dc3924fa42954b5cb8d09ffcaa07d19a3892b25737a6c29c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778869"
---
# <a name="formula-designer-for-tds-calculations"></a>Képlettervező TDS-számításokhoz

[!include [banner](../includes/banner.md)]

Ez a témakör egy példát mutat arra, hogyan számítják ki a forrásnál levont adót (TDS) az egyes TDS-adókódokra meghatározott képlet alapján. A TDS adókódokat a tranzakcióhoz csatolt TDS csoport határozza meg. A TDS-képletek tervezése előtt töltse ki a TDS-hez szükséges alapbeállítást a következő lépésekben felsoroltak szerint. 

- Állítsa be a TDS-adóelőleg-összetevőkkel kapcsolatos csoportokat az **Adóelőleg-összetevő csoportok** oldalon. 
- Állítsa be a TDS-összetevőket, és csatolja a TDS-összetevők csoportját a TDS-összetevőkhöz az **Adóelőleg-összetevők** oldal használatával. 
- Állítsa be a TDS-adókódokat, és csatolja a TDS-adókódok csoportját az adókódokhoz az **Adóelőlegkódok** oldal használatával. 
- Állítsa be a TDS-adócsoportokat az **Adóelőleg csoportok** oldalon. Ezután csatolja a TDS-adókódokat az adócsoporthoz, és határozza meg a képletet a **Képlettervező** oldalon. 

**Példa képlet**

Ebben a példában a Bérleti díj nevű TDS-csoport az „A” szállító számára létrehozott beszerzési számlához van csatolva. A számla összege $100 000. A számla TDS-számításának megtekintéséhez hivatkozzon az alábbi táblázatra.

| TDS-csoport                                                   | A TDS-csoporthoz csatolt TDS-adókódok | Érték              | Adóalap (Képlettervező) | Számítási kifejezés (Képlettervező) | Alapösszeg | Számított TDS összege |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Bérlet                                                         | TDS (TDS-összetevő - TDS)                | 10%                | Bruttó összeg                      |                                            | 100,000      | 10,000                 |
| Felár (TDS-összetevő - Felár)                         | 10%                                     | Kiz. bruttó összeg | +TDS                              |                   10000                    | 1000        |                       |
| PE-Cess (TDS-összetevő - PE-Cess)                            | 2%                                      | Kiz. bruttó összeg | +TDS+Pótdíj                    |                   11000                    | 220         |                       |
| SHE Cess (TDS-összetevő - SHE Cess)                          | 1%                                      | Kiz. bruttó összeg | +TDS+Pótdíj                    |                   11000                    | 110         |                       |
| **A** **számlára** **számított** **összes** **TDS** | **11,330**                               |                    |                                   |                                            |             |                       |

A bizonylatbejegyzések az alábbiak szerint jönnek létre.

| Könyvelési számla           | Tartozik  | Követel |
| ----------------- | ------ | ------ |
| Bérlet              | 100,000 |        |
| Szállító A          |        | 100,000 |
| Szállító A          | 11,330  |        |
| TDS-fizetendő       |        | 10,000  |
| Fizetendő pótdíj |        | 1000   |
| PE-Cess fizetendő   |        | 220    |
| SHE Cess fizetendő  |        | 110    |
