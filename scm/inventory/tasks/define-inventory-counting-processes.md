--- 
title: "Készletleltár-folyamatok meghatározása"
description: "Ez az eljárás végigvezeti az alapvető leltározási folyamatokon a leltárcsoport és a leltárnapló létrehozásával."
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
ms.openlocfilehash: 62c60faafd9ad96ce636a08102bc8652f9fff870
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="define-inventory-counting-processes"></a>Készletleltár-folyamatok meghatározása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás végigvezeti az alapvető leltározási folyamatokon a leltárcsoport és a leltárnapló létrehozásával. Azt is bemutatja, hogy hogyan engedélyezheti a leltározási irányelveket raktár vagy cikk szintjén. Ezeket a feladatokat jellemzően egy raktárvezető végzi el. Ez előfeltétele annak, hogy legyen létező kiadott termék és raktár. Ha bemutató adatokat használ, ezt az eljárást az USMF vállalatban bármilyen raktározott cikkre futtathatja.


## <a name="create-a-counting-group"></a>Leltárcsoport létrehozása
1. Ugorjon a Készletkezelés > Beállítás Készlet > Leltárcsoportok pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Leltárcsoport mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. A Leltárcsoport mezőben válasszon ki egy lehetőséget.
    * Manuális − a feladat minden egyes futtatásakor tartalmazza a sorokat. Más szóval megadható a leltárcsoport leltározási időszaka.  Időszakos − tartalmazza az időszak sorait a leltárnaplóban az időtartam lejárta után.   Nulla a készleten − ha az aktuális készlet nullára (0) csökken, akkor a feladat futtatásakor létrejönnek sorok a leltárnaplóban. Ha az aktuális készlet nullára csökken a leltározás során, akkor a sorok a leltározás következő indításakor jönnek létre.   Minimum − sorok létrehozása a leltárnaplóban, ha az aktuális készlet a megadott minimummal egyenlő vagy a minimum alá csökken.  
    * Opcionális: Ha a leltárkód mezőben az Időszak elemet választja, a Leltáridőszak mezőbe kell beírnia az időszak tartamát. Az időszakok egysége a nap.  
    * Amikor futtatja a leltárnapló új sorainak létrehozására szolgáló feladatot, a jelen mezőben meghatározott intervallum szerint kerülnek létrehozásra az új sorok, függetlenül az adott feladat futtatási gyakoriságától. Ha például a Leltározási időszak 7 és a naplósorokat a leltárhoz utoljára január 1-jén hozta létre, ha január 5-én újabb feladatot indít, még nem telt el hét nap, ezért a rendszer nem hoz létre új sort a naplóban ahhoz az időszaki intervallumhoz. Ha január 8-án újra elindítja a feladatot, akkor az időtartamhoz kapcsolódó sorok létrejönnek a leltárnaplóban, mivel már eltelt 7 nap.  
6. Kattintson a Mentés gombra.

## <a name="create-a-counting-journal-name"></a>Hozzon létre egy leltárnaplónevet.
1. Ugorjon a Készletkezelés > Beállítás > Naplónevek > Készlet pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Naplótípus mezőben válassza ki a „Leltár” lehetőséget.
    * Opcionális: másik bizonylatsorozat-azonosítót is választhat, ha adott számsort kíván beállítani a bizonylati azonosítónak a leltárnaplók létrehozásakor. A bizonylatsorozat a Számsorozatok oldalon hozható létre.  
6. Válasszon egy lehetőséget a Részletezési szint mezőben.
    * Ez a napló feladásakor alkalmazott részletességi szint.  
    * Opcionális: módosíthatja a Foglalás mezőben levő értéket. Ezzel a módszerrel leltár során foglalhat cikkeket.   
    * Kézi – a cikkek foglalása manuálisan történik a Foglalás képernyőn.   Automatikus – a rendelési mennyiséget a program a cikk elérhető aktuális készletében foglalja le.   Alábontás – a foglalás része a tranzakció alaptervezésének.  
7. Kattintson a Mentés gombra.

## <a name="set-standard-counting-journal-name"></a>Szokásos leltárnaplónév beállítása
1. Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.
2. Kattintson a Naplók fülre.
3. A Leltár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Válassza ki a korábban létrehozott naplót.
    * Ez a napló lesz ezután az alapértelmezett naplónév a Számlálási típus készletnaplóihoz.  
5. Kattintson az Általános fülre.
    * Opcionális: Válassza ezt a lehetőséget az egyik cikk lezárásához a számolási folyamat során, hogy megakadályozza a szállítólevelek és kitárolási listák frissítését vagy kitárolási listák regisztrációját.  

## <a name="set-the-counting-policy-for-an-item"></a>Leltározási irányelv beállítása egy cikkhez
1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. A listában kattintson a Cikkszám hivatkozására annál a terméknél, amelynél leltározási irányelvet szeretne beállítani.
    * Olyan cikket kell kiválasztania, amely a készletben nyomon követett. A nem készletezett termék nem számlálható. Az USMF bemutatóadatok használata esetén válassza az A0001 cikket.  
3. Kattintson a Szerkesztés lehetőségre.
4. A Készletkezelés szakasz bővítésének átváltása.
5. A Leltárcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A listán kattintson a korábban létrehozott leltárcsoportra.
    * Ez a termék mostantól mindig hozzáadásra kerül, ha ezen leltárcsoport használatával hoz létre készletleltárnapló-sorokat.  
7. Kattintson a Mentés gombra.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Leltározási irányelv beállítási egy cikkhez egy adott raktárban
1. A Művelet panelen kattintson a Készletkezelés elemre.
2. Kattintson a Raktárcikkekre.
3. Kattintson az Új elemre.
4. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listán válassza ki azt a raktárt, amelyhez leltározási irányelveket kíván beállítani.
6. A Leltárcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listán válasszon leltárcsoportot
    * Itt kiválaszthat egy adott leltárcsoportot, amely vonatkozik a kiválasztott raktár adott cikkére. Ha abban a raktárban leltár történik, ez a leltározási irányelv felülírja az általános leltározási irányelvet a cikkre.  
8. Kattintson a Mentés gombra.


