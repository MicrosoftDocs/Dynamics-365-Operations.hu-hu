---
title: A Power Apps beágyazása
description: Ez a témakör leírja, hogyan végezhető el a Power Apps beágyazása az ügyfélbe a termék funkcionalitásának kibővítése érdekében.
author: jasongre
manager: AnnBe
ms.date: 09/20/2019
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
ms.openlocfilehash: 755a30f89725ca0a7e1c14252984c617d6ba280e
ms.sourcegitcommit: 4162d9ef4239c9d4e5297b8aaa903dd54f9cafc3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/21/2019
ms.locfileid: "2824493"
---
# <a name="embed-microsoft-power-apps"></a>A Microsoft Power Apps beágyazása

[!include [banner](../includes/banner.md)]

A 14-es platformfrissítés támogatja a Microsoft Power Apps integrációt, amely egy fejlesztők és nem szakember felhasználók számára készült szolgáltatás, amellyel egyedi üzleti alkalmazások készíthetők mobilkészülékekre, táblagépekre és a webre, kód írása nélkül. Ön, a szervezete vagy a szélesebb ökoszisztéma által kifejlesztett Power Apps alkalmazások beilleszthetők a Finance and Operations alkalmazásokba, hogy kiterjesszék a termék funkcionalitását. Létrehozhat például egy Power App alkalmazást a Finance and Operations-alkalmazások adatainak egy másik rendszerből lekért információkkal való kiegészítéséhez.

Ha többet szeretne megtudni a Power Apps beágyazásáról, nézze meg a rövid [A Power Apps beágyazása a rendszerben](https://www.youtube.com/watch?v=x3qyA1bH-NY) videót.

## <a name="adding-an-embedded-power-app-to-a-page"></a>Beágyazott Power App hozzáadása egy oldalhoz

### <a name="overview"></a>Áttekintés

Mielőtt Power Appot ágyazna be az ügyfélbe, először meg kell találnia vagy létre kell hoznia a kívánt megjelenéssel és/vagy funkciókkal rendelkező Power Appot. Itt nem írjuk le a Power App-építés részletes folyamatát. A [Power Apps – bevezetés](https://docs.microsoft.com/powerapps/getting-started) témakör jó kiindulási pont el, ha még nem használta a Power Apps megoldást.

Ha készen áll egy adott Power App beágyazására, két lehetőség közül választhat a Power App adott lapon való eléréséhez (annak megfelelően válasszon, hogy melyik illeszkedik jobban az igényeihez). Az első módszer a Power Apps gomb használata, amely hozzá lett adva a szokásos műveletpanelhez. Ily módon hozzáadott Power Apps alkalmazások a Power Apps menügombon belüli menüben jelennek meg. Kiválasztása esetén a menüpontok mindegyike olyan oldalsó ablaktáblát nyit meg, amelyen a beágyazott Power App található. Másik lehetőségként választhatja a Power App közvetlen megjelenítését egy oldalon új lap, gyorslap, panel vagy munkaterület-szakasz formájában.

A beágyazott Power App beállításakor az alkalmazásban kiválaszthat egyetlen olyan mezőt, amelyet el szeretne küldeni a Power App számára bevitelként. Ez lehetővé teszi, hogy a Power App az aktuálisan megtekintett adatok alapján legyen válaszképes.

### <a name="details"></a>Részletek

Az alábbi utasítások azt mutatják be, hogyan történik a Power App beágyazása a webes ügyfélbe.

1. Lépjen arra az oldalra, ahol be szeretné ágyazni a Power Appot. Ez az az oldal lesz, amely olyan adatokat tartalmaz, amelyeket át kell adni a Power App számára bemenetként.
2. Nyissa meg a **Power App beszúrása** ablakot:

    - Kattintson a **Beállítások** elemre, majd válassza a **Képernyő személyre szabása** elemet. A **Beszúrás** menüben válassza a **Power App** lehetőséget. Végül válassza ki a területet, ahova a Power Appot hozzá kívánja adni. Ha a Power App alkalmazást a Power Apps menügomb alá szeretné beágyazni, válassza a műveletpanelt. Ha közvetlenül a lapra szeretné beágyazni a Power App alkalmazást, válassza ki a megfelelő lapot, gyorslapot, panelt vagy szakaszt (ha munkaterületen tartózkodik).
    - Ha a Power App a Power Apps menügomb segítségével lesz érhető, a normál Műveletpanelen kattintson a **Power Apps** menügombra, majd válassza a **Power App beszúrása** lehetőséget.

3. Beágyazott Power App konfigurálása:

    - A **Név** mező jelzi annak a gombnak vagy lapnak a megjelenő szövegét, amely tartalmazza a beágyazott Power Appot. Gyakran érdemes megismételni a Power App nevét ebben a mezőben.
    - **Alkalmazás azonosítója:** a beágyazni kívánt Power App GUID azonosítója. Az érték lekérdezéséhez keresése meg a Power App alkalmazást a [web.powerapps.com](https://web.powerapps.com) oldalon, majd keresse meg az **Alkalmazás azonosítója** mezőt a **Részletek** területen.
    - A **Power App adatbevitel** elemnél kiválaszthatja azt a mezőt, amely a Power App számára bemenetként továbbítandó adatokat tartalmazza. Arról, hogy a Power App hogyan elérheti el a Finance and Operations-alkalmazásokból továbbított adatokat, a cikk későbbi részén olvashat: [A Finance and Operations-alkalmazások adatait használó Power App felépítése](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations-apps).
    - Válassza azt az **Alkalmazásméretet**, amely megfelel a beágyazott Power App típusának. Válassza ki **Vékony** lehetőséget a mobileszközök számára épített Power Apps, és a **Széles lehetőséget** a táblagépekhez létrehozott Power Apps esetében. Ez biztosítja, hogy a beágyazott Power App számára elég terület kerüljön kiosztásra.
    - A **Jogi személyek** gyorslapon választható ki, hogy melyik jogi személyek számára legyen elérhető a Power App. Alapértelmezés szerint a Power App minden jogi személynél megjelenik.

4. Miután megerősítette, hogy a konfiguráció helyes, kattintson a **Beszúrás** elemre a Power App oldalba való beágyazásához. A rendszer kéri a böngésző frissítését, hogy megjelenjen a beágyazott Power App.

## <a name="sharing-an-embedded-power-app"></a>A beágyazott Power App megosztása

Miután beágyazott egy Power App alkalmazást egy oldalra, és meggyőződött, hogy megfelelően működik az oldalról átadott adatkontextusokkal, érdemes megosztani a beágyazott Power App alkalmazást a rendszer többi felhasználójával. Ez kétféleképpen érhető el a termék személyre szabási képességeinek használatával:

- Az ajánlott forgatókönyv a rendszergazdán keresztüli lebonyolítás, aki a személyre szabást közzéteheti az összes felhasználónak vagy a felhasználók egy részhalmazának.
- Alternatívaként exportálhatja az oldal személyre szabásait, elküldheti őket egy vagy több felhasználónak, és e felhasználók mindegyike importálhatja a módosításokat. A személyre szabási eszköztáron található Kezelése opcióval bonyolítható a személyes beállítások exportálása és importálása.

A termék személyre szabási funkcióival és a használatukkal kapcsolatos bővebb információért lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások adatait használó Power App felépítése

A Finance and Operations-alkalmazásokba beágyazott Power App felépítésének fontos része a Finance and Operations-alkalmazások beviteli adatainak felhasználása. A Power App alkalmazáson belül a bemeneti adatok a Param("EntityId") változó segítségével érhetők el.

Például a Power App OnStart függvényében a Finance and Operations-alkalmazásokból származó bemeneti adatokat egy változóra állíthatja be:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-power-app"></a>Beágyazott Power App megtekintése

Egy beágyazott Power App Finance and Operations-alkalmazásokban való megtekintéséhez, ugorjon a beágyazott Power App oldalára. Emlékezzünk vissza, hogy a Power Apps alkalmazások a Power Apps gombon keresztül érhetők el a normál műveletpanelen, vagy megjelenhetnek közvetlenül új lapként, gyorslapként, lapátként vagy munkaterület új részeként. Amikor egy felhasználó először próbál betölteni egy oldalon egy Power App alkalmazást, a rendszer megkéri a Power Apps rendszerbe való bejelentkezésre; így ellenőrizhető, hogy a felhasználó rendelkezik a megfelelő engedélyekkel a Power App futtatásához.

## <a name="editing-an-embedded-power-app"></a>Beágyazott Power App szerkesztése

Egy Power App oldalba ágyazását követően előfordulhat, hogy módosítania kell a Power App konfigurációját. Lehet, hogy például módosítani szeretné a beágyazott Power App társított címkéjét, vagy a Power App új verziója érhető el, és frissíteni kell az alkalmazásazonosítót, hogy a legújabb a Power Appre mutasson.

Beágyazott Power App konfigurációjának módosításához kövesse az alábbi lépéseket:

1. Lépjen a **Power App szerkesztése** panelre.

    - A beágyazott Power App a Power Apps menügombbal érhető el: kattintson a jobb gombbal a Power Apps menügombra, és válassza a **Személyre szabás** lehetőséget. Jelölje ki a **Power App kiválasztása** legördülő menüből a konfigurálni kívánt Power Appet.
    - Ha a beágyazott Power App közvetlenül az oldalon jelenik meg, válassza a **Beállítások** lehetőséget, majd a **Képernyő személyre szabása** elemet. Használja a **Kiválasztás** eszközt, kattintson a beágyazott Power Appre.

2. Végezze el a szükséges módosításokat a Power Apps konfiguráción, és kattintson a **Mentés** elemre.

## <a name="removing-an-embedded-power-app"></a>Beágyazott Power App eltávolítása

Egy Power App oldalba ágyazását követően szükség esetén kétféle módon távolíthatja el az alkalmazást:

- Lépjen a **Power App szerkesztése** panelre, a jelen cikk fenti, [Beágyazott Power App szerkesztése](#editing-an-embedded-powerapp) részében olvasható módon. Győződjön meg róla, hogy az ablaktáblában az eltávolítani kívánt beágyazott Power App adatai láthatók, majd kattintson a **Törlés** gombra.
- Mivel a beágyazott Power App mentése személyre szabási adatokként történik, az oldal személyre szabásának törlése az összes az oldalba beágyazott Power Apps alkalmazásokat szintén eltávolítja. Vegye figyelembe, hogy a lap személyre szabása végleges, és nem vonható vissza. Ha el szeretné távolítani egy lap személyes beállításait, válassza a **Lehetőségek** elemet, majd kattintson a **Képernyő személyre szabása** elemre. A **Kezelés** menüben válassza a **Törlés** gombot. A böngésző frissítése után az oldal összes korábbi személyre szabási beállítása eltávolításra kerül. A lapok személyre szabással való optimalizációjával kapcsolatos további tudnivalók: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="appendix"></a>Melléklet

### <a name="developer-control-over-where-a-power-app-can-be-embedded"></a>A Power App beágyazási helyének fejlesztői ellenőrzése

Alapértelmezés szerint a felhasználók minden lapon beágyazhatnak Power Apps alkalmazásokat vagy a Power Apps menügombbal, vagy közvetlenül az oldalon lap, gyorslap, lapát vagy munkaterület új szakasza formájában. Szükség esetén azonban a fejlesztők beállíthatják ezt a funkciót úgy is, hogy csak a Power Apps alkalmazások egyes oldalakon történő beágyazását engedélyezze az alábbi módszerek végrehajtásával:

- **isPowerAppPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a Power Apps menügomb nem lesz látható, a felhasználók nem tudnak beágyazni Power Apps alkalmazást sehova ezen az oldalon, lapként sem.
- **isPowerAppTabPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a felhasználók nem tudnak Power Apps alkalmazásokat beágyazni közvetlenül az oldalon sem lapként, sem gyorslapként, sem panorámaszakaszként. A felhasználók továbbra is beágyazhatják a Power Apps alkalmazásokat a Power Apps menügombbal, ha az oldalon megengedett a beágyazás.

A következő példa bemutat egy új osztályt a két konfigurálandó metódussal, ahol a Power Apps beágyazható.

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
