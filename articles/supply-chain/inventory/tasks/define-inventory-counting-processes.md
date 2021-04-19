---
title: Készletleltár-folyamatok meghatározása
description: Ez az témakör bemutatja az alapvető leltározási folyamatokon a leltárcsoport és a leltárnapló létrehozásával.
author: MarkusFogelberg
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4166ffd043db24e814bcb85df07f0b940d5328d9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833881"
---
# <a name="define-inventory-counting-processes"></a>Készletleltár-folyamatok meghatározása

[!include [banner](../../includes/banner.md)]

Ez az témakör bemutatja az alapvető leltározási folyamatokon a leltárcsoport és a leltárnapló létrehozásával. Azt is bemutatja, hogy hogyan engedélyezheti a leltározási irányelveket raktár vagy cikk szintjén. Ezeket a feladatokat jellemzően egy raktárvezető végzi el. Ez előfeltétele annak, hogy legyen létező kiadott termék és raktár. Ha bemutató adatokat használ, ezt az eljárást az USMF vállalatban bármilyen raktározott cikkre futtathatja.


## <a name="create-a-counting-group"></a>Leltárcsoport létrehozása
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Készlet részletezése > Leltárcsoportok** részre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket az új sor **Leltárcsoport** mezőbe.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Leltárcsoport** mezőben válasszon ki egy lehetőséget.

    - **Manuális** − a feladat minden egyes futtatásakor tartalmazza a sorokat. Más szóval megadható a leltárcsoport leltározási időszaka.  
    - **Időszakos** − tartalmazza az időszak sorait a leltárnaplóban az időtartam lejárta után.  
    - **Nulla a készleten** − ha az aktuális készlet nullára (0) csökken, akkor a feladat futtatásakor létrejönnek sorok a leltárnaplóban. Ha az aktuális készlet nullára csökken a leltározás során, akkor a sorok a leltározás következő indításakor jönnek létre.  
    - **Minimum** − sorok létrehozása a leltárnaplóban, ha az aktuális készlet a megadott minimummal egyenlő vagy a minimum alá csökken.  
    - Opcionális: Ha a leltárkód mezőben az **Időszak** elemet választja, a **Leltáridőszak** mezőbe kell beírnia az **Leltárkódot** tartamát. Az időszakok egysége a nap.  
    - Amikor futtatja a leltárnapló új sorainak létrehozására szolgáló feladatot, a jelen mezőben meghatározott intervallum szerint kerülnek létrehozásra az új sorok, függetlenül az adott feladat futtatási gyakoriságától. Ha például a **Leltározási időszak** 7 és a naplósorokat a leltárhoz utoljára január 1-jén hozta létre, ha január 5-én újabb feladatot indít, még nem telt el hét nap, ezért a rendszer nem hoz létre új sort a naplóban ahhoz az időszaki intervallumhoz. Ha január 8-án újra elindítja a feladatot, akkor az időtartamhoz kapcsolódó sorok létrejönnek a leltárnaplóban, mivel már eltelt 7 nap.  

6. Válassza a **Mentés** lehetőséget.

## <a name="create-a-counting-journal-name"></a>Hozzon létre egy leltárnaplónevet.
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Naplónevek > Készlet** részre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Név** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Naplótípus** mezőben válassza ki a **Leltár** lehetőséget. Opcionális: másik bizonylatsorozat-azonosítót is választhat, ha adott számsort kíván beállítani a bizonylati azonosítónak a leltárnaplók létrehozásakor. A bizonylatsorozat a **Számsorozatok** oldalon hozható létre.  
6. Válasszon egy lehetőséget a **Részletezési szint** mezőben.  

    - Ez a napló feladásakor alkalmazott részletességi szint.  
    - Opcionális: módosíthatja a Foglalás mezőben levő értéket. Ezzel a módszerrel leltár során foglalhat cikkeket.   
    - **Kézi** – a cikkek foglalása manuálisan történik a Foglalás képernyőn.  
    - **Automatikus** – a rendelési mennyiséget a program a cikk elérhető aktuális készletében foglalja le.   
    - **Alábontás** – a foglalás része a tranzakció alaptervezésének.  

7. Válassza a **Mentés** lehetőséget.

## <a name="set-standard-counting-journal-name"></a>Szokásos leltárnaplónév beállítása
1. A Navigációs ablaktáblában válassza a **Modulok > Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek** lehetőséget.
2. Válassza ki a **Naplók** lapot.
3. A **Leltár** mező legördülő menüjében válassza ki azt a naplót, amelyet korábban létrehozott. Ez a napló lesz ezután az alapértelmezett naplónév a **Számlálási** típus készletnaplóihoz.  
4. Válassza az **Általános** lapot. Opcionális: Válassza ezt a lehetőséget az egyik cikk lezárásához a számolási folyamat során, hogy megakadályozza a szállítólevelek és kitárolási listák frissítését vagy kitárolási listák regisztrációját.  

## <a name="set-the-counting-policy-for-an-item"></a>Leltározási irányelv beállítása egy cikkhez
1. A navigációs ablaktáblán ugorjon a **Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek** lehetőségre.
2. A listában kattintson a Cikkszám hivatkozására annál a terméknél, amelynél leltározási irányelvet szeretne beállítani. Olyan cikket kell kiválasztania, amely a készletben nyomon követett. A nem készletezett termék nem számlálható. Az USMF bemutatóadatok használata esetén válassza az A0001 cikket.  
3. Válassza ki a **Szerkesztés** opciót.
4. A **Készletkezelés** szakasz bővítésének átváltása.
5. A **Leltárcsoport** mező legördülő menüjében válassza ki azt a leltárcsoportot, amelyet korábban létrehozott. Ez a termék mostantól mindig hozzáadásra kerül, ha ezen leltárcsoport használatával hoz létre készletleltárnapló-sorokat.  
6. Válassza a **Mentés** lehetőséget.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Leltározási irányelv beállítási egy cikkhez egy adott raktárban
1. A Művelet panelen kattintson a **Készletkezelés** elemre.
2. Válassza a **Raktárcikkek** lehetőséget
3. Válassza az **Új** lehetőséget.
4. A **Raktár** mező legördülő menüjében válassza ki azt a raktárt, amelyhez speciális leltározási szabályokat kíván beállítani.
5. A **Raktárcsoport** mezőjének legördülő menüjében válassza ki a leltározási csoportot. Kiválaszthat egy adott leltárcsoportot, amely vonatkozik a kiválasztott raktár adott cikkére. Ha abban a raktárban leltár történik, ez a leltározási irányelv felülírja az általános leltározási irányelvet a cikkre.  
6. Válassza a **Mentés** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]