---
title: Harmadik fél alkalmazások beágyazása
description: Ez a cikk bemutatja, hogy hogyan lehet beágyazni a külső alkalmazásokba a termék funkcióinak bővítésére.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ef5ed6c3c99d62010643940f3e2f158963ff0dc2
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2022
ms.locfileid: "9123718"
---
# <a name="embed-third-party-apps"></a>Harmadik fél alkalmazások beágyazása

[!include [banner](../includes/banner.md)]

Sok ügyfél különféle alkalmazások használatával végzi üzleti tevékenységét. Ezek közül a alkalmazások közül egyesek külső alkalmazások, amelyek a pénzügyi és műveleti alkalmazásokkal együtt működnek. A felhasználói felület problémamentesebb használata érdekében a Teljes oldalas alkalmazásokkal közvetlenül beágyazhatja ezeket a **külső** alkalmazásokat a pénzügyi és műveleti alkalmazásokba (feltéve, hogy a külső alkalmazások lehetővé teszik saját maguk beágyazát). Így a felhasználók anélkül is elérhetik a szükséges webhelyeket és alkalmazásokat, hogy a fülek vagy ablakok között kellene ingázniuk.

Mielőtt harmadik féltől származó alkalmazásokat ágyazhatna be a termékbe, a funkciókezelésben be kell kapcsolnia a **Teljes oldal alkalmazásai** funkciót. Ezután a következő módszerek egyikével beágyazhat egy harmadik fél alkalmazást vagy webhelyet. Ezek a módszerek hasonlóak ahhoz Microsoft Power Apps a módszerhez, amely a vásznas alkalmazásokat a pénzügyi és műveleti alkalmazásokba beágyazza.

- Az alkalmazás vagy webhely beágyazása meglévő lapra új lapként (kimutatás fül, gyorslap, panel vagy munkaterület rész).
- Új teljes képernyős élmény létrehozása alkalmazáshoz vagy webhelyhez az irányítópulton.

## <a name="embed-a-website-on-an-existing-page"></a>Webhely beágyazása meglévő lapra

Ezt az eljárást akkor használja, ha a rendszerben egy létező oldalt ki szeretne egészíteni egy alkalmazás beágyazásával.

1. Menjen arra az oldalra, ahol be szeretné ágyazni az alkalmazást.
2. Nyissa meg az **Alkalmazás hozzáadása** lapot:

    1. Válassza a **Beállítások**, majd a **Személyre szabás** lehetőséget a **Személyre szabábi** eszközsáv megnyitásához.
    2. Válassza a **További \> alkalmazás hozzáadása** lehetőséget.

3. Válassza ki az oldal régióját, ahova az alkalmazást hozzá kívánja adni. Ennek a régiónak egy kimutatáslap, gyorslap, panel vagy munkaterület rész *fültárolójának* kell lennie.
4. Válassza ki a **Webhely** lehetőséget.
5. Beágyazott alkalmazás konfigurálása:

    - **Név** – Írja be a szöveget, amit szeretne, ha a beágyazott alkalmazást tartalmazó lapnál megjelenne. Gyakran hasznos, ha ez a szöveg az alkalmazás neve.
    - **URL** – Adja meg az alkalmazás helyét.

    > [!IMPORTANT]
    > - Biztonsági okokból az URL-címnek HTTPS-t (Hypertext Transfer Protocol Secure) kell használnia.
    > - Az alkalmazást vagy webhelyet úgy kell konfigurálni, hogy lehetővé tegye a saját beágyazását.

6. Válassza a **Mentés** lehetőséget az alkalmazás lapon történő beágyazásához. Az alkalmazás a csoport utolsó füleként vagy részeként lesz hozzáadva.
7. Győződjön meg arról, hogy az alkalmazás a vártnak megfelelően jelenik meg. Ha az alkalmazás nem jelenik meg, a témakör későbbi [Hibaelhárítás szakaszában](#troubleshooting) olvashatja.
8. Nyissa meg a nézetválasztót, és válassza a **Mentés** (ha az alkalmazást az aktuális nézethez kell társítani) vagy a **Mentés másként** lehetőséget (ha az alkalmazást másik nézetbe szeretné menteni).

    Ha az oldalnak nincs nézetválasztója (például párbeszédpanel vagy munkaterület), ezt a lépést kihagyhatja.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Webhely beágyazása teljes képernyős élményként az irányítópultból

Ezt a műveletet akkor kell használni, ha a beágyazni kívánt alkalmazás nem létező laphoz kapcsolódik, vagy ha az alkalmazásnak csak egy teljes oldalas felhasználói élményre van szükség a pénzügy és a műveletek alkalmazáson belül.

1. Nyissa meg az irányítópultot.
2. Válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) az irányítópultot, válassza a **Testreszabás**, majd az **Oldal hozzáadása** lehetőséget.
3. A **Lap hozzáadása** panelen válassza a **Webhely** lehetőséget.
4. Beágyazott alkalmazás konfigurálása:

    - **Név** – Adja meg azt a szöveget, amelyet az irányítópult beágyazott alkalmazásához hozzáadott csempén szeretne megjelentetni. Gyakran hasznos, ha ez a szöveg az alkalmazás neve.
    - **URL** – Adja meg az alkalmazás helyét.

    > [!IMPORTANT]
    > - Biztonsági okokból az URL-címnek HTTPS-t kell használnia.
    > - Az alkalmazást vagy webhelyet úgy kell konfigurálni, hogy lehetővé tegye a saját beágyazását.

5. A **Mentés** gombra kattintva új csempeként hozzáadhatja az alkalmazást a irányítópulthoz.
6. Válassza ki az új csempét az irányítópult, és győződjön meg arról, hogy az alkalmazás a vártnak megfelelően jelenik meg. Ha az alkalmazás nem jelenik meg, a [témakör későbbi Hibaelhárítás szakaszában](#troubleshooting) olvashatja.

## <a name="sharing-embedded-apps"></a>A beágyazott alkalmazások megosztása

Miután az előző részekben ismertetett valamelyik módszerrel beágyazott egy alkalmazást, érdemes lehet a nézetet megosztani a rendszer más felhasználóival. Beágyazott alkalmazás megosztásához használja a következő módszerek egyikét:

- **A nézet közzététele (ajánlott):** Ha a beágyazott alkalmazás egy nézetbe lett mentve, a megosztás ajánlott és előnyben részesített módja a nézet közzététele a megfelelő biztonsági szerepkörrel rendelkező felhasználók számára a célzott jogalanyoknál. Ebben az esetben csak a kívánt felhasználók fogják látni a beágyazott alkalmazást az adott oldalon. További információért a nézet közzétételéhez lásd a [Nézetek közzététele](saved-views.md#publishing-views) lehetőséget.

    Olyan alkalmazást is közzé lehet tenni, amely teljes képernyős élményként van beágyazva az irányítópultról. Az irányítópulton jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombbal) az alkalmazáshoz társított csempét, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap közzététele** lehetőséget. Megjelenik egy, a *nézetek közzététele* élményhez hasonló élmény, és kiválaszthatja a közzéteendő biztonsági szerepköröket. A 10.0.21-es vagy újabb frissítésben, ha a **Mentett nézetek javított jogi személy támogatása** funkció be van kapcsolva, akkor az alkalmazást a kívánt jogi személyek számára is közzéteheti.

- **Személyre szabás másolása:** Olyan lapok esetén, amelyek nem támogatják a nézeteket (például párbeszédpanelek vagy munkaterületek), vagy a teljes oldalas alkalmazással való használatnál, átmásolhatja a személyre szabást a megfelelő felhasználókhoz. A további tudnivalókat lásd: [Személyre szabások megosztása](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>A beágyazott alkalmazások megtekintése

A pénzügyi és műveletalkalmazások egy lapján található beágyazott alkalmazás megtekintéséhez nyissa meg azt a lapot, amelybe a beágyazott alkalmazás van be ágyazva. Ne felejtse el, hogy egyes oldalakon a beágyazott alkalmazásokat a szokásos Művelet ablaktábla **Power Apps** gombján keresztül érheti el. Másik lehetőségként megjelenhetnek közvetlenül egy oldalon új lap, gyorslap vagy lapát, illetve a munkaterület új szakasza formájában.

## <a name="editing-or-removing-embedded-apps"></a>Beágyazott alkalmazások szerkesztése vagy eltávolítása

Miután az alkalmazás be lett ágyazva egy lapra, lehet, hogy módosítania kell a konfigurációját (például a szakasz címkéjének vagy URL-címének módosításával). Arra is lehetőség van, hogy eltávolítsa az oldalról. A következő eljárások valamelyikével szerkesztheti egy beágyazott alkalmazás konfigurációját, vagy teljesen el is távolíthatja azt.

### <a name="apps-that-are-embedded-on-existing-pages"></a>A meglévő lapokra ágyazott alkalmazások

1. Menjen arra az oldalra, ahol be van ágyazva az alkalmazás.
2. Válassza a **Beállítások**, majd a **Személyre szabás** lehetőséget a **Személyre szabábi** eszközsáv megnyitásához.
3. Válassza ki a **Kijelölés** eszközt, majd válassza ki a beágyazott alkalmazást.
4. Az alkalmazás szerkesztéséhez módosítsa a konfigurációját a szükséges változtatásokkal, majd kattintson a **Mentés** gombra.

    Vagy válassza a **Törlés** lehetőséget az alkalmazás eltávolításához.

5. A nézet ismételt mentése vagy ismételt közzététele. Ne feledje, hogy ha a nézet explicit mentése nélkül elhagyja a lapot, a **Webhely szerkesztése** ablakban végrehajtott műveletek egyike sem lesz megtartva.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>Az irányítópultr=l beágyazott alkalmazások

1. Nyissa meg az irányítópultot.
2. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombbal) a beágyazott alkalmazáshoz társított csempét, majd válassza a **Személyre szabás** lehetőséget.
3. Az alkalmazás szerkesztéséhez válassza a **Lap szerkesztése** lehetőséget. A **Weboldal szerkesztése** panelen módosítsa az alkalmazás konfigurációját a szükséges változtatásokkal, majd kattintson a **Mentés** gombra.

    Vagy válassza a **Lap eltávolítása** lehetőséget az alkalmazás eltávolításához.

## <a name="appendix"></a>Melléklet

### <a name="troubleshooting"></a>Hibaelhárítás

Ha egy webhely nem jelenik meg megfelelően a Finance and Operation alkalmazásba való beágyazás után, vagy ha egy hibaüzenet jelenik meg arról, hogy az URL-cím egy kapcsolata meg lett tagadva, akkor a webhely valószínűleg úgy van beállítva, hogy megakadályozza, hogy be legyen ágyazva egy iFrame-be. Kövesse az alábbi lépéseket ahhoz, hogy eldöntse, egy webhely beágyazható-e vagy sem.

1. Nyissa meg a használt böngésző fejlesztői eszközeit.
2. A **Hálózat** lapon keresse meg és válassza ki a választ a beágyazott webhelyről.
3. A **Fejlécek** fülön, a **Válaszfejlécek** alatt keresse meg az **x-keret beállítások** lehetőséget. Ha az **x-keret beállítások** a válaszfejlécben vannak, és a **DENY** vagy **SAMEORIGIN** értékkel rendelkezik, akkor a webhely jelenleg nem ágyazható be. A biztonságos beágyazás engedélyezéséhez együtt kell működnie az alkalmazás tulajdonosával.

### <a name="developer-modeling-a-website-on-a-form"></a>[Fejlesztő] Webhely modellezése egy űrlapon

Bár ez a cikk a külső alkalmazások és webhelyek személyre szabásán keresztül történő beágyazásán van fókuszálva, a Visual Studio fejlesztők a fejlesztői tapasztalat segítségével egy képernyőbe is beágyazhatja őket. Csak adjon hozzá a **WebsiteHostControl** vezérlőt az űrlaphoz. A vezérlőhöz elérhető metaadat-tulajdonságok a személyre szabási élményekkel azonos lehetőségeket biztosítanak.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

