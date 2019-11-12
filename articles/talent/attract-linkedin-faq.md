---
title: Az Attact és a LinkedIn integrációjával kapcsolatos gyakori kérdések
description: Ez a témakör azokat a kérdéseket válaszolja meg, amelyekkel a LinkedIn és a Microsoft Microsoft Dynamics 365 Talent - Attract közötti integrációval kapcsolatosan merülhetnek fel.
author: hasrivas
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: b77ad598ba209dbbd73765c49947e84a3995153d
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550367"
---
# <a name="attract-integration-with-linkedin-faq"></a>Az Attact és a LinkedIn integrációjával kapcsolatos gyakori kérdések

[!include [banner](includes/banner.md)]

A LinkedIn a világ legnagyobb online szakmai hálózata. Microsoft Dynamics Talent: Attract integrálható a LinkedIn-nel hogy hozzáférjen a világ legjobb tehetségeihez. Az Attract lehetővé teszi a állások közvetlen feladását a LinkedIn felületére és azt is lehetővé teszi, hogy a jelölt adatait beimportálja a LinkedIn-ből az Attract megoldásba.

## <a name="for-recruiters-and-hiring-managers"></a>Toborzók és felvételi vezetők számára

Az alábbiakban a gyakran feltett kérdésekre adott válaszok találhatók az Attract és a LinkedIn együttes használatáról.

### <a name="what-linkedin-features-do-i-get-with-attract"></a>Milyen LinkedIn funkciókat kapok az Attract megoldással?

Az Attract LinkedIn integrációjával a következő feladatokat lehet végrehajtani:

- [Munkák feladása a LinkedIn-re](./attract-post-jobs-to-linkedin.md) (ingyenes LinkedIn-hirdetésként).
- [A pályázó adatainak exportálása a LinkedIn rendszerből az Attract megoldásba](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click).
- [Annak engedélyezése a jelöltek számára, hogy jelentkezzenek munkáira a LinkedIn-en keresztül](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract).

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>Mire van szükség a munkák a LinkedIn felületére történő feladása előtt?

Az adminisztrátornak [be kell állítania a LinkedIn integrációt az Attract-ben](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). Azután készen is áll.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>Hogyan adhatok fel munkát a LinkedIn felületére az Attract szolgáltatásból?

Miután létrehozta a munkát az Attract megoldásban, válassza a **Feladás most** gombot, amely a LinkedIn-hez tartozik. További tájékoztatás: [Munkák feladása a LinkedIn felületére az Attract megoldásból](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>Lekérhetem a pályázó adatait a LinkedIn rendszerből az Attract megoldásba?

Igen. Ha megjelenik egy jó jelentkező a LinkedIn-ben, akkor egyszerűen exportálhatja a pályázó adatait az Attract megoldásba. További tudnivalókért lásd: [Jelöltek biztosítása a LinkedIn Recruiter segítségével](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>Hogyan kaphatok segítséget a LinkedIn eléréshez az Attract megoldásban?

Ha nem sikerül bejelentkeznie a LinkedIn rendszerbe, vagy állást közzétennie az Attract megoldásból, lásd [A LinkedIn integráció hibaelhárítása](./attract-troubleshoot-linkedin.md)

Az Attract megoldással kapcsolatos egyéb problémákkal kapcsolatban lásd: [Támogatás kérése a Talent alkalmazáshoz](./talent-support.md). A LinkedIn felülettel kapcsolatos segítségért lásd a [LinkedIn támogatási oldalát](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>Rendszergazdák és fejlesztők számára

Az alábbiakban a gyakran feltett kérdésekre adott válaszok találhatók az Attract és a LinkedIn integrációjának konfigurálásáról.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>Hogyan lehet beállítani az Attract megoldást, hogy a toborzók és a felvételi vezetők munkákat tehessen közzé a LinkedIn felületén?

Az felügyeleti központban konfigurálhatja a **LinkedIn-integráció** lapon az elérhető beállításokat. További tájékoztatás: [A LinkedIn-integráció beállítása](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>A pályázó adatainak exportálása lehetséges a LinkedIn rendszerből?

Igen, de előbb konfigurálnia kell a LinkedIn Recruiter integrációt. További tájékoztatás: [A LinkedIn-integráció beállítása](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>Hogyan lehet a LinkedIn Premium Job Slotjaiba állásokat feladni?

Bár a Attract megoldás hatékony magoldást kínál az állások közzétételéhez a LinkedIn felületére, előfordulhat, hogy további rugalmasságra van szükség. Előfordulhat például, hogy az ingyenes hirdetéseken kívül fel szeretné adni állásokat Premium Job Slotokba, vagy azt szeretné, ha a LinkedIn csak naponta egyszer dolgozza fel a kötegelt állásközzétételt.

#### <a name="types-of-linkedin-job-posts"></a>A LinkedIn álláshirdetések típusai

A LinkedIn a következő típusú álláshirdetéseket kínálja:

- **Limited Listing** – A keresési eredményekben megjelenő ingyenes álláshirdetések, amikor a jelentkezők a LinkedIn-en és a vállalat LinkedIn oldalán keresnek állásokat. A Limited Listingek az aktív álláskeresők felé irányulnak. Az ilyen típusú hirdetést knálja az Attract a LinkedIn esetében. Nem tudja népszerűsíteni a Limited Listingeket a LinkedIn-en. Ha népszerűsíteni szeretné a Limited Listingeket akkor a LinkedIn felületén kell engedélyeznie a Job Wrappinget. A Job Wrappinggel kapcsolatos további tudnivalókat lásd: [Limited Listings és Premium Job Slotok összehasonlítása Job Wrapping eseté](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) és [Job Wrapping Plus GYIK](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Premium Job slot** – a LinkedIn különböző helyein, például a LinkedIn-hírcsatornában, e-mailekben és a **Az előfordulhat, hogy érdeklik ezek az állások** területen megjelenő fizetős hirdetések. A Premium Job Slotok passzív jelöltek felé irányulnak, de megjelennek az álláskeresésekben is.

Az Attract Limited Listingként ad fel állásokat LinkedIn felületre. Ha Premium Job Slotokat szeretne használni, akkor a Job Wrapping funkciót kell használnia LinkedIn Recruiter megoldáson keresztül. A Job Wrapping funkcióhoz job wrapping szerződés szükséges a LinkedIn-nel. A további tudnivalókat lásd: [Job Wrapping LinkedIn Recruiter megoldáson keresztül - Áttekintés](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>A kötegelt feldolgozásának gyakorisága a LinkedIn-en

A LinkedIn az Attarct kötegelt feladatait naponta egyszer dolgozza fel. Emiatt akár 48 óráig is eltarthat, amíg megjelennek a munkák a LinkedIn felületén az Attracat megoldással történő feladásuk után. Ha a LinkedIn alkalmazásban a feladatoknak hamarabb meg kell jelennie, vagy ha további rugalmasságra van szüksége, akkor használhatja a Recruiter System Connect API-t a LinkedIn-től. További információ [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect).

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Beállítások táblázata a LinkedIn álláshirdetésekhez

A következő táblázatban a különböző lehetőségek láthatók állások közzétételéhez a LinkedIn felületére. Az egyes lehetőségek és előnyeit és további információkat is tartalmaz.

|  | Attract | Job Wrapping a LinkedIn Recruiter megoldáson keresztül | Recruiter System Connect API használatával |
|---|---|---|---|
| **Leírás** | Az Attract XML-csatornaként ad fel állásokat LinkedIn felületére. | A vállalat szerződik a LinkedIn-nel és biztosítja az XML-csatornát az állások feladásához. | A vevő az API-t használja az Attract és a LinkedIn Recruiter között az adatok szinkronizálására. |
| **Milyen típusú állást lehet feladni?** | Korlátozott hirdetés | Premium Job Slot vagy Limited Listing | Korlátozott hirdetés |
| **Népszerűsíthetem az állást a LinkedIn-en?** | Nem | Premium Job Slotok: Igen<br>Limited Listingek: Nem | Nem |
| **Milyen gyakran történik a LinkedIn állások feladása?** | Naponta egyszer | Naponta egyszer | Naponta többször, az API által meghatározott módon |
| **A LinkedIn javasolta?** | Nem | Igen | Nem |
| **Mit kell tennem?** | Az Attract megvásárlása | Job wrapping zserződés kötése a LinkedIn-nel és Premium Job Slotok vásárlása | A LinkedIn-rel kötött API-megállapodás | 
| **Hol található további információ** | [A LinkedIn integrációjának beállítása](./attract-admin-linkedin.md) | [Job Wrapping a LinkedIn Recruiter megoldáson keresztül – Áttekintés](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> Nem szükséges LinkedIn Recruiter System Connect licencet beszereznie ahhoz, hogy állásokat tegyen közzé a LinkedIn-en az Attract használatával.

## <a name="see-also"></a>Lásd még

[A LinkedIn integrációjának beállítása](./attract-admin-linkedin.md)

[Állások feladása a LinkedIn felületére az Attract szolgáltatásból](./attract-post-jobs-to-linkedin.md)

[Jelöltek felkutatása a LinkedIn Recruiter segítségével](./attract-linkedin-recruiter.md)

[A LinkedIn integrációjának hibaelhárítása](./attract-troubleshoot-linkedin.md)
