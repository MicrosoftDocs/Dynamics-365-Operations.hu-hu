---
title: (RCS) Fájlok importálása XML-formátumban opcionális attribútumokkal
description: Ez a témakör azt mutatja be, hogy egy felhasználó hogyan tud ER-formátumkonfigurációt tervezni arra, hogy opcionális attribútumokat tartalmazó XML-formátumban importáljon fájlokat.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1290598d8dbd5b72d679ccf3e642e75b6dc3215
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727075"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) Fájlok importálása XML-formátumban opcionális attribútumokkal

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések bemutatják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó hogyan alakíthat ki Elektronikus jelentés (ER) formátumkonfigurációt választható attribútumokat tartalmazó XML-formátumú fájlok importálásához. Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit. A kezdés előtt töltse le és mentse helyileg az IncomingDocumentToLearnHowToHandleOptionalAttributes.xml fájlt a [Microsoft letöltőközpontból](https://go.microsoft.com/fwlink/?linkid=874684).

1.  Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra.
2.  Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket.
3.  Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.

## <a name="create-a-new-data-model-configuration"></a>Új adatmodell-konfiguráció létrehozása
1.  A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2.  A **Név** mezőbe írja be: „Modell xml-fájl importálásához”.
3.  Kattintson a **Konfiguráció létrehozása** lehetőségre.
4.  Kattintson a **Tervező** pontra.
5.  Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6.  A **Név** mezőbe írja be a következőt: „Gyökér”.
7.  Kattintson a **Hozzáadás** parancsra.
8.  Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
9.  A **Név** mezőbe írja be a következőt: „Lista”.
10. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
11. Kattintson a **Hozzáadás** parancsra.
12. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
13. A **Név** mezőbe írja be a következőt: „Kód”.
14. A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
15. Kattintson a **Hozzáadás** parancsra.
16. Kattintson a **Mentés** gombra.
17. Zárja be a lapot.
18. Kattintson az **Állapot módosítása** elemre.
19. Kattintson a **Befejezés** gombra.
20. Kattintson az **OK** gombra.

## <a name="create-a-format-for-data-import"></a>Adatimportálási formátum létrehozása
1.  A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2.  Az **Új** mezőbe írja be a „Formátum alapja a következő adatmodell: Modell xml-fájl importálásához” kifejezést.
3.  A **Név** mezőbe írja be: „Formátum xml-fájl importálásához”.
4.  Az **Igen** értéket válassza ki a **Támogatja az adatimportálást** mezőben.
5.  Kattintson a **Konfiguráció létrehozása** lehetőségre.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>XML-formátumú bejövő fájl elemzésére szolgáló formátum kialakítása
1.  Kattintson a **Tervező** pontra.
2.  Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.
3.  A fában válassza ki az **XML\Element** csomópontot.
4.  A **Név** mezőbe írja be a következőt: „Gyökér”.
5.  Kattintson az **OK** gombra.
6.  A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
7.  A fában válassza ki az **XML\Element** csomópontot.
8.  A **Név** mezőbe írja be a következőt: „Dokumentum”.
9.  A **Multiplicitás** mezőben válassza ki az **Egy a többhöz** értéket.
10. Kattintson az **OK** gombra.
11. A fastruktúrában válassza ki a **root\document** csomópontot.
12. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
13. A fastruktúrában válassza ki az **XML\Attribute** elemet.
14. A **Név** mezőbe írja be az ID szöveget.
15. Kattintson az **OK** gombra.
16. Kattintson a **Mentés** gombra.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Az elemzett adatok adatmodellbe való mentéséhez használandó formátum-hozzárendelés kialakítása
1. Kattintson a **Formátum hozzárendelése modellhez** elemre.
2. Kattintson az **Új** elemre.
3. A **Definíció** mezőben adjon meg vagy válasszon ki egy értéket.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. A **Név** mezőbe írja be a következőt: „Hozzárendelés”.
6. Kattintson a **Mentés** gombra.
7. Kattintson a **Tervező** pontra.
8. A fastruktúrában bontsa ki a **format** csomópontot.
9. A fastruktúrában bontsa ki a **format\root: XML Element(root)** csomópontot.
10. A fastruktúrában válassza ki a **format\root: XML Element(root)\document: XML Element 1..* (dokumentum)**.
11. Kattintson a **Kötés** gombra.
12. A fastruktúrában bontsa ki a **format\root: XML Element(root)\document: XML Element 1..* (dokumentum)**.
13. A fastruktúrában válassza ki a **format\root: XML Element(root)\document: XML Element 1..* (document)\id**.
14. A fastruktúrában bontsa ki a **List = format.root.document** részt.
15. A fastruktúrában válassza ki a **List = format.root.document\Code** pontot.
16. Kattintson a **Kötés** gombra.
17. Kattintson a **Mentés** gombra.
18. Zárja be a lapot.
 
## <a name="run-format-mapping"></a>Formátum-hozzárendelés futtatása
1. Kattintson a **Futtatás** parancsra.
2. Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** elemet.
3. Kattintson az **OK** gombra.

> [!NOTE]
> A kiválasztott fájl importálása nem történt meg, mert a formátum terve azt feltételezi, hogy a „dokumentum” elemhez létezik az „azonosító” attribútum, az importált fájl viszont nem tartalmaz ilyen attribútumot.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>A formátum szerkezetének módosítása az XML-attribútumot nem kötelezőként való kezeléséhez
1. Zárja be a lapot.
2. A fastruktúrában bontsa ki a **root\document** csomópontot.
3. A fastruktúrában válassza ki a **root\document\id** pontot.
4. A **Hiányzó attribútumhoz tartozó üres karakterlánc** mezőben válassza az **Igen** értéket.
5. Kattintson a **Mentés** gombra.
 
## <a name="run-format-mapping-to-test-changes"></a>Formátum-hozzárendelés futtatása a módosítások teszteléséhez
1. Kattintson a **Formátum hozzárendelése modellhez** elemre.
2. Kattintson a **Futtatás** parancsra.
3. Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** fájlt.
4. Kattintson az **OK** gombra.
5. Ellenőrizze a létrehozott fájlt. 

> [!NOTE]
> Ugyanazt a fájlt importálta, mivel a formátumtervező most az „azonosító” attribútumot a „dokumentum” elemhez opcionálisnak veszi.
