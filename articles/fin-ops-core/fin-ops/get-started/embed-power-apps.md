---
title: A Power Apps beágyazása
description: Ez a témakör leírja, hogyan végezhető el a Power Apps beágyazása az ügyfélbe a termék funkcionalitásának kibővítése érdekében.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 9585d5a399ebf45b0ad7640f3c4e48d8afc46cd8
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017728"
---
# <a name="embed-microsoft-power-apps"></a>A Microsoft Power Apps beágyazása

[!include [banner](../includes/banner.md)]

A Finance and Operations támogatja a Microsoft Power Apps integrációt, amely egy fejlesztők és nem szakember felhasználók számára készült szolgáltatás, amellyel egyedi üzleti alkalmazások készíthetők mobilkészülékekre, táblagépekre és a webre, kód írása nélkül. Ön, a szervezete vagy a szélesebb ökoszisztéma által kifejlesztett Power Apps alkalmazások beilleszthetők a Finance and Operations alkalmazásokba, hogy kiterjesszék a termék funkcionalitását. Például létrehozhat egy Power Apps alkalmazást egy Finance and Operations alkalmazás kiegészítésére egy másik rendszerből lekért információkkal.

Ha többet szeretne megtudni a Power Apps beágyazásáról, nézze meg a rövid [A Power Apps beágyazása a rendszerben](https://www.youtube.com/watch?v=x3qyA1bH-NY) videót.

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Beágyazott alkalmazás Power Apps megoldáshoz hozzáadása egy oldalhoz

### <a name="overview"></a>Áttekintés

Mielőtt Power Apps-ból alkalmazást ágyazna be a kliensbe, először meg kell találnia vagy létre kell hoznia egy alkalmazást a kívánt megjelenéssel és/vagy funkcionalitással. Itt nem írjuk le az alkalmazásépítés részletes folyamatát. A [Power Apps – bevezetés](https://docs.microsoft.com/powerapps/getting-started) témakör jó kiindulási pont el, ha még nem használta a Power Apps megoldást.

Ha készen áll egy adott alkalmazás beágyazására, kétféle lehetőség közül választhat a hozzáférésnél a alkalmazáshoz a lapon, annak megfelelően, hogy melyik illeszkedik jobban a forgatókönyvhöz. Az első módszer a Power Apps gomb használata, amely hozzá lett adva a szokásos műveletpanelhez. Ily módon hozzáadott alkalmazások a Power Apps menügombon belüli menüben jelennek meg. Kiválasztás esetén a menüpontok mindegyike oldalsó ablaktáblát nyit meg, amely a beágyazott alkalmazást tartalmazza. Másik lehetőségként választhatja az alkalmazás beágyazását közvetlenül egy oldalon új lap, gyorslap, lapát vagy munkaterület új szakasza formájában.

A beágyazott alkalmazás beállításakor az alkalmazásban kiválaszthat egyetlen olyan mezőt, amelyet el szeretne küldeni az alkalmazásba kontextusként. Ez lehetővé teszi, hogy az alkalmazás az aktuálisan megtekintett adatok alapján legyen válaszképes.

### <a name="details"></a>Részletek

Az alábbi utasítások azt mutatják be, hogyan történik az alkalmazás Power Apps-ba beágyazása a webes ügyfélbe.

1. Lépjen arra az oldalra, ahol be szeretné ágyazni az alkalmazást. Ez ugyanaz az oldal lesz, amely bármilyen olyan adatot tartalma, amelyet át kell adni az alkalmazás számára bemenetként.
2. Nyissa meg az **Alkalmazás hozzáadása a Power Apps-ból** lapot:

    - Kattintson a **Beállítások** elemre, majd válassza az **Oldal személyre szabása** elemet. A **Beszúrás** menü alatt válassza a **Power Apps** lehetőséget. Végül válassza ki a területet, ahova az alkalmazást hozzá kívánja adni. Ha az alkalmazást a Power Apps menügomb alá szeretné beágyazni, válassza a műveletpanelt. Ha szeretné közvetlenül a lapra beágyazni az alkalmazást, válassza ki a megfelelő lapot, gyorslapot, lapátot vagy szakaszt (ha munkaterületen tartózkodik).
    - Ha az alkalmazás a Power Apps menügomb segítségével lesz érhető, a normál Műveletpanelen kattintson a **Power Apps** menügombra, majd válassza az **Alkalmazás hozzáadása** lehetőséget.

3. Beágyazott alkalmazás konfigurálása:

    - A **Név** mező jelzi annak a gombnak vagy lapnak a megjelenő szövegét, amely tartalmazza a beágyazott alkalmazást. Gyakran érdemes megismételni az alkalmazás nevét ebben a mezőben.
    - **Alkalmazás azonosítója:** a beágyazni kívánt alkalmazás GUID azonosítója. Az érték lekérdezéséhez keresése meg az alkalmazást a [web.powerapps.com](https://web.powerapps.com) oldalon, majd keresse meg az **Alkalmazás azonosítója** mezőt a **Részletek** alatt.
    - Az **Alkalmazás kontextusának bevitele** elemnél kiválaszthatja azt a mezőt, amely az alkalmazás számára bemenetként továbbítandó adatokat tartalmazza. Lásd a következő című részt a témakör későbbi részében: [A Finance and Operations alkalmazások adatait használó alkalmazás felépítése](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) arról, hogy az alkalmazás hogyan elérheti el a Finance and Operations alkalmazásból továbbított adatokat.
    - Válassza azt az **Alkalmazásméretet**, amely megfelel a beágyazott alkalmazás típusának. Válassza ki **Vékony** lehetőséget a mobileszközök számára épített alkalmazások, és a **Széles** lehetőséget a táblagépekhez létrehozott alkalmazások esetében. Ez biztosítja, hogy a beágyazott alkalmazás számára elegendő mennyiségű hely kerül kiosztásra.
    - A **Jogi személyek** gyorslap teszi lehetővé annak a kiválasztását, hogy melyik jogi személyekre nézve érhető el az alkalmazás. Alapértelmezés szerint a alkalmazás minden jogi személy számára hozzáférhető. Ez a lehetőség csak akkor érhető el, ha le van tiltva a [Mentett nézetek](saved-views.md) funkció. 

4. Miután megerősítette, hogy a konfiguráció helyes, kattintson a **Beszúrás** elemre a Power App oldalba való beágyazásához. A rendszer rákérdez a böngésző frissítésére ahhoz, hogy megjelenjen a beágyazott alkalmazás.

## <a name="sharing-an-embedded-app"></a>A beágyazott alkalmazás megosztása

Miután beágyazott egy alkalmazást egy oldalra, és meggyőződött, hogy megfelelően működik az oldalról átadott adatkontextusokkal, érdemes megosztani a rendszer többi felhasználójával. Ez kétféleképpen érhető el a termék személyre szabási képességeinek használatával:

- Az ajánlott forgatókönyv a rendszergazdán keresztüli lebonyolítás, aki a személyre szabást közzéteheti az összes felhasználónak vagy a felhasználók egy részhalmazának.
- Alternatívaként exportálhatja az oldal személyre szabásait, elküldheti őket egy vagy több felhasználónak, és e felhasználók mindegyike importálhatja a módosításokat. A személyre szabási eszköztáron található műveletekkel végezhető el a személyes beállítások exportálása és importálása.

A termék személyre szabási funkcióival és a használatukkal kapcsolatos bővebb információért lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>A Finance and Operations alkalmazásokból küldött adatokat kihasználó alkalmazás létrehozása

Fontos része az alkalmazás építésének a Power Apps-ból – amely be lesz ágyazva a Finance and Operations alkalmazásba – a bemeneti adatoknak az alkalmazásból történő felhasználása. A Power Apps fejlesztői élményből a Finance and Operations alkalmazás által átadott bemeneti adat a Param("EntityId") változó használatával érhető el.

Például az alkalmazás OnStart függvényében a Finance and Operations alkalmazásokból származó bemeneti adatokat egy változóra állíthatja be:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Egy alkamazás megtekintése

Egy beágyazott alkalmazás megtekintéséhez egy lapon a Finance and Operations alkalmazásokban, ugorjon a beágyazott alkalmazás oldalára. Emlékezzünk vissza, hogy az alkalmazások a Power Apps gombon keresztül érhetők el a normál műveletpanelen, vagy megjelenhetnek közvetlenül új lapként, gyorslapként, lapátként vagy munkaterület új részeként. Amikor egy felhasználó először próbál betölteni egy oldalon egy alkalmazást, a rendszer megkéri a bejelentkezésre; így ellenőrizhető, hogy a felhasználó rendelkezik a megfelelő engedélyekkel az alkalmazás futtatásához.

## <a name="editing-an-embedded-app"></a>Beágyazott alkalmazás szerkesztése

Egy alkalmazás egy oldalba ágyazását követően előfordulhat, hogy módosítania kell az alkalmazás konfigurációját. Például, esetleg módosítani szeretné a beágyazott alkalmazáshoz társított címkét, vagy létrejött az alkalmazás új verziója, és frissítenie kell az alkalmazásazonosítót, hogy a legújabbra mutasson.

Beágyazott alkalmazás konfigurációjának módosításához kövesse az alábbi lépéseket:

1. Lépjen az **Alkalmazás szerkesztése** panelre.

    - A beágyazott alkalmazás a Power Apps menügombbal érhető el: kattintson a jobb gombbal a Power Apps menügombra, és válassza a **Személyre szabás** lehetőséget. Jelölje ki az **Alkalmazás kiválasztása** legördülő menüből a konfigurálni kívánt alkalmazást.
    - Ha a beágyazott alkalmazás közvetlenül az oldalon jelenik meg, válassza a **Beállítások** lehetőséget, majd az **Oldal személyre szabása** elemet. Használja a **Kiválasztás** eszközt, kattintson a beágyazott alkalmazásra.

2. Végezze el a szükséges módosításokat az alkalmazáskonfiguráción, és kattintson a **Mentés** elemre.

## <a name="removing-an-app"></a>Egy alkalmazás eltávolítása

Egy alkalmazás oldalba ágyazását követően szükség esetén kétféle módon távolíthatja el azt:

- Lépjen az **Alkalmazás szerkesztése** panelre, a jelen cikk fenti, [Beágyazott alkalmazás szerkesztése](#editing-an-embedded-power-app) részében olvasható módon. Győződjön meg róla, hogy az ablaktáblában az eltávolítani kívánt beágyazott alkalmazás adatai láthatók, majd kattintson a **Törlés** gombra.
- Mivel a beágyazott alkalmazás mentése személyre szabási adatokként történik, az oldal személyre szabásának törlése az összes az oldalba beágyazott alkalmazásokat szintén eltávolítja. Vegye figyelembe, hogy a lap személyre szabása végleges, és nem vonható vissza. Ha el szeretné távolítani egy lap személyes beállításait, válassza a **Lehetőségek** elemet, majd kattintson az **Oldal személyre szabása** elemre, végül kattintson a **Törlés** gombra. A böngésző frissítése után az oldal összes korábbi személyre szabási beállítása eltávolításra kerül. A lapok személyre szabással való optimalizációjával kapcsolatos további tudnivalók: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="appendix"></a>Melléklet

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Fejlesztői ellenőrzés afölött, hogy hova ágyazható be egy alkalmazás

Alapértelmezés szerint a felhasználók minden lapon beágyazhatnak alkalmazásokat vagy a Power Apps menügombbal, vagy közvetlenül az oldalon lap, gyorslap, lapát vagy munkaterület új szakasza formájában. Szükség esetén azonban a fejlesztők beállíthatják ezt a funkciót úgy is, hogy csak az alkalmazások egyes oldalakon történő beágyazását engedélyezze az alábbi módszerek végrehajtásával:

- **isPowerAppPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a Power Apps menügomb nem lesz látható, a felhasználók nem tudnak beágyazni alkalmazásokat sehova ezen az oldalon, lapként sem.
- **isPowerAppTabPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a felhasználók nem tudnak alkalmazásokat beágyazni közvetlenül az oldalon sem lapként, sem gyorslapként, sem panorámaszakaszként. A felhasználók továbbra is beágyazhatják az alkalmazásokat a Power Apps menügombbal, ha az oldalon megengedett a beágyazás.

A következő példa bemutat egy új osztályt a két konfigurálandó metódussal, ahol alkalmazások ágyazhatók be.

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```
