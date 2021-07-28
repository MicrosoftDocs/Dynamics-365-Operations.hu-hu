---
title: Feladatlisták létrehozása és feladatok hozzáadása
description: Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat létrehozni, és feladatokat adni azokhoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e7964181a739a8138011abca77d0321d819e0a98
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354493"
---
# <a name="create-task-lists-and-add-tasks"></a>Feladatlisták létrehozása és feladatok hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat létrehozni, és feladatokat adni azokhoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A *feladat* egy meghatározott munkát vagy egy műveletet határoz meg, amelyet valakinek el kell végeznie a megadott esedékességi dátumig vagy azt megelőzően. A Dynamics 365 Commerce alkalmazásban egy feladathoz a kapcsolattartóval kapcsolatos részletes utasítások és információk is tartozhatnak. Tartalmazhat a háttérben történő irodai műveletekre, pénztári (POS) műveletekre vagy a webhelyoldalakra mutató hivatkozásokat is, amelyek segítségével javíthatja a termelékenységet, és egy kontextust adhat meg, hogy a feladat tulajdonosa hatékonyan végezhesse el a feladatot.

A *feladatlista* olyan feladatok gyűjteménye, amelyeket egy üzleti folyamat részeként kell végrehajtani. Előfordulhat például, hogy az új dolgozónak be kell fejeznie egy feladatlistát a felvétel során, vagy van egy feladatlista a pénztárosoknak, akik az esti műszakban dolgoznak, vagy van egy olyan feladatlista, amivel felkészítik az üzletet a közelgő ünnepi szezonra. A Commerce alkalmazásban minden olyan feladatlistát, amelynek van a megadott dátuma, tetszőleges számú üzlethez vagy alkalmazotthoz hozzá lehet rendelni, és be lehet állítani, hogy ismétlődjön.

A vezetők és a dolgozók egyaránt létrehozhatnak feladatlistát a Commerce háttérirodájában, majd ezeket üzletek egy halmazához hozzárendelhetik.

## <a name="create-a-task-list"></a>Feladatlista létrehozása

Feladatlista létrehozásához kövesse az alábbi lépéseket.

1. Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.
1. Válassza az **Új** lehetőséget, majd írja be a kívánt értékeket a **Név**, a **Leírás** és a **Tulajdonos** mezőbe.
1. Válassza a **Mentés** lehetőséget.

## <a name="add-tasks-to-a-task-list"></a>Feladatok hozzáadása egy feladatlistához

Feladatok hozzáadásához egy feladatlistához tegye a következőket:
 
1. Egy meglévő Feladatlista **Feladatok** gyorslapján válassza az **Új** lehetőséget, ha feladatot szeretne hozzáadni.
1. Az **Új feladat létrehozása** párbeszédpanelen írjon be egy egyedi nevet a feladat számára a **Név** mezőbe.
1. Írjon be egy pozitív vagy egy negatív egész értéket a **Határidő eltolása a céldátumhoz képest** mezőbe. Írja be például a **-2** értéket, ha a feladatnak két nappal a feladatlista esedékességi dátuma előtt be kell fejeződnie.
1. A **Megjegyzések** mezőbe írja be a részletes utasításokat.
1. A **Kapcsolattartó személy** mezőjébe írja be annak a szakembernek a nevét, akivel a feladat tulajdonosa kapcsolatba tud lépni, ha segítségre van szüksége.
1. A **Feladat hivatkozása** mezőben adjon meg egy hivatkozást a feladat jellegétől függően.

> [!TIP]
> Annak ellenére, hogy a **Hozzárendelve a következőhöz:** mezővel a feladatlista létrehozása során a feladatot hozzárendelheti valakihez, ajánlott elkerülni a feladatok hozzárendelését a Feladatlista létrehozása során. Ehelyett a lista ez egyes üzletekhez való példányosítása után rendelje hozzá a feladatokat.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>A feladatra mutató hivatkozásokkal javíthatja a dolgozó termelékenységét

A Commerce lehetővé teszi a feladatok meghatározott pénztári műveletekhez történő csatolását, például az értékesítési jelentések futtatását, az új alkalmazotti orientációhoz kapcsolódó online képzési videó megtekintését, illetve egy háttérművelet végrehajtását. Ez a funkció segít a feladattulajdonsoknak a feladatok hatékony teljesítéséhez szükséges információk beszerzésében.

A feladatok létrehozása közben feladathoz kapcsolódó hivatkozások hozzáadásához kövesse az alábbi lépéseket.

1. Egy meglévő feladatlista **Feladatok** gyorslapján válassza az **Szerkesztés** lehetőséget.
1. A **Feladat szerkesztése** párbeszédpanel **Feladathivatkozás** mezőjében válasszon ki egyet vagy többet a következő lehetőségek közül:

    - Válassza ki a **Menüelemet** a háttérben történő működés konfigurálásához, például „Termékcsomagok.”
    - Válassza ki a **Pénztári művelet** elemet pénztári művelet konfigurálásához, például „Értékesítési jelentések.”
    - Válasszon **URL-címet** egy abszolút URL-cím beállításához.

A következő ábra a **Feladatok szerkesztése** párbeszédpanel feladathivatkozások beállítását mutatja be.

![A feladathivatkozások kiválasztása a feladat szerkesztése párbeszédpanelen.](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>A pénztári művelet konfigurálása egy feladathoz való csatolás céljából

A pénztári művelet konfigurálásához egy feladathoz való csatolás céljából kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** lehetőségre.
1. Válassz a **Szerkesztés** lehetőséget, keresse meg a pénztári műveletet és jelölje be hozzá a **Feladatkezelés engedélyezése** jelölőnégyzetet.

## <a name="additional-resources"></a>További erőforrások

[Feladatkezelés – áttekintés](task-mgmt-overview.md)

[Feladatkezelés konfigurálása](task-mgmt-configure.md)

[Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz](task-mgmt-assign-lists.md)

[Feladatkezelés a pénztárban](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
