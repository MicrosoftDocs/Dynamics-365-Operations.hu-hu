---
title: A Human Resources paramétereinek konfigurálása
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a vállalatspecifikus paramétereket a következőben:Dynamics 365 Human Resources
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd645dcc79672e7f69afe47b803b90a04c22305d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856280"
---
# <a name="configure-human-resources-parameters"></a>A Human Resources paramétereinek konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Human Resources egyes paramétereinek beállításait közösen használják a vállalatok, azonban vannak olyan paraméter-beállítások, amelyek vállalatonként különböznek. Ez a cikk bemutatja a vállalatspecifikus emberierőforrás-paraméterek beállítását.

A Human Resources paraméterek beállítása két oldalon történik. A vállalatok között megosztott paraméterekhez az **Emberi erőforrások megosztott paraméterei** oldal használatos. A vállalatspecifikus (más szóval, a beállítások csak egy vállalatra vonatkoznak) paraméterekhez az **Emberierőforrás-paraméterek** oldal használatos.

![Lépjen a Humar Resources paramétereihez.](./media/hr-employee-self-service-human-resources-parameters.png)

Az **Emberierőforrás-paraméterek** oldalon a beállítások 6 lapra vannak szétosztva.

- **Általános**
- **Toborzás** (ez a lap nem része a Dynamics 365 Human Resources rendszernek)
- **Kompenzáció**
- **Számsorozatok**
- **FMLA**
- **Alkalmazotti önkiszolgáló rendszer**
- **Vezetői önkiszolgáló rendszer**
- **Juttatáskezelés**
- **Szabadság és távollét**
- **Fizetési módok**

Minden lap egyetlen vállalatra vonatkozóan tartalmaz információkat.

## <a name="general"></a>Általános

Az **Általános** lapon található beállítások határozzák meg a távolléttel, sérüléssel, betegséggel és új munkaerővel kapcsolatos információk megjelenését. Az ezen a lapon található beállítások meghatároznak néhány alapértelmezett tételt is, amelyek a munkavégzés során jelennek meg. Ez a lap a következőt teszi lehetővé:

- A nyitott távolléti tranzakcióra alkalmazni kívánt szín megadása.
- A jelentésekhez használt stíluslap megadása.
- Tanfolyamok és távolléti regisztrációk közötti integráció engedélyezése.
- Az integráció szabályozásához használt távolléti kód kiválasztása.
- Adja meg, mennyi ideig kell megőrizni a sérüléssel és betegséggel kapcsolatos eseményeket.
- Adja meg az új dolgozó felvétele esetén megjelenő alapértelmezett azonosítószámot.
- Adja meg a szolgáltatási évek kiszámításához használt dátumot. 

![Általános fül.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Munkaerő-felvétel

A **Toborzás** lapon megadott beállítások határozzák meg azokat a dokumentumtípusokat, amelyek a pályázóknak automatikusan küldött levelezéshez használatosak. Jelezheti a kéretlen pályázatokhoz használt toborzási projektet is.

A Toborzási projekt korosítási **beállításában** **·** **meghatározott időszak határozza meg, hogy mely toborzási projektek szerepelnek a Toborzáskezelés munkaterület Korosítási projektek csempe** területén. A jelentkezési **határidő** **figyelmeztetéséhez** megadott időszak használatával lehet látni a Toborzás munkaterületen a jelentkezési határidő felé közeledő toborzási projekteket.

A toborzásról a [Jelöltek toborzása](hr-personnel-recruit.md) oldalon található részletes tájékoztatás.

## <a name="compensation"></a>Kompenzáció

A Dynamics 365 Pénzügy programban a Kompenzáció lap beállításai határozzák meg, **hogy** a felhasználóknak meg kell-e erősíteniük, hogy a fix vagy változó kompenzációs konstrukciók adatait menteni kívánják. Ha bejelöli a **Mentésellenőrzés engedélyezése** lehetőséget, amikor a felhasználók bezárnak egy kompenzációval kapcsolatos oldalt, megjelenik egy üzenet, amely megkérdezi, hogy akarják-e menteni a bejegyzést. A Kompenzációkezelés egyes oldalai nem teszik lehetővé adatok törlését felhasználók számára. Az által, hogy megerősítést kér a felhasználóktól az adatok mentésével kapcsolatban, képes lehet korlátozni az elmentett, de a későbbiekben nem törölhető adatok mennyiségét. Ha törli a **Mentésellenőrzés engedélyezése** jelölőnégyzetet, a bejegyzések mentése azonnal megtörténik, esetleg még az előtt, hogy a felhasználó készen állna. Ha Teljesítménymenedzsmentet alkalmaz, akkor a **Kompenzáció** lapon kiválaszthat egy osztályozási modellt, amelyet a teljesítmény osztályozáskor az alkalmazott kompenzációs konstrukciókhoz rendelt modell helyett használhat.

A Human Resources alkalmazásban a **Kompenzáció** lapon kiválaszthatja, hogy korlátozza-e a hozzáférést a kompenzációs konstrukciókhoz, és beállít-e alapértelmezett pénznemet.

A kompenzációval kapcsolatos további információkért lásd: [Kompenzációs konstrukciók áttekintése](hr-compensation-overview.md).

![Kompenzáció lap.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Számsorozatok

A **Számsorozat** lap beállításai határozzák meg, hogy milyen sorrendben rendeljenek automatikusan értékeket a Human Resources alkalmazásban található cikkekhez, például:

- Pályázatok
- Távollét-regisztrációk
- Kompenzációs folyamat eredményei
- Esetszámok
- Tanfolyamok
- Tanfolyami napirendek

A számsorozat-hivatkozások és -kódok karbantartásához használja a **Számsorozatok** listaoldalt (válassza a **Szervezet felügyelete > Számsorozatok > Számsorozatok** lehetőséget).

További információkért lásd: [Számsorozatok áttekintése](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> A ledolgozott órák száma nem haladhatja meg az 1250-et, és a munkaviszony nem lehet hosszabb 12 hónapnál. Ezek a maximális értékek az Egyesült Államok szövetségi törvényének megfelelőek.

![Számsorozatok lap.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

Az FMLA lapon lehet beállítani az FMLA-alkalmazhatósági követelmények és az FMLA-jogosultsági órák beállítását. További tájékoztatás: [Szabadság és távolléti paraméterek konfigurálása](hr-leave-and-absence-parameters.md).

![FMLA lap.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer

Az Alkalmazott – önkiszolgáló **szolgáltatás** lapon megadott beállítások befolyásolják, **hogy** hogyan jelenik meg az alkalmazotti önkiszolgáló rendszer az alkalmazottaknak. Ezen a lapon a következő feladatokat lehet elvégezni:

- Adja meg az Alkalmazott önkiszolgáló **munkaterületének** nevét.
- Adja meg, hogy a vezető mely adatokat adhatja meg az alkalmazottak számára
- Hasznos hivatkozások hozzáadása az alkalmazottak számára
- Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek hozzáadása és szerkesztése tekintetében. A további tudnivalókat lásd: [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md).

Az alkalmazotti önkiszolgáló **rendszer** beállításának további tudnivalókat lásd [az Alkalmazott és vezető önkiszolgáló rendszer áttekintésében](hr-employee-manager-self-service-overview.md).

![Alkalmazotti önkiszolgáló rendszer lap.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Vezetői önkiszolgáló rendszer

A Vezetői önkiszolgáló **lapon megadott beállítások** befolyásolják, hogy milyen vezetők látnak a **vezető önkiszolgáló rendszerében**. Ezen a lapon a következő beállításokat lehet beállítani:

- A lejáró rekordok tartománya
- A vezetők által a lejáró rekordokban látható információk
- Azt jelzi, hogy a vezetők megtekinthetnek-e nyitott pozíciókat a kiterjesztett jelentésekhez
- A kilépő dolgozók nézete
- Hasznos hivatkozások a vezetőknek

A vezetői önkiszolgáló **rendszer beállításának további tudnivalókat** lásd [az Alkalmazott és vezető önkiszolgáló rendszer áttekintésében](hr-employee-manager-self-service-overview.md).

![Vezetői önkiszolgáló rendszer lap.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Juttatáskezelés

A Juttatások **kezelése** lapon beállíthatja a Juttatások kezelése e-mailben megadott beállításait. A juttatások kezelésének [beállítását és használatát lásd a Juttatások kezelése témakörben](hr-benefits-management-overview.md).

![Juttatáskezelés lap.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Szabadság és távollét

A Szabadság és távollét beállításával és használatával kapcsolatos további tudnivalókat lásd: [Szabadság és a távollét áttekintése](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Fizetési módok

A **Fizetési módok** lapon kiválaszthatja a szervezet által támogatott fizetési módokat. A kompenzáció konfigurálásával kapcsolatos további információkért lásd: [Kompenzációs konstrukciók áttekintése](hr-compensation-overview.md).

![Fizetési módok lap.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
