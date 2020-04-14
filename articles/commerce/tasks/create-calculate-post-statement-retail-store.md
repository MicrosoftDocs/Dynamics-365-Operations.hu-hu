---
title: Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása
description: Ez az témakör leírja egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21f1b0a34205e192957405bc9d298c45c8bb4d25
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141014"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása

[!include [banner](../includes/banner.md)]

Ez az témakör leírja egy üzlet kimutatása létrehozásának, kiszámításának és feladásának manuális lépéseit. Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók. A kötegelt feladatok konfigurálásának és futtatásának lépései egy másik témakörben találhatók meg. Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics 365 Commerce programba. Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat.

1. Válassza ki az **Üzlet pénzügyei** lehetőséget a kezdőlapról.
2. Válassza az **Új kimutatás** lehetőséget.
3. Az **Üzlet száma** mezőben válasszon ki egy opciót a legördülő menüben.
4. Válassza ki az **OK** lehetőséget.
5. A **Beállítások** csoportban beállíthatja, hogy mely tranzakciók szerepeljenek a kimutatásban, és hogy azok hogyan legyenek sorokba csoportosítva. Megnyithatja a **Beállítások** csoportot és megváltoztathatja a beállításokat, vagy használhatja az alapértelmezett beállításokat is.  
    - A **Kimutatás módja** mező megadja, hogy a kimutatás sorai hogyan lesznek csoportosítva.  
    - Válasszon ki egy munkatársat vagy egy jegyzéket a **munkatárs/jegyzék** mezőben, ha a kimutatást csak egy bizonyos munkatársra vagy jegyzékre vonatkozóan szeretné elkészíteni.  
6. Válassza ki valamelyik lehetőséget a **Zárási mód** mezőben.
7. Válassza a **Kimutatás számítása** lehetőséget a Művelet alaktábláról.
8. Válassza ki az **Igen** lehetőséget.
    - A kimutatás elkészítése után külön sorokban kell szerepelnie a teljes összegnek minden alkalmazott fizetési mód és kimutatási mód esetén.  
    - Adjon meg egy leszámolt összeget minden sorban, amelyben meg kell adni vagy frissíteni kell az értéket. A leszámolt értéket tartalmazó mező a pénztárban végrehajtott fizetőeszköz-elszámolások során kapott összeggel van kitöltve.  
9. Válassza a **Kimutatás feladása** lehetőséget a Művelet alaktábláról.
10. Válassza **Bezárás** lehetőséget.
11. Zárja be a panelt.
12. A kezdőlapon válassza ki az **Üzlet pénzügyei** lehetőséget.
13. Kattintson a **Feladott kimutatások** fülre.

