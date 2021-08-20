---
title: Harmadik fél alkalmazások beágyazása
description: Ez a témakör azt mutatja be, hogyan végezhető el a harmadik fél alkalmazások beágyazása a termék funkcionalitásának kibővítése érdekében.
author: jasongre
ms.date: 04/22/2021
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
ms.openlocfilehash: f47fb6a2fdb586fbc9f25938c3b9c1cfc16ddc1af432b91621421bd829b23925
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737799"
---
# <a name="embed-third-party-apps"></a>Harmadik fél alkalmazások beágyazása

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Sok ügyfél különféle alkalmazások használatával végzi üzleti tevékenységét. Az alkalmazások közül vannak olyan harmadik fél alkalmazások, amelyek a Finance and Operations alkalmazásokkal együtt működnek. A felhasználói felület problémamentesebb használata érdekében az **(Előzetes verzió) Teljes oldalas alkalmazások** funkció használatával közvetlenül beágyazhatja ezeket a harmadik fél alkalmazásokat a saját Finance and Operations alkalmazásaiba (feltéve, hogy a harmadik fél alkalmazások engedélyezik a beágyazásukat). Így a felhasználók anélkül is elérhetik a szükséges webhelyeket és alkalmazásokat, hogy a fülek vagy ablakok között kellene ingázniuk.

Mielőtt harmadik fél alkalmazásokat ágyazna be a termékbe, be kell kapcsolnia a Funkciókezelésben az **(Előzetes verzió) Teljes oldalas alkalmazások** funkciót. Ezután a következő módszerek egyikével beágyazhat egy harmadik fél alkalmazást vagy webhelyet. Ezek a módszerek hasonlóak ahhoz a módszerhez, amely a vászonalapú alkalmazásokat beágyazza a Microsoft Power Apps szolgáltatásból a Finance and Operations alkalmazásokba.

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
7. Győződjön meg arról, hogy az alkalmazás a vártnak megfelelően jelenik meg. Ha az alkalmazás nincs renderelve, akkor tekintse meg témakör későbbi [Hibaelhárítás](#troubleshooting) szakaszát.
8. Nyissa meg a nézetválasztót, és válassza a **Mentés** (ha az alkalmazást az aktuális nézethez kell társítani) vagy a **Mentés másként** lehetőséget (ha az alkalmazást másik nézetbe szeretné menteni).

    Ha az oldalnak nincs nézetválasztója (például párbeszédpanel vagy munkaterület), ezt a lépést kihagyhatja.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Webhely beágyazása teljes képernyős élményként az irányítópultból

Akkor használja ezt az eljárást, ha a beágyazni kívánt alkalmazás nem létező laphoz kapcsolódik, vagy ha a Finance and Operations alkalmazáson belül teljes képernyős élményre van szükség.

1. Nyissa meg az irányítópultot.
2. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombra) az oldalt, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap hozzáadása** lehetőséget.
3. A **Lap hozzáadása** panelen válassza a **Webhely** lehetőséget.
4. Beágyazott alkalmazás konfigurálása:

    - **Név** – Adja meg azt a szöveget, amelyet az irányítópult beágyazott alkalmazásához hozzáadott csempén szeretne megjelentetni. Gyakran hasznos, ha ez a szöveg az alkalmazás neve.
    - **URL** – Adja meg az alkalmazás helyét.

    > [!IMPORTANT]
    > - Biztonsági okokból az URL-címnek HTTPS-t kell használnia.
    > - Az alkalmazást vagy webhelyet úgy kell konfigurálni, hogy lehetővé tegye a saját beágyazását.

5. A **Mentés** gombra kattintva új csempeként hozzáadhatja az alkalmazást a irányítópulthoz.
6. Válassza ki az új csempét az irányítópult, és győződjön meg arról, hogy az alkalmazás a vártnak megfelelően jelenik meg. Ha az alkalmazás nincs renderelve, akkor tekintse meg témakör későbbi [Hibaelhárítás](#troubleshooting) szakaszát.

## <a name="sharing-embedded-apps"></a>A beágyazott alkalmazások megosztása

Miután az előző részekben ismertetett valamelyik módszerrel beágyazott egy alkalmazást, érdemes lehet a nézetet megosztani a rendszer más felhasználóival. Beágyazott alkalmazás megosztásához használja a következő módszerek egyikét:

- **Nézet közzététele (Ajánlott):** Ha a beágyazott alkalmazást elmentették egy nézetbe, a megosztás javasolt és preferált módja a nézet közzétételének a megfelelő biztonsági szerepkörekkel rendelkező felhasználók számára. Majd minden olyan felhasználó, aki a közzétett nézet által tervezett biztonsági szerepkörökkel rendelkezik, látja az alkalmazást a Finance and Operations alkalmazások képernyőjén. További információért a nézet közzétételéhez lásd a [Nézetek közzététele](saved-views.md#publishing-views) lehetőséget.

    Olyan alkalmazást is közzé lehet tenni, amely teljes képernyős élményként van beágyazva az irányítópultról. Az irányítópulton jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombbal) az alkalmazáshoz társított csempét, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap közzététele** lehetőséget. Jelenleg csak biztonsági szerepkörökhöz tud közzétenni. A jogi személyek számára való közzétételt azonban csak azt megelőzően lehet hozzáadni, hogy a funkció általánosan elérhetővé válik.

- **Személyre szabás másolása:** Olyan lapok esetén, amelyek nem támogatják a nézeteket (például párbeszédpanelek vagy munkaterületek), vagy a teljes oldalas alkalmazással való használatnál, átmásolhatja a személyre szabást a megfelelő felhasználókhoz. A további tudnivalókat lásd: [Személyre szabások megosztása](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>A beágyazott alkalmazások megtekintése

Egy beágyazott alkalmazás megtekintéséhez egy lapon a Finance and Operations alkalmazásokban, nyissa meg a beágyazott alkalmazást tartalmazó oldalt. Ne felejtse el, hogy egyes oldalakon a beágyazott alkalmazásokat a szokásos Művelet ablaktábla **Power Apps** gombján keresztül érheti el. Másik lehetőségként megjelenhetnek közvetlenül egy oldalon új lap, gyorslap vagy lapát, illetve a munkaterület új szakasza formájában.

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

Bár ez a témakör a harmadik fél alkalmazások és webhelyek személyre szabáson keresztüli beágyazására összpontosít, a fejlesztők a Visual Studio fejlesztői élmény segítségével egy űrlapba is beágyazhatják őket. Csak adjon hozzá a **WebsiteHostControl** vezérlőt az űrlaphoz. A vezérlőhöz elérhető metaadat-tulajdonságok a személyre szabási élményekkel azonos lehetőségeket biztosítanak.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
