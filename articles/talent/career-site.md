---
title: Attract előmeneteli webhely funkció
description: Ez a témakör áttekintést a pályázó által használt karrierwebhely funkcióiról az Attract-ban.
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/13/2019
ms.locfileid: "389966"
---
# <a name="career-site-functionality-in-attract"></a>Attract előmeneteli webhely funkció

[!include[banner](../includes/banner.md)]

Ez a témakör áttekintést a pályázó által használt karrierwebhely funkcióiról a Microsoft Dynamics 365 for Talent: Attract-ban. A funkciók beállítását is ismerteti.

Az Attract egy karrierwebhelyet biztosít minden egyes környezethez a bérlőben. Például ha egy szervezet fejlesztői környezettel és tesztkörnyezettel rendelkezik, egy karrierwebhely lesz telepítve a fejlesztői környezethez, és egy másik a tesztkörnyezethez. Valamennyi karrierwebhely teljesen elszigetelt, és saját hitelesítési módszere van. Az állások és a jelöltprofilok nincsenek a karrierwebhelyek között megosztva.

Alapértelmezés szerint a karrierwebhely nyilvános. Ezért a pályázók anélkül, hogy bejelentkeznének, megtekinthetik a külsőként megjelölt állásokat. Minden egyéb művelethez azonban szükséges, hogy a pályázók bejelentkezzenek.

## <a name="career-site-management"></a>Karrierwebhely kezelése

Az alábbi elemek értékének beállításához jelentkezzen be az Attract rendszerébe rendszergazdaként, válassza az **Adminisztrációs központ** lehetőséget a **Beállítások** menüben (fogaskerék szimbólum), és válassza ki a **Vállalati adatok** lapot.

-   **Szervezet neve:** – A szervezet neve megjelenik az előmeneteli webhely felső navigációs sávján. A szervezet nevének kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.

-   **Szervezet emblémája** – A cég emblémájának képe a bal felső részén jelenik meg az előmeneteli webhelynek. Az emlémakép kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.

    >   [!NOTE] 
    >   A karrierwebhelyen megjelenő emblémához 20 képpont rögzített magasság tartozik. Az Adminisztrációs központban felvett kép át lesz méretezve, hogy elférjen. Ezért, a képtől függően a kép szélessége megváltozhat.
 
Az alábbi elemek értékének beállításához jelentkezzen be az Attract rendszerébe rendszergazdaként, válassza az **Adminisztrációs központ** lehetőséget a **Beállítások** menüben, és válassza ki a **Karrieroldal kezelése** lapot.

-   **Keresőmotor optimalizálása** -Ha engedélyezve van, az Attract karrierwebhelyre feladott összes nyilvános állás kereshető keresőmotorok, Bing és Google segítségével.

    >   [!NOTE] 
    >   A beállítás bekapcsolása és a keresési eredmények megjelenése között eltelhet egy kis idő, és attól függően, hogy milyen keresőmotor használ.
         
## <a name="career-site-urls"></a>Karrierwebhely URL-címek

Az alábbi lista a gyakran használt karrierwebhely URL-címeket és azok elérési módját tartalmazza.

-   **Karrierwebhely kezdőlapjának URL-címe** – A karrierwebhely kezdőlapja URL-címének megtekintéséhez, jelentkezzen be az Attract-be rendszergazdaként, válassza a **Felügyeleti központ** lehetőséget **Beállítások** menüben, és válassza a **Karrieroldal kezelése** lapot.

-   **Egyéni álláshirdetés jelentkezési URL-címe** [Ha első alkalommal ad fel egy külső állást](Creating-jobs-Attract.md#postings) át lehet másolni a **Jelentkezés** hivatkozást az Attract alkalmazásból. A hivatkozás URL-cím formátuma a következő lesz: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **Egyéni álláshirdetés URL-címe** – Az álláshirdetés URL-címe a Jelentkezés URL-cím alkarakterlánca. Mindent tartalmaz a munkaszámig. Emiatt az előző Jelentkezés URL-címnél az álláshirdetés URL-címe: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)

## <a name="authentication-options"></a>Hitelesítési lehetőségek

A pályázók bejelentkezési lehetőségei az Attract karrierwebhelyen a következők:

-   Személyes fiók:

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Munkahelyi vagy iskolai fiók:

    -   Microsoft Azure Active Directory (Azure AD)

Az Azure AD-bejelentkezés csak belső pályázók számára készült. Ennek megfelelően csak a belső pályázóknál működik, akik a vállalat Azure AD hitelesítő adatait használják. Például a pályázó jelenleg a Contoso Kft alkalmazottja, és jelentkezni szeretne egy állásra az Alpine Ski House független vállalatnál. Ebben az esetben a bejelentkezés sikertelen lesz, ha az alkalmazott megkísérli Contoso Kft Azure AD hitelesítő adatait használni.

## <a name="create-and-maintain-a-profile"></a>Profil létrehozása és karbantartása

Miután a pályázók bejelentkeztek a karrierwebhelyre, kiválaszthatják a **Saját profilt** a lap felső navigációs sávján a saját profil létrehozásához és karbantartásához.
A profil tartalmaz személyes adatokat, gyakorlattal kapcsolatos információkat, tanulmányokat, dokumentumokat, hivatkozásokat, képzettséggel kapcsolatos adatokat. A profilt a létrehozása után alkalmazni lehet a jelentkezőt érdeklő állásokra való jelentkezésre. A profilok segítségével a megfelelő állásokra javasol jelölteket az Attrat.

>   [!NOTE]
>   Ha pályázó által használt egy e-mailes azonosítót használ a bejelentkezéshez a fenti hitelesítési szolgáltatók valamelyikének használatával, ez az e-mail-azonosító lesz a profilhoz társított alapértelmezett e-mail-azonosító. Azonban az utóbbi bármikor módosítható, és teljesen független az előzőtől. Az Attract mindig a kapcsolattartói e-mail-azonosítót használja, hogy társítsa profilját minden e-mail kommunikációval.

## <a name="find-the-right-job"></a>A megfelelő állás keresése

Az állás listaoldalon a pályázók kereshetnek egy bizonyos állást keresési feltételek megadásával. A keresési funkció a beosztásokban és munkaköri leírásokban keresőszavakat keres, és a megfelelő állásokat jeleníti meg. A pályázók szűrhetik az eredményeket bármikor, beosztási funkció vagy a feladat helye alapján.

A pályázók ajánlott állásokat is megtekinthetnek a karrierwebhelyen. Az állások, amelyek a pályázóknak javasoltak, a jelölt múltbeli pályázatain, profilján és önéletrajzán alapulnak.

>   [!NOTE] 
>   Csak akkor jelennek meg javaslatok, ha legalább 10 állást adtak fel a karrierwebhelyen, és a jelentkező profilja kész van.

## <a name="apply-for-jobs"></a>Jelentkezés állásokra

Miután a jelölt megtalálta a megfelelő állást, jelentkezhet a **Jelentkezés** gombbal az **Állás részletei** lapon. Ezen a ponton a pályázók új profilt hozhatnak létre, vagy áttekinthetik a meglévő profil információit.
A pályázó feltölthet önéletrajzot, szükség szerint, majd küldje el a jelentkezést az állásra.

## <a name="check-application-status"></a>Pályázat állapotának ellenőrzése

Egy vagy több állásra való pályázás után a jelentkező kiválaszthatja a **Jelentkezések** lehetőséget az oldal felső navigációs sávján, hogy megtekintse a nyitott és lezárt jelentkezéseket. Amikor a pályázó megnyit egy jelentkezést, látja a jelenlegi szakaszt és minden függőben lévő teendőt, amelyet ki kell töltenie. Például ha egy potenciális személyes interjú dátumát kell megadni, a lapon láthatók az elérhető lehetőségek.

## <a name="internal-jobs"></a>Belső állások

Jelenleg a belsőnek megjelölt, és az Attract karrierwebhelyre feladott állások nem jelennek meg a karrierwebhelyen. Csak a közvetlen **Jelentkezés** URL-címen hozzáférhetők, amely átmásolható az Attract alkalmazásból.
