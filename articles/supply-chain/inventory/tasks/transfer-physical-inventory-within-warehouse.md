---
title: Tényleges készlet áthelyezése a raktáron belül
description: Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79b3e91be8aeab10188b6d3925d44a9ec1106406
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "367294"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Tényleges készlet áthelyezése a raktáron belül

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

