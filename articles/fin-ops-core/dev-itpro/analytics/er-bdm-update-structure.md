---
title: Üzleti dokumentumsablon szerkezetének frissítése
description: Ez a témakör azt mutatja be, hogyan lehet frissíteni egy üzleti dokumentumsablon szerkezetét az üzleti dokumentumkezelő funkció segítségével.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 203c9f0990051c1618660959dad0e184add68ffa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750484"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Üzleti dokumentumsablon szerkezetének frissítése 

[!include[banner](../includes/banner.md)]

Az **Üzleti Dokumentumkezelés** sablonszerkesztő [Sablonszerkeze](er-business-document-management.md) paneljén módosíthatja az üzleti dokumentum sablonját [új mezők hozzáadásával](er-bdm-add-field-to-excel-template.md) egy sablonhoz a Microsoft Excel alkalmazásban. A program ezután automatikusan frissíti a sablon struktúráját Dynamics 365 Finance alkalmazásban, hogy az tükrözze a **Sablon szerkezete** ablaktáblán elvégzett változtatásokat.

A sablonokat az Office 365 online funkció használatával is módosíthatja. Hozzáadhat például egy új névvel ellátott elemet, például képet vagy alakzatot a szerkeszthető munkalapra. Ebben az esetben a sablon szerkezete nem frissül automatikusan a Finance alkalmazásban, és a hozzáadott tétel nem jelenik meg a **Sablon szerkezete** ablaktáblán. A sablon struktúrájának manuális frissítése a Finance-ban a sablonszerkesztő lap **Szerkezet frissítése** lehetőségének kiválasztásával.

Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Példa: Üzleti dokumentumsablon szerkezetének frissítése

Ez a példa azt mutatja be, hogy a rendszergazda milyen módon frissítheti egy üzleti dokumentumsablon szerkezetét, miután a sablon módosult az Office Online szolgáltatásban. A következő szakaszok a szóban forgó lépéseket mutatják be.

### <a name="prepare-a-business-document-template-for-editing"></a>Üzleti dokumentum sablonjának előkészítése szerkesztésre

Hajtsa végre a következő lépéseket az [Üzleti dokumentumkezelés áttekintése](er-business-document-management.md) részben.

1. [ER-paraméterek konfigurálása](er-business-document-management.md#configure-er-parameters)
2. [ER-megoldások importálása](er-business-document-management.md#import-er-solutions)
3. [Az Üzletidokumentum-kezelés engedélyezése](er-business-document-management.md#enable-business-document-management)
4. [Paraméterek konfigurálása](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Üzleti dokumentumsablonok szerkesztése

1. Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.
2. Az **Új sablon létrehozása** lapon válassza ki a **Szabadszöveges számla (ER minta) (Excel)** sablont.
3. Válassza a **Dokumentum létrehozása** lehetőséget.
4. A **Cím** mezőbe írja be a következőt: **FTI minta Litware**.
5. Válassza az **OK** lehetőséget egy új sablon létrehozásához.

    > [!NOTE]
    > Ha még nem jelentkezett be az Office Online-szolgáltatásba, akkor [az Office 365 bejelentkezési oldalára](er-business-document-management.md#frequently-asked-questions) lesz irányítva. A pénzügyi környezethez történő visszatéréshez kattintson a böngésző **Vissza** gombjára.

    Az új sablon szerkesztésre megnyílik az Excel Online beágyazott vezérlőben a sablonszerkesztő lapon.

[![Üzleti dokumentumsablon szerkesztésének megkezdése az Üzleti dokumentumkezelő munkaterületen](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>A szerkeszthető sablon aktuális szerkezetének áttekintése

1. Az Excel Online alkalmazásban a menüszalag **Nézet** lapján a **Megjelenítés** csoportban válassza ki a **Rácsvonalak** lehetőséget.
2. A szerkeszthető sablonban válassza ki a sablon címéhe fölött látható téglalapot. Ez a téglalap egy **rptHeaderCompLogo** nevű kép.
3. Ha a **Sablon szerkezete** ablaktábla rejtett, válassza a **Szerkezet megjelenítése** elemet.
4. A **Sablon szerkezete** ablaktáblán bontsa ki a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** elemet.
5. Figyelje meg, hogy a sablonstruktúra a Finance-ban, a **rptHeaderCompLogo** elem a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** származtatott elemeként jelenik meg.

[![Egy szerkeszthető sablon aktuális szerkezetének áttekintése az Üzleti dokumentumkezelés munkaterületen](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Üzleti dokumentumsablon szerkezetének frissítése a kép törlésével

1. Az Excel Online alkalmazásban a szerkeszthető sablonban válassza ki a **rptHeaderCompLogo** képet.
2. Hajtsa végre a következő lépések egyikét, ha a szerkeszthető sablonból törölni szeretné a kijelölt képet:

    - Nyomja meg a **Delete** billentyűt billentyűzeten.
    - Jelölje ki és tartsa megnyomva a képet (vagy kattintson rá a jobb gombbal), majd válassza a **Kivágás** parancsot.

    > [!NOTE]
    > Az **rptHeaderCompLogo** elem jelenleg még mindig szerepel a Finance sablonstruktúrájában, még akkor is, ha a kép már nem szerepel az Excel-sablonban.

3. Az Excel és a Finance szerkeszthető sablon struktúrájának szinkronizálásához válassza a **Struktúra frissítése** lehetőséget.
4. A **Sablon szerkezete** ablaktáblán bontsa ki a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** elemet.
5. Figyelje meg, hogy az **rptHeaderCompLogo** elem tétel már nem szerepel a Finance sablonstruktúrájában.

[![Üzleti dokumentumsablon egy képének törlése az Üzleti dokumentumkezelő munkaterületen](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Üzleti dokumentumsablon szerkezetének frissítése egy kép hozzáadásával

1. Az Excel Online alkalmazásban a menüszalag **Beszúrás** lapján az **Illusztrációk** csoportban válassza ki a **Kép** lehetőséget.
2. Válassza ki a **Fájl kiválasztása** elemet , tallózzon a hozzáadni kívánt képhez, jelölje ki, majd kattintson az **OK** gombra.
3. Válassza a **Beszúrás** lehetőséget.
4. Mozgassa az új képet, amíg az a megfelelő helyre nem kerül. Alapértelmezés szerint az Excel nevezi el a képet. Például kaphatja a **Kép 2** nevet.
5. Az Excel és a Finance szerkeszthető sablon struktúrájának szinkronizálásához válassza a **Struktúra frissítése** lehetőséget.
6. A **Sablon szerkezete** ablaktáblán bontsa ki a **Jelentés \> Számla \> rptHeader \> rptHeaderPart1** elemet.
7. Figyelje meg, hogy az új kép immár elemként szerepel a Finance sablonstruktúrájában.

[![Üzleti dokumentumsablonhoz kép hozzáadása az Üzleti dokumentumkezelő munkaterületen](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Kapcsolódó hivatkozások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Üzletidokumentum-kezelés – áttekintés](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]