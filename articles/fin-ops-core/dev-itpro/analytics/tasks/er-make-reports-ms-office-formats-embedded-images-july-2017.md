---
title: Konfigurációk tervezése jelentések készítéséshez Office formátumban, beágyazott képekkel
description: Ez a témakör azt mutatja be, hogyan tervezhetők konfigurációk beágyazott képeket tartalmazó Excel- és Word-formátumú elektronikus dokumentumok létrehozására.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944557"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Konfigurációk tervezése jelentések készítéséshez Office formátumban, beágyazott képekkel

[!include [banner](../../includes/banner.md)]

A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit. Ez az eljárás bemutatja, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk beágyazott képeket tartalmazó Microsoft Excel vagy Word-dokumentumok létrehozására. Ebben az eljárásban a szükséges ER konfigurációkat a Litware, Inc. mintavállalathoz hozza létre. Ezek a lépések az USMF adatkészlet segítségével tölthetők be. Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. Mielőtt belekezdene, a következő fájlokat is le kell töltenie és mentenie kell: 

| Leírás                                          | Fájlnév                   |
|------------------------------------------------------|-----------------------------|
| ER-adatmodell konfigurációja                          | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER-formátum konfigurációja                              | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Vállalati embléma képe                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Aláírás képe                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Alternatív aláírási kép                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Microsoft Word sablon a kifizetési csekkek nyomtatásához  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>Az előfeltételek ellenőrzése  
 1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.  
 2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.   
 3. Kattintson a Jelentéskészítés konfigurációi lehetőségre.  
 
## <a name="add-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció hozzáadása  
 1. Új modell létrehozása esetén betöltheti a korábban mentett ER modellkonfigurációs fájlt (Model for cheques.xml). Ez a fájl tartalmazza a fizetési csekkek mintaadatmodelljét és az adatmodell Dynamics 365 for Operations alkalmazás adatösszetevőire való leképezését.   
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
  Kapcsolja be a „Vázlat futtatása” jelzőt a kijelölt formátum piszkozatverziójának elindításához a befejezett verzió helyett.  
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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
