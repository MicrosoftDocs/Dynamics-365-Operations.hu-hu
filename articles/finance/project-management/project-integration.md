---
title: Microsoft Project-ügyfélintegráció
description: A projektek ütemtervének megtervezése és karbantartása összetett lehet, ezért a projektmenedzsereknek olyan eszközöket kell használniuk, amelyek segítenek nekik elvégezni ezt a feladatot. A Microsoft Project ügyféllel való integráció támogatást nyújt a projekt munkalebontási struktúrájának megnyitásához és kezeléséhez.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 610990612d5fb38025bf39cc648d0c9572da37b6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174882"
---
# <a name="microsoft-project-client-integration"></a>Microsoft Project-ügyfélintegráció

[!include [banner](../includes/banner.md)]

A projektek ütemtervének megtervezése és karbantartása összetett lehet, ezért a projektmenedzsereknek olyan eszközöket kell használniuk, amelyek segítenek nekik elvégezni ezt a feladatot. A Microsoft Project ügyféllel való integráció támogatást nyújt a projekt munkalebontási struktúrájának megnyitásához és kezeléséhez. A projektmenedzser bármikor közzéteheti a változtatásokat a Dynamics 365 Finance projekt munkalebontási struktúrájába.

> [!NOTE]
> A júliusi frissítés (10.0.4 verzió) használata esetén, telepítenie kell a KB 4054797 és 4055884 csomagokat.

## <a name="configure-the-microsoft-project-client-add-in"></a>A Microsoft Project ügyfél bővítmény konfigurálása
A Microsoft Project ügyféllel való integráció engedélyezéséhez a Microsoft Dynamics 365 ügyfelet telepíteni kell a felhasználó ügyfél Microsoft Project alkalmazásában. Ehhez meg kel nyitni a **Projektvezetési munkaterületet**.

•   Kattintson az **Ügyfélbővítmény konfigurálása** elemre a munkaterület **Hivatkozások** > **Beállítás** részében.

• Kattintson a **Megnyitás** elemre, majd a kérdésnél kattintson az **Futtatás** elemre.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Meglévő vázlat munkalebontási struktúra megnyitása és szerkesztése a Microsoft Project ügyfélben
Ha a projekt a Dynamics 365 Finance programban már rendelkezik létrehozott munkalebontási struktúrával, a munkalebontási struktúra megnyitható a Microsoft Project ügyfél alkalmazásban, ha a munkalebontási struktúra „vázlat” állapotú. A **Projekt** oldalról történő megnyitáshoz kattintson a **Megnyitás a Microsoft Project programban** hivatkozásra a **Terv** lapon. Ez a lap a Microsoft Project ügyfél alkalmazáson belül is megnyitható a **Megnyitás** elemre kattintva a **Microsoft Dynamics 365** fülön. Válassza a **Jogi személy** és a **Projekt** lehetőséget a listából.

> [!NOTE]
> Ha Internet Explorer böngészőt használ, kattintson a **Mentés** elemre a fájl letöltési helyéről való manuális megnyitáshoz. Másik lehetőségként kattintson **Mentés és megnyitás** elemre a fájlt a Microsoft Project ügyfélben történő megnyitásához. A mentés során ne nevezze át a fájlnevet.

Mielőtt bármilyen módosítást végezne a fájlban a Microsoft Project ügyfél használatával, ki kell vennie. Kattintson a **Kivétel** elemre a **Microsoft Dynamics 365** lapon. Ez megakadályozza, hogy más felhasználók egy időben szerkesszék a munkalebontási struktúrát a Finance programban. Ha szeretné közzétenni a munkalebontási struktúrát bármilyen módosítás befejezése után, kattintson a **Beadás** elemre a **Microsoft Dynamics 365** lapon.

Ha egy projektcsapat már hozzá lett adva a projekthez a Finance programban, a rendszer kitölti az erőforráslistát a csapattagokkal. Ha projektcsapat még nincs hozzáadva a projekthez, kiválaszthat erőforrásokat kijelölése és létrehozhatja a csapatot a Microsoft Project ügyfélen belül, ha az **Erőforrások** gombra kattint a **Microsoft Dynamics 365** lapon. 

A következő adatokat a rendszer visszafelé szinkronizálja a Finance irányába a beadási folyamat részeként:

•   Feladat neve

•   Kezdő dátum

•   Befejezési dátum

•   Megelőző tevékenységek

•   Erőforrásnevek

•   Kategória

•   Erőforrás-kategória

•   Munkaórák

•   Megjegyzések

•   Prioritás

> [!NOTE]
> Ha más oszlopokat ad hozzá a Microsoft Project ügyfél fájlhoz, akkor ezek nem lesznek elmentve a fájlba, és nem jelennek meg a fájl megnyitásakor.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Meglévő projekt munkalebontási struktúrájának létrehozása a Microsoft Project ügyfél segítségével
Új munkalebontási struktúra létrehozásához a Microsoft Project ügyfél segítségével kövesse az alábbi lépéseket:


1.  Nyissa meg a Microsoft Project ügyfelet.

2.  A **Microsoft Dynamics 365** lapon kattintson a **Megnyitás** gombra.

3.  Válassza **Jogi személyt** a projekthez.

4.  Válassza ki a kívánt **Projektet**.

5.  Kattintson a **Kivétel** lehetőségre a **Microsoft Dynamics 365** lapon.

6.  Ha készen áll a Finance programba történő közzétételre, kattintson a **Beadás** elemre a **Microsoft Dynamics 365** lapon.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Meglévő projekt meglévő munkalebontási struktúrájának cseréje a Microsoft Project ügyfél segítségével
A Microsoft Project ügyfél segítségével új munkalebontási struktúra létrehozásához és egy meglévő projekt meglévő munkalebontási struktúra lecseréléséhez kövesse az alábbi lépéseket:

1.  Nyissa meg a Microsoft Project ügyfelet.

2.  Hozza létre az ütemezést a Microsoft Project ügyfélben.

3.  A **Microsoft Dynamics 365** lapon kattintson a **Módosítások mentése** > **Meglévő projekt lecserélése** elemre.

4.  Válassza **Jogi személyt** a projekthez.

5.  Válassza ki a kívánt **Projektet**.

6.  Kattintson az **OK** gombra.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Új projekt létrehozása a Microsoft Project ügyfélen belül


1.  Nyissa meg a Microsoft Project ügyfelet.

2.  Hozza létre az ütemezést a Microsoft Project ügyfélben.

3.  A **Microsoft Dynamics 365** lapon kattintson a **Módosítások mentése** > **Mentés új projektbe** elemre.

4.  Válassza **Jogi személyt** a projekthez.

5.  Adja meg a **Projektazonosító** értékét, ha szükséges.

6.  Írja be a **Projekt nevét**.

7.  Válassza ki a **Projekttípus**, **Projektcsoport** és a **Projektszerződés azonosítója** értékét. Azt is megteheti, hogy létrehozhat új projektszerződést az **Új** elemre kattintva.

8.  Válassza ki az erőforrásként használni kívánt **Naptárat**.

11. Kattintson az **OK** gombra.
