---
title: Affordable Care Act-jelentések készítése a Juttatáskezelésben
description: Ez a témakör azt ismerteti, hogyan követheti a Juttatáskezelés funkcióval a 1095-B és az 1095-C űrlapon az ACA munkáltatói felhatalmazás keretén belül jelentett információkat.
author: andreabichsel
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a41195ea3b52a707ce9deae38f12eb90de2ff5aa
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805802"
---
# <a name="generate-aca-reports-in-benefits-management"></a>ACA-jelentések készítése a Juttatáskezelésben

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Juttatáskezelés funkcióval követheti a 1095-B és az 1095-C űrlapon az ACA munkáltatói felhatalmazás keretén belül jelentett információkat. A régi **Juttatások** munkaterületen történő ACA jelentéskészítési képességhez hasonlóan ez a funkció csak az Egyesült Államokban érvényes jogi személyekre vonatkozik.

A funkció használatához először be kell kapcsolnia a **Speciális juttatások kezelése** funkciót. A további tudnivalókat, többek között a juttatások kezelésével kapcsolatos fontos figyelmeztetéseket lásd: [Juttatáskezelés funkció engedélyezése vagy letiltása](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Az ACA-jelentéskészítés csak a **Juttatáskezelés** munkaterületről vagy a régi **Juttatások** munkaterületről használható, mindkettőből nem. Ha például a Juttatáskezelés szolgáltatásra vált, az ACA-jelentéskészítés csak a **Juttatáskezelés** munkaterületről érhető el, a régi **Juttatások** munkaterületről nem.
>
> Ha egy beléptetési év közepén vált a Juttatáskezelés beállításra, az egész évre vonatkozóan helyesen kell konfigurálnia az alkalmazotti adatokat a Juttatáskezelés eszközben. Ezzel a módszerrel biztosíthatja, hogy pontos jelentési adatokat kapjon az egész évre.

## <a name="getting-started"></a>Első lépések

Az adatoknak az 1095 űrlapok esetében történő nyomon követéséhez először létre kell hozni egy vagy több Affordable Care fedezeti csoportot. Ezek a csoportok a következő információkat jelzik:

- Az alkalmazottnak nyújtott fedezeti ajánlat
- Az alkalmazott részesedése a legkisebb költségalapú havi díjból, ha költség magasabb a szövetségi szegénységi küszöbnél
- A munkáltató által használt Safe Harbor, ha van ilyen

Az Affordable Care fedezeti csoportok segítségével több olyan alkalmazotti rekord adatait kezelheti, amelyekre ugyanazok a feltételek vonatkoznak. A csoportokat egyszerűen hozzárendelheti egy vagy több alkalmazotthoz.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Affordable Care fedezeti csoport létrehozása vagy szerkesztése

1. A **Juttatáskezelés** munkaterületen válassza az **Affordable Care fedezeti csoport** lehetőséget.

    ![Az Affordable Care fedezeti csoport kiválasztása](./media/hr-benefits-management-aca-coverage-group.png)

2. Válassza az **Új** lehetőséget, ha új Affordable Care fedezeti csoportot szeretne létrehozni vagy a **Szerkesztés** lehetőséget egy meglévő csoport módosításához.

    ![Új vagy Szerkesztés kiválasztása](./media/hr-benefits-management-aca-new.png)

3. Állítsa be a következő mezőket.

    | Mező | Leírás |
    |---|---|
    | Név | Adja meg a csoport nevét. |
    | Leírás | A csoport leírásának megadása. |
    | Jogosultságra vonatkozó ajánlat | Az alkalmazottaknak, házastársuknak vagy partnerüknek és eltartottaiknak nyújtott fedezet. |
    | Alkalmazott költségmegosztása | Az az összeg, amelyért az alkalmazott felelős. |
    | 4980H alkalmazható szakasza, Safe Harbor | A 4980H Safe Harbor vagy az átmeneti mentesség kódja. |
    | A terv kezdő hónapja | Válassza ki azt a naptári hónapot, amikor a juttatási terv éve elkezdődik. |
    | Csoport érvényességének kezdete | A rekord érvényességének első dátuma. |
    | Csoport érvényességi tartománya | A rekord érvényességének utolsó dátuma. Ha nincs lejárati dátum, akkor a **Soha** lehetőséget írja be. |

    ![Fedezeti csoport létrehozása](./media/hr-benefits-management-aca-new-group.png)

4. Válassza a **Mentés** lehetőséget.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Több alkalmazott hozzárendelése egy Affordable Care fedezeti csoporthoz

1. A **Juttatáskezelés** munkaterületen válassza az **Affordable Care fedezeti csoport** lehetőséget.
2. Válassza ki azt a csoportot, amelyhez alkalmazottakat szeretne rendelni.
3. Válassza a **Tömeges hozzárendelés** lehetőséget.

    ![A Tömeges hozzárendelés lehetőség kiválasztása](./media/hr-benefits-management-aca-mass-assignment.png)

4. Válassza ki az alkalmazottakat a listából, majd válassza a **Hozzárendelés** lehetőséget.

    ![Kiválasztott alkalmazottak hozzárendelése egy csoporthoz](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Fedezeti lehetőségek több változatának karbantartása

A fedezeti csoportok több változatának karbantartása lehetséges. Ha valami változás történik a szervezetben vagy a felkínált juttatásokban, akkor a csoport információit naprakészen tarthatja anélkül, hogy új csoportot kell létrehoznia és alkalmazottakat kellene hozzárendelnie.

Az Affordable Care fedezeti csoportok létrehozása után tömegesen rendelheti hozzájuk az alkalmazottakat. Az alkalmazottakat egyesével is hozzárendelheti a csoportokhoz, és jelezheti, hogy az ACA-adatokat nyomon követhetik-e és lejelentik-e.

Ha nem kell egy alkalmazott ACA-adatait nyomon követnie és jelentenie, a **Jogosultság bejelentése** lehetőséget **Nem** értékre állíthatja. Előfordulhat például, hogy olyan részmunkaidős alkalmazottak is vannak, akiknek nincs szükségük az ACA-jelentéskészítésre.

### <a name="override-default-values-for-an-employee"></a>Alkalmazott alapértelmezett értékeinek felülbírálása

Az Affordable Care fedezeti csoporthoz hozzárendelt alkalmazottak esetében a következő beállításokat módosíthatja az olyan hónapokra, amelyekben eltérő értékekre van szükség:

- Jogosultságra vonatkozó ajánlat
- Alkalmazott költségmegosztása
- 4980H alkalmazható szakasza, Safe Harbor

> [!NOTE]
> A 2020-as ACA-jelentésekhez az 1095-C űrlapon a munkahelyi és az otthoni irányítószámot is le kell jelenteni. A program az aktuális aktív helyek alapján automatikusan kitölti az értékeket. Ha bármelyik hely más volt az év bármely részében, felül kell bírálnia az értéket. Az 1095-C jelentés **Irányítószám** mezője (17. sor) csak akkor van kitöltve, ha a **Jogosultságra vonatkozó ajánlat** kódja **1L** és **1Q** közötti értékeket tartalmaz az alábbiak szerint:
>
> - **1L, 1M vagy 1N:** az elsődleges lakóhely irányítószáma
> - **1O, 1P, 1Q:** az elsődleges munkahely irányítószáma

A következő lépésekkel kivételeket adhat meg egy Affordable Care fedezeti csoport bármely értékére.

1. A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások**, majd a **Dolgozók** elemet.
2. A listából válassza ki az alkalmazottat.
3. A **Foglalkoztatás** lap **További információk** szakaszában válassza az **Affordable Care fedezet** lehetőséget.

    ![Egyetlen alkalmazott beállításainak módosítása](./media/hr-benefits-management-aca-change-single-employee.png)

4. Válassza ki a **Szerkesztés** opciót.
5. Minden, változtatást igénylő hónap esetén jelölje be az **Alapértelmezett érték felülbírálása** jelölőnégyzetet, majd szükség szerint módosítsa a többi értéket.

    ![Alapértelmezett értékek felülbírálása](./media/hr-benefits-management-aca-override-default.png)

6. Válassza a **Mentés** lehetőséget.

## <a name="report-health-care-coverage"></a>Egészségügyi fedezeti jelentés

Nyomon kell követni a teljes munkaidős és részmunkaidős alkalmazottaknak a munkáltató által biztosított, a munkavállaló által fizetett ellátását. Az összes alkalmazottat és eltartottjaikat meg kell adni annak a hónapnak az 1095-C jelentésében, amelyben a csomag vonatkozik rájuk.

Azt, hogy a juttatácsomagot jelenteni kell-e, kövesse a következő lépéseket.

1. A **Juttatáskezelés** munkaterületen válassza a **Juttatási tervek** elemet.
2. Válassza ki a jelenteni kívánt juttatási tervet.
3. Válassza ki a **Szerkesztés** opciót.
4. Állítsa a **Jelentve az Affordable Care Act értelmében** lehetőséget **Igen** értékre.

    ![Egészségügyi fedezeti jelentés](./media/hr-benefits-management-aca-report-coverage.png)

5. Válassza a **Mentés** lehetőséget.

Ha az alkalmazott egy eltartottra vonatkozóan egészségügyi fedezetet választ, az eltartott fedezeti időszakát az eltartott beléptetésének vagy eltávolításának dátuma határozza meg. Az eltartottak fedezeti dátumának számítása automatikusan azon az időszakon alapul, amikor az eltartott jogosultságokkal rendelkezett és aktív volt a csomagban a beléptetési év során.

## <a name="generate-1095-b-and-1095-c-forms"></a>1095-B és 1095-C űrlapok létrehozása

Lehetőség van az ACA 1095-B és 1095-C űrlapok létrehozására és a továbbításukra az összes alkalmazottnak. Elektronikusan is generálhat 1095-C űrlapot és a megfelelő 1094-C benyújtandó fájlokat az IRS (Internal Revenue Service) számára.

1. A **Juttatáskezelés** munkaterületen válassza az **ACA 1095-B űrlap** vagy az **ACA 1095-C űrlap** lehetőséget.
2. Szükség szerint módosítsa a paramétereket, majd válassza az **OK** gombot.

    > [!NOTE]
    > Ha több mint 500 alkalmazottnak nyomtat 1095-C űrlapot, egynél több PDF-fájlt fog kapni. Javasoljuk, hogy a **Dokumentumkezelés paraméterei** lapon a **Maximális fájlméret megabájtban** mező értékét **150**-re növelje. (Az oldal gyors megnyitásához használhatja a navigációs sáv keresőmezőjét.)
    >
    > ![A maximális fájlméret módosítása](./media/hr-benefits-management-aca-maximum-file-size.png)

3. A jelentések állapotának ellenőrzésére és megtekintésére használja a navigációs sáv keresőmezőjét az **Elektronikus jelentéskészítési feladatok** oldal megnyitásához.

    ![Az Elektronikus jelentéskészítési feladatok oldal keresése](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Válassza ki a megtekinteni kívánt jelentést, majd válassza a **Fájlok megjelenítése** lehetőséget.

    ![Fájlok megjelenítése](./media/hr-benefits-management-aca-show-files.png)

5. Válassza ki a **Megnyitás** lehetőséget.

    ![Fájl megnyitása](./media/hr-benefits-management-aca-open-file.png)

6. Nyissa meg az irányítószámot a böngésző ablakának alján látható értesítési sávról, majd válassza ki a jelentést. Megtekintheti vagy kinyomtathatja a PDF-fájlt.

    ![Minta: 1095-C űrlap](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>ACA-fedezeti információk megtekintése

A **Dolgozói Affordable Care jogosultság** oldal a következő adatokat jeleníti meg:

- Az egyes fedezeti csoportokhoz hozzárendelt alkalmazottak
- Azok az alkalmazottak, akiknek nem kell szerepelniük a jelentésben
- Nem hozzárendelt alkalmazottak

Az adatok megtekintéséhez kövesse az alábbi lépéseket.

1. A **Juttatáskezelés** munkaterületen válassza az **Dolgozói Affordable Care fedezeti jogosultság** lehetőséget.
2. A **Csoport neve** mezőben válasszon ki egy csoportot.

    ![ACA-fedezet megtekintése](./media/hr-benefits-management-aca-view-coverage.png)

Ha az Affordable Care fedezeti csoport bármely alapértelmezett értékét felülírták, egy csillag jelenik meg a módosított érték mellett. Ha az értékek a tizenkét hónap mindegyikében megegyeznek, és nem bírálták felül őket, az értéket a rendszer a **Mind a 12 hónap** oszlopba nyomtatja.

Azok az alkalmazottak is megtekinthetők, akik az ACA szerint nem bejelentendők, és akik esetében nincs szükség 1095-C űrlapra. A **Szűrés alapja:** mezőben válassza **Az ACA szerint nem bejelentendő** lehetőséget.

Megtekintheti azokat az alkalmazottakat, akik nincsenek csoporthoz rendelve, vagy akik lejárt csoporthoz vannak hozzárendelve. A **Szűrés alapja:** mezőben válassza a **Nem hozzárendelt vagy lejárt csoport** lehetőséget.

### <a name="export-to-excel"></a>Exportálás Excel-fájlba

Ha a listák bármelyikét exportálni szeretné Microsoft Excel alkalmazásba, kövesse ezeket a lépéseket.

1. Válassza a **Megnyitás Microsoft Office-ban** gombot.
2. Válassza a **HCM Human Resources ideiglenes tábla belső használatra** lehetőséget.
3. Válassza a **Letöltés** lehetőséget.

### <a name="view-aca-reportable-dependents"></a>ACA szerint bejelentendő eltartottak megtekintése

Ha kötelező jelentenie az eltartott személyeket, mert munkáltatóként a munkavállaló által fizetett egészségügyi biztosítást nyújt, lehetőség van a juttatási csomagok által lefedett, **ACA szerint bejelentendő** megjelölésű eltartottak megtekintésére. A Művelet ablaktáblán válassza **Az eltartott fedezetének megtekintése** lehetőséget.

![Eltartott fedezetének megtekintése](./media/hr-benefits-management-aca-view-dependent-coverage.png)

Megjelennek az alkalmazott eltartottakkal kapcsolatos fedezeti adatai.

![Függő fél jogosultsága](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> Az oldalon csak az **ACA szerint bejelentendő** típusú megjelölt juttatási tervek jelennek meg.


[!INCLUDE[footer-include](../includes/footer-banner.md)]