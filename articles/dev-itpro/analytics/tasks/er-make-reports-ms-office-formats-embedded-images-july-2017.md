--- 
title: "Konfigurációk tervezése jelentések készítéséshez Microsoft Office formátumokban, beágyazott képekkel"
description: "E témakör lépései azt mutatják be, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk Microsoft Office formátumokban (Excelben és Wordben) beágyazott képeket tartalmazó elektronikus dokumentumok létrehozására."
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5e3ba5c76df3dcc5042074a565d102ceaeeadfb0
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="design-configurations-to-generate-reports-in-microsoft-office-formats-with-embedded-images"></a>Konfigurációk tervezése jelentések készítéséshez Microsoft Office formátumokban, beágyazott képekkel

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit. Ez az eljárás bemutatja, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk beágyazott képeket tartalmazó Microsoft Excel vagy Word-dokumentumok létrehozására. Ebben az eljárásban a szükséges ER konfigurációkat a Litware, Inc. mintavállalathoz hozza létre. Ezek a lépések az USMF adatkészlet segítségével tölthetők be. Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. Mielőtt elkezdené, töltse le és mentse el a [Képek és alakzatok beágyazása az Elektronikus jelentéskészítés eszköz által generált üzleti dokumentumokba](../electronic-reporting-embed-images-shapes.md) súgótémában felsorolt fájlokat. A fájlok: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png és Cheque template Word.docx.

## <a name="verify-prerequisites"></a>Az előfeltételek ellenőrzése  
 1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.  
 2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.   
 3. Kattintson a Jelentéskészítés konfigurációi lehetőségre.  
 
## <a name="add-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció hozzáadása  
 1. Új modell létrehozása esetén betöltheti a korábban mentett ER modellkonfigurációs fájlt (Model for cheques.xml). Ez a fájl tartalmazza a fizetési csekkek mintaadatmodelljét és az adatmodell a Dynamics 365 for Operations alkalmazás adatösszetevőire való leképezését.   
 2. A verzió gyorslapon kattintson az Átváltás lehetőségre.   
 3. Kattintson a Betöltés XML-fájlból lehetőségre.  
 4. Kattintson a Tallózás gombra, majd válassza ki a Model for cheques.xml dokumentumot.   
 5. Kattintson az OK gombra.  
 6. A rendszer a betöltött modellt használja információforrásként a képeket tartalmazó Excel- és Word-dokumentumok létrehozására.  

## <a name="add-a-new-er-format-configuration"></a>Új ER-formátum hozzáadása  
 1. Új formátum létrehozása esetén betöltheti a korábban mentett ER-formátumkonfigurációs fájlt (Cheques printing format.xml). A fájl a csekkek nyomtatásához használt formátum mintaelrendezését tartalmazza egy előre nyomtatott űrlap segítségével, valamint a formátum „Model for cheques” adatmodellre való leképezését.   
 2. Kattintson az Átváltás lehetőségre.  
 3. Kattintson a Betöltés XML-fájlból lehetőségre.  
 4. Kattintson a Tallózás gombra, és válassza ki a Cheques printing format.xml fájlt.   
 5. Kattintson az OK gombra.  
 6. A fastruktúrában bontsa ki ezt: „Model for cheques”.  
 7. A fában válassza ki ezt: „Model for cheques\Cheques printing format”.  
 8. A rendszer a betöltött formátumot használja képeket tartalmazó Excel- és Word-dokumentumok létrehozására.   

## <a name="configure-er-user-parameters"></a>ER felhasználói paraméterek konfigurálása  
 1. Kattintson a Konfigurációk lehetőségre a Művelet Panelen.  
 2. Kattintson a Felhasználói paraméterek lehetőségre.  
 3. Válassza az Igen lehetőséget a Beállítások futtatása mezőben.  
  Kapcsolja be a Vázlat futtatása jelzőt a kijelölt formátum piszkozatverziójának elindításához a befejezett verzió helyett.  
 4. Kattintson az OK gombra.  

## <a name="configure-cash--bank-management-parameters"></a>Készpénz- és bankkezelési paraméterek konfigurálása  
 1. Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.  
 2. A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.  
 3. A műveleti ablaktáblán kattintson a Beállítások elemre.  
 4. Kattintson az ellenőrzés lehetőségre.  
 5. Bontsa ki a Beállítások szakaszt.  
 6. Kattintson a Szerkesztés lehetőségre.  
 7. Válassza ki az Igen lehetőséget a Vállalat emblémája mezőben.  
 8. Kattintson a Vállalat emblémája lehetőségre.  
 9. Kattintson a Módosítás gombra.  
 10. Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Company logo.png.   
 11. Kattintson a Mentés gombra.  
 12. Zárja be a lapot.  
 13. Bontsa ki az Aláírás szakaszt.  
 14. Válassza az Igen lehetőséget az Első aláírás nyomtatása mezőben.  
 15. Kattintson a Módosítás gombra.  
 16. Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Signature image.png.   
 17. Bontsa ki a Példányok szakaszt.  
 18. A Vízjel mezőben válasszon egy lehetőséget.  
 19. Válassza az Igen beállítást az Exportálási formátum mezőben.  
 20. Válassza a „Csekkek nyomtatása képernyő” konfigurációt.  
 21. Ekkor a rendszer a kijelölt ER-formátumot használja csekkek nyomtatására.  
 22. Kattintson a Csatolás elemre.  
 23. Kattintson az Új lehetőségre.  
 24. Kattintson a Fájlra.  
 25. Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Signature image2.png.   
 26. Zárja be a lapot.  
 27. Zárja be a lapot.  
 28. Zárja be a lapot.  
 29. Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.  
 30. AZ Ellenőrző tranzakció létrehozásának engedélyezése az inaktív bankszámláknál: mezőben válassza az Igen lehetőséget.  
 31. Kattintson a Mentés gombra.  
 32. Zárja be a lapot.  

