---
title: EUR-00011 Értékesítési lista jelentés beállítása
description: Ez a feladat végigvezeti az EU értékesítési lista jelentéséhez szükséges előfeltételeken.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c312e14247c42acd5e0de5df02833275d9e3a4f1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408019"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a>EUR-00011 Értékesítési lista jelentés beállítása

[!include [banner](../../includes/banner.md)]

Ez a feladat végigvezeti az EU értékesítési lista jelentéséhez szükséges előfeltételeken. További tájékoztatásért az EU értékesítési lista jelentéséről, a kötelező előfeltételeket is beleértve, lásd a Súgót.

Ez a feladat minden európai országra/régióra vonatkozik. Ez az útmutató a DEMF bemutatócég adataival lett létrehozva, így a példa ország/régió Németország lett. Az útmutató EU-s ország/régió példájaként Portugáliát is használja.

Ezek a feladatok rendszergazdáknak szólnak.


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a>Elektronikus jelentési konfigurációk importálása EU értékesítési lista jelentéséhez
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson erre: Beállítás aktívként.
3. Kattintson a Tárházak gombra.
4. Kattintson a Megnyitás gombra.
5. A Művelet ablaktáblában kattintson a Beállítások elemre.
6. Kattintson a Speciális szűrés/rendezés lehetőségre.
7. Kattintson a Hozzáadás gombra.
8. A Mező mezőben válassza ki a „Konfigurációnév” lehetőséget.
9. A Feltétel mezőbe írja be, hogy „EU értékesítési lista (DE)”
10. Kattintson az OK gombra.
11. Kattintson az Importálás gombra.
12. Kattintson az Igen gombra.
13. A Művelet ablaktáblában kattintson a Beállítások elemre.
14. Kattintson a Speciális szűrés/rendezés lehetőségre.
15. Kattintson az Alaphelyzet gombra.
16. Kattintson a Hozzáadás gombra.
17. A Mező mezőben válassza ki a „Konfigurációnév” lehetőséget.
18. A Feltétel mezőbe írja be, hogy „EU értékesítési lista kimutatási sorok alapján”.
19. Kattintson az OK gombra.
20. Kattintson az Importálás gombra.
21. Kattintson az Igen gombra.

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a>Áfakódok beállítása EU értékesítési lista jelentéséhez
1. Ugrás az Adó > Közvetett adók > Áfa > Áfakódok pontra.
2. A gyorsszűrő használatával keresse meg azokat az Áfakód mezőket, ahol a „VAT19” érték szerepel.
3. Bontsa ki a Jelentésbeállítás szakaszt.
    * Ellenőrizze, hogy a Kizárva kiválasztás a Nem lehetőségre van állítva.  
    * A beállítás módosításához szükség lehet a feladat-útmutató feloldására.  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a>Áfacsoport beállítása EU értékesítési lista jelentéséhez
1. Ugorjon az Adó > Közvetett adók > Áfa > Áfakódcsoportok pontra.
2. A gyorsszűrő használatával keresse meg azokat az Áfacsoport mezőket, ahol a „AR-DOM” érték szerepel.
3. Kattintson a Szerkesztés lehetőségre.
4. Bontsa ki a Beállítások szakaszt.
5. A listában jelölje meg az első sort.
6. Jelölje be az Adómentes jelölőnégyzetet.
7. A listában jelölje meg a második sort.
8. Jelölje be az Adómentes jelölőnégyzetet.
9. A listában jelölje meg a harmadik sort.
10. Jelölje be az Adómentes jelölőnégyzetet.

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a>Cikkáfacsoport beállítása EU értékesítési lista jelentéséhez
1. Ugorjon az Adó > Közvetett adók > Áfa > Áfakódcsoportok pontra.
2. A gyorsszűrő használatával keresse meg azokat a Cikkáfacsoport mezőket, ahol a „FULL” érték szerepel.
    * Ellenőrizze, hogy a Jelentéstípus kiválasztás a „Cikk” lehetőségre van állítva.  
    * A mező értékének a módosításához szükség lehet a feladat-útmutató feloldására.  
3. A gyorsszűrő használatával keresse meg azokat a Cikkáfacsoport mezőket, ahol a „RED” érték szerepel.
    * Ellenőrizze, hogy a Jelentéstípus kiválasztás a „Szolgáltatás” lehetőségre van állítva.  
    * A mező értékének a módosításához szükség lehet a feladat-útmutató feloldására.  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a>Ország/régió paramétereinek beállítása EU értékesítési lista jelentéséhez
1. Ugorjon az Adó > Beállítás > Áfa> Országok és régiók paraméterei pontra.
2. Kattintson az Új lehetőségre.
3. Írja be a „PRT” értéket az Ország/régió mezőbe.
4. Az Áfakód mezőbe írja be a „PT” értéket.

## <a name="create-tax-exempt-numbers"></a>Adószámok létrehozása
1. Ugorjon az Adó > Beállítás > Áfa > Adószámok pontra.
2. Kattintson az Új lehetőségre.
3. Írja be a „PRT” értéket az Ország/régió mezőbe.
4. Az Adószám mezőbe írja be a „PT12345” értéket.

## <a name="set-up-eu-sales-list-reporting-parameters"></a>EU értékesítési lista jelentési paraméterek beállítása
1. Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.
2. Kattintson az EU értékesítési lista fülre.
3. Válassza az Igen lehetőséget a Beszerzések átvitele mezőben.
4. Bontsa ki a Kerekítési szabályok szakaszt.
5. Kerekítési szabálynak adja meg a „0,1” értéket.
6. A Minimum érték használata mezőben válassza az Igen lehetőséget.
7. A Tizedesek száma mezőben adja meg a „2” értéket.
8. Bontsa ki az elektronikus jelentéskészítés szakaszát.
9. A Fájlformátum-hozzárendelés mezőben válassza ki az „EU értékesítési lista (DE)” lehetőséget.
10. A Jelentésformátum-hozzárendelés mezőben válassza ki az „EU értékesítési lista kimutatási sorok alapján” lehetőséget.
11. Kattintson az Ország/régió tulajdonságai lapra.
    * Ellenőrizze, hogy az Ország/régió típusa mező „Helyi” lehetőségre van állítva a DEU Ország/régió esetén.  
    * A mező értékének a módosításához szükség lehet a feladat-útmutató feloldására.  
12. Kattintson az Új lehetőségre.
13. Írja be a „PRT” értéket az Ország/régió mezőbe.
14. Az Intrastat-kód mezőbe írja be, hogy „PT”.
15. Az Ország/régió típusa mezőben válassza ki az „EU” lehetőséget.
16. Kattintson a Számsorozatok lapra.
    * Ellenőrizze, hogy a Szám sorozatkód meg van határozva az „EU értékesítési lista” referenciájára.  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a>Vevő létrehozása EU értékesítési lista jelentés bemutatói céljára
1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőbe írja be a „PRT-001” szöveget.
4. A Név mezőbe írja be a „Vevő Portugáliából” szöveget.
5. A Vevőcsoport mezőben válassza ki a „10” lehetőséget.
6. Az Áfacsoport mezőben válassza ki az „AR-DOM” lehetőséget.
7. Az Adószám mezőbe válassza ki a „PT12345” értéket.
8. Írja be a „PRT” értéket az Ország/régió mezőbe.
9. Kattintson a Mentés gombra.

