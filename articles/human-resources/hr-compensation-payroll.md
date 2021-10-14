---
title: Kifizetésre kész
description: Ez a témakör azt mutatja be, hogyan lehet az alkalmazottat fizetésre készként megjelölni a Dynamics 365 Human Resources alkalmazásban.
author: marcelbf
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b9536a6e12b4037458910b7a2d27450ac175fd9d
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559607"
---
# <a name="ready-to-pay"></a>Kifizetésre kész

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> Ha egy alkalmazottat fizetésre készként szeretne megjelölni, először engedélyeznie kell az **(Előzetes verzió) bérszámfejtés integrációja** funkciót a funkciókezelésben. Az előzetes funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.

Ez a funkció lehetővé teszi az emberi erőforrásokkal dolgozó szakemberek számára, hogy megértsék, mely alkalmazottak állnak készen bérlista-feldolgozásra, és melyek esetében szükséges művelet, mielőtt átkerülnének egy külső bérszámfejtés-szolgáltatónak.

## <a name="mark-employee-as-ready-to-pay"></a>Alkalmazott megjelölése fizetésre készként

Az alkalmazotti adatok összegyűjtése és ellenőrzése sok időt emészthet fel, és hibák is történhetnek. Az emberi erőforrásokkal dolgozó szakemberek számára lehetővé teszi az alkalmazotti adatok áttekintését és egyszerű frissítését, így a Dynamics 365 Human Resources csökkentheti a feldolgozásra kész bérlista elkészítéséhez szükséges időt.

Alkalmazott megjelölése fizetésre készként:

1. Nyissa meg a **Kompenzációkezelés** lehetőséget. A munkaterületen két csempe található: 
    - **Kifizetésre kész alkalmazottak**
    - **Azok az alkalmazottak, akik nem állnak készen a fizetésre**
    ![Kompenzációkezelési munkaterület.](./media/hr-ready-to-pay-1-workspace.png)

2. Válassza ki az **Azok az alkalmazottak, akik nem állnak készen a fizetésre** csempét.

3. Válassza ki az ellenőrizni kívánt alkalmazottakat. A **Bérlista lap** **Fizetésre kész** csoportjában válassza az **Ellenőrzés** lehetőséget.
    ![Alkalmazottak ellenőrzése.](./media/hr-ready-to-pay-2-validate.png)

4. Az eredmények áttekintéséhez a **Bérlista lap** **Fizetésre kész** csoportjában válassza az **Eredmények** lehetőséget.

## <a name="validation"></a>Ellenőrzés

Mielőtt fizetésre készként jelöl egy alkalmazottat, az alkalmazott profilja ellenőrizve lesz teljesség szempontjából.

![Eredmények ellenőrzése.](./media/hr-ready-to-pay-3-results.png)

| Ellenőrzés | Részletek |
| --- | --- |
| **Cím célparamétere** | Megerősíti, hogy ki van-e választva a **Bérlistacímek céljainak használata** paraméter. |
| **Bérlista címe** | Megerősíti, hogy a dolgozói profilban van-e legalább egy cím **Bérlista szerinti lakóhely** vagy **Bérlista szerinti munkavégzési hely** céllal, és célonként csak egy cím van. |
| **Alkalmazás** | Megerősíti, hogy a dolgozónak van-e legalább egy munkaviszonya (jelenlegi, előző vagy jövőbeli). |
| **Azonosítószám** | Megerősíti, hogy az **Azonosítótípusok használata a bérlista feldolgozásában** mező értéke **Igen**-e a **Human Resources paranéterek** oldalon és hogy a paraméterben megadott azonosítási típus ki van töltve a dolgozói profilban. |
| **Keresztnév és vezetéknév** | Megerősíti, hogy a **Név** és a **Vezetéknév** mező ki van-e töltve.|
| **Sorszám** | Megerősíti, hogy van-e hozzárendelve beosztás a dolgozóhoz. |
| **Születési dátum** | Megerősíti, hogy a **Születésnapok** mező ki van-e töltve. |
| **Kompenzáció** | Megerősíti, hogy a dolgozó fix kompenzációs konstrukcióban van. |

Ha valamelyik ellenőrzés sikertelen, akkor az alkalmazott nem jelölhető meg fizetésre készként.

Ha a **Fizetésre kész** mező értéke **Nem**, az azt jelzi, hogy végre kell hajtania egy műveletet, hogy a dolgozói profil teljes legyen. Ezzel nem lehet leállítani az adatentitások közötti adatelérést. 

## <a name="process-automation"></a>Folyamatok automatizálása

A [Folyamatautomatizálás](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation) funkcióval automatizálhatja az összes alkalmazott ellenőrzését. A **Kompenzációkezelés** munkaterületen lépjen a **Hivatkozások** \> **Paraméterek** \> **Folyamatautomatizálás** menüpontra.

## <a name="see-also"></a>Lásd még

[Bérlista-integrációs API bemutatása](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
