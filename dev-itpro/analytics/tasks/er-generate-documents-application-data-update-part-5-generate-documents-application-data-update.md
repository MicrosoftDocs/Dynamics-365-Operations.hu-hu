--- 
title: "Alkalmazásadatok módosítását tartalmazó dokumentumok létrehozása az elektronikus jelentéskészítéshez (ER)"
description: "Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (4. rész: Formátum módosítása)” eljárást."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 2c562c397ad93b1bbb919b69439f8eea1a9d2644
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Alkalmazásadatok módosítását tartalmazó dokumentumok létrehozása az elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (4. rész: Formátum módosítása)” eljárást.



Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését és az alkalmazásadatok frissítését mutatják be. Ebben az eljárásban végrehajtja az ER-formátumkonfigurációt az Intrastat-jelentés létrehozása, illetve az alkalmazásadatoknak a jelentési folyamat részleteinek archiválásához szükséges frissítése céljából.



Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. A lépések a DEMF-adathalmazzal hajthatók végre. Mielőtt hozzálátna, győződjön meg arról, hogy a DEMF vállalat országfüggő környezete BEL (Belgium).


## <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása
1. Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.
2. Kattintson a Számsorozatok lapra.
    * Az Intrastat jelentési folyamat részleteinek archiválása során azonosítani kell a létrehozott archívumokat. Ehhez egy speciális számsorozatot kell beállítani.  
3. Válassza ki az „Intrastat-archívum azonosítója” hivatkozást.
4. Adjon meg egy értéket a Számsorozat kódja mezőben.
    * A Számsorrend kódja mezőben adja meg vagy válassza ki a „Fore_2” értéket.  
5. ResolveChanges a számsorozat kódja.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="run-modified-er-format"></a>Módosított ER-formátum futtatása
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki az „Instrastat (model)” elemet.
3. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (format)”.
4. Kattintson a Futtatás elemre.
5. Az Enter fájlnévmezőbe írja be a következőt: intrastat2.xml.
    * intrastat2.xml  
6. Kattintson az OK gombra.

## <a name="review-er-format-executions-results"></a>ER-formátum végrehajtási eredményeinek áttekintése
    * Tekintse át a létrehozott XML-fájlt.  
1. Zárja be a lapot.
2. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.
    * Nyissa meg azon Intrastat-tranzakciókat tartalmazó képernyőt, amelyek szerepelnek a létrehozott elektronikus dokumentumban.  
3. Kattintson az Intrastat archívum elemre.
    * Mivel a végrehajtott ER-formátum most az alkalmazásadatok módosításának beállításait tartalmazza, a rendszer archiválta a kitöltött Intrastat-jelentés részleteit. Ezen a képernyőn megtekintheti a létrehozott archívum fejlécrekordját.  
4. Kattintson a Részletek gombra.
    * Ezen a képernyőn megtekintheti a létrehozott archívum részleteit.  
5. Zárja be a lapot.
6. Zárja be a lapot.
7. Zárja be a lapot.


