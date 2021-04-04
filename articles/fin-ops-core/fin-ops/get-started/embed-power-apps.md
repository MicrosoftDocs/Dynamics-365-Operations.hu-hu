---
title: 'Vászonalapú alkalmazások beágyazása a következőből: Power Apps'
description: Ez a témakör azt mutatja be, hogyan végezhető el a vászonalapú alkalmazás Microsoft Power Apps szolgáltatásból az ügyfélbe történő beágyazása a termék funkcionalitásának kibővítése érdekében.
author: jasongre
manager: AnnBe
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: f8c7ad4322de594a06a09102c8eb7d09299d1d71
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564784"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Vászonalapú alkalmazások beágyazása a következőből: Power Apps

[!include [banner](../includes/banner.md)]

A Microsoft Power Apps egy olyan szolgáltatás, amely a fejlesztők és a nem műszaki felhasználók számára is lehetővé teszi egyedi üzleti alkalmazások megalkotását mobileszközökre, táblagépekre és internetre, kód írása nélkül. A Finance and Operations alkalmazások támogatják a Power Apps szolgáltatással való integrációt. A vászonalapú alkalmazások, amelyeket Ön, a szervezete vagy a szélesebb ökoszisztéma által kifejlesztett alkalmazások beilleszthetők a Finance and Operations alkalmazásokba, hogy kiterjesszék a termék funkcionalitását. Például létrehozhat egy Power Apps vászonalapú alkalmazást egy Finance and Operations alkalmazás kiegészítésére egy másik rendszerből lekért információkkal.

Ha többet szeretne megtudni a Power Apps beágyazásáról, nézze meg a rövid [A Power Apps beágyazása a rendszerben](https://www.youtube.com/watch?v=x3qyA1bH-NY) videót.

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Beágyazott vászonalapú alkalmazás Power Apps megoldáshoz hozzáadása egy oldalhoz

### <a name="overview"></a>Áttekintés

Mielőtt Power Apps-ból vászonalapú alkalmazást ágyazna be a kliensbe, meg kell találnia vagy létre kell hoznia egy alkalmazást a kívánt megjelenéssel vagy funkcionalitással. Ez a témakör nem tartalmazza az alkalmazások készítéséhez szükséges folyamat részletes leírását. Ha még nem járatos a Power Apps terén, akkor tekintse meg a [Power Apps-dokumentációt](https://docs.microsoft.com/powerapps/).

Kétféle módszer érhető el egy adott vászonalapú alkalmazás számára egy oldalon, amikor készen áll az alkalmazás beágyazására. Kiválaszthatja, hogy melyik a megközelítés illik a legjobban az Ön helyzetéhez. Az első megközelítés a **Power Apps** gombot használja, amely hozzá lett adva a szokásos műveletpanelhez. Az ezzel a megközelítéssel hozzáadott alkalmazások a **Power Apps** menü gombjának elemeiként jelennek meg. Ha kiválaszt egyet az elemek közül, akkor megnyílik a beágyazott alkalmazást tartalmazó oldalsó ablaktábla. Másik lehetőségként választhatja az alkalmazás beágyazását közvetlenül egy oldalon új lap, gyorslap vagy lapát, illetve a munkaterület új szakasza formájában.

A beágyazott alkalmazás konfigurálásakor a vászonalapú alkalmazásban kiválaszthat egyetlen olyan mezőt, amelyet el szeretne küldeni az alkalmazásba kontextusként. Ez a lépés lehetővé teszi, hogy az alkalmazás az aktuálisan megtekintett adatok alapján legyen válaszképes.

> [!NOTE]
> Ez a mechanizmus jelenleg nem használható a modellezett alkalmazások beágyazására.  

### <a name="details"></a>Részletek

Az alábbi eljárás megmutatja, hogyan történik a vászonalapú alkalmazás Power Apps-be beágyazása a webes ügyfélbe.

1. Lépjen arra az oldalra, ahol be szeretné ágyazni a vászonalapú alkalmazást. Ez az oldal bármilyen olyan adatot tartalmaz, amelyet át kell adni az alkalmazás számára bemenetként.
2. Nyissa meg az **Alkalmazás hozzáadása a Power Apps-ból** lapot:

    - Kattintson a **Beállítások** elemre, majd válassza az **Oldal személyre szabása** elemet. A **Beszúrás** menü alatt válassza a **Power Apps** lehetőséget. Végül válassza ki a területet, ahova az alkalmazást hozzá kívánja adni. Ha az alkalmazást a Power Apps menügomb alá szeretné beágyazni, válassza a műveletpanelt. Ha szeretné közvetlenül a lapra beágyazni az alkalmazást, válassza ki a megfelelő lapot, gyorslapot, lapátot vagy szakaszt (ha munkaterületen tartózkodik).
    - Ha az alkalmazás a Power Apps menügomb segítségével lesz érhető, a normál Műveletpanelen kattintson a **Power Apps** menügombra, majd válassza az **Alkalmazás hozzáadása** lehetőséget.

3. Beágyazott alkalmazás konfigurálása:

    - A **Név** mező jelzi annak a gombnak vagy lapnak a megjelenő szövegét, amely tartalmazza a beágyazott alkalmazást. Gyakran érdemes megismételni az alkalmazás nevét ebben a mezőben.
    - Az **Akalmazás aznonosítója** mező a beágyazni kívánt vászonalapú alkalmazás globálisan egyedi azonosítóját (GUID) adja meg. Az érték lekérdezéséhez keresse meg az alkalmazást a [make.powerapps.com](https://make.powerapps.com) oldalon, majd keresse meg az **Alkalmazás azonosítója** mezőt a **Részletek** alatt.
    - Az **Alkalmazás kontextusának bevitele** elemnél kiválaszthatja azt a mezőt, amely az alkalmazás számára bemenetként továbbítandó adatokat tartalmazza. Lásd a következő című részt a témakör későbbi részében: [A Finance and Operations alkalmazásokból küldött adatokat használó alkalmazás felépítése](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) arról, hogy az alkalmazás hogyan elérheti el a Finance and Operations alkalmazásból továbbított adatokat.
    - Válassza azt az **Alkalmazásméretet**, amely megfelel a beágyazott alkalmazás típusának. Válassza ki **Vékony** lehetőséget a mobileszközök számára épített alkalmazások, és a **Széles** lehetőséget a táblagépekhez létrehozott alkalmazások esetében. Ez biztosítja, hogy a beágyazott alkalmazás számára elegendő mennyiségű hely kerül kiosztásra.
    - A **Jogi személyek** gyorslap teszi lehetővé annak a kiválasztását, hogy melyik jogi személyekre nézve érhető el az alkalmazás. Alapértelmezés szerint a alkalmazás minden jogi személy számára hozzáférhető. Ez a lehetőség csak akkor érhető el, ha le van tiltva a [Mentett nézetek](saved-views.md) funkció. 

4. Miután megerősítette, hogy a konfiguráció helyes, kattintson a **Beszúrás** elemre a Power App oldalba való beágyazásához. A rendszer rákérdez a böngésző frissítésére ahhoz, hogy megjelenjen a beágyazott alkalmazás.

## <a name="sharing-an-embedded-app"></a>A beágyazott alkalmazás megosztása

Miután beágyazott egy vászonalapú alkalmazást egy oldalra, és meggyőződött, hogy megfelelően működik az oldalról átadott adatkontextusokkal, érdemes megosztani a rendszer többi felhasználójával. Egy beágyazott vászonalapú alkalmazás megosztásához kövesse az alábbi lépéseket.

1. [Ossza meg a vászonalapú alkalmazást](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) a megfelelő felhasználókkal, hogy hozzáférhessenek az alkalmazáshoz a Power Apps szolgáltatásban. 

2. Győződjön meg róla, hogy a megcélzott felhasználók rendelkeznek a megfelelő testreszabásokkal, így a beágyazott alkalmazás akkor jelenik meg, amikor a felhasználók megtekintik az oldalt. A következő megközelítések közül választhat:

    - Ajánlott: Használja a [Mentett nézetek](saved-views.md) funkciót a beágyazott alkalmazást tartalmazó nézet létrehozásához és közzétételéhez. Ez a megközelítés biztosítja, hogy minden olyan felhasználó, aki a közzétett nézet által tervezett biztonsági szerepkörökkel rendelkezik, lássa az alkalmazást a Finance and Operations alkalmazások képernyőjén. 
    - Ha nincs bekapcsolva a Mentett nézetek funkció, akkor a rendszergazda elküldheti a beágyazott alkalmazást tartalmazó személyre szabást minden felhasználónak vagy a felhasználók egy részhalmazának. Másik lehetőségként exportálhatja az oldal személyre szabásait, és elküldheti őket egy vagy több felhasználónak. Ezután ezek a felhasználók importálhatják a saját személyre szabásaikat. A személyre szabási eszköztáron található műveletek segítségével végezhető el a személyes beállítások exportálása és importálása. 
    
> [!NOTE]
> Ha a vászonalapú alkalmazást külső felhasználókkal osztották meg, akkor ezek a felhasználók nem használhatják a beágyazott alkalmazást a Finance and Operations alkalmazásokon belül. Az alkalmazást azonban közvetlenül a Power Appsen belül elérhetik. A külső felhasználók azok a vendégek és felhasználók, akik nem tartoznak a Microsoft 365 Azure Directory-hoz ott, ahova telepítették a Finance and Operations alkalmazást.

A termék személyre szabási funkcióival és a használatukkal kapcsolatos bővebb információért lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>A Finance and Operations alkalmazásokból küldött adatokat használó vászonalapú alkalmazás építése

Amikor egy Finance and Operations alkalmazásba beágyazott vászonalapú alkalmazást hoz létre, akkor a folyamat egyik fontos része, hogy használja az adott Finance and Operations alkalmazásból származó bemeneti adatokat. A Power Apps fejlesztői élményből a Finance and Operations alkalmazás által átadott bemeneti adat a **Param(„EntityId”)** változó használatával érhető el.

Például az alkalmazás OnStart függvényében a Finance and Operations alkalmazásokból származó bemeneti adatokat egy változóra állíthatja be:

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-a-canvas-app"></a>Vászonalapú alkalmazás megtekintése

Egy beágyazott alkalmazás megtekintéséhez egy lapon a Finance and Operations alkalmazásokban, ugorjon a beágyazott vászonalapú alkalmazás oldalára. Ne felejtse el, hogy az alkalmazásokat a szokásos Művelet ablaktábla **Power Apps** gombján keresztül érheti el. Másik lehetőségként megjelenhetnek közvetlenül egy oldalon új lap, gyorslap vagy lapát, illetve a munkaterület új szakasza formájában. Amikor a felhasználók először megpróbálnak betölteni egy alkalmazást egy oldalon, a rendszer meg fogja kérni őket, hogy jelentkezzenek be. Ez a lépés biztosítja, hogy a felhasználók megfelelő jogosultságokkal rendelkeznek az alkalmazás használatához.

## <a name="editing-an-embedded-app"></a>Beágyazott alkalmazás szerkesztése

Egy alkalmazás egy oldalba ágyazását követően előfordulhat, hogy módosítania kell az alkalmazás konfigurációját. Például, esetleg módosítani szeretné a beágyazott alkalmazáshoz társított címkét, vagy létrejött az alkalmazás új verziója, és frissítenie kell az alkalmazásazonosítót, hogy a legújabbra mutasson.

Beágyazott alkalmazás konfigurációjának módosításához kövesse az alábbi lépéseket:

1. Lépjen az **Alkalmazás szerkesztése** panelre.

    - A beágyazott alkalmazás a Power Apps menügombbal érhető el: kattintson a jobb gombbal a Power Apps menügombra, és válassza a **Személyre szabás** lehetőséget. Jelölje ki az **Alkalmazás kiválasztása** legördülő menüből a konfigurálni kívánt alkalmazást.
    - Ha a beágyazott alkalmazás közvetlenül az oldalon jelenik meg, válassza a **Beállítások** lehetőséget, majd az **Oldal személyre szabása** elemet. Használja a **Kiválasztás** eszközt, kattintson a beágyazott alkalmazásra.

2. Végezze el a szükséges módosításokat az alkalmazáskonfiguráción, és kattintson a **Mentés** elemre.

## <a name="removing-an-app"></a>Egy alkalmazás eltávolítása

Egy alkalmazás oldalba ágyazását követően szükség esetén kétféle módon távolíthatja el azt:

- Lépjen az **Alkalmazás szerkesztése** panelre, a jelen cikk fenti, [Beágyazott alkalmazás szerkesztése](#editing-an-embedded-app) részében olvasható módon. Győződjön meg róla, hogy az ablaktáblában az eltávolítani kívánt beágyazott alkalmazás adatai láthatók, majd kattintson a **Törlés** gombra.
- Mivel a beágyazott alkalmazás mentése személyre szabási adatokként történik, az oldal személyre szabásának törlése az összes az oldalba beágyazott alkalmazásokat szintén eltávolítja. Vegye figyelembe, hogy a lap személyre szabása végleges, és nem vonható vissza. Ha el szeretné távolítani egy lap személyes beállításait, válassza a **Lehetőségek** elemet, majd kattintson az **Oldal személyre szabása** elemre, végül kattintson a **Törlés** gombra. A böngésző frissítése után az oldal összes korábbi személyre szabási beállítása eltávolításra kerül. A lapok személyre szabással való optimalizációjával kapcsolatos további tudnivalók: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="appendix"></a>Melléklet

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Fejlesztői] Egy alkalmazás beágyazásának helymeghatározása

Alapértelmezés szerint a felhasználók minden lapon beágyazhatnak alkalmazásokat vagy a Power Apps menügombbal, vagy közvetlenül az oldalon lap, gyorslap, lapát vagy munkaterület új szakasza formájában. Szükség esetén azonban a fejlesztők beállíthatják ezt a funkciót úgy is, hogy csak az alkalmazások egyes oldalakon történő beágyazását engedélyezze az alábbi módszerek végrehajtásával:

- **isPowerAppPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a Power Apps menügomb nem lesz látható, a felhasználók nem tudnak beágyazni alkalmazásokat sehova ezen az oldalon, lapként sem.
- **isPowerAppTabPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a felhasználók nem tudnak alkalmazásokat beágyazni közvetlenül az oldalon sem lapként, sem gyorslapként, sem panorámaszakaszként. A felhasználók továbbra is beágyazhatják az alkalmazásokat a Power Apps menügombbal, ha az oldalon megengedett a beágyazás.

A következő példa bemutat egy új osztályt a két konfigurálandó metódussal, ahol alkalmazások ágyazhatók be.

```powerapps
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]