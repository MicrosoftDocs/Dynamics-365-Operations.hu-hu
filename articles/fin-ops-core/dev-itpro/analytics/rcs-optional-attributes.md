---
title: Fájlok importálása XML-formátumban opcionális attribútumokkal
description: Ez a rész az olyan ER-formátumok kialakítását ismerteti, amelyek meghatározzák az XML-formátumú beérkező elektronikus dokumentumok elemzésére használt XML-attribútumokat.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 14b14dd609805a7cf9331427012b991791698cfd
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686661"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a>Fájlok importálása XML-formátumban opcionális attribútumokkal

[!include [banner](../includes/banner.md)]

Olyan elektronikus jelentési (ER) formátumokat tervezhet, amelyekkel elemezhetők az XML-formátumú bejövő elektronikus dokumentumok. Az XML-elemek bizonyos attribútumai választhatóként adhatók meg a tervezett ER-formátumban. Ezzel a megoldással megfelelően kezelhetők az ilyen XML-attribútumokkal rendelkező és nem rendelkező bejövő fájlok. Az ezekből a fájljokból származó tartalmakat felhasználhatja az alkalmazásadatok frissítésére.

Ha további információt szeretne erről a szolgáltatásról, hajtsa végre az [(RCS) Fájlok importálása XML-formátumban opcionális attribútumokkal](tasks/import-files-xml-format-optional-attributes.md) című cikk lépéseit. Ez a cikk a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része. Ez a feladat-útmutató és a kapcsolódó mintafájlok a [Microsoft letöltőközpontjából](https://go.microsoft.com/fwlink/?linkid=874684) tölthetők le.


| Tartalom leírása       | Fájl                                                         |
|---------------------------|--------------------------------------------------------------|
| Mintafájl XML-formátumban | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml     |
| Feladat-útmutatók                | RCS fájlok importálása XML-formátumban opcionális attribútumokkal.axtr |


A következő lépések bemutatják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó hogyan alakíthat ki Elektronikus jelentés (ER) formátumkonfigurációt választható attribútumokat tartalmazó XML-formátumú fájlok importálásához. Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárás lépéseit. A kezdés előtt töltse le a Microsoft letöltőközpontjából (https://go.microsoft.com/fwlink/?linkid=874684 ) és mentse helyileg az IncomingDocumentToLearnHowToHandleOptionalAttributes.xml fájlt.

1. Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre.
2. Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.
3. Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.

## <a name="create-a-new-data-model-configuration"></a>Új adatmodell-konfiguráció létrehozása
1. A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. A **Név** mezőbe írja be: „Modell xml-fájl importálásához”.
3. Kattintson a **Konfiguráció létrehozása** lehetőségre.
4. Kattintson a **Tervező** pontra.
5. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. A **Név** mezőbe írja be a következőt: „Gyökér”.
7. Kattintson a **Hozzáadás** parancsra.
8. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
9. A **Név** mezőbe írja be a következőt: „Lista”.
10.    A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
11.    Kattintson a **Hozzáadás** parancsra.
12.    Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
13.    A **Név** mezőbe írja be a következőt: „Kód”.
14.    A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
15.    Kattintson a **Hozzáadás** parancsra.
16.    Kattintson a **Mentés** gombra.
17.    Zárja be a lapot.
18.    Kattintson az **Állapot módosítása** elemre.
19.    Kattintson a **Befejezés** gombra.
20.    Kattintson az **OK** gombra.

## <a name="create-a-format-for-data-import"></a>Adatimportálási formátum létrehozása
1. A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Az **Új** mezőbe írja be a „Formátum alapja a következő adatmodell: Modell xml-fájl importálásához” kifejezést.
3. A **Név** mezőbe írja be: „Formátum xml-fájl importálásához”. 
4. Az **Igen** értéket válassza ki a **Támogatja az adatimportálást** mezőben.
5. Kattintson a **Konfiguráció létrehozása** lehetőségre.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>XML-formátumú bejövő fájl elemzésére szolgáló formátum kialakítása
1. Kattintson a **Tervező** pontra.
2. Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.
3. A fában válassza ki az **XML\Element** csomópontot.
4. A **Név** mezőbe írja be a következőt: „Gyökér”.
5. Kattintson az **OK** gombra.
6. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
7. A fában válassza ki az **XML\Element** csomópontot.
8. A **Név** mezőbe írja be a következőt: „Dokumentum”.
9. A **Multiplicitás** mezőben válassza ki az **Egy a többhöz** értéket.
10.    Kattintson az **OK** gombra.
11.    A fastruktúrában válassza ki a **root\document** csomópontot.
12.    A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
13.    A fastruktúrában válassza ki az **XML\Attribute** elemet.
14.    A **Név** mezőbe írja be az „azonosító” kifejezést.
15.    Kattintson az **OK** gombra.
16.    Kattintson a **Mentés** gombra.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Az elemzett adatok adatmodellbe való mentéséhez használandó formátum-hozzárendelés kialakítása
1.    Kattintson a **Formátum hozzárendelése modellhez** elemre.
2.    Kattintson az **Új** elemre.
3.    A **Definíció** mezőben adjon meg vagy válasszon ki egy értéket.
4.    A **Név** mezőbe írja be a következőt: „Hozzárendelés”.
5.    Kattintson a **Mentés** gombra.
6.    Kattintson a **Tervező** pontra.
7.    A fastruktúrában bontsa ki a **format** csomópontot.
8.    A fastruktúrában bontsa ki a **format\root: XML Element(root)** csomópontot.
9.    A fastruktúrában válassza ki a **format\root: XML Element(root)\document: XML Element 1..* elemet (dokumentum)**.
10.    Kattintson a **Kötés** gombra.
11.    A fastruktúrában bontsa ki a **format\root: XML Element(root)\document: XML Element 1..* elemet (dokumentum)**.
12.    A fastruktúrában válassza ki a **format\root: XML Element(root)\document: XML Element 1..* elemet (document)\id**.
13.    A fastruktúrában bontsa ki a **List = format.root.document** részt.
14.    A fastruktúrában válassza ki a **List = format.root.document\Code** pontot.
15.    Kattintson a **Kötés** gombra.
16.    Kattintson a **Mentés** gombra.
17.    Zárja be a lapot.

## <a name="run-format-mapping"></a>Formátum-hozzárendelés futtatása
1. Kattintson a **Futtatás** parancsra.
2. Kattintson a **Tallózás** gombra, és válassza az **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** fájlt.
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
5. Ellenőrizze a létrehozott fájlt. Ügyeljen rá, hogy ugyanazt a fájlt importálta, mivel a formátumtervező most az „azonosító” attribútumot a „dokumentum” elemhez opcionálisnak veszi.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]