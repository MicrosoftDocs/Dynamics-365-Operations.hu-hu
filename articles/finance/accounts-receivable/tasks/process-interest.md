---
title: Kamatfeldolgozás
description: Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 093fbd23f9fcaf62db9988a98a94b8cebf582768
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443999"
---
# <a name="process-interest"></a>Kamatfeldolgozás

[!include [banner](../../includes/banner.md)]

Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be. Ez a feladat az USMF bemutatócéget használja.


## <a name="set-up-interest-on-the-posting-profile"></a>Állítsa be a kamatot a feladási profilon
1. A **navigációs ablaktáblán** lépjen a **Modulok > Követelések és beszedések > Beállítás > Vevői feladási profilok** részre.
2. Kattintson a **Szerkesztés** lehetőségre.
3. A **Beállítás** gyorslap **Kamatkód** mezőjében válassza ki a kamatkódot a legördülő listából. Ha nem szeretne kamatot számítani a tranzakciókhoz ehhez a feladói profilhoz, hagyja a mezőt üresen. A **Táblakorlátozások** gyorslapon módosíthatja a kamatfeldolgozás módját. Ha ez a mező Igen értékre van állítva, a rendszer számít kamatot a feladási profilhoz.  

## <a name="calculate-interest"></a>Kamatszámítás
1. A **navigációs ablaktáblán** lépjen a **Modulok > Követelések és beszedések > Kamat > Kamatlevelek létrehozása** részre.
2. Ki kell választania azokat a tranzakciótípusokat, amelyekhez kamatot kíván számítani. Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.  
3. Ha a **Kamat** beállításnál az „Igen” értéket adja meg, kamatos kamatot számíthat. A kamatos kamat számításához ellenőrizze az adott törvényeket, mielőtt ilyen tranzakciókat végezne.  
4. A **Kezdő dátum** mezőben adja meg a dátumot, amikortól kamatot szeretne számolni. Ha nem ad meg értéket a **Kezdő dátum** mezőben, akkor a rendszer törli a fel nem adott kamatleveleket, majd újraszámítja a kamatot a tranzakció dátumától.
5. A **Záró dátum** mezőben adja meg a dátumot, ameddig kamatot szeretne számolni.
6. A **Használt feladási profil helye** mezőben válasszon ki egy beállítást. Háromféle feladási profil létezik:
    - Számla – az egyes kamatlevelek vevőkódjához rendelt feladási profil használata. 
    - Kiválasztott – a Feladási mezőben megadott feladási profil használata.
    - Tranzakció – az egyes kamatleveleknél kamat számításához használt tranzakciók egyéni feladási profiljának használata. Az olyan tranzakciók esetében, amelyekhez nincs hozzárendelve feladási profil, a rendszer a Kinnlevőségek paraméterei képernyő Főkönyv és áfa területén megadott feladási profilt fogja használni.  
7. Bontsa ki a **Szerepeltetni kívánt rekordok** gyorslapot.
8. Kattintson a **Szűrő** parancsra.
9. A **Feltétel** mezőben adjon meg Vevőazonosítót. Adja meg például az „US-001”értéket.
6. Kattintson az **OK** gombra.
7. Kattintson az **OK** gombra.

## <a name="print-interest-notes"></a>Kamatlevelek nyomtatása
1. A **navigációs ablaktáblán** lépjen a **Modulok > Követelések és beszedések > Kamat > Kamatlevelek áttekintése és feldolgozása** részre.
2. Az **Állapot** mezőben válassza ki a „Létrehozva” értéket.
3. A **Nyomtatott** mezőben válassza a „Nem nyomtatva” lehetőséget.
4. Kattintson a **Nyomtatás** parancsra.
5. Bontsa ki a **Szerepeltetni kívánt rekordok** gyorslapot.
6. Kattintson az **OK** gombra.
7. Zárja be a lapot.

## <a name="post-the-interest-note"></a>Kamatlevél feladása
1. Válasszon ki egy olyan kamatlevelet, amely már feladásra kész (az állapota létrehozott).
2. Kattintson a **Bejegyzés** lehetőségre.
3. A kamatlevél feladási dátumának megadása. Jelölje be az Igent, ha az egyes kamatlevelekhez egyenként szeretné létrehozni a főkönyvi tranzakciókat. Ha nem jelöli be az Igent, akkor a vevő kamatleveleinek kamatai halmozódnak és egyetlen tranzakcióként kerülnek a főkönyvbe.  
4. Bontsa ki a **Szerepeltetni kívánt rekordok** gyorslapot.
5. Kattintson az **OK** gombra.
6. Az **Állapot** mezőben válassza ki a „Feladott” értéket.

