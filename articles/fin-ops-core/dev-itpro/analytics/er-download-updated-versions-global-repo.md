---
title: Az ER-konfigurációk frissített verzióinak importálása
description: Ez a témakör azt mutatja be, hogyan lehet importálni az elektronikus jelentéskészítési (ER) konfigurációk frissített verzióit a konfigurációs szolgáltatás globális tárából.
author: NickSelin
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4f167a0209713b5bca0cefe0135abd46a149a515
ms.sourcegitcommit: 1e6a7b50596eaf9d965e0155f3f2c50f7f50747e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2020
ms.locfileid: "3498096"
---
# <a name="import-updated-versions-of-er-configurations"></a>Az ER-konfigurációk frissített verzióinak importálása

[!include [banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) [adattárak](general-electronic-reporting.md#Repository) az [ER-konfigurációk](general-electronic-reporting.md#Configuration) megosztására szolgálnak. Az ER-konfigurációkat különböző adattárakból [importálhatja](download-electronic-reporting-configuration-lcs.md) a Microsoft Dynamics 365 Finance-példányába. Az ER-konfigurációk importálásakor a [konfigurációszolgáltatók](general-electronic-reporting.md#Provider) közzétehetik új [verziók](general-electronic-reporting.md#component-versioning) adattárait, így azok megoszthatók.

Ez a témakör azt mutatja be, hogyan lehet importálni az ER-konfigurációk frissített verzióit a konfigurációs szolgáltatás globális tárából. A további tudnivalókat lásd: [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, konfigurációs szolgáltatás](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>A rendelkezésre álló frissített verziók áttekintése

1. Jelentkezzen be a Finance and Operations rendszerbe az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. A **Honosítási konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációk verziófrissítéseinek importálása** elemet.

    ![Honosítási konfigurációk oldala](./media/er-download-updated-versions-global-repo1.png)

4. Az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** párbeszédpanel **Futtatási mód** mezőjében válassza a **Csak rendelkezésre álló frissítések megjelenítése** lehetőséget. Majd kattintson az **OK** lehetőségre. 

    ![A Futtatási mód mező Csak rendelkezésre álló frissítések megjelenítése beállítással](./media/er-download-updated-versions-global-repo2.png)

5. Tekintse át a kapott üzeneteket. Ezek az üzenetek a következő információkat tartalmazzák az aktuális Finance-példányban található ER-konfigurációkról, valamint a globális adattár tartalmának összehasonlításáról:

    - Az ER-konfigurációk teljes száma
    - A globális adattárban nem szereplő ER-konfigurációk száma.
    - Azok az ER-konfigurációk, amelyekhez a legfrissebb verzió már elérhető az aktuális Finance-példányban (ha meg szeretné tekinteni ezeknek az ER-konfigurációknak a teljes listáját, válassza az **Üzenet részletei** hivatkozást).

        !["A következő konfigurációk legújabb verziói már importálva vannak" üzenet és az üzenet részletei](./media/er-download-updated-versions-global-repo3.png)

    - Azok az ER-konfigurációk, amelyekhez a legfrissebb verzió elérhető a globális adattárban, és amelyek az aktuális Finance-példányba importálhatók (ha meg szeretné tekinteni ezeknek az ER-konfigurációknak a teljes listáját, válassza az **Üzenet részletei** hivatkozást).

        !["Elérhető frissítések" üzenet és az üzenet részletei](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>A rendelkezésre álló frissített verziók importálása

1. Jelentkezzen be a Finance and Operations rendszerbe az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. A **Honosítási konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációk verziófrissítéseinek importálása** elemet.
4. Az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** párbeszédpanel **Futtatási mód** mezőjében válassza a **Legújabb frissítések importálása** lehetőséget, ha a globális adattárból az ER-konfigurációk legfrissebb verzióit szeretné importálni az aktuális Finance-példányba.
5. Ha ütemezni szeretne egy kötegelt feladatot az importáláshoz, a **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozás** beállítást **Igen** értékre. Ha időnként meg szeretné ismételni az importálást, konfigurálja a szükséges ismétlődést.

    ![Futtatási mód mező a Legújabb frissítések importálása beállítással](./media/er-download-updated-versions-global-repo5.png)

6. Válassza ki az **OK** lehetőséget.
7. A következő lépések egyikével megtudhatja, hogy mely konfigurációverziók importálása történt meg:

    - Ha az importálást interaktívan futtatja a kötegelt feladat használata helyett, tekintse át a kapott üzeneteket.

        ![Interaktív importálás futtatása közben kapott üzenetek](./media/er-download-updated-versions-global-repo6.png)

    - Ha kötegelt módban futtatja az importálást, hajtsa végre a következő lépéseket:

        1. Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.
        2. Keresse meg és jelölje ki az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** feladatot, majd a művelet ablaktáblán a **Kötegelt feladat** lapon válassza a **Kötegelt feladat előzményei** lehetőséget a feladatok előzményeinek megtekintéséhez.
        3. A **Kötegelt feladat előzményei** oldalon válassza a **Napló** lehetőséget. Ezután a megjelenő üzenetben válassza ki az **Üzenet részletei** hivatkozást a feladat naplójának megtekintéséhez.

        ![Feladat naplója](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> A program nem javasolja ismétlődő kötegeltfeladat-ütemezést az ER-konfigurációk frissített verzióinak közvetlenül a globális adattárból a működési környezetbe való importálásához, mert az importált verziók azonnal használhatók. Ehelyett ennek a módszernek a segítségével egy tesztkörnyezetbe telepítse az ER-konfigurációk verzióit. Ezeket azután a tesztkörnyezetében lehet értékelni, mielőtt termelési környezetbe telepítené őket.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából](er-download-configurations-global-repo.md)
