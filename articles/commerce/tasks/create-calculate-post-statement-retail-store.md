---
title: Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása
description: Ez a témakör az áruházi kimutatások létrehozásához, kiszámításához és feladására vonatkozó kézi lépéseket ismerteti.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 740857e6a902e21588855eef5e36cac68e560898
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873278"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Kiskereskedelmi üzlet kimutatásainak létrehozása, kiszámítása és feladása

[!include [banner](../includes/banner.md)]

Ez a témakör az áruházi kimutatások létrehozásához, kiszámításához és feladására vonatkozó kézi lépéseket ismerteti. Kötegelt feladatok is léteznek, amelyek ugyanazon eljárásokhoz konfigurálhatók. A kötegelt feladatok konfigurálásához és futtatásához szükséges lépések más cikkekben találhatók. Az eljárás végrehajtásához rendelkeznie kell olyan tranzakciókkal, amelyeket a pénztárban hajtottak végre, majd átvezették a Dynamics 365 Commerce programba. Ez a bejegyzés az USRT cég adatait használja, mint bemutatóadatokat.

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]