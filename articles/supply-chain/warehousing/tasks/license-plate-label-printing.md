---
title: Azonosítótábla-címke nyomtatásának engedélyezése
description: Ez az eljárás lehetővé teszi a Konténer sorszáma (SSCC) címke automatikus nyomtatását, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d906ca9f5a6536870fa0c322a0792ed5672c25e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "324031"
---
# <a name="enable-license-plate-label-printing"></a>Azonosítótábla-címke nyomtatásának engedélyezése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás lehetővé teszi a Konténer sorszáma (SSCC) címke automatikus nyomtatását, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során. Ezt a folyamatot lefuttathatja az USMF bemutatócégen. Ha a saját adatok használatával futtatja le, akkor szüksége lesz egy az azonosítótáblákhoz beállított számsorozatra. A feladat megkezdése előtt be kell állítania egy címkenyomtatót. Lépjen a Szervezetadminisztráció > Beállítás > Hálózati nyomtatókra. A Műveleti ablakban kattintson az Opciókra, majd a Dokumentumirányítási ügynök telepítőjének letöltése gombra. Futtassa a telepítőt, és győződjön meg arról, hogy van-e működő hálózati nyomtató, amely aktív, mielőtt folytatná a műveletet.


## <a name="set-up-the-gs1-company-prefix"></a>GS1 vállalatelőtag felállítása.
1. Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.
2. Az GS1 vállalatelőtag mezőbe írja be vállalata 7-jegyű GS1 számát.
3. Kattintson a Mentés gombra.
4. Zárja be a lapot.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>SSCC azonosítótábla számsorozat beállítása
1. Ugorjon a Szervezeti adminisztráció > Számsorozatok > Számsorozatokra pontra.
2. Egy lehetőség kiválasztása a Terület mezőben.
3. Egy lehetőség kiválasztása a Hivatkozás mezőben.
4. Írjon be egy értéket a Vállalat mezőbe.
5. A listában jelölje meg a kiválasztott sort.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Bontsa ki a Szegmensek szakaszt.
8. Kattintson a Szerkesztés lehetőségre.
9. A Szegmens táblában válassza ki az első sort.
10. Kattintson az Eltávolítás gombra.
11. Kattintson az Eltávolítás gombra.
12. Kattintson a Mentés gombra.
13. Zárja be a lapot.

## <a name="create-the-document-route-layout"></a>Dokumentum útvonal-elrendezés létrehozása
1. Ugrás a Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányító elrendezésekre.
    * SSCC-elrendezés engedélyezése.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Elrendezésazonosító mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
6. Kattintson a Beszúrás a szöveg végére lehetőségre.
7. Kattintson a Mentés gombra.
8. Zárja be a lapot.

## <a name="set-up-the-document-routing"></a>Dokumentumirányítás beállítása
1. Ugrás a Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányítás pontra.
2. A Munkarendelés típusa mezőben válasszon ki egy lehetőséget.
3. Kattintson az Új elemre.
4. Érték beírása a Raktár mezőbe.
5. Írjon be egy értéket a Név mezőbe.
6. Kattintson az Új elemre.
7. Az Elrendezésazonosító mezőben adjon meg vagy válasszon ki egy értéket.
8. A Név mezőben adja meg a használni kívánt nyomtató nevét.
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.

## <a name="create-mobile-device-menu"></a>Mobileszköz menüjének létrehozása
1. Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Menüelem neve mezőbe.
4. Érték beírása a Címmezőbe.
5. Egy lehetőség kiválasztása a Mód mezőben.
6. A Meglévő munka használata mezőben válassza az Igen lehetőséget.
7. Válassza az Igen lehetőséget az Azonosítótábla előállítása mezőben.
8. Bontsa ki a Munkaosztályok szakaszt.
9. Kattintson az Új lehetőségre.
10. Írjon be egy értéket a Munkaosztály azonosítója mezőbe.
11. Kattintson a Mentés gombra.
12. Zárja be a lapot.
13. Ugrás a Raktárkezelés > Beállítás Mobileszköz > Mobileszköz menüre.
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. A fán válassza ki az „A fán válassza ki a menüelemet, amelyet korábban hozott létre.” lehetőséget.
16. Kattintson a Szerkesztés lehetőségre.
17. Kattintson a nyílra a menüpont menühöz való hozzáadásához.
18. Kattintson a Mentés gombra.
19. Zárja be a lapot.

## <a name="update-a-work-template"></a>Munkasablon frissítése
1. Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Kattintson a Szerkesztés lehetőségre.
4. Kattintson az Új elemre.
5. A listában jelölje meg a kiválasztott sort.
6. A Munkatípus mezőben válassza a „Nyomtatás” lehetőséget.
7. A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson a Felfelé gombra.
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.

