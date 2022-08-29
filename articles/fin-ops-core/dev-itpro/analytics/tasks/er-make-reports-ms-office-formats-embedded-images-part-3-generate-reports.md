---
title: Jelentések készítése Office formátumokban, beágyazott képekkel
description: Ez a témakör azt mutatja be, hogyan lehet elektronikus jelentéskészítési (ER) konfigurációkat tervezni a beágyazott képeket tartalmazó excel- és Word-dokumentumok előállításához.
author: kfend
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfd4aca1013d7fdf408f9057810feedc4b44e586
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290274"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>Jelentések készítése Office formátumokban, beágyazott képekkel

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhet meg egy új Elektronikus jelentés (ER) konfigurációkat, beágyazott képeket tartalmazó MS Office (Excel vagy Word) formátumú elektronikus dokumentumok létrehozásához.

Ebben a példában a Litware, Inc. mintavállalatra vonatkozóan létrehozott ER-konfigurációkat használjuk.  A lépések végrehajtásához először végre kell hajtani az „ER – Jelentések létrehozása Microsoft Office-formátumokban, beágyazott képekkel (2. rész: Konfigurációk áttekintése)” feladat-útmutató lépéseit. Ezeket a lépéseket a USMF vállalatban hajthatja végre.


## <a name="run-format-with-initial-model-mapping"></a>Futtassa a formátumot a kiindulási modell-hozzárendeléssel
1. Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.
2. A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.
3. A műveleti ablaktáblán kattintson a Beállítások elemre.
4. Kattintson az ellenőrzés lehetőségre.
5. Kattintson a Tesztnyomtatás lehetőségre.
    * Futtassa a formátumot tesztelési céllal.  
6. Válassza az Igen lehetőséget az Átruházható csekkformátum mezőben.
7. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. A vállalati embléma megjelenik a jelentésben, a jogosult személy aláírásával együtt. Az aláírás képe a kiválasztott bankszámlával társított csekkelrendezése-rekord „Konténer” adattípusú mezőjéből származik.  
8. Bontsa ki a Példányok szakaszt.
9. Kattintson a Szerkesztés lehetőségre.
10. A Vízjel mezőjébe írja be a következőt: „Vízjel nyomtatása érvénytelenként”.
    * Módosítsa a vízjel elrendezése beállítást, hogy egy Excel-alakzat elemen dokumentum létrehozásakor megjelenjen a vízjel szövege.  
11. Kattintson a Tesztnyomtatás lehetőségre.
12. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. A vízjel a beállítással összhangban jelenik meg a létrehozott jelentésen.  
13. Zárja be a lapot.
14. A Művelet panelen kattintson a Kifizetések kezelése elemre.
15. Kattintson a Csekkek lehetőségre.
16. Kattintson a Szűrők megjelenítése pontra.
17. Alkalmazza a következő szűrőket: adja meg a „381”, „385”, „389” szűrőértéket a „Csekk száma” mezőben „a következők valamelyike” szűrési operátor használatával.
18. A listában jelöljön ki minden sort.
19. Kattintson a Csekk másolatának nyomtatása elemre.
    * Futtassa a formátumot a kiválasztott csekkek újranyomtatásához.  
    * Tekintse át a létrehozott kimenetet. A kiválasztott csekkek újra lettek nyomtatva. A vállalati embléma és a címkék nem lesznek kinyomtatva, mivel azok megjelennek az előre nyomtatott űrlapon.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Módosítsa az importált adatok modell-hozzárendelését
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
4. A fastruktúrában válassza ki ezt: „Model for cheques”.
5. Kattintson a Tervező pontra.
6. Kattintson a Modell hozzárendelése adatforráshoz gombra.
7. Kattintson a Tervező pontra.
    * Megváltoztatjuk az adatmodell aláírás elemének kötését, hogy a kiválasztott bankszámlával társított csekkelrendezése-rekordhoz társított fájlból vegye az aláírás képét.  
8. Kapcsolja ki a Részletek megjelenítését.
9. A fastruktúrában bontsa ki ezt: „layout”.
10. A fában bontsa ki az „layout\signature” elemet.
11. A fában válassza ki ezt: „layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp”.
12. A fában bontsa ki a „chequesaccount” elemet.
13. A fastruktúrában bontsa ki a „chequesaccount\<Relations” elemet.
14. A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout” elemet.
15. A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout\<Relations” elemet.
16. A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents” elemet.
17. A fában válassza ki a „chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()” elemet.
18. Kattintson a Kötés gombra.
19. Kattintson a Mentés gombra.
20. Zárja be a lapot.
21. Zárja be a lapot.
22. Zárja be a lapot.
23. Zárja be a lapot.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Futtassa a formátumot a módosított modell-hozzárendeléssel
1. Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Bankszámla mezővel az „USMF OPER” értéket beírva.
3. A műveleti ablaktáblán kattintson a Beállítások elemre.
4. Kattintson az ellenőrzés lehetőségre.
5. Kattintson a Tesztnyomtatás lehetőségre.
6. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. A Dokumentumkezelés mellékletéből származó kép jelenik meg a jogosult személy aláírásaként.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Microsoft Word dokumentum sablonként való használata az importált formátumban
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
4. A fastruktúrában bontsa ki ezt: „Model for cheques”.
5. A fában válassza ki ezt: „Model for cheques\Cheques printing format”.
6. Kattintson a Tervező pontra.
7. Kattintson a Mellékletek lehetőségre.
8. Kattintson a Törlés gombra.
9. Kattintson az Igen gombra.
10. Kattintson az Új lehetőségre.
11. Kattintson a Fájlra.
    * Kattintson a Tallózás gombra, és töltse le előre a „Cheque template Word.docx” fájlt.  
12. Zárja be a lapot.
13. A Sablon mezőben adjon meg vagy válasszon ki egy értéket.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.
16. Kattintson a Szerkesztés lehetőségre.
17. Válassza az Igen lehetőséget a Vázlat futtatása mezőben.
18. Zárja be a lapot.
19. Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.
20. A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.
21. Kattintson az ellenőrzés lehetőségre.
22. Kattintson a Tesztnyomtatás lehetőségre.
23. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. A kimenet Word dokumentumként jött létre beágyazott képekkel, amelyek a vállalati emblémát, a jogosult személy aláírását és vízjel kiválasztott szövegét tartalmazzák.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
