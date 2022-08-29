---
title: Az ER-konfigurációk frissített verzióinak importálása
description: Ez a cikk bemutatja, hogy hogyan importálhatja az elektronikus jelentéskészítő (ER) konfigurációk frissített verzióit a Konfigurációs szolgáltatás globális tárházaiból.
author: kfend
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
ms.openlocfilehash: 0eef9c9a112fd58a43f6c3a85163ccf44bea3d61
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292646"
---
# <a name="import-updated-versions-of-er-configurations"></a>Az ER-konfigurációk frissített verzióinak importálása

[!include [banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) [adattárak](general-electronic-reporting.md#Repository) az [ER-konfigurációk](general-electronic-reporting.md#Configuration) megosztására szolgálnak. A különböző [tárházból](download-electronic-reporting-configuration-lcs.md) származó ER-konfigurációkat importálhatja a Microsoft Dynamics 365 Pénzügy példányába. Az ER-konfigurációk importálása során [a](general-electronic-reporting.md#Provider) konfigurációs szolgáltatók új verziótárakat tehetnek közzé, hogy meg tudják osztani őket.

Ez a cikk bemutatja, hogyan importálhatja az ER-konfigurációk frissített verzióit a Konfigurációs szolgáltatás globális tárházból. További tájékoztatás: [Microsoft Dynamics 365 Finance - Regulatory Services, Configuration Service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>A rendelkezésre álló frissített verziók áttekintése

1. Jelentkezzen be a Finance and Operations rendszerbe az alábbi szerepkörök egyikének használatával:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. A **Honosítási konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációk verziófrissítéseinek importálása** elemet.

    ![Lokalizációs konfigurációk oldala.](./media/er-download-updated-versions-global-repo1.png)

4. Az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** párbeszédpanel **Futtatási mód** mezőjében válassza a **Csak rendelkezésre álló frissítések megjelenítése** lehetőséget. Majd kattintson az **OK** lehetőségre. 

    ![A Futtatási mód mező Csak rendelkezésre álló frissítések megjelenítése beállítással.](./media/er-download-updated-versions-global-repo2.png)

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

    ![Futtatási mód mező a Legújabb frissítések importálása beállítással.](./media/er-download-updated-versions-global-repo5.png)

6. Válassza ki az **OK** lehetőséget.
7. A következő lépések egyikével megtudhatja, hogy mely konfigurációverziók importálása történt meg:

    - Ha az importálást interaktívan futtatja a kötegelt feladat használata helyett, tekintse át a kapott üzeneteket.

        ![Interaktív importálás futtatása közben kapott üzenetek.](./media/er-download-updated-versions-global-repo6.png)

    - Ha kötegelt módban futtatja az importálást, hajtsa végre a következő lépéseket:

        1. Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.
        2. Keresse meg és jelölje ki az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** feladatot, majd a művelet ablaktáblán a **Kötegelt feladat** lapon válassza a **Kötegelt feladat előzményei** lehetőséget a feladatok előzményeinek megtekintéséhez.
        3. A **Kötegelt feladat előzményei** oldalon válassza a **Napló** lehetőséget. Ezután a megjelenő üzenetben válassza ki az **Üzenet részletei** hivatkozást a feladat naplójának megtekintéséhez.

        ![Feladat naplója.](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> A program nem javasolja ismétlődő kötegeltfeladat-ütemezést az ER-konfigurációk frissített verzióinak közvetlenül a globális adattárból a működési környezetbe való importálásához, mert az importált verziók azonnal használhatók. Ehelyett ennek a módszernek a segítségével egy tesztkörnyezetbe telepítse az ER-konfigurációk verzióit. Ezeket azután a tesztkörnyezetében lehet értékelni, mielőtt termelési környezetbe telepítené őket.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
