---
title: ER konfigurációk tervezése jelentések Word-formátumú előállításához
description: A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy elektronikus jelentés formátumot kimenetek Microsoft Word-fájlként történő létrehozására.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d4959b511022e1aa98544d23da6afcda1f6adf2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681925"
---
# <a name="design-er-configurations-to-generate-reports-in-word-format"></a>ER konfigurációk tervezése jelentések Word-formátumú előállításához

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy elektronikus jelentési (ER) formátumot kimenetek Microsoft Word-fájlként történő létrehozására. Ezeket a lépéseket a GBSI vállalatban hajthatja végre.

Az alábbi lépések végrehajtásához először hajtsa végre az „ER-konfiguráció létrehozása az OPENXML formátumban létrejövő jelentésekre vonatkozóan” feladat-útmutató lépéseit. Előkészítésként le kell tölteni és menteni a következő sablonokat is helyileg a mintajelentéshez:

- [Kifizetési jelentés sablonja](https://go.microsoft.com/fwlink/?linkid=862266)
- [Kifizetési jelentés bekötött sablonja](https://go.microsoft.com/fwlink/?linkid=862266)


Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Microsoft Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="select-the-existing-er-report-configuration"></a>Válassza ki a meglévő ER-jelentéskonfigurációt
1. A **Navigációs ablakban nyissa meg a Modulok > Szervezeti felügyelet > Munkaterületek >elektronikus jelentéskészítés** lehetőséget. Győződjön meg arról, hogy a „Litware, Inc.” konfigurációszolgáltató aktívként van megjelölve.  
2. Kattintson a **Jelentéskészítés konfigurációi** lehetőségre. Újrahasznosítjuk a meglévő ER-konfigurációt, amelyet eredetileg a jelentés OPENXML-formátumban történő előállítására terveztek.  
3. A fában bontsa ki a „Payment model” elemet.
4. A fastruktúrában válassza ki a „Fizetési modell\Minta munkalap jelentés” lehetőséget.
5. Kattintson a Tervező pontra.

## <a name="replace-the-excel-template-with-the-word-template"></a>Az Excel-sablon cseréje a Word-sablonra

Jelenleg az Excel-dokumentum használatos sablonként a kimenet OPENXML-formátumú előállításához. A jelentés sablonját Word-formátumban fogjuk importálni.

1. Kattintson a **Mellékletek** lehetőségre. A meglévő Excel-sablont cserélje le a korábban letöltött SampleVendPaymDocReport.docx Word-sablonra. Megjegyzés: Ez a sablon csak az ER-kimenetként létrehozandó dokumentum elrendezését tartalmazza.  
2. Kattintson a **Törlés** gombra.
3. Kattintson az **Igen** gombra.
4. Kattintson az **Új** elemre.
5. Kattintson a **Fájl** lehetőségre.
6. Kattintson a **Tallózás** lehetőségre. Keresse meg és válassza ki a korábban letöltött SampleVendPaymDocReport.docx dokumentumot. Kattintson az **OK** gombra. Válassza ki az előző lépésben letöltött sablont.  
7. A **Sablon** mezőben adjon meg vagy válasszon ki egy értéket.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Terjessze ki a Word-sablont egy egyéni XML-rész hozzáadásával
1. Kattintson a **Mentés** gombra. A konfigurációs módosítások tárolása mellett a Mentés művelet a csatolt Word-sablont is frissíti. A tervezett formátum szerkezete „jelentés” néven, új egyéni XML-részként kerül bele a csatolt Word-dokumentumba. Vegye figyelembe, hogy a csatolt Word-sablon nem csak az ER-kimentként létrehozandó dokumentum elrendezését tartalmazza, hanem azt az adatszerkezetet is, amelyet az ER futásidőben tölt fel a sablonban.  
2. Kattintson a **Mellékletek** lehetőségre.
    + Most hozzá kell kötnie a „jelentés” egyéni XML-rész elemeit a Word-dokumentum részeihez.  
    + Ha megfelelő ismeretekkel rendelkezik azokról a Word-dokumentumokról, amelyek olyan tartalomszabályozókat tartalmazó űrlapokként tervezhetők meg, amelyek az egyéni XML-részek elemeihez vannak kötve, végezze el a következő alfeladat minden lépését egy ilyen dokumentum létrehozásához. A további tudnivalókat lásd: [A felhasználó által Wordben kitölthető vagy kinyomtatható űrlapok létrehozása](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US). Ellenkező esetben hagyja ki a következő alfeladat minden utasítását.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Az egyéni XML-részt tartalmazó Word-dokumentum adatkötéseinek elvégzése

A Word alkalmazásban nyissa meg ezt a dokumentumot, majd tegye a következőket:  
1. Nyissa meg a Word fejlesztői lapját (ha még nincs engedélyezve, végezze el a Menüszalag testreszabását).
2. Válassza ki az XML-megfeleltetés munkaablakot.
3. Jelölje ki a „jelentés” egyéni XML-részt a keresésben.
4. Végezze el a kijelölt egyéni XML-rész elemeinek hozzárendelését a Word-dokumentum tartalomszabályozóihoz.  5. A frissített Word-dokumentumot mentse helyi meghajtóra.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Az egyéni XML-részt tartalmazó bekötött Word-sablon feltöltése a tartalomvezérlőkbe
1. Kattintson a **Törlés** gombra.
2. Kattintson az **Igen** gombra. Adjon hozzá egy új sablont. Az előző alfeladat lépéseinek végrehajtása után válassza ki az előkészített és helyben mentett Word-dokumentumot. Ellenkező esetben válassza ki a korábban letöltött SampleVendPaymDocReportBounded.docx Microsoft Word-sablont.  
3. Kattintson az **Új** elemre.
4. Kattintson a **Fájl** lehetőségre.
5. Kattintson a **Tallózás** lehetőségre. Keresse meg és válassza ki a korábban letöltött SampleVendPaymDocReportBounded.docx dokumentumot. Kattintson az **OK** gombra.
6. A **Sablon** mezőben válassza ki az előző lépésben letöltött dokumentumot.
7. Kattintson a **Mentés** gombra.
8. Zárja be a lapot.

## <a name="execute-the-format-to-create-word-output"></a>Formátum végrehajtása Word-kimenet létrehozásához
1. Kattintson a **Konfigurációk** lehetőségre a **Művelet** panelen.
2. Kattintson a **Felhasználói paraméterek** lehetőségre.
3. Válassza az Igen lehetőséget a **Beállítások futtatása** mezőben.
4. Kattintson az **OK** gombra.
5. Kattintson a **Szerkesztés** lehetőségre.
6. Válassza az Igen lehetőséget a **Vázlat futtatása** mezőben.
7. Kattintson a **Mentés** gombra.
8. Zárja be a lapot.
9. Zárja be a lapot.
10. A **Navigációs ablaktáblán** válassza a **Modulok > Kötelezettségek > Kifizetések > Kifizetési napló** elemet.
11. Kattintson a **Sorok** pontra.
12. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
13. Kattintson a **Kifizetési állapot** elemre.
14. Kattintson a **Nincs** lehetőségre.
15. Kattintson a **Kifizetések létrehozása** elemre.
16. Kattintson az **OK** gombra.
17. Kattintson az **OK** gombra. Elemezze a létrehozott kimenetet. Ne feledje, hogy a létrehozott kimenet Word-formátumban jelenik meg, és a feldolgozott kifizetések adatait tartalmazza.  

