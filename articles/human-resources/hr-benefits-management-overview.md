---
title: Juttatáskezelés áttekintése
description: Ez a témakör a Dynamics 365 Human Resources rendszerben található Juttatások kezelése funkció áttekintését nyújtja.
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4cbe79a7e64477eaaefd2a5df2ca2ee34ef29f26
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982765"
---
# <a name="benefits-management-overview"></a>Juttatáskezelés áttekintése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A versenyképesség megőrzéséhez juttatások széles választékát kell nyújtania, hogy felkeltse a legjobb alkalmazottak figyelmét, és meg is tudja tartani őket. A szokásos juttatások, például az orvosi és a fogászati biztosítás mellett kiterjesztett szolgáltatásokat is kínálhat, például bevezetési támogatást, rekreációs programokat és ruházati pótlékokat. A juttatások kezelése a Microsoft Dynamics 365 Human Resources rendszerben rugalmas megoldást kínál, amely a juttatási lehetőségek széles skáláját támogatja. A Human Resources szolgáltatás tartalmaz egy egyszerűen használható alkalmazotti felületet is, amelyen bemutathatja az ajánlatait.

- A bővített juttatási konstrukciók lehetővé teszik egyedi juttatási konstrukciók létrehozását és kezelését, valamint összetett juttatásmérték-táblázatok és beágyazott szintek támogatását. Az alkalmazotti élmény javításához könnyen készíthet juttatási programokat, csomagokat és automatikus igénylési szabályokat.
- A rugalmas jóváírási programok lehetővé teszik az arányosítást a nyugdíjazás és az egyéb élettartam-események támogatásához.
- A számos jogosultsági szabály biztosítja, hogy a megfelelő juttatásokat tudja szolgáltatni a megfelelő alkalmazottak számára.
- A juttatások online regisztrálása könnyen használható megoldást nyújt az alkalmazottaknak.
- A minősített életesemények feldolgozása támogatja a jövőbeli életeseményeket.

Ha szeretne hozzáférni a bemutató adatokhoz, újra kell telepítenie a tesztkörnyezetét.

> [!NOTE]
> Mostantól testreszabhatja a Juttatások kezelése oldalakat. A fedezeti díjakkal kapcsolatos egyéni mezők hozzáadhatók a **fedezeti opciós** oldalhoz a juttatási tervek esetében. További információkért az egyéni mezők felhasználásáról lásd: [Egyéni mezők](hr-developer-custom-fields.md).
>
> ![Juttatások kezelésében egyéni mezők](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Juttatáskezelés engedélyezése

A témakör azt írja le, hogyan lehet bekapcsolni funkciókat a Human Resources szolgáltatásban. Azt is elmagyarázza, hogy a Humán erőforrás meglévő funkcióit mely funkciókat váltja fel a Juttatások kezelése, és mely funkciókat tiltja le a Juttatások kezelése bekapcsolása után.

> [!IMPORTANT]
> Miután engedélyezte a juttatások kezelését egy **Termelési** környezetben, azt nem lehet letiltani. Azt ajánljuk , hogy a **Termelési** környezetben történő engedélyezése előtt engedélyezze és tesztelje a juttatások kezelését egy **Teszt** környezetben. Jelentősen különböznek egymástól a korábbi Juttatási funkciók és az új Juttatáskezelés funkciók – ezek további beállításokat igényelnek, és a termelésbe történő helyezés előtt tesztelni kell azokat.

További információért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

## <a name="process-overview"></a>Folyamat áttekintése

A juttatások konfigurálása a következő feladatokat foglalja magában:

1.  Állítsa be a szükséges juttatási adatokat.
2.  Állítsa be az opcionális juttatási adatokat.
3.  Juttatási konstrukciók beállítása.
4.  Rugalmas jóváírási programok beállítása (opcionális).
5.  Szükséges alkalmazotti adatok konfigurálása.
6.  Opcionális alkalmazotti adatok konfigurálása.
7.  Alkalmazottak feldolgozása a jogosultság meghatározásához.
8.  Az alkalmazottak az alkalmazotti önkiszolgáló szolgáltatáson keresztül választják ki a csomagokat (nem kötelező).
9.  Alkalmazotti csomagkiválasztások megerősítése.
10. Életesemény feldolgozása (opcionális).
11. Díjfrissítések (nem kötelező).

## <a name="set-up-required-benefit-information"></a>Állítsa be a szükséges juttatási adatokat

Mielőtt alkalmazottakat beléptetnék a csomagokba több összetevőt kell beállítani:

- **Juttatáskezelési paraméterek** – ezek a beállítások több vállalat között meg vannak osztva. Be lehet állítani az alapértelmezett okkódokat, engedélyezni lehet a **Juttatások éves fizetése** lehetőséget, be lehet állítani az új felvétel esetén az alapértelmezett fizetési gyakoriságot, és engedélyezni lehet az életeseményeket. További információkért lásd: [Juttatáskezelési paraméterek beállítása](hr-benefits-setup-parameters.md).
- **Személyes kapcsolattartóra vonatkozó jogosultsági beállítások** – a személyes kapcsolattartók azok a személyek, akik a beállított csomag függő felei vagy kedvezményezettjei lesznek. Ők általában gyermekek, házastársak vagy alapítványok. További információ: [A személyes kapcsolattartó jogosultsági beállításainak konfigurálása](hr-benefits-setup-contact-eligibility-options.md).
- **Fedezeti lehetőségek** – a tervben elérhető fedezettípusok beállítása. Határozza meg konkrétan, hogy kinek jár fedezet vagy hogy mennyi fedezet érhető el. További információkért lásd: [Fedezeti lehetőségek létrehozása](hr-benefits-setup-coverage-options.md).
- **Tervtípusok** – a juttatási csomag létrehozásakor elérhető tervtípusok beállítása. A tervtípusok között szerepel például a **Fogászati**, **Látás** és **Megtakarítás**. A tervtípus bizonyos fontos beállításai határozzák meg, hogy milyen beállítások érhetők el a juttatási csomagban. További információ: [Konstrukciótípusok létrehozása](hr-benefits-setup-plan-types.md).
- **Jogosultsági szabályok** – a jogosultsági szabályok határozzák meg, hogy az alkalmazott jogosult-e egy csomagra. Minden juttatási csomaghoz legalább egy jogosultsági szabályt hozzá kell rendelni. További információ: [Jogosultsági szabályok és beállítások konfigurálása](hr-benefits-setup-eligibility-rules.md).
- **Fizetési gyakoriságok** – a fizetési gyakoriságokra a juttatási mértékek konfigurálásakor van szükség. A mértékhez alkalmazott fizetési gyakoriság segít meghatározni, hogy az alkalmazott és/vagy a munkáltató hetente, havonta vagy évente mennyi összeggel tartozik. További tudnivalókért lásd: [Fizetési gyakoriságok beállítása](hr-benefits-setup-payment-frequencies.md).
- **Mértékek** – A mértékek határozzák meg, hogy egy juttatás mekkora költséggel jár vagy az alkalmazottnak, vagy a munkáltatónak. Ha az alkalmazottnak pénzt kell visszaosztani (például jóváírás egy edzőtermi tagsághoz), negatív árfolyamot kell megadni. További információ: [Mértékek konfigurálása](hr-benefits-setup-rates.md).
- **Szintmértékek** – a szintmértékek akkor használatosak, amikor bizonyos feltételek alapján módosítani kell a mértéket. A leggyakoribb szintmérték egy, a koron alapuló szint. A kettős szintmértékét is be lehet állítani, ahol a mérték nem, kor vagy más kritérium alapján változhat.
- **Levonások** – A levonások alapvetően azok a fejlécinformációk/kódok, amelyek a bérszámfejtő rendszerbe át lesznek küldve a levonás azonosítása érdekében. Ezeket a levonásokat be kell állítani, mert a juttatási csomagban szükségesek lesznek. További információ: [Levonások konfigurálása](hr-benefits-setup-deductions.md).
- **Juttatási időszakok** – a juttatási időszak az az időszak, amely alatt az alkalmazottak juttatásban részesülnek. Csomagévnek is nevezik. A nyitott beléptetési időszakok is itt vannak beállítva.

## <a name="set-up-optional-benefit-information"></a>Állítsa be az opcionális juttatási adatokat

A következő összetevők beállítása nem szükséges a juttatási csomag létrehozásához:

- **Programok** – a program olyan juttatások halmaza, amelyekre ugyanazok a jogosultsági szabályok vonatkoznak. Az értékesítési osztályon mindenki kap például mobiltelefont.
- **Csomagok** – a csomag juttatások egy csoportja, ahol ki kell választani egy tervet ahhoz, hogy további terveke is kiválaszthatók legyenek. Például egy levonható egészségügyi tervet egy egészségbiztosítási számla (HSA) tervvel lehet csomagba rendezni.
- **Életesemény-típusok** – az életesemények olyan események, amelyek lehetővé teszik az alkalmazott fedezetének módosítását. Az életesemény-típusok egy tervtípushoz kapcsolódnak. Például egy egészségügyi tervtípus lehetővé teheti a tervek változtatását születés, örökbefogadás vagy családi állapot változása miatt. Előfordulhat azonban, hogy egy biztosításiterv-típus az életesemények miatt nem teszi lehetővé a módosításokat. A részleteket lásd: [Életesemény-típusok konfigurálása](hr-benefits-setup-life-event-types.md).
- **Várakozási napok és várakozási időszakok** – a juttatási tervben be lehet állítani fedezeti várakozási időszakot. Például egy újonnan felvett alkalmazott csak három hónap munkaviszonya után tud belépni a 401(k) programba. Ebben az esetben a várakozási időszak három hónap. A várakozási napok a várakozási időszakban használatosak ha az új belépőket csak a hónap meghatározott napján lehet feldolgozni és a szolgáltatónak benyújtani. Ha például a 401(k) tagság csak a hónap tizenötödik napján, három hónap munkaviszony után feldolgozható, akkor a beállított várakozási időszak három hónap, a várakozási nap pedig a tizenötödike. További információ: [Várakozási napok konfigurálása](hr-benefits-setup-waiting-days.md) és [Várakozási időszakok konfigurálása](hr-benefits-setup-waiting-periods.md).
- **Okkódok** – Az okkódok annak indoklására használhatók, hogy miért változik egy juttatás egy alkalmazottnál. További tájékoztatásért lásd: [Okkódok beállítása](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Juttatási konstrukciók beállítása

A juttatási terv beállításakor az alkalmazottak felvételét csak azt követően lehet végrehajtani,m ha elvégezték a következő lépéseket:

- Juttatási időszak hozzárendelése.
- Fedezeti beállítások csatolása.
- Az **Általános** lapon állítsa be az érvényesség kezdő és befejező dátumát.
- Rendeljen hozzá legalább egy jogosultsági szabályt.
- A **Beállítás** lapon állítsa be a **Regisztráció engedélyezése/folytatása** mezőt.

Az juttatási tervek beállításának módjáról bővebben lásd: [Juttatási konstrukciók beállítása](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Rugalmas jóváírási programok beállítása (opcionális)

A rugalmas jóváírási programokkal az alkalmazottakat előre meghatározott számú rugalmas jóváírásnak megfelelően lehet beléptetni a juttatásokba. Az alkalmazottak határozhatják meg, hogyan osztják fel a rugalmas jóváírásaikat. Ha például az alkalmazottak már a házastársuk egészségbiztosítása alá tartoznak, akkor nem kell a jóváírásukat az egészségügyi fedezetre használni. Emiatt előfordulhat, hogy ezeket más juttatásokra érdemes használniuk. A rugalmas jóváírási programokkal kapcsolatos további tudnivalókat lásd [Rugalmas jóváírási programok beállítása](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Szükséges alkalmazotti adatok konfigurálása

Ahhoz, hogy az alkalmazottakat juttatásokhoz lehessen regisztrálni, meg kell adnia a szükséges adatokat hozzájuk. 

Az alkalmazottnak beosztást kell **rendelnie** hozzá. A dolgozó hozzárendelésének frissítésével lehet beosztást hozzárendelni az alkalmazotthoz a Dolgozó vagy a **Beosztás** **·** **·** **lapokon**. 

Ezután az alkalmazottakat a kezdő dátumuk napján fix kompenzációs konstrukcióba kell bevonni, vagy éves juttatásban kell **részesülnie**. A fix kompenzáció alkalmazotthoz való hozzárendelése előtt hozzá kell **rendelni egy** **beosztást**. 

> [!NOTE] 
> A **fix kompenzáció kezdő dátuma** nem lehet a beosztás **hozzárendelési dátuma** előtti.

Másik lehetőségként, ha van olyan alkalmazott, aki jutalékhoz hasonló kiegészítő kompenzációt kap, hozzáadhatja a juttatások éves bérét **az** alkalmazotti rekordhoz. Az Emberi erőforrások az juttatások éves bérének összegét használják a fedezeti összegek meghatározásakor, nem pedig a fix kompenzáció **éves** **összegének** meghatározásakor. A **juttatások évi fizetésének** érvényesnek kell lennie az alkalmazott kezdő dátumától vagy a juttatási időszak kezdetével, amelyik a legújabb. A juttatások éves bérének hozzárendeléséhez azonban nincs **szükség** beosztásra. A Juttatások éves bér funkció engedélyezéséhez használja az Emberi erőforrások megosztott paraméterei lapot **a** Juttatások **kezelése** **lapon**. Ez a funkció alapértelmezés szerint ki van kapcsolva.

> [!IMPORTANT]
> Ha az alkalmazottnak egy fix kompenzációt és egy éves bérösszeget is meg kell adni, a juttatások éves bérét használja a program **a** **·** **fedezeti** összegek meghatározására. A Dolgozó lap Foglalkoztatás részletei szakaszában ki kell választania egy értéket a Juttatás fizetésének **gyakorisága** **·** **mezőben**.

## <a name="configure-optional-employee-information"></a>Opcionális alkalmazotti adatok konfigurálása
Ha olyan juttatási tervet hoz létre, amely nemen vagy életkoron alapuló arányokat használ, akkor meg kell adnia a születési dátumot és a nemet az alkalmazott számára a juttatási költség kiszámításához.

## <a name="process-employees-to-determine-eligibility"></a>Alkalmazottak feldolgozása a jogosultság meghatározásához
Mielőtt az alkalmazottak tervekbe regisztrálhatók lennének, a jogosultsági feldolgozás futtatásával meg kell határozni, hogy mely konstrukciókra jogosultak. Az alkalmazhatósági folyamat eredményeit a Folyamat **eredménymegjelenítője** megtekintheti. További információért tekintse át a [Felvételi jogosultság feldolgozása](hr-benefits-process-enrollment-eligibility.md) részt.

## <a name="employees-select-plans-using-employee-self-service-optional"></a>Alkalmazottak terveket választnak **az Alkalmazott önkiszolgáló rendszer** használatával (nem kötelező)

Nyitott felvétel esetén az alkalmazottakat újonnan felvették, vagy egy életeseményre kerül sor, és az alkalmazottak az alkalmazott önkiszolgáló rendszerével választhatják ki vagy frissíthetik a **juttatásukat**. A további tudnivalókat lásd: [Alkalmazotti önkiszolgáló rendszer konfigurálása](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Alkalmazotti csomagkiválasztások megerősítése

Az alkalmazottak által kiválasztott juttatásokat vissza kell igazolni, mielőtt az alkalmazottak regisztráltnak számítanak azokhoz. A juttatások az alkalmazott nevében is kiválaszthatók. A juttatások kiválasztásához vagy megerősítéséhez az **Alkalmazott** oldalon a **Juttatások** lapon válassza a **Dolgozói juttatási konstrukció** lehetőséget. Több alkalmazott juttatásának kiválasztásához vagy megerősítéséhez használja a **Dolgozói juttatási tervek tömeges frissítése** lapot.

## <a name="life-event-processing-optional"></a>Életesemény feldolgozása (opcionális)

Az alkalmazottak életciklusa során az egyes alkalmazottak különböző életeseményeket élhetnek át, például megváltozhat a munkaviszonyuk vagy változások lehetnek az eltartottjaik vagy kedvezményezettjeik terén. Az életesemények csak akkor használhatók, ha engedélyezi azokat az **Emberi erőforrások megosztott paraméterei** oldalon. Adja meg az életesemények típusait és az életesemények beállításait a konstrukciótípusokhoz.

Az életesemények feldolgozása előtt a felvételi időkereten belül már legalább egyszer futtatni kell a nyitott jelentkezést. Az Egyesült Államokban a nyitott regisztráció általában évente egyszer történik. Az Egyesült Államokon kívül nyitott jelentkezés esetleg a felvételkor történik. Az életesemény feldolgozásához nincs szükség arra, hogy a dolgozók válasszanak egy juttatási konstrukciót. A dolgozóknak azonban szerepelniük kell a nyitott regisztráció-feldolgozásban. További információért tekintse át az alábbi témaköröket:

- [Életesemények feldolgozása](hr-benefits-process-life-events.md)
- [Életesemények változásainak feldolgozása](hr-benefits-process-life-event-changes.md)
- [Életesemény-jogosultság feldolgozása](hr-benefits-process-life-event-eligibility.md)

## <a name="rate-updates-optional"></a>Díjfrissítések (nem kötelező)

Bizonyos esetekben a juttatás mértéke módosul a konstrukciós időszakban. Ha frissíteni kell a konstrukcióra már regisztrált alkalmazottak mértékeit, fel kell feldolgoznia a mértékváltozásokat. További információért tekintse át a [Mértékváltozások feldolgozása](hr-benefits-process-rate-changes.md) részt.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
