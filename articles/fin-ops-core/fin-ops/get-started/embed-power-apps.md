---
title: 'Vászonalapú alkalmazások beágyazása a következőből: Power Apps'
description: Ez a cikk bemutatja, hogy hogyan lehet beágyazni a vásznaalkalmazásokat Microsoft Power Apps az ügyfélbe a termék funkcióinak bővítésére.
author: jasongre
ms.date: 09/13/2021
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
ms.openlocfilehash: fb81aa058e749df346ee87bbe83427b20b234b72
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898398"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Vászonalapú alkalmazások beágyazása a következőből: Power Apps

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

A Microsoft Power Apps egy olyan szolgáltatás, amely a fejlesztők és a nem műszaki felhasználók számára is lehetővé teszi egyedi üzleti alkalmazások megalkotását mobileszközökre, táblagépekre és internetre, kód írása nélkül. A Pénzügy és a Műveletek alkalmazások támogatják az integrációt a Power Apps. Az Ön, a szervezet vagy a szélesebb fejlesztésű alkalmazások beágyazhatók a Pénzügyi és műveleti alkalmazásokba a termék funkcióinak bővítésére. Például felépíthet egy Power Apps vásznaalkalmazást, amely egy másik rendszerből beolvasható adatokat tartalmaz a Pénzügy és műveletek alkalmazás kiegészítéseként.

Ha többet szeretne megtudni a vászonalapú alkalmazások beágyazásáról, nézze meg a rövid [Vászonalapú alkalmazások beágyazása](https://www.youtube.com/watch?v=x3qyA1bH-NY) videót.

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Beágyazott vászonalapú alkalmazás Power Apps megoldáshoz hozzáadása egy oldalhoz

Mielőtt Power Apps-ból vászonalapú alkalmazást ágyazna be a kliensbe, meg kell találnia vagy létre kell hoznia egy alkalmazást a kívánt megjelenéssel vagy funkcionalitással. Ez a cikk nem tartalmazza az alkalmazások gyártási folyamatának részletes leírását. Ha még nem járatos a Power Apps terén, akkor tekintse meg a [Power Apps-dokumentációt](/powerapps/).

A vásznai alkalmazásokat háromféleképpen lehet beágyazni a Pénzügy és műveletek alkalmazásba. Az Ön forgatókönyvéhez legjobban illeszkedő megközelítést alkalmazhatja. 

- A vászonalkalmazás beágyazása a **Power Apps** gombba az oldal standard műveleti ablaktábláján.. Az ilyen módon hozzáadott alkalmazások elemekként jelennek meg a **Power Apps** menügombon, és az alkalmazások oldalablakokban nyílnak meg. 
- A vászonalkalmazás beágyazása közvetlenül egy meglévő oldalra új lapként (pivot lap, gyorslap, lap vagy munkaterület szakasz).
- Hozzon létre egy új teljes oldalas élményt a vászonalkalmazáshoz az irányítópultról.

A beágyazott alkalmazás konfigurálásakor a vászonalapú alkalmazásban kiválaszthat egyetlen olyan mezőt, amelyet el szeretne küldeni az alkalmazásba kontextusként. Ez a lépés lehetővé teszi, hogy az alkalmazás az aktuálisan megtekintett adatok alapján legyen válaszképes.

> [!NOTE]
> Ezt a mechanizmust nem használhatja modellvezérelt alkalmazások beágyazására.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Vászonalkalmazás beágyazása egy meglévő oldalra

A következő eljárás azt mutatja be, hogyan lehet beágyazni egy vászonalkalmazást egy meglévő oldalra a Power Apps-ból.

1. Lépjen arra az oldalra, ahol be szeretné ágyazni a vászonalapú alkalmazást. Ez az oldal tartalmazza azokat az adatokat, amelyeket az alkalmazásnak bemenetként át kell adni.
2. Nyissa meg az **Alkalmazás hozzáadása a Power Apps-ból** lapot:

    - Ha az alkalmazás közvetlenül az oldalra lesz beágyazva, válassza a **Beállítások** \> **Az oldal testreszabása** \> **Továbbiak** elemet, majd kövesse az alábbi lépések egyikét:

        - Ha a **Teljes oldalas alkalmazások** funkció be van kapcsolva, válassza az **Oldal hozzáadása** lehetőséget, majd válassza ki azt a régiót, ahová az alkalmazást szeretné hozzáadni. Az alkalmazás beágyazásához a **Power Apps** menügombba válassza ki a Műveleti ablakot. Ha közvetlenül az oldalra szeretné beágyazni az alkalmazást, válassza ki a megfelelő lapot, gyorslapot, lapot vagy szekciót (ha egy munkaterületen van). Ezután az **Alkalmazás hozzáadása** ablaktáblán válassza a **Power Apps** elemet.
        - Ha a **Teljes oldalas alkalmazások** funkció ki van kapcsolva, válassza az **Alkalmazás hozzáadása lehetőséget a Power Apps oldalon**, majd válassza ki azt a régiót, ahová az alkalmazást hozzá szeretné adni. Az alkalmazás beágyazásához a **Power Apps** menügombba válassza ki a Műveleti ablakot. Ha közvetlenül az oldalra szeretné beágyazni az alkalmazást, válassza ki a megfelelő lapot, gyorslapot, lapot vagy szekciót (ha egy munkaterületen van).

    - Ha az alkalmazást a **Power Apps** menügomb segítségével érik majd el, akkor válassza ki a **Power Apps** menügombot a standard Műveleti ablakban, majd válassza az **Alkalmazás hozzáadása** lehetőséget.

3. Konfigurálja a beágyazott alkalmazást. A további tudnivalókat [lásd a Cikk egy vászna-alkalmazás](#configuring-a-canvas-app) konfigurálása szakaszában.
4. Miután megerősítette, hogy a konfiguráció helyes, válassza a **Beszúrás** lehetőséget.

    - Ha a **Mentett nézetek** funkció ki van kapcsolva, akkor a beágyazott alkalmazás megjelenítéséhez frissítenie kell a böngészőt.
    - Ha a **Mentett nézetek** funkció be van kapcsolva, akkor a nézetet el kell mentenie ahhoz, hogy a módosítások megmaradjanak.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Vászonalkalmazás beágyazása teljes oldalas élményként az irányítópultról

Előfordulhat, hogy egy vásznaalkalmazást szeretne beágyazni a irányítópultba, ha az alkalmazás nem kapcsolódik meglévő laphoz, vagy ha az alkalmazást teljes oldalas felületként szeretné látni a Pénzügy és műveletek alkalmazáson belül.

> [!NOTE]
> Ahhoz, hogy ez a képesség elérhetővé váljon, a funkciókezelésben be kell kapcsolnia a **Teljes oldalas alkalmazások** funkciót. 

1. Nyissa meg az irányítópultot.
2. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombra) az oldalt, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap hozzáadása** lehetőséget.
3. Az **Oldal hozzáadása** ablaktáblán válassza a **Power Apps** elemet.
4. Konfigurálja a beágyazott alkalmazást. A további tudnivalókat [lásd a Cikk egy vászna-alkalmazás](#configuring-a-canvas-app) konfigurálása szakaszában.
5. A **Mentés** gombra kattintva új csempeként hozzáadhatja az alkalmazást a irányítópulthoz.
6. Válassza ki az új csempét az irányítópulton, és erősítse meg, hogy a vászonalkalmazás a várt módon jelenik meg.

### <a name="configuring-a-canvas-app"></a>Vászonalkalmazás konfigurálása

Amikor beágyaz egy vászonalkalmazást, a következő paramétereket kell beállítania:

- **Név** - Adja meg a beágyazott alkalmazást tartalmazó gomb vagy lap megjelenítendő szövegét. Gyakran előfordulhat, hogy ebben a mezőben meg kell ismételni az alkalmazás nevét.
- **App ID** - Adja meg a beágyazni kívánt vászonalkalmazás globálisan egyedi azonosítóját (GUID). Az érték lekérdezéséhez keresse meg az alkalmazást a [make.powerapps.com](https://make.powerapps.com) oldalon, majd keresse meg az **Alkalmazás azonosítója** mezőt a **Részletek** alatt.
- Az **alkalmazás bemeneti kontextusa** - opcionálisan kiválaszthatja azt a mezőt, amely tartalmazza az alkalmazásnak bemenetként átadni kívánt adatokat. Arról, hogy hogyan férhet hozzá az alkalmazás a Pénzügyi és műveleti alkalmazásokból küldött adatokhoz, [a Jelen cikk](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) későbbi, A Pénzügy és műveleti alkalmazások szakaszból elküldött adatokra vonatkozó alkalmazás megépítése című részében olvashat tájékoztatást.

    A 10.0.19-es verzió óta az aktuális jogalany is átadásra kerül a vászonalkalmazásnak kontextusként a **cmp** URL paraméteren keresztül. Ez a viselkedés nem lesz hatással a célvászonalkalmazáson, amíg az alkalmazás nem használja az információt.

- **Alkalmazás mérete** - Válassza ki a beágyazandó alkalmazás típusát. Válassza a **Vékony** opciót a mobileszközökre készült alkalmazásokhoz vagy a **Széles** opciót a táblagépekre készült alkalmazásokhoz. Ez a paraméter biztosítja, hogy elegendő hely álljon rendelkezésre a beágyazott alkalmazás számára.
- **Jogi személyek** - Kiválaszthatja azokat a jogi személyeket, amelyek számára az alkalmazás elérhetővé válik. Az alkalmazás alapértelmezés szerint minden jogi személy számára elérhető. Ez a lehetőség csak akkor érhető el, ha közvetlenül egy meglévő oldalra ágyazza be, és a **[Mentett nézetek](saved-views.md)** funkció ki van kapcsolva.

## <a name="sharing-an-embedded-app"></a>A beágyazott alkalmazás megosztása

Miután beágyazott egy vászonalkalmazást egy oldalra, és meggyőződött arról, hogy az megfelelően működik, érdemes megosztani az alkalmazást a rendszer többi felhasználójával. Egy beágyazott vászonalapú alkalmazás megosztásához kövesse az alábbi lépéseket.

1. [Ossza meg a vászonalkalmazást a Power Appsoldalon](/powerapps/maker/canvas-apps/share-app) a megfelelő felhasználókkal, hogy azok közvetlenül a Power Apps oldalon férhessenek hozzá az alkalmazáshoz.
2. Ossza meg a beágyazott alkalmazáshoz kapcsolódó személyre szabott beállításokat a kívánt felhasználókkal. A következő megközelítések közül választhat:

    - **A nézet közzététele (ajánlott):** Ha a **[Mentett nézetek](saved-views.md)** funkció be van kapcsolva, az ajánlott és előnyben részesített megközelítés a beágyazott vászonalkalmazást tartalmazó nézet létrehozása, majd a nézet közzététele a kívánt felhasználók számára. Ez a megközelítés biztosítja, hogy minden olyan felhasználó, aki rendelkezik a közzétett nézet által megcélzott biztonsági szerepkörrel, látni fogja a vászonalkalmazást az oldalon.

        Az irányítópultról egész oldalas élményként beágyazott vászonalkalmazást is közzétehet. Az irányítópulton jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombbal) az alkalmazáshoz társított csempét, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap közzététele** lehetőséget. Megjelenik egy, a *nézetek közzététele* élményhez hasonló élmény, és kiválaszthatja a közzéteendő biztonsági szerepköröket. A 10.0.21-es vagy újabb frissítésben, ha a **Mentett nézetek javított jogi személy támogatása** funkció be van kapcsolva, akkor az alkalmazást a kívánt jogi személyek számára is közzéteheti.

    - Ha a **Mentett nézetek** funkció ki van kapcsolva, a rendszeradminisztrátor a **Személyre szabás** lapon keresztül a vászonalkalmazást tartalmazó személyre szabást adhat a megfelelő felhasználói csoportnak. Alternatívaként exportálhatja az oldal személyre szabott beállításait, majd elküldheti azokat egy vagy több felhasználónak. Ezután minden egyes felhasználó importálhatja a személyre szabást. A személyre szabási eszköztárban vannak gombok, amelyekkel exportálhatja és importálhatja a személyre szabott beállításokat.

> [!NOTE]
> Ha a vásznaalkalmazás meg van osztva külső felhasználókkal, akkor ezek a felhasználók nem használhatja a Pénzügy és műveletek alkalmazásokba ágyazott alkalmazást. Az alkalmazást azonban közvetlenül a Power Appsen belül elérhetik. A külső felhasználók olyan vendégeket és felhasználókat Microsoft 365 tartalmaznak, akik nem tartoznak ahhoz az Azure Directoryhoz, ahová a Pénzügy és műveletek alkalmazást telepítik.

A termék személyre szabási funkcióival és a használatukkal kapcsolatos bővebb információért lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>A Pénzügy és műveletek alkalmazásokból küldött adatokat használó vásznai alkalmazás telepítése

Amikor olyan vásznaalkalmazást hoz létre, amely be lesz ágyazva a Pénzügy és műveletek alkalmazásba, a folyamat egyik fontos része az, hogy a Pénzügyi és műveleti alkalmazás bemeneteit használja fel. A fejlesztői Power Apps tapasztalatból a Pénzügy és műveletek alkalmazásból átadott bemeneti adatok a **Param("EntityId") változóval érhetők** el. Továbbá a 10.0.19-es verziótól kezdve az aktuális jogi személy is át lesz adva a vászonalapú alkalmazásnak a **Param(„cmp”)** változóval. 

Például az alkalmazás OnStart függvényében a Pénzügyi és Művelet alkalmazásokból származó adatbeviteli adatokat egy ilyen változóra állíthatja:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Vászonalapú alkalmazás megtekintése

A Pénzügy és műveletek alkalmazások egy lapján található beágyazott vásznaalkalmazás megtekintéséhez menjen egy olyan oldalra, amelybe be van ágyazva alkalmazás. Ne felejtse el, hogy az alkalmazásokat a szokásos Művelet ablaktábla **Power Apps** gombján keresztül érheti el. Másik lehetőségként megjelenhetnek közvetlenül egy oldalon új lap, gyorslap vagy lapát, illetve a munkaterület új szakasza formájában. Amikor a felhasználók először megpróbálnak betölteni egy alkalmazást egy oldalon, a rendszer meg fogja kérni őket, hogy jelentkezzenek be. Ez a lépés biztosítja, hogy a felhasználók megfelelő jogosultságokkal rendelkeznek az alkalmazás használatához.

## <a name="editing-an-embedded-app"></a>Beágyazott alkalmazás szerkesztése

Egy alkalmazás egy oldalba ágyazását követően előfordulhat, hogy módosítania kell az alkalmazás konfigurációját. Például, esetleg módosítani szeretné a beágyazott alkalmazáshoz társított címkét, vagy létrejött az alkalmazás új verziója, és frissítenie kell az alkalmazásazonosítót, hogy a legújabbra mutasson.

Beágyazott alkalmazás konfigurációjának módosításához kövesse az alábbi lépéseket:

1. Lépjen az **Alkalmazás szerkesztése** panelre.

    - Ha a beágyazott alkalmazás a Power Apps menügombon keresztül érhető el, válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a Power Apps menügombot, és válassza a **Személyre szabás** parancsot. Jelölje ki az **Alkalmazás kiválasztása** legördülő menüből a konfigurálni kívánt alkalmazást.
    - Ha a beágyazott alkalmazás közvetlenül az oldalon jelenik meg, válassza a **Beállítások** lehetőséget, majd az **Oldal személyre szabása** elemet. Használja a **Kiválasztás** eszközt, kattintson a beágyazott alkalmazásra.
    - Ha a beágyazott alkalmazást az irányítópultról adta hozzá, nyissa meg az irányítópultot, válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a vászonalkalmazáshoz tartozó csempét, válassza a **Személyre szabás**, majd az **Oldal szerkesztése** lehetőséget.

2. Végezze el a szükséges módosításokat az alkalmazáskonfiguráción, és kattintson a **Mentés** elemre.

## <a name="removing-an-app"></a>Egy alkalmazás eltávolítása

Miután egy alkalmazás beágyazódott egy oldalra, szükség esetén többféleképpen is eltávolítható:

- Menjen az Alkalmazás szerkesztése **ablakba**[a](#editing-an-embedded-app) cikk korábbi, Beágyazott alkalmazás szakaszának szerkesztése című részében található útmutatással. Győződjön meg róla, hogy az ablaktáblában az eltávolítani kívánt beágyazott alkalmazás adatai láthatók, majd kattintson a **Törlés** gombra.
- Ha a beágyazott alkalmazást az irányítópultról adta hozzá, nyissa meg az irányítópultot, válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a vászonalkalmazáshoz tartozó csempét, válassza a **Személyre szabás**, majd az **Oldal eltávolítása** lehetőséget. 
- Mivel a beágyazott alkalmazás mentése személyre szabási adatokként történik, az oldal személyre szabásának törlése az összes az oldalba beágyazott alkalmazásokat szintén eltávolítja. Vegye figyelembe, hogy a lap személyre szabása végleges, és nem vonható vissza. Ha el szeretné távolítani egy lap személyes beállításait, válassza a **Lehetőségek** elemet, majd kattintson az **Oldal személyre szabása** elemre, végül kattintson a **Törlés** gombra. A böngésző frissítése után az oldal összes korábbi személyre szabási beállítása eltávolításra kerül. A lapok személyre szabással való optimalizációjával kapcsolatos további tudnivalók: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="appendix"></a>Melléklet

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Fejlesztői] Vászonalapú alkalmazás modellezése egy űrlapon

Miközben ez a cikk a személyre szabás során beágyazza a vásznas alkalmazásokat, a fejlesztőknek arra is lehetősége van, hogy a fejlesztői tapasztalat alapján egy vásznaalkalmazást vegyenek fel a Visual Studio képernyőkbe. Ehhez egyszerűen adja hozzá a PowerAppsHostControl lehetőséget az űrlaphoz. A vezérlőhöz elérhető metaadat-tulajdonságok a személyre szabási élményekkel azonos lehetőségeket biztosítanak.

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
