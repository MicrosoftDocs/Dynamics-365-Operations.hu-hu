---
title: Tényleges készlet áthelyezése a raktáron belül
description: Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez.
author: MarkusFogelberg
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a298f05185f3c81f2fde995e4d731b95a5f8d870
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832106"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Tényleges készlet áthelyezése a raktáron belül

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez. Először be kell állítani egy készletnaplónevet a készletmozgatáshoz. Végig mehet ezen az eljáráson az USMF bemutatócég esetében a megjelenített példaértékeket használva, vagy használhatja a saját adatait is ha beállított termékeket és helyeket. Ezeket a feladatokat általában egy raktári alkalmazott végzi el.


## <a name="create-an-inventory-transfer-journal"></a>Készletátviteli napló létrehozása
1. A **Navigációs ablaktáblán** lépjen a **Készletgazdálkodás > Naplóbejegyzések > Cikkek > Átvitel** elemre.
2. Kattintson az **Új** elemre.
3. A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az **OK** gombra. Az egyes naplósorok esetében meg lehet adni a „Kezdőérték” és a „Végérték” dimenziókat. Ezek a szükségesek ehhez a naplótípushoz. Más szabályokat alkalmazva is lehet cikkeket átszállítani. Ebben a példában egy adott raktáron belül fogunk egy cikket átszállítani, egy olyan helyről, ahol azonosítótábla alapján történik a vezérlés egy olyan helyre, ahol nem azonosítótábla alapján.   

## <a name="create-journal-lines"></a>Naplósorok létrehozása
1. A **Naplósorok gyorslapon** kattintson az **Új** lehetőségre.
2. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja az „A0001” lehetőséget.  
3. A **Forrástelephely** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja az „2” lehetőséget.  
4. A **Céltelephely** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja az „2” lehetőséget.  
5. A **Forrásraktár** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja a „24” lehetőséget  
6. A **Célraktár** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja a „24” lehetőséget  
7. A **Forráshely** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja az „FL-001” lehetőséget.  
8. A **Célhely** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja a „BULK-001” lehetőséget.  
9. Adjon meg egy számot a **Mennyiség** mezőben.
10. A **Sorrészletek** gyorslapon kattintson a **Készletdimenziók** lapra.
11. A **Forrás-készletdimenziók** pontban az **Azonosítótábla** mezőben adjon meg vagy válasszon egy értéket. Az USMF használata esetén választhatja a „24” lehetőséget  
12. Kattintson a **Mentés** gombra.

## <a name="post-the-inventory-transfer-journal"></a>Készletátviteli napló feladása
1. A **Művelet panelen** kattintson a **Feladás** elemre.
2. Kattintson az **OK** gombra.

## <a name="view-inventory-transactions"></a>Készlettranzakciók megtekintése
1. Kattintson a **Készlet** parancsra.
2. Kattintson a **Tranzakciók** elemre. Itt láthatók a napló feladásakor létrehozott tranzakciók.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]