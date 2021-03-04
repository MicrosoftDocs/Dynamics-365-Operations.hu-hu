---
title: Állásjelöltek toborzása
description: Ez a témakör bemutatja, hogyan lehet jelölteket toborozni a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9a35abcb8a2f6aa8031c8d84a44c2a8ad93883ac
ms.sourcegitcommit: 0354ca7e566fbd2eb0aabdd40000d4ac5c44ea78
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/04/2020
ms.locfileid: "4669171"
---
# <a name="recruit-job-candidates"></a>Állásjelöltek toborzása

[!include [banner](includes/preview-feature.md)]

A Dynamics 365 Human Resources segít a toborzási kérelmek kezelésében. Segít abban is, hogy zökkenőmentesen vezessen át állásjelölteket az alkalmazottak közé. Ha a szervezet külön toborzási alkalmazást használ, a toborzási folyamat a következő lépéseket foglalhatja magában:

- Adja meg toborzási kérelmét a Human Resources alkalmazásban.
- Fogadja a toborzási kérelmeket a toborzó alkalmazásból a Human Resources alkalmazásban.
- A jelöltek jóváhagyási folyamatát végezze el a Human Resources alkalmazásban.

Ha nem használ külön toborzási alkalmazást, manuálisan is kezelheti a jelölteket az Human Resources alkalmazásban.

>[!NOTE]
>Ha Ön rendszergazda vagy fejlesztő, és integrálni szeretné az Human Resources alkalmazást egy külső toborzó alkalmazással, olvassa el a [Common Data Service integráció konfigurálása](hr-admin-integration-common-data-service.md) és a [Common Data Service virtuális entitások konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md) című témakört
>
> Integrálható toborzó alkalmazásokat találhat az [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics) felületén is.
>
> A LinkedIn Talent Hub szolgáltatással való integráció előzetes verziójának kipróbálásához lásd: [Integrálás a LinkedIn Talent Hub-szolgáltatással](hr-admin-integration-linkedin.md).

## <a name="enable-recruiting-requests"></a>Toborzási kérelmek engedélyezése

Ha toborzási kérelmeket szeretne benyújtani a Human Resources alkalmazásban szolgáltatásban, először engedélyeznie kell a funkciót az **Human Resources paramétereiben**.

1. A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások** lehetőséget.

2. A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.

3. Az **Általános** lap **TOBORZÁS** részében állítsa a **Toborzási kérelmek engedélyezése** beállítás **Igen** értékre.

   ![Toborzási kérelmek engedélyezése](./media/hr-recruit-0-enable-requests.png)

## <a name="add-a-recruiting-request-location"></a>Toborzási kérelem helyének hozzáadása

Ha a szervezetnek több helyszíne van, hozzáadhatja őket, így a kérelmezők kiválaszthatják azt a helyet, ahol az új belépő dolgozik majd. A hely szerepelni fog az álláshirdetésben.

1. A keresősávban adja meg a **toborzási kérelem helye** kifejezést.

2. Válassza az **Új** lehetőséget.

3. A **Toborzási kérelem helye** mezőben adja meg a hely nevét.

   ![Toborzási kérelem helyének hozzáadása](./media/hr-recruit-0a-add-location.png)

4. A **Leírás** mezőben adja meg a hely leírását.

5. A **Hely** alatt válassz a **Hozzáadás** lehetőséget. Ha megjelenik az **Új cím** előugró ablak, adja meg a hely címét.

   ![Cím megadása](./media/hr-recruit-0b-address.png)

6. A **Kapcsolattartási adatok** alatt adja meg a hely kapcsolattartójának adatait.

7. Válassza a **Mentés** lehetőséget.

## <a name="add-a-recruiting-request"></a>Toborzási kérelem hozzáadása

A vezetők toborzási kérelmeket nyújthatnak be a Human Resources alkalmazásba. Ha külön toborzási alkalmazást használ, a lépések végrehajtása toborzási kérelmet küld, és elindítja a toborzási folyamatot az adott alkalmazásban. Ellenkező esetben hajtsa végre ezt az eljárást a munkafolyamat elindításához a saját belső toborzási folyamatához.

1. Válassza az **Alkalmazotti önkiszolgáló rendszer** lehetőséget.

2. Válassza ki a **Saját csapat** lapot.

3. Válassza a **Toborzás kérése** lehetőséget.

   ![Toborzási kérelem indítása](./media/hr-recruit-1-request-to-recruit.png)

4. Töltse ki a **Leírás**, **Munka** és a **Becsült kezdési dátum** mezőket.

   ![A toborzási kérelem befejezése](./media/hr-recruit-2-request-to-recruit.png)

5. Válassza **Folytatás** parancsot. Megjelenik a toborzási kérelem a pozíciójához.

6. Az **Általános** részben válasszon ki egy toborzót a **Toborzó** legördülő menüből, majd válasszon ki egy helyet a **Toborzási kérelem helye** legördülő menüből.

7. A **Munka** részben szükség szerint módosítsa az adatokat, majd válassza a **Részletek létrehozása a munkából** lehetőséget.

   ![Részletek létrehozása a feladatból](./media/hr-recruit-3-create-details-from-job.png)

   A toborzási kérelem többi része ki lesz töltve a megadott munka alapértelmezett adataival.

8. A **Külső leírás** részben adjon meg egy a szervezeten kívülről megtekinthető leírást.

9. A **Pozíciók** részben válassza a **Hozzáadás** lehetőséget, majd válassza ki a toborzási kérelemhez tartozó beosztást.

   ![Pozíció hozzáadása](./media/hr-recruit-4-select-position.png)

10. A **Szakértelmek** részben válassza a **Hozzáadás** lehetőséget, majd válasszon ki egy szakértelmet.

11. Az **Oktatási követelmények** csoportban válassza a **Hozzáadás** lehetőséget, majd válasszon értékeket a **Végzettség** és az **Végzettség szintje** legördülő menüből.

   ![Végzettségi követelmények hozzáadása](./media/hr-recruit-5-select-educational-requirements.png)

12. A **Megjegyzés** részben szükség szerint fűzzön hozzá megjegyzéseket.

13. A **Kompenzáció** részben válasszon egy szintet a **Szint** legördülő menüből, majd szükség szerint módosítsa az **Alacsony küszöb**, az **Ellenőrzőpont** és a **Magas küszöb** értéket.

14. Amikor a toborzási kérelem elkészült, és készen áll a toborzási folyamat elindítására, válassza az **Aktiválás** lehetőséget a menüsorban.

   ![Toborzási kérelem aktiválása](./media/hr-recruit-6-activate-recruit-request.png)

15. Válassza a **Mentés** lehetőséget.

## <a name="view-and-edit-your-recruiting-requests"></a>A toborzási kérelmek megtekintése és szerkesztése

Ha Ön vezető, és szeretné megtekinteni a saját kéréseit:

1. Válassza az **Alkalmazotti önkiszolgáló rendszer** lehetőséget.

2. Válassza ki a **Saját csapat** lapot.

3. A **Saját csapat adatai** területen válassza a **Toborzási kérelmek** lapot.

   ![Toborzási kérelmek lap kiválasztása](./media/hr-recruit-7-recruiting-requests.png)

4. A toborzási kérelem megtekintéséhez vagy szerkesztéséhez jelölje ki azt a rácsban.

Ha Ön HR-szakember, és szeretné megtekinteni az összes toborzási kérelmet:

1. Válassza a **Személyzetkezelés** lehetőséget.

2. Válassza a **Toborzási kérelmek** lehetőséget.

   ![Toborzási kérelmek megtekintése a Személyzetkezelésben](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. A toborzási kérelem megtekintéséhez vagy szerkesztéséhez jelölje ki azt a rácsban.

## <a name="add-or-edit-a-candidate-profile"></a>Jelöltprofil hozzáadása vagy szerkesztése

Ha a szervezet integrált egy másik alkalmazást a toborzási kérelmek kezeléséhez, a toborzási kérelmek továbbítva vannak az adott alkalmazáshoz. A toborzási alkalmazás ezután visszaküldi a pályázók adatait a Human Resourcesnak. Máskülönben követheti a saját belső toborzási folyamatait, és manuálisan adhatja meg a jelöltadatokat.

1. Válassza a **Személyzetkezelés** lehetőséget.

2. Válassza a **Hivatkozások** lehetőséget.

3. A **Toborzás** csoportban válassza a **Jelöltek** lehetőséget.

   ![Jelentkezők megtekintése](./media/hr-recruit-9-candidates.png)

4. Jelölt hozzáadásához válassza az **Új** lehetőséget. Meglévő jelentkező szerkesztéséhez jelölje ki a jelentkezőt a listában, majd válassza a **Szerkesztés** lehetőséget. Megjelenik a jelölt profilja.

5. A **Jelölt összegzése** részben szükség szerint adja meg vagy szerkessze a pályázó adatait.

6. A **Toborzási kérelem** alatt válassza ki azt a toborzási kérelmet, amelyhez a jelöltet kapcsolni szeretné. Ezután töltse ki a **Becsült kezdési dátum**, **Felvételi vezető**, **Beosztás** és **Leírás** mezőket igény szerint.

   ![Toborzási kérelemre mutató hivatkozás](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Töltse ki az összes információt a következő területeken, amelyeket fel szeretne venni a jelölt rekordjába:
   - **Megjegyzések**
   - **Szakmai tapasztalat**
   - **Kapcsolattartó adatai**
   - **Végzettség**
   - **Szakértelem**
   - **Diplomák**
   - **Szűrések**

8. Válassza a **Mentés** lehetőséget.

## <a name="hire-a-candidate"></a>Jelentkező felvétele

Ha készen áll egy jelölt felvételére, kövesse ezt az eljárást a jelölt alkalmazottá való átalakításához.

1. A jelölt űrlapon válassza a **Felvétel** l ehetőséget.

   ![Jelentkező felvétele](./media/hr-recruit-11-hire.png)

2. Az **Új dolgozó felvétele** képernyő **Részletek** csoportban töltse ki az összes mezőt.

   ![Új felvétel adatainak megadása](./media/hr-recruit-12-hire-new-worker.png)

3. A **Pozíció részletei** részben szükség szerint ellenőrizze és módosítsa az adatokat.

4. Az **Előkészítési ellenőrzőlisták** alatt válassza ki az alkalmazotthoz tartozó előkészítési ellenőrzőlistákat.

5. Válassza a **Folytatás** lehetőséget az alkalmazotti rekord létrehozásához.

   >[!NOTE]
   >A szervezet munkafolyamataitól függően a jelölt rekordja további jóváhagyási lépéseken is átmehet, mielőtt alkalmazotti rekorddá válna.

## <a name="decide-not-to-hire-a-candidate"></a>Úgy dönt, hogy nem vesz fel jelöltet

Ha úgy dönt, hogy nem vesz fel jelöltet, kövesse ezt az eljárást, hogy távolítsa el őket az ellenőrzési folyamatból. 

1. A jelölt űrlapon válassza a **Nincs felvétel** lehetőséget.

   ![Nem vesz fel jelentkezőt](./media/hr-recruit-13-do-not-hire.png)

2. Válasszon ki egy **Okkódot**, és adja meg a megjegyzéseket.

3. Válassza ki az **OK** lehetőséget.

## <a name="dismiss-a-candidate"></a>Jelölt elvetése

Szükség esetén a felvétel után elbocsáthat egy jelöltet. Előfordulhat például, hogy egy jelölt elutasítja az ajánlatot, vagy nem jelenik meg az első napon.

- A jelölt űrlapon válassza a **Jelölt elvetése** lehetőséget.

  ![Jelölt elutasítása](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Lásd még

[Common Data Service-virtuális entitások konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Munkaerő-szervezés](hr-personnel-departments-jobs-positions.md)<br>
[Feladat összetevőinek beállítása](hr-personnel-jobs.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]