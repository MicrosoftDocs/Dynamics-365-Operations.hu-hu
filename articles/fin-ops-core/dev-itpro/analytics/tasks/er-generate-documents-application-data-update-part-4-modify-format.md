---
title: Formátum módosítása alkalmazásadatokkal rendelkező dokumentumok létrehozásához
description: 'Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (3. rész: Modell és hozzárendelés módosítása)” eljárást.'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6132d48f276b27797e86fbcde11746b7e4da7d3b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142455"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Formátum módosítása alkalmazásadatokkal rendelkező dokumentumok létrehozásához

[!include [banner](../../includes/banner.md)]

Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (3. rész: Modell és hozzárendelés módosítása)” eljárást.

Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését és az alkalmazásadatok frissítését mutatják be. Ebben az eljárásban módosítjuk az ER-konfigurációkat, hogy ne csak az elektronikus dokumentumok létrehozásához használjuk őket, hanem az alkalmazásadatok frissítéséhez is. Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. A lépések a DEMF-adathalmazzal hajthatók végre.


## <a name="modify-format-to-collect-details-of-reporting"></a>Módosítsa a formátumot a jelentés adatainak összegyűjtéséhez
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki az „Instrastat (model)” elemet.
3. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (format)”.
4. Kattintson a Tervező pontra.
5. A fastruktúrában bontsa ki ezt: „File”.
6. A fában bontsa ki a „File\Declaration” elemet.
7. A fastruktúrában válassza ki ezt: „File\Declaration\Data”.
8. A Multiplicitás mezőben válassza ki ezt: 'Egy a többhöz'.
    * Konfigurálja ezt a formátumelemet az Intrastat-jelentési folyamat adatainak archiválásához. Ez az elem az archívum fejlécrekordját jelöli.  
9. A fában bontsa ki ezt: „File\Declaration\Data”.
10. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item”.
11. A Multiplicitás mezőben válassza ki ezt: 'Nulla sok'.
    * Konfigurálja ezt a formátumelemet az Intrastat-jelentési folyamat adatainak archiválásához. Ez az elem az archivált sorok listáját fogja jelölni.  
12. A fában bontsa ki ezt: „File\Declaration\Data\Item”.
13. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim1”.
14. Válassza az Igen lehetőséget a Kizárás mezőben.
    * Ezeket az adatokat nem fogja archiválni, ezért ezt a formátumelemet kizárhatja az Intrastat-jelentés részleteinek adatforrásából.  
15. A fában bontsa ki ezt: „File\Declaration\Data\Item\Dim1”.
16. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim1\property”.
17. Válassza az Igen lehetőséget a Kizárás mezőben.
18. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim1\date”.
19. Válassza az Igen lehetőséget a Kizárás mezőben.
20. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim2”.
21. Válassza az Igen lehetőséget a Kizárás mezőben.
22. A fában bontsa ki ezt: „File\Declaration\Data\Item\Dim2”.
23. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim2\property”.
24. Válassza az Igen lehetőséget a Kizárás mezőben.
25. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim2\code”.
26. Válassza az Igen lehetőséget a Kizárás mezőben.
27. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim3”.
    * Több formátumelemnek lehet ugyanaz a neve. Például Dim. Nem lehet közvetlenül felismerni őket a formátum használatakor adatforrásként az Intrastat-jelentés részleteinek archiválása céljából, ezért meg kell adni a másodlagos neveket ezekhez a formátumelemekhez.   
28. A Név mezőbe írja be az 'Amount' szöveget.
    * Összeg  
29. A Multiplicitás mezőben válassza ki ezt: 'Pontosan egy'.
30. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item\Dim4”.
31. A Név mezőbe írja be az Item szót.
    * Tétel  
32. A Multiplicitás mezőben válassza ki ezt: 'Pontosan egy'.
    * A tervezési formátumelemek mellett a következő Intrastat-jelentési adatokat is archiválni kell: az egyes árucikkek egyedi rekordazonosítója, valamint a létrehozott fájl neve. Mivel ezek az adatok az Intrastat-jelentésben nem lesznek kitöltve, adatforráselemként hozzá kell adni az ezekhez az adatelemekhez kapcsolódó formátumot.  
33. A fastruktúrában válassza ki ezt: „File\Declaration\Data”.
34. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
35. Válassza ki az „Data source\Item” lehetőséget a fastruktúrában.
36. A Név mezőbe írja be a következőt: „Fájlnév”.
    * Fájlnév  
37. Az Adattípus mezőben válassza ki a „Karakterlánc” lehetőséget.
38. Kattintson az OK gombra.
39. A fastruktúrában válassza ki ezt: „File\Declaration\Data\Item”.
40. Kattintson a Cikk hozzáadása elemre.
41. A Név mezőben írja be az „Árucikk rekordazonosító” szöveget.
    * Árucikk rekordazonosító  
42. Az Adattípus mezőben válassza ki az „Int64” lehetőséget.
43. Kattintson az OK gombra.
44. Kattintson a Hozzárendelés fülre.
45. A fastruktúrában válassza ki ezt: „File\Declaration\Data\File name”.
46. Kattintson a Kötés gombra.
47. A fában bontsa ki a „model” elemet.
48. A fastruktúrában bontsa ki ezt: „model\Transactions”.
49. A fában jelölje ki ezt: „File\Declaration\Data\Item =  model.Transactions\Commodity rec id”.
50. A fán válassza ki ezt: „model\Transactions\Commodity rec id”.
51. Kattintson a Kötés gombra.
52. Kattintson a Mentés gombra.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Módosítsa a formátumot a jelentés adatainak memorizálásához
1. Kattintson a Formátum hozzárendelése modellhez lehetőségre.
2. Kattintson az Új elemre.
3. A Definíció mezőben adja meg vagy válassza ki az 'Alkalmazásadatok frissítéséhez' gyökérelemet.
    * Alkalmazásadatok módosításához  
4. A Név mezőbe írja be a következőt: „Hozzárendelés az adatok frissítéséhez”.
    * Hozzárendelés az adatok frissítéséhez  
5. Kattintson a Mentés gombra.
    * Ez a hozzárendelés határozza meg, hogyan kell összegyűjteni az Intrastat-jelentés adatait az adatmodellben, amelynek a szerkezetét az „Alkalmazásadatok módosításához” kiválasztott gyökérelem határozza meg. Ezeket az adatokat – a modell-hozzárendelés az azonos „Alkalmazásadatok módosításához” gyökérelemmel, valamint a „Célhoz” irány – az alkalmazásadatok frissítéséhez használja a rendszer. Az alkalmazásadatok frissítése azonnal elindul, amint megtörtént a kimenő Intrastat-jelentés előállítása. Fontos megjegyezni, hogy az alkalmazásadatok frissítése kihagyható futásidőben, de az adatmodellnek üresnek kell lennie (üres rekordok listáját tartalmazó).   
6. Kattintson a Tervező pontra.
    * Vegye figyelembe, hogy a kimenő Intrastat-jelentésformátum alapértelmezés szerint hozzá lesz adva ehhez a modell-hozzárendeléshez adatforrásként.  
    * Kösse össze a tervezett jelentés elemeit (adatforrásként jelennek meg) az adatmodell elemeivel, amelynek a szűrése a kiválasztott modell gyökéreleme alapján történik.  
7. A fában bontsa ki az „Archive header” lehetőséget.
8. A fában bontsa ki ezt: „Archive header\Archive lines”.
9. A fastruktúrában bontsa ki ezt: „format”.
10. A fában bontsa ki a „format\Declaration: XML Element(Declaration)”.
11. A fán jelölje bontsa ki ezt: „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)”.
12. A fában bontsa ki ezt: „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)”.
13. A fában bontsa ki ezt: „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)”.
14. A fában bontsa ki a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)” lehetőséget.
15. A fában válassza ki az „Archive header\Number of lines” lehetőséget.
16. Kattintson a Szerkesztés lehetőségre.
17. A fastruktúrában válassza ki a „List\COUNT” csomópontot.
18. Kattintson a Függvény hozzáadása gombra.
19. A fastruktúrában bontsa ki ezt: „format”.
20. A fában bontsa ki a „format\Declaration: XML Element(Declaration)”.
21. A fán jelölje bontsa ki ezt: „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)”.
22. A fában válassza ki a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)” lehetőséget.
23. Kattintson az Adatforrás hozzáadása pontra.
24. A Képlet mezőben adja meg ezt: 'COUNT(format.Declaration.Data.Item)'.
    * COUNT(format.Declaration.Data.Item)  
25. Kattintson a Mentés gombra.
26. Zárja be a lapot.
27. A fában válassza ki az „Archive header\File name” lehetőséget.
28. A fán jelölje ki a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\File name: Item String(File name)” lehetőséget.
29. Kattintson a Kötés gombra.
30. A fában válassza ki a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)” lehetőséget.
31. A fában válassza ki ezt: „Archive header\Archive lines\Item number”.
32. Kattintson a Kötés gombra.
33. A fában válassza ki a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)” lehetőséget.
34. A fában válassza ki ezt: „Archive header\Archive lines\Amount”.
35. Kattintson a Kötés gombra.
36. A fában jelölje ki ezt: „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec id: Item Int64(Commodity rec id)”.
37. A fában válassza ki ezt: „Archive header\Archive lines\Commodity rec id”.
38. Kattintson a Kötés gombra.
39. A fában válassza ki ezt: „Archive header\Archive lines”.
40. A fában válassza ki a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)” lehetőséget.
41. Kattintson a Kötés gombra.
42. A fáról válassza ki a Fejléc archiválása lehetőséget.
43. A fán jelölje be a „format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)” lehetőséget.
44. Kattintson a Kötés gombra.
45. Kattintson a Mentés gombra.
46. Zárja be a lapot.
47. Zárja be a lapot.
48. Zárja be a lapot.

