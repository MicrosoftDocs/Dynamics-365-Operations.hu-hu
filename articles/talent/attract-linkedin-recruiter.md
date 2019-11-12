---
title: Jelöltek felkutatása a LinkedIn Recruiter megoldással a Microsoft Dynamics 365 Talent - Attract programban.
description: A Microsoft Dynamics 365 Talent - Attract LinkedIn integrációját használhatja a jelöltek felkutatásához a LinkedIn Recruiter megoldáson keresztül.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8f2e95e74bbc8d78ed5d970f29b61150a45c6740
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551564"
---
# <a name="source-candidates-with-linkedin-recruiter-in-microsoft-dynamics-365-talent---attract"></a>Jelöltek felkutatása a LinkedIn Recruiter megoldással a Microsoft Dynamics 365 Talent - Attract programban.
[!include[banner](../includes/banner.md)]

A LinkedIn a világ legnagyobb online szakmai hálózata, amely hozzáférést biztosít a világ legjobb tehetségéhez. Microsoft Dynamics 365 Talent: Attract segítségével felkutathat pályázókat közvetlenül a LinkedIn felületről. Ezért könnyebb, mint valaha, megtalálnia azokat a tehetségeket, akikkel betöltheti nyitott állásait. Miután a LinkedIn alkalmazással beállította a kapcsolatot az Attract megoldáson keresztül, megtekintheti a beosztásokhoz tartozó esetleges LinkedIn-jelöltek adatait, és egyetlen kattintással exportálhatja azokat az Attract megoldásba.

Ha úgy tűnik, hogy nem rendelkezik ezzel a képességgel, forduljon a rendszergazdához. Csak akkor veheti igénybe LinkedIn Recruiter megoldást az Attract alkalmazásból ha az adminisztrátor [beállította a LinkedIn integrációt](./attract-admin-linkedin.md). Ezután beállíthatja a kapcsolatot a LinkedIn Recruiter megoldással és megkezdheti a jelöltek megtalálását.

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>A kapcsolat beállítása a LinkedIn Recruiter megoldással

Mielőtt használhatná a LinkedIn Recruiter megoldást az Attract alkalmazáson keresztül be kell állítania a kapcsolatot LinkedIn Recruiter megoldással. Ehhez a lépéshez szüksége van a LinkedIn Recruiter hitelesítő adataira.

1. Kattintson a lap jobb felső sarkában látható **Beállítások** (fogaskerék ikon) gombra.
2. Válassza a **Felhasználói beállítások** lehetőséget.
3. A **Kapcsolatok** lapon jelölje be a **Csatlakozás** lehetőséget a **LinkedIn** mellett. Kövesse a LinkedIn által biztosított utasításokat.

    ![[Kapcsolat beállítása LinkedIn Recruiter és az Attract között](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>A LinkedIn-jelöltek megtekintése az Attract megoldásban

Miután csatlakozott a LinkedIn Recruiter alkalmazáshoz, megtekintheti a jelentkezők LinkedIn-profiljait az Attract megoldásban.

1. Az Attract megoldásban válassza a **Munkák** vagy **Tehetségállományok** lehetőséget a bal oldalon, majd válassza ki a pályázót.

    ![[A LinkedIn jelöltek megtekintése az Attract megoldásban](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. A pályázó profiljában válassza a **LinkedIn** fület. A pályázó profilját a az InMail és LinkedIn jegyzetek előzményeivel együtt tekintheti meg.

Innen mentheti a pályázót egy LinkedIn Recruiter projektbe, elküldheti az InMail-be, vagy az Update Me funkciót egy figyelmeztetés beállításához a LinkedIn Recruiter megoldásban.

> [!NOTE]
> A pályázó LinkedIn-profilja akkor jelenik meg az Attract megoldásban, ha a pályázónak Attract és LinkedIn adatai megegyeznek. Itt találja a használt egyezetetési szabályokat:
> 
> 1. Ha az e-mail cím és a LinkedIn tagazonosító egyezik az Attract megoldásban és a LinkedIn felületen, megjelenik a pályázó profilja. A jelentkezőknek lehetősége van arra, hogy a LinkedIn profilját összekapcsolja vagy leválassza az Attract megoldásból.
> 2. Ha az e-mail cím vagy a LinkedIn tagazonosító nem egyezik, akkor megjelenik a lehetséges jelöltek listája. Ezután ki lehet választani egy pályázót a listában, és csatolhatja a profilhoz.
> 3. Ha nincsenek jó egyezések, akkor a program értesítést küldött, hogy nem talált egyezést.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>LinkedIn jelöltek exportálás az Attract megoldásba egyetlen kattintással

Amikor a jelentkezőket a LinkedIn Recruiter megoldásban tekinti meg, akkor őket olyan feladatokba exportálhatja, amelyek jelenleg meg vannak nyitva az Attract megoldásban. Ehhez a lépéshez Toborzó vagy Felvételi vezető engedélyek szükségesek a Vonzásban. Az Attract szerepköreivel kapcsolatos további tudnivalókért tekintse át a [Biztonság és szerepkörkezelés az Attract alkalmazásban](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract) részt.

Arról is meg kell győződnie arról, hogy a feladatnak van Potenciális jelölt szakasza. További információ: [Potenciális jelöltekkel kapcsolatos tevékenységek](./activities-attract.md#prospect-activity).

1. Az Attract megoldásban hozzon létre egy állást, végezze el a megfelelő szerepkörök hozzárendelését, és aktiválja az állást.
2. A LinkedIn Recruiter alkalmazásban keressen egy jó jelentkezőt a feladatra, és nyissa meg a pályázó profilját.
3. A névjegykártya álláskeresés mezőjével keresse meg az állást az Attract rendszerében aktivált álláscím vagy állásazonosító alapján. Ha nem találja az állást, kattintson az **ATS módosítása** elemre a megfelelő Attract-példány megkereséséhez.
4. Válassza ki az állást, válassza az **Exportálás** elemet.
5. Az Attract megoldásban nyissa meg az állást. Az állásnak a **Potenciális jelölt** lapján fog megjelenni az exportált pályázó.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Az Attract információinak megtekintése a LinkedIn Recruiter megoldásban

A LinkedIn Recruiter megoldásban nyomon követheti, hogy pályázó jelentkezett-e a szervezeténél más állásokra, megnézheti, hogy hol tart az álláspályázatok különböző szakaszaiban, és megtekintheti az Attract visszajelzéseit és megjegyzéseit.

1. Nyissa meg a LinkedIn Recruiter lehetőséget, és válassza ki a pályázó profilját.
2. Vigye az egeret az**ATS-ben** elem fölé.
3. Válassza ki a következő lehetőségek egyikét, hogy megtekintse a jelentkezők adatait, amelyek tárolva vannak az Attract megoldásban:

    - **Állások és állapotok** – Azokat a állásokat jeleníti meg, amelyeken a pályázó része, a legfrissebb állapotot, valamint a pályázónak az egyes állásokra vonatkozó előrehaladását.
    - **Interjú-visszajelzés** – Az interjúbonyolítók által az Attract rendszerébe beküldött visszajelzések megtekintéséhez.
    - **Megjegyzések** – Tekintse meg, hogy milyen megjegyzések kerültek be ehhez a pályázóhoz az Attract megoldásban.

    ![[Attract információk megtekintése a LinkedIn Recruiter megoldásból](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> A pályázó- és pályázati adatok nem lesznek szinkronizálva a LinkedIn Recruiter rendszerrel, ha a jelentkező nem lépett túl a Potenciális szakaszon.

## <a name="view-linkedin-talent-pools"></a>LinkedIn tehetségállományok megtekintése

Ha a jelentkezők beleegyeznek abba, hogy a saját LinkedIn-profiljaikat a szervezet bármelyik felhasználója számára megosztják, egy új pályázói rekord jön létre az Attract megoldásban. Ezek a jelöltek ezután egy rendszer által létrehozott LinkedIn tehetségállományban jelennek meg.

1. A Vonzásban válassza a **tehetségállomány** lehetőséget a bal oldalon.
2. Válassza ki a LinkedIn tehetségállományt. Látni fogja a jelentkezők listáját és a LinkedIn-ről származó csonka profiljaikat. A csonka profilok tartalmazzák a pályázó kereszt- és vezetéknevét és e-mail címét, ha a pályázó úgy döntött, hogy megosztja.

## <a name="see-also"></a>Lásd még

[LinkedIn GYIK](./attract-linkedin-faq.md)

[A LinkedIn integrációjának beállítása](./attract-admin-linkedin.md)

[Állások létrehozása](./creating-jobs-attract.md)

[Állások feladása a LinkedIn felületére az Attract szolgáltatásból](./attract-post-jobs-to-linkedin.md)

[A LinkedIn integrációjának hibaelhárítása](./attract-troubleshoot-linkedin.md)
