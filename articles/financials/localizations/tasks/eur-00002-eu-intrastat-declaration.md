--- 
title: "Az Uniós Intrastat nyilatkozat létrehozása"
description: "Ez az eljárás bemutatja azokat a lépéseket, amelyeket el kell végezni az Intrastat nyilatkozat elektronikus fájlformátumba történő exportálásához és egy Excel fájlformátum bevallási dokumentumainak áttekintéséhez."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 34ec97b7cf761ee4478fa982fa6c153e66ad3a28
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="generate-an-eu-intrastat-declaration"></a>Az Uniós Intrastat nyilatkozat létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja azokat a lépéseket, amelyeket el kell végezni az Intrastat nyilatkozat elektronikus fájlformátumba történő exportálásához és egy Excel fájlformátum bevallási dokumentumainak áttekintéséhez. 

Mielőtt végrehajtaná ezt az eljárást, át kell helyeznie a tranzakciókat az Intrastatba. 

Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.


## <a name="import-configurations-with-settings"></a>A konfiguráció beállításokkal történő importálása
1. Ugorjon a Munkaterületek > Elektronikus jelentés pontra
2. Kattintson erre: Beállítás aktívként.
3. Kattintson a Tárházak gombra.
4. Kattintson a Megnyitás gombra.
5. Nyissa meg a Konfiguráció neve oszlopszűrőt.
6. Alkalmazzon szűrőt a „Konfiguráció neve” mezőben a „Intrastat (DE)” értékkel az „Ezzel kezdődik” szűrési operátor használatával.
    * Ki kell választania a jogi személy országára vonatkozó konfigurációs nevet. Ez az eljárás a német jogi személyt (DEMF) példaként használja, ezért az „Intrastat” lehetőséget kell kiválasztani.  
    * Kattintson az Importálás, majd az Igen lehetőségre.  
7. Nyissa meg a Konfiguráció neve oszlopszűrőt.
8. Alkalmazzon szűrőt a „Konfiguráció neve” mezőben a „Intrastat jelentés” értékkel az „Ezzel kezdődik” szűrési operátor használatával.
    * Kattintson az Importálás, majd az Igen lehetőségre.  

## <a name="set-up-foreign-trade-parameters"></a>A Külkereskedelmi paraméterek beállítása
1. Ugrás az Adó > Beállítás > Külkereskedelem > Külkereskedelmi paraméterek pontra
2. Bontsa ki az elektronikus jelentéskészítés szakaszát.
3. A Fájlformátum-hozzárendelés mezőben adja meg vagy válassza ki a Intrastat (DE) értéket.
4. A Jelentésformátum-hozzárendelés mezőben adja meg vagy válassza ki a Intrastat jelentés értéket.
5. Bontsa ki a Kerekítési szabályok szakaszt.
    * Be kell állítania azokat a kerekítési szabályokat, amelyek az országában/régiójában alkalmazhatóak az Intrastat-jelentésekhez.  
6. A Kerekítési szabályok mezőben adjon meg egy számot.
    * Adja meg a kerekítési pontosságot, például adja meg a „0,01” értéket.  
7. Adjon meg egy számot Az összeg tizedesjegyeinek száma mezőben.
    * Adja meg például a „2” értéket.  
8. Válasszon ki egy lehetőséget a Kerekítés 1 kg alatt mezőben.
    * Válassza ki például a „Felkerekítés 1 kg-ra” lehetőséget.  
9. A Kerekítési szabályok mezőben adjon meg egy számot.
    * Adja meg példáié az „1” a súly kerekítése az egész számhoz.  
10. Bontsa ki a Minimumhatár szakaszt.
11. Adjon meg egy számot a Súly mezőben.
    * Adja meg, például minimális súlyként a „10”értéket.  
12. Az Összeg mezőben adjon meg egy számot.
    * Adja meg, például minimális összegként a „200” értéket.  
13. Az Árucikk mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="set-up-compression-of-intrastat"></a>Az Intrastat Tömörítés beállítása
1. Ugorjon az Adó > Beállítás > Külkereskedelem > Intrastat tömörítése pontra.
2. Kattintson az Eltávolítás gombra.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki például az Árucikk a Rendelkezésre álló szakaszban lehetőséget.  
4. Kattintson a Hozzáadás gombra.

## <a name="generate-intrastat-declaration"></a>Az Intrastat nyilatkozat létrehozása
1. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra
2. Kattintson az Érvényesítés gombra.
    * A rendszer az ellenőrzést a Beállítások ellenőrzése mező szerint végzi el a Külkereskedelem paraméterei lapon.  
3. Kattintson az OK gombra.
4. Kattintson a Módosítás gombra.
5. Kattintson a Minimumhatár lehetőségre.
6. Adja meg a dátumot a Kezdő dátum mezőben.
    * Adja meg például a 2015. január 1-jei dátumot.  
7. Válassza ki az Igen lehetőséget a Tömörítés mezőben.
8. Adja meg a dátumot a Záró dátum mezőben.
    * Adja meg például a 2015. január 31-ei dátumot.  
9. Kattintson az OK gombra.
10. Kattintson a Módosítás gombra.
11. Kattintson a Tömörítés lehetőségre.
    * Ezt a tömörítést a rendszer attól függően végzi el, hogy hogyan állítják be az Intrastat beállítások Tömörítését.  
12. Adja meg a dátumot a Kezdő dátum mezőben.
    * Adja meg például a 2015. január 1-jei dátumot.  
13. Adja meg a dátumot a Záró dátum mezőben.
    * Adja meg például a 2015. január 31-ei dátumot.  
14. Kattintson az OK gombra.
15. Kattintson a Módosítás gombra.
16. Kattintson a Sorszámok újbóli létrehozása lehetőségre.
17. Kattintson az OK gombra.
18. Kattintson a Kimenet lehetőségre.
19. Kattintson a Jelentésre.
20. A Kezdő dátum mezőben adja meg a jelentési időszak első napját.
    * Állítsa át a dátumot például 2015. január 1-jére.  
21. Adja meg a dátumot a „Záró dátum” mezőben.
    * Adja meg például a 2015. január 31-ei dátumot.  
22. Válassza az Igen lehetőséget a Fájl létrehozása mezőben.
23. Írjon be egy értéket a Fájlnév mezőbe.
24. Válassza az Igen lehetőséget a Jelentés létrehozása mezőben.
25. Írjon be egy értéket a Jelentésfájl neve mezőbe.
26. Válasszon ki egy lehetőséget az Irány mezőben.
    * Válassza ki például a „Feladások” lehetőséget.  
27. Kattintson az OK gombra.


