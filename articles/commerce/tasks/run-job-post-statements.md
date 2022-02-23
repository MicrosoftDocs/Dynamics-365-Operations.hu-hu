---
title: Kimutatások feladásához használt feladat konfigurálása és futtatása
description: Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport esetén kimutatásokat feladni.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89203850b302b769b22920fa5c42d2b0b877684
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412894"
---
# <a name="configure-and-run-job-to-post-statements"></a>Kimutatások feladásához használt feladat konfigurálása és futtatása

[!include [banner](../includes/banner.md)]

Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport esetén kimutatásokat feladni. Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.

1. Lépjen Az összes munkaterület > .. > Üzlet pénzügyei.
2. Kattintson a Kimutatások kötegelt feladása lehetőségre.
    * Válasszon ki egy szervezeti hierarchiát, majd a szervezeti csomópontok fastruktúrájában válasszon ki egy egyéni üzletet vagy egy csomópontot. Válasszon ki egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.  
    * Kattintson a nyílra a kiválasztás hozzáadásához.  
3. Kattintson a Futtatás a háttérben lapra. ![Futtatás a háttérben](../dev-itpro/media/runbackground.png "Futtatás a háttérben") 
4. Jelölje be vagy törölje a jelölést a Kötegelt feldolgozás jelölőnégyzetben.
![Kötegelt feldolgozás](../dev-itpro/media/batchprocessing.png "Kötegelt feldolgozás és ismétlődés") 
5. Kattintson az Ismétlődésre.
6. Adja meg a dátumot a Kezdő dátum mezőben.
7. A Kezdés ideje mezőben adjon meg egy időt.
    * Válassza ki, hogy mikor kívánja befejezni az ismétlődést: egy bizonyos számú lefutás után, egy meghatározott dátum elérésekor, vagy soha. Majd a különféle lehetőségek segítségével adja meg, hogy milyen gyakran szeretné futtatni a feladatot.  
8. Kattintson az OK gombra.
9. Kattintson az OK gombra.

