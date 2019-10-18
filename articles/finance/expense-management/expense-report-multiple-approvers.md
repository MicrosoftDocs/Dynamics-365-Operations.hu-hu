---
title: Költségjelentések és több jóváhagyó
description: Ez a témakör az egynél több személy jóváhagyását igénylő költségjelentésekkel kapcsolatban tartalmaz tájékoztatást.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d83a473e2e894856c12b36b4d005c6cb06b765a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178095"
---
# <a name="expense-reports-and-multiple-approvers"></a>Költségjelentések és több jóváhagyó

[!include [banner](../includes/banner.md)]

A szervezet költségjóváhagyási szabályaitól függően elképzelhető, hogy több mint egy személynek kell jóváhagynia egy adott alkalmazott által benyújtott költségjelentést. A költségjelentés jóváhagyási munkafolyamatának beállításakor olyan munkafolyamat-elemeket adhat meg, amelyek feladatokat vagy lépéseket tartalmaznak egy vagy több költségjelentés-jóváhagyó számára. Például előfordulhat, hogy minden költségjelentést először jóvá kell hagynia először a jelentést elküldő alkalmazott vezetőjének, majd a kötelezettségek koordinátorának.

Ha úgy dönt, hogy több költségjelentés-jóváhagyó szükséges, a munkafolyamat-elemeket a következő módok bármelyikével hozzáadhatja:

- Egy jóváhagyási elem hozzáadása, amelynek egy lépése van. Előfordulhat például, hogy lépés azt követelik meg, hogy a költségjelentés egy felhasználócsoporthoz legyen hozzárendelve, és ezután jóvá kell hagynia a felhasználói csoport tagjainak 50 százalékának.
- Egy jóváhagyási elem hozzáadása, amelynek több lépése van. Például a jóváhagyási elemnek a következő lépésekei lehetnek:

    1. A költségjelentést elküldő alkalmazott felettese jóváhagyja a költségjelentést.
    2. A Kötelezettségkezelő adminisztrátor ellenőrzi a nyugtákat és a költségjelentés elemeit.
    3. A költségvetésjóváhagyó jóváhagyja a költségjelentést.

- Több jóváhagyási elem hozzáadása, amelyek mindegyikének egy lépése van. Például különálló jóváhagyási elem hozzáadása az alábbi lépések mindegyikéhez:

    1. Az alkalmazott felettese jóváhagyja a költségjelentést.
    2. A költségvetésjóváhagyó jóváhagyja a költségjelentést.
