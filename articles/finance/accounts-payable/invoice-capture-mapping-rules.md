---
title: Számlarögzítési megoldás hozzárendelési szabályai
description: Ez a cikk a Számlarögzítési megoldás hozzárendelési szabályainak beállításával kapcsolatban tartalmaz tájékoztatást.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690997"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Számlarögzítési megoldás hozzárendelési szabályai

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A hozzárendelési szabályok az Microsoft Dynamics alapvető alapadatokat a 365 Pénzügy vagy a vállalati erőforrás-tervezési (ERP) rendszerből hozzák létre. A megfeleltetési szabályok beállítása után a pénzügyben a szállítói számlák létrehozásához szükséges információk származnak. A megfeleltetési szabályok használata esetén a Kötelezettségek (AP) adminisztrátora ellenőrzi az állapotot, és nem kell manuálisan kitöltenének minden hiányzó mezőértéket.

A leképezési szabályoknak négy típusa van:

- Jogi személy
- Szállítói számla
- Cikk
- Kiadás típusa

## <a name="manage-mapping-rules-by-using-the-app"></a>A hozzárendelési szabályok kezelése az alkalmazás segítségével

A hozzárendelési szabályok alkalmazással való kezeléséhez válassza a Beállítás **lehetőséget**. A Hozzárendelési **szabály beállítása lapon** négy lehetőség áll rendelkezésre:

- Jogi személy 
- Szállítói számla 
- Cikkleképezés 
- Kiadás típusa

Például válassza a Jogi személy hozzárendelési **szabályok lehetőséget**. A jogi személy kódját a vállalat neve, címe és adószáma azonosítja. LE-USPM **nevű szabály esetén, ha a vállalat neve tartalmazza a "Contoso Contoso Contosoics USA" szöveget,** akkor a **jogi személy kódja AZ USPM** lesz.

A lapon az összes aktív hozzárendelési szabály látható. Ha meg szeretné tekinteni az inaktív hozzárendelési szabályokat, válassza **az Aktív hozzárendelés jogi** személy szabályait, majd **válassza az Inaktív hozzárendelés jogi személy szabályait**.

A következő műveletek érhetők el hozzárendelési szabályokhoz.

### <a name="create-a-mapping-rule"></a>Hozzárendelési szabály létrehozása

Hozzárendelési szabály létrehozásához két módszer használható:

- Új hozzárendelési **szabály** létrehozásához válassza az Új lehetőséget. Ezután adja meg a hozzárendelési szabály adatait. A **Szabálynév értéknek** egyedinek kell lennie minden megfeleltetési szabálytípushoz.
- Ha meglévő hozzárendelési szabályt választ, elérhetővé válik **a Másolás** gomb. Válassza ki, majd a **megjelenő párbeszédpanelen kattintson az OK** gombra. Hozzárendelési szabály létrehozása a kiválasztott szabály másolása alapján történik.

### <a name="edit-a-mapping-rule"></a>Hozzárendelési szabály szerkesztése

Hozzárendelési szabály szerkesztéséhez jelöljön ki egy mezőt, és módosítsa az értéket.

### <a name="activatedeactivate-mapping-rules"></a>Leképezési szabályok aktiválása/inaktiválása

Egy vagy több hozzárendelési szabály inaktiválásához jelölje **ki őket az Aktív** hozzárendelési szabályok lapon, majd válassza az Inaktiválás **lehetőséget**. A szabályok átkerülnek az Aktív hozzárendelési **szabályok** lapról az Inaktív **hozzárendelési szabályok lapra**.

Hasonlóképpen a hozzárendelési szabályok aktiválásához jelölje ki **őket** az Inaktív hozzárendelési szabályok lapon, majd válassza az Aktiválás **lehetőséget**.

### <a name="remove-mapping-rules"></a>Hozzárendelési szabályok eltávolítása

A hozzárendelési szabályok eltávolításához jelölje ki őket, majd válassza a Törlés **lehetőséget**.

### <a name="check-for-conflicts"></a>Ütközések ellenőrzése

Ha két **hozzárendelési** **szabályban** megegyezik a jogi személy és a szállítói számla értéke, **de** eltérő cikknév-értékek vannak, a rendszer ütközést észlel, és a hozzárendelési szabályt nem fogja létrehozni vagy frissíteni.

## <a name="importexport-mapping-rules-from-excel"></a>Hozzárendelési szabályok importálása és exportálása az Excel programból

Az Excel-bővítmények segítségével kötegben kezelhetők a szabályok. Ehhez a következő lehetőségek állnak rendelkezésre:

- Excel-sablon letöltése
- Exportálás az Excel programba
- Importálás az Excel programból

### <a name="download-an-excel-template"></a>Excel-sablon letöltése

Excel-sablon letöltéséhez válassza a Letöltés **sablont**. Ezután válassza ki a sablonban szerepelni kívánt mezőket.

### <a name="export-to-excel"></a>Exportálás Excel-fájlba

Kétféleképpen exportálhat:

- A **fájl Excel programban való megnyitásához válassza a Megnyitás az Excel Online** programban lehetőséget. Ezután a fájlt online szerkesztheti. Amikor elkészült, válassza a **Mentés** elemet. A program minden változtatást ment a Leképezési **szabály lapon**.
- Jelölje ki **a Letöltési munkalapot** egy hozzárendelési szabályokat tartalmazó Excel-fájl letöltéséhez. Ezután szerkesztheti a fájlt. Ha végzett, **az Importálás az Excel** programból lehetőséget választva töltse fel a frissített munkalapot.

### <a name="import-from-excel"></a>Importálás az Excel programból

1. Válassza az **Importálás az Excel** programból lehetőséget az ADATOK XLSX-fájlból történő importáláshoz. Vesszővel elválasztott értékekből (CSV) vagy XML-fájlokból is lehet importálni. Mielőtt importál, el kell döntenie, hogy engedélyezett-e az ismétlődés.
2. Az Attribútumok **megfeleltetésének** ellenőrzéshez és a helyesség meghatározásához válassza az Ellenőrzés hozzárendelése lehetőséget. A megfeleltetési kapcsolat módosítható.
3. Ha végzett, az importálás befejezéséhez **válassza az Importálás befejezése** lehetőséget.
4. Az importálási folyamat **előrehaladásának** nyomon követéséhez a Folyamat követése lehetőséget választja.

    Az importálás állapota **Befejezés** **állapotról Parsingre**, **majd Átalakítás**, végül **Kész állapotra módosul.**

Az importálási folyamat befejeztével megjelenik a sikerességekkel, a részleges hibákkal, a hibákkal és a feldolgozott összesen feldolgozott adatokkal kapcsolatos statisztika.
