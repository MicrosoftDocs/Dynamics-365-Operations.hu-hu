---
title: Személyes információk szerkesztése
description: Ez a cikk azt mutatja be, hogyan lehet módosítani a személyes adatokat az Alkalmazottak és a Vezetők önkiszolgáló szolgáltatásában.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7e78873d0995334ac80ac22e8058b7fe0bc31ac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686122"
---
# <a name="edit-personal-information"></a>Személyes adatok szerkesztése


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources alkalmazásban az **Alkalmazotti önkiszolgáló munkaterületen** található adatok szerkeszthetők.

A szerkeszthető személyes adatok a következők:

- Címek
- Kapcsolattartó adatai
- Személyes kapcsolattartók
- Azonosítószámok
- Kifizetési mód
- A Human Resources alkalmazásban használt kép

>[!NOTE]
>Lehet, hogy bizonyos típusú személyes adatokat, például üzleti kapcsolattartó adatait nem szerkesztheti. A további tudnivalókat lásd: [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md).

A **Globális címjegyzék paraméterei** oldalon beállított paraméterek határozzák meg, hogy milyen szerepek tekinthetik meg az Ön személyes adatait.

1. Válassza ki az **Alkalmazotti önkiszolgáló szolgáltatást** lehetőséget a Human Resources modulban.

2. Válassza a **Személyes adatok szerkesztése** elemet.

3. A cím módosításához válassza a **Címek** lapot. Az elvégzett módosítások megjelennek a **Személyzetkezelés** munkaterületen a HR figyelmeztetéséhez.

    - Kattintson a **Hozzáadás** lehetőségre egy új cím hozzáadásához.
    - Meglévő cím szerkesztéséhez jelölje ki a címet, majd válassza a **Szerkesztés** parancsot.
    - Egy térkép megtekintéséhez válassza a **Térkép** elemet.
    - Kapcsolattartó hozzáadásához vagy eltávolításához válassza ki a **További beállítások** lehetőséget majd a **Speciális** elemet. A **Kapcsolattartási adatok** területen válassza a **Hozzáadás** vagy az **Eltávolítás** lehetőséget, és módosítsa a mezőket, ha szükséges.
    - Az időzóna és a hely beállításához válassza ki a **További beállítások** lehetőséget, majd válassza a **Speciális** elemet. Az **Általános** területen igény szerint szerkessze a mezőket.

4. A kapcsolattartási adatok módosításához válassza a **Kapcsolattartási adatok** lapot. A kapcsolattartási adatok különböző típusait adhatja meg, például a telefon, e-mail-cím és közösségi oldalra mutató hivatkozások. A kapcsolattartó adatait elsődlegesként is beállíthatja, de mindegyik típusból csak egyet állíthat be elsődlegesként.

    - Kattintson a **Hozzáadás** lehetőségre egy új kapcsolattartói információ hozzáadásához. Szükség szerint szerkessze a mezőket.
    - Meglévő cím kapcsolattartási adatok szerkesztéséhez válassza ki az elemet, majd válassza a **Szerkesztés** parancsot. Szükség szerint szerkessze a mezőket.
    - Ha privátként szeretne beállítani kapcsolattartói adatokat, válassza a **Speciális** lehetőséget, majd állítsa a **Privát** kapcsolót **Igen** állásba. Válassza ki az **OK** lehetőséget.
      >[!NOTE]
      >A **Speciális** gomb nem érhető el, ha a rendszergazda engedélyezte az **(Előzetes verzió) Alkalmazottak korlátozása a cím és kapcsolatfelvételi adatok hozzáadásánál és szerkesztésénél adott célok esetén** funkciót a környezetben. A további tudnivalókat lásd: [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md).
  
5. A személyes kapcsolattartók módosításához válassz a **Személyes kapcsolattartók** lapot. Kijelölhet vészhelyzeti kapcsolattartókat, a kedvezményezetteket és a gondozottakat. Egy kapcsolattartó lehet személy vagy szervezet. A **Juttatások kezelése** funkció személyes kapcsolattartási adatokat használ. További információ: [A személyes kapcsolattartó jogosultsági beállításainak konfigurálása](hr-benefits-setup-contact-eligibility-options.md).

6. Ha módosítani szeretné az azonosítószámait, például a TAJ számot, válassz az **Azonosítószámok** lapot. A módosítások egy jóváhagyási folyamaton keresztül mehetnek át, ha a szervezetnél be van állítva jóváhagyási munkafolyamat.

    - Azonosító szám hozzáadásához válassza az **Új** lehetőséget. Szükség szerint töltse ki a mezőket, és válassza a **Mentés** parancsot.
    - Szám szerkesztéséhez válassza a **Szerkesztés** elemet. Szükség szerint szerkessze a mezőket, és válassza a **Mentés** parancsot.

7. A saját fizetés módjai a Saját fizetési adatok lapon **változtatva választhatók** ki. Ez a lap csak akkor érhető el, ha a fizetési módok engedélyezve vannak az Emberi erőforrások **paraméterei lapon**. A HR a következők engedélyezheti: **Banki levétel**, **Készpénz**, **Csekk**, **Elektronikus fizetés** vagy **Egyéb**. A HR letilthatja az elektronikus fizetések érvényesítését (az Egyesült Államokban használt bérlista esetében), valamint a bankszámla-és a regisztrációs szám ellenőrzését is.

8. Ha módosítani szeretné a Human Resources alkalmazásban a profiljához megjelenítő képet, válassza a **Kép** lapot. A szervezet beállításaitól függően előfordulhat, hogy a képek jóváhagyásra lesznek küldve.

    - Kép feltöltéséhez válassza az **Új kép feltöltése** lehetőséget.
    - Kép eltávolításához jelölje ki a képet, majd válassza az **Eltávolítás** elemet.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
