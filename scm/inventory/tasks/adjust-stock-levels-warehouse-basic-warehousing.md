--- 
title: "Készletszintek kiigazítása a raktárban (alap raktározáskészlet-nyilvántartás)"
description: "Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készlethelyesbítési napló a raktárban található termékek készletszintjének helyesbítéséhez."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: f96db79bcb6ec26daaeb66d29edb18486daafab0
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# Készletszintek kiigazítása a raktárban (alap raktározáskészlet-nyilvántartás)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készlethelyesbítési napló a raktárban található termékek készletszintjének helyesbítéséhez. Ennek megkezdése előtt először be kell állítani egy készletnaplónevet a készlethelyesbítéshez. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. Ezeket a feladatokat általában egy raktári alkalmazott végzi el.


## Készlethelyesbítési napló létrehozása
1. Ugrás a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Készlethelyesbítés lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a készlethelyesbítési naplónévre, amelyet használni kíván.
    * Ki lesz töltve néhány más mező a kiválasztott készlethelyesbítés naplónév beállításai alapján.  
5. Kattintson az OK gombra.

## Naplósorok létrehozása
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

## Készlethelyesbítési napló érvényesítése és feladása
1. Kattintson az Érvényesítés gombra.
2. Kattintson az OK gombra.
3. Kattintson a Feladás lehetőségre.
    * Az ilyen típusú napló feladásakor a rendszer egy készletbevételezést vagy készletkiadást ad fel, módosítja a készletszintet és a készletértéket, és főkönyvi tranzakciókat generál.  
4. Kattintson az OK gombra.
5. Zárja be az űrlapot.
6. Zárja be a lapot.

