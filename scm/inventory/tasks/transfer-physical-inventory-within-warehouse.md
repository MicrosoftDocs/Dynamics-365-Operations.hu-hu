--- 
title: "Tényleges készlet áthelyezése a raktáron belül"
description: "Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: fedb209ab111ed1fb6281fda2f4dea345e0905ef
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Tényleges készlet áthelyezése a raktáron belül

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez. Először be kell állítani egy készletnaplónevet a készletmozgatáshoz. Végig mehet ezen az eljáráson az USMF bemutatócég esetében a megjelenített példaértékeket használva, vagy használhatja a saját adatait is ha beállított termékeket és helyeket. Ezeket a feladatokat általában egy raktári alkalmazott végzi el.


## <a name="create-an-inventory-transfer-journal"></a>Készletátviteli napló létrehozása
1. Ugrás az Áthelyezéshez.
2. Kattintson az Új lehetőségre.
3. A Név mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.
    * Az egyes naplósorok esetében meg lehet adni a „Kezdőérték” és a „Végérték” dimenziókat. Ezek a szükségesek ehhez a naplótípushoz. Más szabályokat alkalmazva is lehet cikkeket átszállítani. Ebben a példában egy adott raktáron belül fogunk egy cikket átszállítani, egy olyan helyről, ahol azonosítótábla alapján történik a vezérlés egy olyan helyre, ahol nem azonosítótábla alapján.   

## <a name="create-journal-lines"></a>Naplósorok létrehozása
1. Kattintson az Új lehetőségre.
2. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja az „A0001” lehetőséget.  
3. A Forrástelep mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja az „2” lehetőséget.  
4. A Céltelep mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja az „2” lehetőséget.  
5. A Forrásraktár mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a „24” lehetőséget  
6. A Célraktár mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a „24” lehetőséget  
7. A Forráshely mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja az „FL-001” lehetőséget.  
8. A Célhely mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a „BULK-001” lehetőséget.  
9. Adjon meg egy számot a Mennyiség mezőben.
10. Kattintson a Készlet dimenziók lapra.
11. Az Azonosítótábla mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a „24” lehetőséget  
12. Kattintson a Mentés gombra.

## <a name="post-the-inventory-transfer-journal"></a>Készletátviteli napló feladása
1. Kattintson a Feladás lehetőségre.
2. Kattintson az OK gombra.

## <a name="view-inventory-transactions"></a>Készlettranzakciók megtekintése
1. Kattintson a Készlet parancsra.
2. Kattintson a Tranzakciók elemre.
    * Itt láthatók a napló feladásakor létrehozott tranzakciók.  


