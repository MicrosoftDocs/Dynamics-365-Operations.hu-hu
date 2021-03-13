---
title: Eszközkezelés mobil munkaterület használata
description: Ez a témakör az Eszközkezelési mobil munkaterületével kapcsolatban tartalmaz tájékoztatást.
author: josaw1
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: afda807714f14efb1cbab4ecfdd273aac52f4558
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033152"
---
# <a name="use-the-asset-management-mobile-workspace"></a>Eszközkezelés mobil munkaterület használata

[!include [banner](../../includes/banner.md)]

Ez a témakör az **Eszközkezelés** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. Ez a munkaterület lehetővé teszi a felhasználók számára a karbantartási kérelmek és munkarendelések megtekintését és létrehozását. A felhasználók naptár vagy lista nézetben is megtekinthetik a hozzárendelt munkarendelési feladatokat. A tárgyi eszközök és a funkcionális helyszínek is megtekinthetők és kereshetők.

## <a name="overview"></a>Áttekintés

Az Eszközkezelés az eszközök és a munkarendelés-feladatok a Dynamics 365 Supply Chain Management rendszerben történő kezelésére szolgáló speciális modul. A **Eszközkezelés** mobil munkaterületen a felhasználók gyorsan megtekinthetik a hozzájuk rendelt munkarendelési feladatokat az általluk választott mobileszközön. A felhasználók létrehozhatnak és kezelhetnek karbantartási kérelmeket, frissíthetik az életciklus-állapotot, és megtekinthetik a tárgyi eszközök és a munkavégzési helyszínek adatait mobileszköz használatával.

Az **Eszközkezelés** mobil munkaterület használatával a felhasználók a következő feladatokat hajthatják végre:

- Karbantartási kérések létrehozása, megtekintése és szerkesztése, fénykép készítése vagy meglévő kép csatolása a karbantartási kéréshez, illetve a karbantartási kérelem életciklus-állapotának módosítása. 
- Munkarendelések létrehozása, megtekintése és szerkesztése, fénykép készítése vagy meglévő kép csatolása a munkarendeléshez, munkarendelés életciklus-állapotának módosítása, munkarendelés feladatok megtekintése.
- A hozzárendelt munkarendelési feladatok megtekintése naptár nézetben.
- Létrehozhat, megtekinthet és szerkeszthet munkarendelési feladatot, frissíthet tárgyieszköz-számlálókat, megtekinthet, szerkeszthet munkarendelési feladatokhoz tartozó jegyezeteket, megtekintheti és szerkesztheti a munkarendelési feladatokhoz szükséges eszközöket.
- Adott eszköz vagy munkavégzési helyszín megtekintése vagy keresése.

## <a name="prerequisites"></a>Előfeltételek

Az **Eszközkezelés** mobil munkaterület használata előtt a rendszergazdának be kell állítania a szükséges felhasználói és dolgozói fiókokat, és közzé kell tennie a munkaterületet. A további tudnivalókat lásd [Az Eszközkezelés mobil munkaterület beállítása](set-up-asset-management-mobile.md).

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése

Töltse le és telepítse a Dynamics 365 for Unified Operations mobilalkalmazást:

- [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
- [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1. Indítsa el az alkalmazást a mobileszközén.

1. Adja meg a Dynamics 365 URL-címét.

1. Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.

1. A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

    ![Válasszon munkaterületet](media/am-mobile-01.png "Válasszon munkaterületet")

## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>A hozzárendelt munkarendelési feladatok megtekintése naptár nézetben.

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza ki a **Saját munkarendelési feladatok naptára** elemet.

1. Válassza ki azt a dátumot, amelyhez meg szeretné tekinteni a munkarendelési feladatokat. A listában megjelenik az eszköz azonosítója és a munkavégzési helyszín azonosítója mindegyik munkarendelési feladathoz.

1. Válassza ki a megfelelő munkarendelést a listán a feladatok adatainak megtekintéséhez: Eszköz és munkavégzési helyszín adatait, valamint egyéb navigációs hivatkozások magtekintése **Mellékletek**, **Ellenőrzőlisták**, **Eszközök**, **Eszközszámlálók**, **Jegyzetek**, **Naplók**.

    ![A hozzárendelt munkarendelési feladatok megtekintése naptár nézetben.](media/am-mobile-02.png "A hozzárendelt munkarendelési feladatok megtekintése naptár nézetben.")

## <a name="create-a-work-order-job"></a>Munkarendelés-feladat létrehozása

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási munkarendelés** lehetőséget.

1. Válassza ki a munkarendelést, amelyhez az új munkarendelési feladatot szeretné létrehozni.

1. Válassza a **Sor hozzáadása** gombot.

1. Válassza ki az **Eszközt**, amelyhez az új munkarendelési feladatot szeretné létrehozni.

1. Válassza ki a **Karbantartás feladat típust**, a **Karbantartó feladattípus változatát** és a **Szakmát**.

1. Válassza a **Kész** lehetőséget.

    ![A Sor hozzáadása képernyő](media/am-mobile-03.png "A Sor hozzáadása képernyő")


## <a name="add-attachment-to-a-work-order-job"></a>Melléklet hozzáadása munkarendelési feladathoz

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási munkarendelés** lehetőséget.

1. Válassza a munkarendelés > munkarendelési feladat elemet, amelyhez mellékletet szeretne adni.
    - Azt is megteheti, hogy a kezdőlapon a **Saját munkarendelési feladatok naptára** vagy **Saját munkarendelési feladatok listája** elemet választja a **Munkarendelési feladat adatai** oldal megnyitásához.

1. Válassza ki a **Mellékleteket** a **Munkarendelési feladat részletei** oldalon.

1. A munkarendelési feladaton szereplő meglévő mellékleteket fogja látni. Válassza a **Melléklet hozzáadása** lehetőséget.

1. Adja meg a melléklet **Nevét** és **Megjegyzéseit**.

1. Válassza a **Kép kiválasztása** lehetőséget, ha ki szeretné választani a fényképet a mobil galériából, vagy fényképet készíthet a **Fénykép készítése** lehetőséggel.

1. Válassza a **Kész** lehetőséget.

    ![Munkarendelési feladat mellékletének megtekintése és hozzáadása](media/am-mobile-04.png "Munkarendelési feladat mellékletének megtekintése és hozzáadása")

## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Karbantartási ellenőrzőlista megtekintése egy munkarendelési feladaton

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási munkarendelés** lehetőséget.

1. Válassza ki a munkarendelés > munkarendelési feladatot, amelyhez az ellenőrzőlistákat meg szeretné tekinteni.
    - Azt is megteheti, hogy a kezdőlapon a **Saját munkarendelési feladatok naptára** vagy **Saját munkarendelési feladatok listája** elemet választja a **munkarendelési feladat adatai** oldal megnyitásához.

1. Válassza ki az **Ellenőrzőlistákat** a **Munkarendelési feladat részletei** oldalon.

1. A munkarendelési feladathoz kapcsolódó ellenőrzőlista-sorok listája jelenik meg. Jelöljön ki egy ellenőrzőlista-sort az **Utasítások** megtekintéséhez és a **Megjegyzések** hozzáadásához.

1. Válassza ki a Vissza gombot (**<**) az előző oldalhoz való visszatéréshez.

    ![Karbantartási ellenőrző lista és soradatok](media/am-mobile-05.png "Karbantartási ellenőrző lista és soradatok")

## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>A munkarendelési feladathoz tartozó eszközszámlálók megtekintése és frissítése

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási munkarendelés** lehetőséget.

1. Válassza ki a munkarendelés > munkarendelési feladatot, amelyhez az eszközszámlálókat meg szeretné tekinteni.
    - Azt is megteheti, hogy a kezdőlapon a **Saját munkarendelési feladatok naptára** vagy **Saját munkarendelési feladatok listája** elemet választja a **munkarendelési feladat adatai** oldal megnyitásához.

1. Válassza ki az **Eszközszámlálók** elemet a **Munkarendelési feladat részletei** oldalon.

1. A munkarendelési feladathoz kapcsolódó eszközszámlálók listája jelenik meg. Egy számláló értékének frissítéséhez jelölje ki az eszközszámláló során látható ceruzaikont.

1. Írjon be egy új számlálóértéket, majd válassza a **Kész** lehetőséget.

    ![Eszközszámlálók megtekintése és frissítése](media/am-mobile-06.png "Eszközszámlálók megtekintése és frissítése")

## <a name="register-consumption-on-a-work-order-job"></a>Felhasználás regisztrálása egy munkarendelési feladathoz

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási munkarendelés** lehetőséget.

1. Válassza ki a munkarendelés > munkarendelési feladatot, amelyhez felhasználást szeretne regisztrálni.
    - Azt is megteheti, hogy a kezdőlapon a **Saját munkarendelési feladatok naptára** vagy **Saját munkarendelési feladatok listája** elemet választja a **munkarendelési feladat adatai** oldal megnyitásához.

1. Válassza ki a **Naplók** elemet a **Munkarendelési feladat részletei** oldalon.

1. A munkaidő- nyilvántartások létrehozásához válassza az **Órák hozzáadása** lehetőséget.
    1. Válassza ki a **Kategóriát** a keresésből.
    1. Írja be az **Órák** mezőbe a munkarendelési feladatra fordított munkaórák számát.
    1. Válassza ki a megfelelő **Sortulajdonságot**.
    1. Válassza a **Kész** lehetőséget.

1. Válassza a **Cikkek hozzáadása** lehetőséget cikkregisztrációk létrehozásához.
    1. Válassza ki a **Cikkszámot** a keresésből.
    1. Válasszon **Helyszínt** a keresésből.
    1. Adja meg a fogyasztott cikkek **Mennyiségét**.
    1. Válassza a **Kész** lehetőséget.

1. A költségnyilvántartások létrehozásához válassza a **Költség hozzáadása** lehetőséget.
    1. Válassza ki a **Kategóriát** a keresésből.
    1. Mennyiség megadása a költségregisztrációhoz.
    1. Válassza ki az **Értékesítési pénznemet** a kereséséből.
    1. **Önköltségi ár** megadása a költségregisztrációhoz.
    1. Válassza a **Kész** lehetőséget.

    ![Munkarendelési napló frissítése](media/am-mobile-07.png "Munkarendelési napló frissítése")

## <a name="update-lifecycle-state-on-a-work-order"></a>Egy munkarendelés életciklus-állapotának frissítése.

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási munkarendelés** lehetőséget.

1. Válassza ki a munkarendelést, amelyhez az életciklus-állapotot frissíteni szeretné.

1. Válassza a képernyő alján látható **Állapot frissítése** gombot.

1. Válassza ki az új életciklus-állapotot a listáról.

1. Válassza a **Kész** lehetőséget.

    ![Egy munkarendelés életciklus-állapotának frissítése.](media/am-mobile-08.png "Egy munkarendelés életciklus-állapotának frissítése.")

## <a name="create-a-maintenance-request"></a>Új karbantartási kérés létrehozása

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási kérés** elemet.

1. Válassza ki a képernyő alsó részén található **Műveletek** elemet, és válassza a **Karbantartási kérelem létrehozása** lehetőséget.

1. Ha az **Eszközkezelés** alatt a számsorozat engedélyezve van a karbantartási kérésekhez, akkor a **Karbantartási kérés** mező el van rejtve, mert a program automatikusan kitölti. Ha látható a **Karbantartási kérés** mező, adja meg a karbantartási kérés azonosítóját.

1. Válassza ki a **Karbantartási kérés típusát**.

1. Írja be a karbantartási kérés nevét és a **Leírását**.

1. Válassza ki azt az **Eszközt** amelyhez a kérést létre szeretné hozni.

1. Válassza ki a karbantartási kérelem **Szolgáltatási szintjét**.

1. Válassza a **Kész** lehetőséget.

    ![Új karbantartási kérés létrehozása](media/am-mobile-09.png "Új karbantartási kérés létrehozása")

## <a name="add-attachment-to-a-maintenance-request"></a>Melléklet hozzáadása a karbantartási kéréshez

1. A mobileszközön nyissa meg a **Eszközkezelés** munkaterület.

1. Válassza a **Minden karbantartási kérés** elemet.

1. Válassza ki azt a karbantartási kérést, amelyhez mellékletet kíván hozzáadni.

1. Válassza a képernyő alján található **Mellékletek** lehetőséget.

1. Válassza a **Mellékletek hozzáadása** lehetőséget.

1. Adja meg a melléklet **Nevét** és **Megjegyzéseit**.

1. Válassza a **Kép kiválasztása** lehetőséget, ha ki szeretné választani a fényképet a mobil galériából, vagy fényképet készíthet a **Fénykép készítése** lehetőséggel.

1. Válassza a **Kész** lehetőséget.

    ![Melléklet hozzáadása a karbantartási kéréshez](media/am-mobile-10.png "Melléklet hozzáadása a karbantartási kéréshez")
