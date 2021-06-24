---
title: Készségek megadása
description: A dolgozók és a vezetők megadhatják a szakértelemeket a Dynamics 365 Human Resources rendszerben.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5a65f1884ea87bbf2519cc94e4c52a40ac1a91bd
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193977"
---
# <a name="enter-skills"></a>Készségek megadása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A dolgozók, a pályázók vagy a kapcsolattartók a megcélzott vagy a már megszerzett készségeket is rögzíthetik a Dynamics 365 Human Resources rendszerben. A megcélzott szakértelem olyan szakértelem, amelyet az adott személy el szeretne érni. A tényleges szakértelem az, amivel már rendelkezik.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Munkafolyamat létrehozása a készségek automatikus jóváhagyásához

A készségek jóváhagyás nélkül történő megadásához létre kell hoznia egy munkafolyamatot a készségek automatikus jóváhagyásához.

> [!NOTE]
> A dolgozók által beírt készségek esetében mindig szükség van a vezető jóváhagyására. Ez a munkafolyamat csak a vezetők által a dolgozóik nevében megadott készségeket hagyja jóvá automatikusan.

1. A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások** lehetőséget.

2. A **Beállítás** részen válassza az **Emberi erőforrások munkafolyamatai** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. A **Munkafolyamat létrehozása** panelen válassza ki a **Dolgozó szakértelmei** lehetőséget.

   [![A Dolgozó szakértelmei munkafolyamat kiválasztása](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. A **Megnyitja ezt a fájlt?** párbeszédpanelen válassza a **Megnyitás** lehetőséget. Amikor a rendszer kéri, adja meg a hitelesítő adatait.

6. A munkafolyamat-szerkesztőben válassza ki a **Készségek jóváhagyása** munkafolyamat-elemet, és húzza a vászonra.

   [![A Készségek jóváhagyása munkafolyamat-elem kiválasztása](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Kapcsolja össze a **Kezdés** és az **1. készségek jóváhagyása**, majd az **1. készségek jóváhagyása** és a **Befejezés** elemet. Előfordulhat, hogy a **Záró** elem eléréséhez görgetni kell. Az elemet közelebb húzhatja a többi elemhez.

   [![Munkafolyamat-elemek összekapcsolása](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Kattintson duplán az **1. készségek jóváhagyása** munkafolyamat-elemre, majd kattintson a jobb gombbal az **1. lépés elemre**. Kattintson a jobb gombbal az **1. lépés** elemre, majd válassza a **Tulajdonságok** parancsot.

9. A **Tulajdonságok** ablakban válassza a **Feltétel** lehetőséget a bal oldali navigációs sávon.

10. Válassza a **Csak akkor fusson ez a lépés, ha teljesül a következő feltétel** lehetőséget.

11. Válassza ki a **Feltétel hozzáadása** lehetőséget. Az **Ahol** elem után válassza a **Alkalmazotti készségek önkiszolgáló módon**, majd az **Alkalmazotti készségek önkiszolgáló módon.Személy** lehetőséget. A **van** elem után válassza ki a **mezőt**, majd a **Felhasználó és szermély kapcsolata.Személy** lehetőséget.

    [![Feltétel megadása](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Válassza a **Hozzárendelés** lehetőséget a bal oldali navigációs sávon.

13. A **Hozzárendelés típusa** lapon válassza a **Hierarchia** lehetőséget.

14. A **Hierarchia kiválasztása** lapon **Hierarchia típusa:** mezőjében válassza a **Vezetői hierarchia** lehetőséget.

    [![Vezetői hierarchia megadása](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Válassza a **Bezárás**, majd a vászon útkövető modulján a **Munkafolyamat** elemet, végül a **Mentés és bezárás** lehetőséget.

További tájékoztatás a munkafolyamatok létrehozásáról: [A munkafolyamat-rendszer áttekintése](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Dolgozó készségeinek megadása

1. Jelöljön ki egy dolgozót.

2. A **Dolgozó** oldal műveletsávján válassza ki a **Személy**, majd a **Készségek** lehetőséget.

3. A **Készségek** oldalon minden készségnél töltse ki a következő mezőket:

   - **Készség**: Válasszon ki egy készséget.
   - **Szinttípus**: Válassza a **Tényleges** lehetőséget az olyan szakértelemekhez, amelyekkel a dolgozó már rendelkezik, és válassza a **Cél** lehetőséget az olyan szakértelmekhez, amelyeket a dolgozó próbál megszerezni.
   - **Szint**: A dolgozó szakértelmének megfelelő szint kiválasztása.
   - **Szint dátuma**: A naptárban válasszon ki dátumot.
   - **Vizsgáló**: Ha lehetséges, válasszon ki egy vizsgáztatót a listáról. A keresés szűrhető.
   - **Tapasztalat (év)**: Adja meg, hány éves tapasztalata van az illetőnek.
   - **Ellenőrizve**: Ha a készséget ellenőrizték van, jelölje be a jelölőnégyzetet.
   - **Ellenőrizte**: Adja meg az ellenőrző nevét.

4. Ha megadta a szakértelmek részleteit, válassza a **Mentés** lehetőséget.

## <a name="see-also"></a>Lásd még

[Készségek konfigurálása](hr-develop-skills.md)<br>
[Készségek hozzárendelése](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]