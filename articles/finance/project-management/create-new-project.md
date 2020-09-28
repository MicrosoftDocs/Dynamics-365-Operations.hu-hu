---
title: Új projekt létrehozása
description: Ez a témakör új projekt létrehozásával kapcsolatban tartalmaz tájékoztatást.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760563"
---
# <a name="create-a-new-project"></a>Új projekt létrehozása

[!include [banner](../includes/banner.md)]

Új projekt létrehozásához hajtsa végre az alábbi lépéseket.

1. A **Projektvezetés** oldalon válassza az **Új projekt** lehetőséget, és adja meg a következő értékeket:

    - **Projekt típusa:** Idő és anyag
    - **Projekt neve:** XYZ Frissítési Fázis 2
    - **Projektcsoport:** TM\_WIP
    - **Projektszerződés azonosítója:** 00000002

2. Válassza a **Projekt létrehozása** elemet.

## <a name="assign-a-resource-to-a-project"></a>Erőforrás hozzárendelése egy projekthez

1. A **Dolgozók** oldalon a **Dolgozók** listában válassza ki az ahhoz a dolgozóhoz tartozó rekordot, akihez korábban kompetenciákat állított be, majd nyissa meg azt.
2. A Műveleti ablaktáblán a **Projekt** lapon a **Beállítás** csoportban válassza a **Projekt hozzárendelése** lehetőséget.
3. Az **Erőforrás-ellenőrzés projekt-hozzárendelései** oldalon a **Projektek** lapon a **Projekt hozzáadása a kiválasztott projektekhez** mezőben alkalmazzon szűrőt az **XYZ frissítési szakasz 2** projektre.
4. A **Fennmaradó projektek** ablaktáblán válasszon ki egy projektet, majd válassza a nyílgombot, hogy hozzáadja azt a **Kiválasztott projektek** ablaktáblához.

Igény szerint hozzárendelhet kategóriákat egy erőforráshoz. A kategória típusa **Költség** vagy **Bevétel** lehet. A kategória típusát a szervezet határozza meg. Ha nincsenek az erőforráshoz hozzárendelt kategóriák, a Finance kikeresi az alapértelmezett óránkénti árat a költségekhez és bevételekhez.

## <a name="set-up-project-resource-and-role-characteristics"></a>Projekt erőforrások és szerepkör jellemzők beállítása

A projektvezető a projekterőforrás funkció segítségével hozhat létre a projekthez szükséges szerepköröket. A szerepkörök akkor használhatóak, ha a visszaigazolt erőforrások ismeretlenek az erőforrások fenntartásakor. A szerepkörök ideiglenes fenntarthatók tervezett erőforrásként, így tovább folytathatja a projekttervezést.

[![Példa szerepkörre](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Forgatókönyv:** Contoso egy olyan Idő- és anyagprojekt elvégzésére lett felvéve, amely rendelkezik egy jóváhagyott projekt alapszabállyal. A beosztott projektvezető továbbra is a projekt hatókörét tölti ki. Az erőforrás-kezelő jelenleg azokat a fenntartott erőforrásokat azonosítja, amelyek az új projekthez lesznek rendelve. A projekt kritikus jellege miatt a projekttámogató a Vezető projektmenedzser szerepkört kérte. Az erőforrás-kezelőnek új erőforrást kell szereznie, majd meghatároznia a szerepkört a rendszerben, hogy ha a beosztott projektvezetőnek szüksége lenne az erőforrás-információkra a projekttervezés alatt, akkor az rendelkezésre álljon.

Az alábbi lépések bemutatják, hogy az erőforrás-kezelő hogyan tud beállítani Vezető projektmenedzser szerepkört a rendszerben, valamint hogyan tud erőforrás jellemzőket társítani hozzá. A későbbiek folyamán a szerepkör használható lesz olyan kereséseknél, amelyek azon elérhető erőforrásokat keresik meg, amelyek megfelelnek a szükséges erőforrás kompetenciáknak.

1. A **Szerepkörök beállítása** oldalon válassza az **Új** lehetőséget, és adja meg a következő értékeket:

    - **Szerepkör-azonosító:** Vezető Projektmenedzser
    - **Leírás:** Vezető Projektmenedzser

2. Válassza a **Létrehozása** lehetőséget.
3. Válassza a **Vezető projektmenedzser** szerepkört, és válassza a **Jellemzők konfigurálása** lehetőséget.
4. A **Jellemzők típusa** mezőben válassza ki a **Szakértelem** lehetőséget.
5. Az **Elérhető jellemzők** mezőbe írja be a keresett szakértelem típusát.
6. A **Jellemző típusa** mezőben válassza ki a **Diploma** lehetőséget.
7. Az **Elérhető jellemzők** mezőbe írja be a keresett diploma típusát.

## <a name="assign-a-project-resource-to-a-project"></a>Projekterőforrás hozzárendelése egy projekthez

1. A **Minden projekt** oldalon válassza az **XYZ frissítési fázis 2** projektet.
2. A **Projektcsapat és ütemezés** fülön válassza a **Hozzáadás** lehetőséget.
3. A **Szerepkör** mezőben válassza a **Csapat tagja** lehetőséget.
4. Válassza a **Foglalás naptárból** lehetőséget.
5. Az **Erőforrás elérhetősége** lapon válassza a **Beállítások megtekintése** lehetőséget.
6. A **Nézet beállításának módosítása** lapon adja meg az alábbi értékeket:

    - **Dátumtartomány-nézet formátuma:** Nap
    - **Elérhetőség leírásának megjelenítése:** Igen
    - **Hátralévő kapacitás megjelenítése:** Igen

7. Az erőforrások listájából válasszon egy erőforrást.
8. Válassza a **Végleges lefoglalás** és a **Teljes kapacitás** lehetőségeket.

## <a name="assign-a-resource-to-a-default-role"></a>Erőforrás hozzárendelése egy alapértelmezett szerepkörhöz

A projekthez fenntartható erőforrásokon történő leásás segítheti a projektvezetőket és az erőforrás-kezelőket. Alapértelmezett szerepkört társíthat már meglévő, valamint újonnan szerzett erőforrásokhoz. Amikor például Danielt felvették, megfelelő tapasztalattal és készségekkel rendelkezett az üzleti elemző szerep betöltéséhez. Az erőforrás-kezelő ezt a szerepkört rendelte Danielhez alapértelmezett szerepkörként. Ezért az erőforrás-kezelő Danielt hozzáadta az üzleti elemzők készletéhez, akik rendelkezésre állnak a projekteken végzett munkához.

Erőforrás-fenntartás során a projektvezetők szűrhetik a szerepkör erőforrásait, amelyek rendelkezésre állnak projekteken való munkához. Ezeket az adatokat használhatják egy feltételként több kritérium felhasználásával történő döntéshozatal végrehajtásakor erőforrás teljesítése során. Más erőforrás tulajdonságait is hozzáadhatják a szűrőhöz meghatározott szakértelemmel, végzettséggel és adott projekttapasztalattal rendelkező erőforrások keresésekor.

**Eset:** Egy jóváhagyott projekt elindult, és a Vezető projektmenedzser szerepkört tervezett erőforrásként tartották fenn a projekt tervezési szakaszában. Az erőforrás-kezelő már megszerezte az erőforrást a Vezető projektmenedzser szerepkör betöltéséhez.

1. Az **Erőforráslista** oldalon válassza a **Daniel Goldschmidt** nevet.
2. Az **Erőforrás szerepköre** oldalon válassza az **Új** lehetőséget, és adja meg a következő értékeket:

    - **Hatályos:** adja meg a jelenlegi dátumot.
    - **Lejárat:** adja meg a **Soha** értéket.
    - **Szerepkör:** adja meg a **Vezető Projektmenedzser** lehetőséget.

3. Válassza a **Mentés** gombot, majd zárja be az oldalt.
4. A **Kompetenciák** lapon adja hozzá a **ProjectMgmt** szakértelem és **PMP** tanúsítványt.
