---
title: "Attract előmeneteli webhely funkció"
description: "A cikk a Microsoft Dynamics 365 for Talent - Attract jelöltek számára rendelkezésre álló karrierwebhely funkcióit ismerteti. A funkciók beállítását is ismerteti."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: hu-hu
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>Attract előmeneteli webhely funkció

[!include [banner](includes/banner.md)]

A cikk a Microsoft Dynamics 365 for Talent - Attract jelöltek számára rendelkezésre álló karrierwebhely funkcióit ismerteti. A funkciók beállítását is ismerteti.

## <a name="overview"></a>Áttekintés

Az Attract egy előmeneteli webhelyet biztosít a bérlőnek minden egyes környezetben. Például ha egy szervezet fejlesztői környezettel és tesztkörnyezettel rendelkezik, egy előmeneteli webhely lesz telepítve a fejlesztői környezethez, és egy másik a tesztkörnyezethez. Valamennyi előmeneteli webhely **teljesen elszigetelt**, és saját hitelesítési módszere van. Az állások és a jelöltprofilok nincsenek az előmeneteli webhelyek között megosztva.

Alapértelmezés szerint az előmeneteli webhely nyilvános. Ezért a pályázók anélkül, hogy bejelentkeznének, megtekinthetik a külsőként megjelölt állásokat. Minden egyéb művelethez azonban szükséges, hogy a pályázók bejelentkezzenek.

## <a name="career-site-management"></a>Karrierwebhely kezelése

A következő elemek az előmeneteli webhelyen beállításokkal szabályozottak:

- **Szervezet neve:** A szervezet neve megjelenik az előmeneteli webhely felső navigációs sávján. A szervezet nevének kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.
- **Szervezet emblémája:** A cég emblémájának képe a bal felső részén jelenik meg az előmeneteli webhelynek. Az emlémakép kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.

A szervezet neve és az embléma értékének beállításához jelentkezzen be az Attract rendszerébe rendszergazdaként, válassza az **Adminisztrációs központ** lehetőséget a **Beállítások** menüben (fogaskerék szimbólum), és válassza ki a **Vállalati adatok** lapot.

> [!NOTE]
> A előmeneteli webhelyen megjelenő emblémához 20 képpont rögzített magasság tartozik. Az Adminisztrációs központban felvett kép át lesz méretezve, hogy elférjen. Ezért a kép szélessége megváltozhat.

## <a name="career-site-url"></a>Karrierwebhely URL-címe

Ha első alkalommal [ad fel egy külső állást](./Creating-jobs-Attract.md#postings) át lehet másolni a **Jelentkezés** hivatkozást az Attract alkalmazásból. A hivatkozás URL-cím formátuma a következő lesz: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

Az URL-címe az előmeneteli webhelynek egy részét az **Jelentkezés** URL-címnek. Mindent tartalmaz a vállalat nevéig. Emiatt az előző **Jelentkezés** URL-címnél az előmeneteli webhely URL-címe: `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Hitelesítési lehetőségek

A pályázók bejelentkezési lehetőségei az Attract előmeneteli webhelyen a következők:

- Személyes fiók:

    - LinkedIn
    - Microsoft
    - Google
    - Facebook

- Munkahelyi vagy iskolai fiók:

    - Microsoft Azure Active Directory (Azure AD)

Az Azure Active Directory-bejelentkezés csak belső pályázók számára készült. Ennek megfelelően csak a belső pályázóknál működik, akik a vállalat Azure Active Directory hitelesítő adatait használják. Például a pályázó jelenleg a Contoso Kft alkalmazottja, és jelentkezni szeretne egy állásra az Alpine Ski House független vállalatnál. Ebben az esetben a bejelentkezés sikertelen lesz, ha az alkalmazott megkísérli Contoso Kft-s Azure Active Directory hitelesítő adatait használni.

## <a name="create-and-maintain-a-profile"></a>Profil létrehozása és karbantartása

Miután a pályázók bejelentkeztek az előmeneteli webhelyre, kiválaszthatják a **Saját profilt** a lap felső navigációs sávján a saját profil létrehozásához és karbantartásához. A profil tartalmaz személyes adatokat, gyakorlattal kapcsolatos információkat, tanulmányokat, dokumentumokat, hivatkozásokat, képzettséggel kapcsolatos adatokat. A profilt a létrehozása után alkalmazni lehet a jelentkezőt érdeklő állásokra való jelentkezésre. A profilok segítségével a megfelelő állásokra javasol jelölteket az Attrat.

## <a name="find-the-right-job"></a>A megfelelő állás keresése

Az állás listaoldalon a pályázók kereshetnek egy bizonyos állást keresési feltételek megadásával. A keresési funkció a beosztásokban és munkakörökben keresőszavakat keres, és a megfelelő állásokat jeleníti meg. A pályázók szűrhetik az eredményeket bármikor, beosztási funkció vagy a feladat helye alapján.

A pályázók ajánlott állásokat is megtekinthetnek az előmeneteli webhelyen. Az állások, amelyek a pályázóknak javasoltak, a jelölt múltbeli pályázatain, profilján és önéletrajzán alapulnak.

> [!NOTE]
> Csak akkor jelennek meg javaslatok, ha legalább 10 állást adtak fel az előmeneteli webhelyen, és a jelentkező profilja kész van.

## <a name="apply-for-jobs"></a>Pályázat állásokra

Miután a jelölt megtalálta a megfelelő állást, jelentkezhet a **Jelentkezés** gombbal az állás részletes adatai lapon. Ezen a ponton a pályázók vadonatúj profilt hozhatnak létre, vagy áttekinthetik a meglévő profil információit. A pályázó feltölthet önéletrajzot, szükség szerint, majd küldje el a jelentkezést az állásra.

## <a name="check-application-status"></a>Pályázat állapotának ellenőrzése

Egy vagy több állára való pályázás után a jelentkező kiválaszthatja a **Jelentkezések** lehetőséget az oldal felső navigációs sávján, hogy megtekintse a nyitott és lezárt jelentkezéseket. Pályázók nyissa meg egy jelentkezést, látják a jelenlegi szakaszt és minden függőben lévő teendők, amelyet ki kell tölteniük. Például ha egy potenciális személyes interjú dátumát kell megadni, a lapon láthatók a lehetőségek.

## <a name="internal-jobs"></a>Belső állások

Jelenleg a belső, és az Attract előmeneteli webhelyre feladott állások nem jelennek meg az előmeneteli webhelyen. Csak a közvetlen **Jelentkezés** URL-címen keresztül hozzáférhetők, amely átmásolható az Attract alkalmazásból.

