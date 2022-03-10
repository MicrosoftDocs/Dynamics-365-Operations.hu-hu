---
title: Készlet számlálása egy raktárban
description: Ez a témakör leírja azt a folyamatot amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához.
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7dd3788d3cbf80bfba373f5b6ce9d2e0ca0c07
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578415"
---
# <a name="count-inventory-in-a-warehouse"></a>Készlet számlálása egy raktárban

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja azt a folyamatot amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához. Ez az eljárás az „alapvető raktározás” szolgáltatásra vonatkozik, amely a Készletgazdálkodás modul része, és nem a „raktározás” szolgáltatásra, amely a Raktárkezelés modul része. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. Ha a saját adatait használja, ügyeljen rá, hogy legyenek beállított termékek és helyek, és hogy létrehozzon egy készletnaplónevet a leltárnaplókhoz. A készletleltározást általában egy raktári alkalmazott végzi el.


## <a name="create-an-inventory-counting-journal"></a>Készletleltározási napló létrehozása
1. Lépjen a **Navigációs panel > Modulok >Készletgazdálkodás > Naplóbejegyzések > Cikkleltár > Leltár** menüpontba.
2. Válassza az **Új** lehetőséget.
3. A **Név** mezőben válassza ki a használni kívánt készletleltár-napló nevét a legördülő listáról. Ki lesz töltve néhány más mező a kiválasztott készletleltározási naplónév beállításai alapján.  
4. A **Dolgozó** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listából **Válassza ki** a használni kívánt dolgozót.
6. Válassza ki az **OK** lehetőséget.

## <a name="create-journal-lines"></a>Naplósorok létrehozása
1. Válassza az **Új** lehetőséget.
2. A **Cikkszám** mezőben válassza ki a kívánt rekordot a legördülő listából. Az USMF bemutatócég használata esetén válassza az **A0001** lehetőséget.  
3. A **Hely** mezőben válassza ki a kívánt rekordot a legördülő listából. Az USMF bemutatócég használata esetén válassza a **2** telephelyet.
4. A **Raktár** mezőben válassza ki a kívánt rekordot a legördülő listából. Az USMF bemutatócég használata esetén válassza az **24** raktárat.  
5. A **Hely** mezőben válassza ki a kívánt rekordot a legördülő listából. Az USMF bemutatócég használata esetén válassza a **BULK-001** helyet  
6. Adjon meg egy számot a Leltározva mezőben. Ha olyan megszámolt darabszámot ír be, amely különbözik az **Aktuális készlet** mezőben láthatótól, akkor a **Mennyiség** mező frissül, hogy mutassa az értékeltérést.  
7. Válassza a **Mentés** lehetőséget.

## <a name="post-the-inventory-counting-journal"></a>Készletleltározási napló feladása
1. Válassza a **Feladás** parancsot. Készletleltározási napló feladásakor, ha a megszámolt darabszám különbözik az **Aktuális készlet** mezőben láthatótól, feladásra kerül egy készletbevétel vagy -kiadás, módosul a készletszint és a készletérték, és főkönyvi tranzakciók jönnek létre.
2. Válassza ki az **OK** lehetőséget.

## <a name="view-inventory-transactions"></a>Készlettranzakciók megtekintése
1. Válassza a **Készlet** lehetőséget.
2. Válassza a **Tranzakciók** lehetőséget. Itt láthatók a kapcsolódó tranzakciók, amelyek a készletleltározási napló feladásakor jönnek létre.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]