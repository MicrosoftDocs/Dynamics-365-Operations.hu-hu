---
title: Azonosítótábla-címke nyomtatásának engedélyezése
description: Ez az eljárás bemutatja a Konténer sorszáma (SSCC) címke automatikus nyomtatásának engedélyezését, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e548e5e5528733412d47478dd740b87217cdac2
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429875"
---
# <a name="enable-license-plate-label-printing"></a>Azonosítótábla-címke nyomtatásának engedélyezése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja a Konténer sorszáma (SSCC) címke automatikus nyomtatásának engedélyezését, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során. Ezt a folyamatot lefuttathatja az USMF bemutatócégen. Ha a saját adatok használatával futtatja le, akkor szüksége lesz egy az azonosítótáblákhoz beállított számsorozatra. A feladat megkezdése előtt be kell állítania egy címkenyomtatót. Lépjen a Szervezetadminisztráció > Beállítás > Hálózati nyomtatókra. A Művelet panelen kattintson az Opciókra, majd a Dokumentumirányítási ügynök telepítőjének letöltése gombra. Futtassa a telepítőt, és győződjön meg arról, hogy van-e működő hálózati nyomtató, amely aktív, mielőtt folytatná a műveletet.


## <a name="set-up-the-gs1-company-prefix"></a>GS1 vállalatelőtag felállítása.
1. Ugrás a **Navigációs ablaktábla > Modulok > Raktárkezelés > Beállítás > Raktárkezelési paraméterekre**
2. Az **GS1 vállalatelőtag** mezőbe írja be vállalata 7-jegyű GS1 számát.
3. Válassza a **Mentés** lehetőséget.
4. Zárja be a lapot.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>SSCC azonosítótábla számsorozat beállítása
1. Ugorjon a **Navigációs ablaktábla > Modulok > Szervezeti adminisztráció > Számsorozatok > Számsorozatok** elemre.
2. Egy lehetőség kiválasztása a **Terület** mezőben.
3. Egy lehetőség kiválasztása a **Hivatkozás** mezőben.
4. Írjon be egy értéket a **Vállalat** mezőbe.
5. Bontsa ki a **Szegmensek** szakaszt.
6. Válassza ki a **Szerkesztés** opciót.
7. A **Szegmensek** táblában válassza ki az első sort.
8. Válassza az **Eltávolítás** lehetőséget.
9. Válassza az **Eltávolítás** lehetőséget.
10. Válassza a **Mentés** lehetőséget.
11. Zárja be a lapot.

## <a name="create-the-document-route-layout"></a>Dokumentum útvonal-elrendezés létrehozása
1. Ugrás a **Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányító elrendezésekre**. SSCC-elrendezés engedélyezése.  
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket az **Elrendezésazonosító** mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Válassza a **Beszúrás szöveg végére** lehetőséget.
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.

## <a name="set-up-the-document-routing"></a>Dokumentumirányítás beállítása
1. Ugrás a **Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányítás** helyre.
2. A **Munkarendelés típusa** mezőben válasszon ki egy lehetőséget.
3. Válassza az **Új** lehetőséget.
4. Érték beírása a **Raktár** mezőbe.
5. Írjon be egy értéket a **Név** mezőbe.
6. Válassza az **Új** lehetőséget.
7. Az **Elrendezésazonosító** mezőben adjon meg vagy válasszon ki egy értéket.
8. A **Név** mezőben adja meg a használni kívánt nyomtató nevét.
9. Válassza a **Mentés** lehetőséget.
10. Zárja be a lapot.

## <a name="create-mobile-device-menu"></a>Mobileszköz menüjének létrehozása
1. A **Navigációs ablaktáblán ugorjon a Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menüpontjai** elemre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Menüelem neve** mezőbe.
4. Érték beírása a **Cím** mezőbe.
5. Egy lehetőség kiválasztása a **Mód** mezőben.
6. A **Meglévő munka használata** mezőben válassza az **Igen** lehetőséget.
7. Válassza az **Igen** lehetőséget az **Azonosítótábla előállítása** mezőben.
8. Bontsa ki a **Munkaosztályok** szakaszt.
9. Válassza az **Új** lehetőséget.
10. Írjon be egy értéket a **Munkaosztály** azonosítója mezőbe.
11. Válassza a **Mentés** lehetőséget.
12. Zárja be a lapot.
13. A **Navigációs ablaktáblán ugorjon a Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü** elemre.
14. A fán válassza ki az előzőleg létrehozott menüpontot.
15. Válassza ki a **Szerkesztés** opciót.
16. Kattintson a nyílra a menüpont menühöz való hozzáadásához.
17. Válassza a **Mentés** lehetőséget.
18. Zárja be a lapot.

## <a name="update-a-work-template"></a>Munkasablon frissítése
1. A **Navigációs ablaktáblán > ugorjon a Modulok > Raktárkezelés > Beállítás > Munka > Munkasablonok** lehetőségre.
2. Válassza ki a **Szerkesztés** opciót.
3. Válassza az **Új** lehetőséget.
4. A **Munkatípus** mezőben válassza a **Nyomtatás** lehetőséget.
5. A **Munkaosztály-azonosító** mezőben írjon be vagy válasszon ki egy értéket.
6. Válassza a **Feljebb** lehetőséget.
7. Válassza a **Mentés** lehetőséget.
8. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]