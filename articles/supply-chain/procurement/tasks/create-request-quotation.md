---
title: Ajánlatkérés létrehozása
description: Ez az eljárás bemutatja az ajánlatkérés létrehozásának módját.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59202cb6678660ae035f9f76ebe4267bac01d78f
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019904"
---
# <a name="create-a-request-for-quotation"></a>Ajánlatkérés létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja az ajánlatkérés létrehozásának módját. Ez általában egy beszerzési ügynök által történik. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. A kezdés előtt be kell állítania a meghirdetési típusokat. Miután befejezte ezt a feladatot, és létrehozta, illetve elküldte az Ajánlatkérést, megadhatja ezt követően szállítónként a válaszokat, összehasonlíthatja azokat, és hozzá rendelheti a szerződéshez.


## <a name="prepare-a-new-rfq"></a>Egy új Ajánlatkérések előkészítése
1. Navigáljon a következő helyre: **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Ajánlatkérések Összes ajánlatkérés**.
2. Kattintson az **Új** elemre.
    A következő beszerzési lehetségesek: Beszerzési rendelés (Ez az alapértelmezett): olyan dokumentum, amely megerősíti az ajánlatot a termékek megvásárlásához, vagy egy ajánlat elfogadását a termékek fizetés ellenében történő eladásához. Beszerzési igénylés: A rendszer automatikusan ezt a típust választja ki, ha az Ajánlatkérést közvetlenül egy beszerzési igény alapján hoz létre. Ha manuálisan választja ezt a beállítást, akkor hibaüzenetet kap. Beszerzési szerződés: Megállapodás egy megadott mennyiségű vagy értékű termék hosszabb idő alatt történő beszerzéséhez. Ha ezt a beállítást választja, ki kell választania azt a dátumtartományt, amelyre a beszerzési szerződés vonatkozik.  
3. A **Dokumentum címe** mezőbe írjon be egy értéket.
4. A **Meghirdetés típusa** mezőben adjon meg vagy válasszon ki egy értéket.
    + Ha a pontozási módhoz meghirdetési típus is társul, akkor ez lesz a létrejövő ajánlatkérésre vonatkozó alapértelmezett pontozási módja. Lehetőség van később a pontozási módszer módosítására.  
    + Adjon meg egy dátumot a **Kiszállítási dátum** mezőben.  
    + Válassza ki azt a dátumot, amikor meg szeretné kapni a cikkeket.  
    + A **Lejárati dátum és idő** mezőben adjon meg egy dátumot és időpontot.  
    + Adja meg a mezőben azt a dátumot és időt, amikor a szállítóknak válaszolni kell az ajánlatkérésre.  
5. A **Raktár mezőben** adjon meg vagy válasszon ki egy értéket. A szállítási cím lesz a raktár alapértelmezett címe.  
6. Kattintson az **OK** gombra.

## <a name="add-lines"></a>Sorok hozzáadása

Miután megadta az ajánlatkérés alapvető információit, adja meg, hogy milyen termékekre és szolgáltatásokra kíván ajánlatokat kérni a szállítóktól. A cikk az alapértelmezett típus.

1. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket. Ha az USMF használja, választhatja a T0020-as cikket.  
2. Adjon meg egy számot a **Mennyiség** mezőben.
3. Kattintson az **Új sor hozzáadása** elemre.
4. A **Sor típusa** mezőben válassza ki a „Kategóriát”. A Kategóriasor típus segítségével a nem készlet árukra vagy szolgáltatásokra vonatkozó ajánlatkéréseket hozhat lére. Akkor ki kell választania az áruk vagy szolgáltatások típusát a beszerzési kategóriák hierarchiája alapján.  
5. A **Beszerzési kategória** mezőben adjon meg vagy válasszon ki egy értéket.
6. Írjon be egy értéket a **Terméknév** mezőbe.
7. Adjon meg egy számot a **Mennyiség** mezőben.
8. Az **Egység** mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="add-vendors"></a>Szállítók hozzáadása
1. Kattintson a **Fejlécre** a Sorok nézetéről a Fejléc nézetére történő módosításhoz. 
2. Bontsa ki a **Szállító** szakaszt.
3. Kattintson a **Szállítók automatikus hozzáadása** elemre. Automatikusan hozzáadhatja a szállítókat az ajánlatkéréshez az igényelt cikkek beszerzési kategóriája alapján. Ha a sorokban szereplő kategóriákra vonatkozóan engedélyezett szállító nem szerepel, akkor manuálisan adhat hozzá szállítókat.  
4. Kattintson a **Hozzáadás** parancsra.
5. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson a **Hozzáadás** parancsra.
7. A **Szállítószámla** mezőben adjon meg vagy válasszon ki egy értéket. Ha kijelölt egy szállítót, akkor az állapota „Létrehozva”. Ez azt jelenti, hogy mentette a szállítói információkat az ajánlatkérésben, de nem küldte el az ajánlatkérést a szállítónak. A szállító ajánlatkérésbe való felvételét nem befolyásolja a szállító állapota.  

## <a name="send-the-rfq-to-vendors"></a>RFQ küldése a szállítóknak
1. A **Műveleti panelen** kattintson a **Küldés** elemre. Az ajánlatkérés elküldése lapon ellenőrizze, hogy azok a szállítók szerepelnek-e a listában, akiktől meg szeretné kapni az ajánlatkérést.  
2. Kattintson a **Nyomtatás** parancsra. Ez a párbeszédpanel lehetővé teszi az Ajánlatkérés nyomtatását. Ha egy válaszlap nyomtatását választja, akkor annak tartalmát a Beszerzés és forrás paramétereiben határozza meg a rendszer. A válaszlapok nyomtatási módjának kiválasztásához, a nyomtatási párbeszédpanel megnyitása után kattintson a Speciális nyomtatási beállítások elemre. Az ajánlatkérést minden egyes szállítóra vonatkozóan kinyomtatják, ami Létrehozva vagy Elküldve állapotú sorokat tartalmaz. A törölt sorok és a regisztrált válaszokkal rendelkező sorok nem kerülnek kinyomtatásra.   
3. Kattintson a **Mégse** gombra.
4. Kattintson az **OK** gombra.
5. Zárja be a lapot.
6. Zárja be a lapot.

## <a name="view-the-rfq-journal"></a>Ajánlatkérési napló megjelenítése.
1. Ugorjon a **Beszerzések és források > Ajánlatkérések > Ajánlatkérések követése > Ajánlatkérési naplók** pontra.
2. Kattintson az **Előnézet/nyomtatás** gombra.
3. Kattintson az **Eredeti előnézete** lehetőségre.
4. Zárja be a lapot.
5. Zárja be a lapot.

