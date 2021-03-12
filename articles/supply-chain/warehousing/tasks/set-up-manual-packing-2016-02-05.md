---
title: A kézi csomagolás beállítása (2016. február és 2016. május)
description: A csomagolási folyamat lehetővé teszi az érvényesítést és a termékek tárolókba történő csomagolását.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84a405b2a0afa3541fa0d691d751ecea0ad6606a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976988"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a>A kézi csomagolás beállítása (2016. február és 2016. május)

[!include [banner](../../includes/banner.md)]

A csomagolási folyamat lehetővé teszi az érvényesítést és a termékek tárolókba történő csomagolását. Ebben a folyamatban a raktárosok a tárolási helyekből helyezik át a termékeket és azon csomagolási állomásra helyezik át ezeket, ahol a cikk mennyiségét és minőségét ellenőrzik, illetve hozzárendelik ezeket a megfelelő tárolókhoz. Amikor a tároló teljesen tele van, bezárhatja, illetve áthelyezheti a kiszállítási területekre, és a termékek készen állnak a szállításra. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás csak a Dynamics 365 for Operations 2016. februári és 2016. májusi verzióira vonatkozik.


## <a name="set-up-location-profiles"></a>Helyprofilok beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési > Helyprofilok pontra.
2. Kattintson az Új lehetőségre.
    * A helyprofilt a csomagoló helyekre vonatkozóan használja a rendszer, és a helyre vonatkozó információkat és szabályokat tartalmaz.  
3. Írjon egy értéket a Helyprofil azonosítója mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Helyformátum mezőben adjon meg vagy válasszon ki egy értéket.
6. A Hely típusa mezőben adjon meg vagy válasszon ki egy értéket.
7. Válassza ki az Igen lehetőséget a Vegyes cikkek engedélyezése mezőben.
8. Válassza ki az Igen lehetőséget a Vegyes készletállapotok engedélyezése mezőben.
9. Válassza ki az Igen lehetőséget a Kötegelési időszak szabályainak felülbírálása mezőben.
10. Zárja be a lapot.

## <a name="set-up-warehouse-management-parameters"></a>Raktárkezelési paraméterek beállítása 
1. Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.
2. Kattintson Csomagolás fülre.
3. Adjon meg vagy válasszon ki egy értéket a Csomagolási hely profilazonosítója mezőben.
    * Válassza ki a csomagolásra használni kívánt helyprofilt.  
4. Zárja be a lapot.

## <a name="set-up-container-types"></a>Tárolótípusok beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolótípusok pontra.
2. Kattintson az Új lehetőségre.
    * Meghatározhatja a használni kívánt tároló típusait. Megadhatja a tároló fizikai dimenzióit, többek között a csomagolási súlyát, az össztömegét, a maximális térfogatát, a hosszúságát, a szélességét és a súlyát.  Az attribútumok olyan testreszabott mezők, amelyek lehetővé teszik az extra dimenziók hozzáadását a tárolótípuson.     
3. Írjon be egy értéket a Tároló típuskódja mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Adjon meg egy számot a Tárasúly mezőben.
6. Adjon meg egy számot a Maximális súly mezőben.
7. A Térfogat mezőben adjon meg egy számot.
8. Adjon meg egy számot a Hosszúság mezőben.
9. Adjon meg egy számot a Szélesség mezőben.
10. Adjon meg egy számot a Magasság mezőben.
11. Kattintson a Mentés gombra.
12. Zárja be a lapot.

## <a name="set-up-packing-profiles"></a>Csomagolási profilok beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Csomagolás > Csomagolási profilok pontra.
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket a Csomagolási profil azonosítója mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Adjon meg vagy válasszon ki egy értéket a Tárolólezárási profil azonosítója mezőben.
    * A tárolólezárási profil azonosítója nem kötelező, és a csomagolási profilra vonatkozó alapértelmezett tárolólezárási profil.  
6. Válasszon ki egy lehetőséget a Tárolóazonosító mód mezőben.
    * Ez a beállítás határozza meg, hogy a rendszer létrehozza-e automatikusan a tárolóazonosítót a tároló létrehozásakor vagy manuálisan hozzák létre a tárolóazonosítót.  
7. A tárolótípus mezőben adjon meg vagy válasszon ki egy értéket.
    * Alapértelmezés szerint használják a tárolótípust, amikor létrejön egy új tároló.  
8. Válassza ki a Tároló automatikus létrehozása a tároló lezárásakor jelölőnégyzetet.
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.

## <a name="set-up-container-closing-profiles"></a>Tárolólezárási profilok beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolólezárási profilok pontra.
    * A tárolólezárási profilok határozza meg, hogy mi történjen, ha a tároló le van zárva. Több tárolólezárási profilt állíthat be.       
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Tárolólezárási profil azonosítója mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Válasszon ki egy lehetőséget a Jegyzékfájl ekkor: mezőben.
    * Határozza meg, hogy a jegyzékbe foglalás a tárolók lezárásakor vagy a szállítmány megerősítésekor történjen. Vegye figyelembe, hogy a jegyzékbe foglalás Szállításkezelést igényel. A Jegyzékbe foglalást a Szállításkezelő kalkulátorokban kell végrehajtani a működéshez.  
6. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
7. Adjon meg vagy válasszon ki egy értéket a Végső szállítmány alapértelmezett helye mezőben.
    * Ez a hely, ahova a termékeket áthelyezik a tárolók bezárása után. Ezen helynek rendelkeznie kell a Raktárház paramétereiben meghatározott helyprofillal.  
8. A Súlyegység mezőben adjon meg, vagy válasszon ki egy értéket.
9. Kattintson a Mentés gombra.

