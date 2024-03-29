---
title: Készletszintek kiigazítása a raktárban (alap raktározáskészlet-nyilvántartás)
description: Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készlethelyesbítési napló a raktárban található termékek készletszintjének helyesbítéséhez.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02458d588c9925a1f4cb9afeada793dfc55a2071
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573825"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Készletszintek kiigazítása a raktárban (alap raktározáskészlet-nyilvántartás)

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készlethelyesbítési napló a raktárban található termékek készletszintjének helyesbítéséhez. Ennek megkezdése előtt először be kell állítani egy készletnaplónevet a készlethelyesbítéshez. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. Ezeket a feladatokat általában egy raktári alkalmazott végzi el.


## <a name="create-an-inventory-adjustment-journal"></a>Készlethelyesbítési napló létrehozása
1. Ugrás a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Készlethelyesbítés lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a készlethelyesbítési naplónévre, amelyet használni kíván.
    * Ki lesz töltve néhány más mező a kiválasztott készlethelyesbítés naplónév beállításai alapján.  
5. Kattintson az OK gombra.

## <a name="create-journal-lines"></a>Naplósorok létrehozása
1. Kattintson az Új lehetőségre.
2. A listában jelölje ki a Cikkszám mezőt.
3. Válasszon egy cikket a Cikkszám mezőben. Az USMF bemutatócég használata esetén írja be a „D0001” kódot.
4. A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában válasszon ki egy telephelyet.
6. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listában válasszon ki egy raktárat.
    * Ha egy olyan cikket választott ki, amelynek kötelező dimenziója a Hely, itt kell megadnia a helyet.  
8. Adjon meg egy számot a Mennyiség mezőben.
    * Az önköltségi ár mező meghatározza az egységenkénti költséget a készletbevételek számára. Ha nincs megadva a költség a cikkszámhoz, vagy ha manuálisan szeretné módosítani a költséget, azt itt teheti meg.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Készlethelyesbítési napló érvényesítése és feladása
1. Kattintson az Érvényesítés gombra.
2. Kattintson az OK gombra.
3. Kattintson a Feladás lehetőségre.
    * Az ilyen típusú napló feladásakor a rendszer egy készletbevételezést vagy készletkiadást ad fel, módosítja a készletszintet és a készletértéket, és főkönyvi tranzakciókat generál.  
4. Kattintson az OK gombra.
5. Zárja be az űrlapot.
6. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]