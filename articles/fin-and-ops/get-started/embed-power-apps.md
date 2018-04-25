---
title: "PowerApps beágyazása"
description: "Ez a témakör leírja, hogyan végezhető el a PowerApps beágyazása a Finance and Operations ügyfélbe a termék funkcionalitásának kibővítése érdekében."
author: jasongre
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.translationtype: HT
ms.sourcegitcommit: 454368ab5a467002ebf973db97fd98e31885dfe0
ms.openlocfilehash: 0fd0b1e5f94e39455b3c0799c89eea5a59444ad7
ms.contentlocale: hu-hu
ms.lasthandoff: 03/23/2018

---

# <a name="embed-powerapps"></a>PowerApps beágyazása

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/pre-release.md)] 

A Microsoft Dynamics 365 for Finance and Operations 14-es platformfrissítése támogatja a Microsoft PowerApps-hez való integrációt, amely egy fejlesztők és nem szakember felhasználók számára készült szolgáltatás, amellyel egyedi üzleti alkalmazások készíthetők mobilkészülékekre, táblagépekre és a webre, kód írása nélkül. Az Ön, a szervezete vagy a szélesebb ökoszisztéma által kifejlesztett PowerApp alkalmazások beilleszthetők a Finance and Operations kliensbe, hogy kiterjesszék a termék funkcionalitását. Például létrehozhat egy PowerApp-ot a Finance and Operations adatainak egy másik rendszerből lekért információkkal való kiegészítéséhez.  

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Beágyazott PowerApp hozzáadása egy oldalhoz
### <a name="overview"></a>Áttekintés
Mielőtt PowerApp-ot ágyazna be a Finance and Operations kliensbe, először meg kell találnia vagy létre kell hoznia egy PowerApp-ot a kívánt megjelenéssel és/vagy funkcionalitással. Itt nem írjuk le a PowerApp-építés részletes folyamatát. A [PowerApps – bevezetés](https://docs.microsoft.com/en-us/powerapps/getting-started) témakör jó kiindulási pont el, ha még nem használta a PowerApps megoldást.

Ha készen áll egy adott PowerApp beágyazására, kétféle lehetőség közül választhat a hozzáférésnél a PowerApphez a lapon, annak megfelelően, hogy melyik illeszkedik jobban a forgatókönyvhöz. Az első módszer a PowerApps gomb használata, amely hozzá lett adva a szokásos műveletpanelhez. Ily módon hozzáadott PowerApps alkalmazások a PowerApps menügombon belüli menüben jelennek meg. Kiválasztás esetén a menüpontok mindegyike oldalsó ablaktáblát nyit meg, amely a beágyazott PowerAppet tartalmazza. Másik lehetőségként választhatja a PowerApp megjelenítését közvetlenül egy oldalon új lap, gyorslap, lapát vagy munkaterület új szakasza formájában. 

A beágyazott PowerApp beállításakor a Finance and Operations alkalmazásban kiválaszthat egyetlen olyan mezőt, amelyet el szeretne küldeni a PowerAppba bevitelként. Ez lehetővé teszi, hogy a PowerApp válaszképes legyen a Finance and Operations alkalmazásban jelenleg megtekintett adatok alapján.  

### <a name="details"></a>Részletek
Az alábbi utasítások azt mutatják be, hogyan történik a PowerApp-beágyazás a Finance and Operations webes ügyfélbe.  

1. Menjen arra az oldalra, ahol be szeretné ágyazni a PowerApp-ot. Ez ugyanaz az oldal lesz, amely bármilyen olyan adatot tartalma, amelyet át kell adni a PowerApp számára bemenetként.  
2. Nyissa meg a **PowerApp beszúrása** ablakot:
   - Kattintson a **Beállítások** elemre, majd válassza a **Képernyő személyre szabása** elemet. A **Beszúrás** menü alatt válassza a **PowerApp** lehetőséget. Végül válassza ki a területet, ahol a PowerAppot hozzá kívánja adni. Ha azt szeretné a PowerApp alkalmazást a PowerApps menügomb alá beágyazni, válassza a műveletpanelt. Ha szeretné közvetlenül a lapra beágyazni a PowerApp alkalmazást, válassza ki a megfelelő lapot, gyorslapot, lapátot vagy szakaszt (ha munkaterületen tartózkodik).   
   - Ha a PowerApp a PowerApps menügomb segítségével lesz érhető, a normál Műveletpanelen kattintson a **PowerApps** menügombra, majd válassza a **PowerApp beszúrása** lehetőséget.  
3. Beágyazott PowerApp konfigurálása:
   - A **Név** mező jelzi annak a gombnak vagy lapnak a megjelenő szövegét, amely tartalmazza a beágyazott PowerAppet. Gyakran előfordulhat, hogy érdemes megismételni a PowerApp nevét ebben a mezőben.  
   - **Alkalmazás azonosítója:** a beágyazni kívánt PowerApp GUID-je. Az érték lekérdezéséhez keresése meg a PowerAppet a [web.powerapps.com](https://web.powerapps.com) oldalon, majd keresse meg az **Alkalmazás azonosítója** mezőt a **Részletek** alatt.  
   - A **PowerApp adatbevitel** elemnél opcionálisan kiválaszthatja azt a mezőt, amely a PowerApp számára bemenetként továbbítandó adatokat tartalmazza. Lásd a következő című részt a témakör későbbi részében arról, hogy a PowerApp hogyan elérheti el a Finance and Operations alkalmazásból továbbított adatokat: [A Finance and Operations adatait használó PowerApp felépítése](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations).  
   - Válassza azt az **Alkalmazásméretet**, amely megfelel a beágyazott PowerApp típusának. Válassza ki **Vékony** lehetőséget a mobileszközök számára épített PowerApps, és a **Széles** lehetőséget a táblagépekhez létrehozott PowerApps esetében. Ez biztosítja, hogy a beágyazott PowerApp számára elegendő mennyiségű hely kerül kiosztásra.
   - A **Jogi személyek** gyorslap teszi lehetővé annak a kiválasztását, hogy melyik jogi személyekre nézve érhető el a PowerApp. Az alapértelmezés a PowerApp megjelenítése minden jogi személynél.  
4. Miután megerősítette, hogy a konfiguráció helyes, kattintson a **Beillesztés** elemre a PowerApp az oldalba ágyazásához. A rendszer rákérdez a böngésző frissítésére ahhoz, hogy megjelenjen a beágyazott PowerApp. 

## <a name="sharing-an-embedded-powerapp"></a>A beágyazott PowerApp megosztása
Miután beágyazott egy PowerApp alkalmazást egy oldalra, és meggyőződött, hogy megfelelően működik az oldalról átadott adatkontextusokkal, érdemes megosztani a beágyazott PowerApp alkalmazást a rendszer többi felhasználójával. Ez kétféleképpen érhető el a termék személyre szabási képességeinek használatával:

- Az ajánlott forgatókönyv a rendszergazdán keresztüli lebonyolítás, aki a személyre szabást közzéteheti az összes felhasználónak vagy a felhasználók egy részhalmazának. 

- Alternatívaként exportálhatja az oldal személyre szabásait, elküldheti őket egy vagy több felhasználónak, és e felhasználók mindegyike importálhatja a módosításokat. A személyre szabási eszköztáron található Kezelése opcióval bonyolítható a személyes beállítások exportálása és importálása.

A termék személyre szabási funkcióival és a használatukkal kapcsolatos bővebb információért lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>PowerApp felépítése, amely a Finance and Operations rendszerből származó adatokat hasznosítja
A Finance and Operations programba beágyazott PowerApp felépítésének fontos része a Finance and Operations beviteli adatainak felhasználása. A PowerApp alkalmazáson belül a bemeneti adatok a Param("EntityId") változó segítségével érhetők el.  

Például a PowerApp OnStart függvényében a Finance and Operations rendszerből származó bemeneti adatokat egy változóra állíthatja be:

If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, "")); 

## <a name="viewing-an-embedded-powerapp"></a>Egy beágyazott PowerApp megtekintése
Egy beágyazott PowerApp megtekintéséhez a Finance and Operations alkalmazásban, egyszerűen ugorjon a beágyazott PowerApp oldalára. Emlékezzünk vissza, hogy a PowerApp alkalmazások a PowerApps gombon keresztül érhetők el a normál műveletpanelen, vagy megjelenhetnek közvetlenül új lapként, gyorslapként, lapátként vagy munkaterület új részeként. Amikor egy felhasználó először próbálja meg egy oldalon egy PowerApp betöltését, a rendszer felkéri a PowerAppsba való bejelentkezésre annak a biztosítására, hogy a felhasználó rendelkezzen a megfelelő engedélyekkel a PowerApp futtatásához.   

## <a name="editing-an-embedded-powerapp"></a>Beágyazott PowerApp szerkesztése
Egy PowerApp egy oldalba ágyazását követően előfordulhat, hogy módosítania kell a PowerApp konfigurációját. Például, esetleg módosítani szeretné a beágyazott PowerApp-hez társított címkét, vagy létrejött egy PowerApp új verziója, és frissítenie kell az alkalmazásazonosítót, hogy a legújabb a PowerApp-re mutasson. 

Beágyazott PowerApp konfigurációjának módosításához kövesse az alábbi lépéseket:
1. Lépjen az **Egy PowerApp szerkesztése** panelre. 
   - A beágyazott PowerApp a PowerApps menügombon keresztül érhető el, kattintson a jobb gombbal PowerApps menügombra, és válassza a **Személyre szabás** lehetőséget. Jelölje ki a **PowerApp kiválasztása** legördülő menüből a konfigurálni kívánt PowerAppet.  
   - Ha a beágyazott PowerApp közvetlenül az oldalon jelenik meg, válassza a **Beállítások** lehetőséget, majd a **Képernyő személyre szabása** elemet. Használja a **Kiválasztás** eszközt, kattintson a beágyazott PowerAppre.  
2. Végezze el a szükséges módosításokat a PowerApps konfiguráción, és kattintson a **Mentés** elemre.  

## <a name="removing-an-embedded-powerapp"></a>Beágyazott PowerApp eltávolítása
Egy PowerApp egy oldalba ágyazását követően szükség esetén kétféle módon távolíthatja el azt: 

- Lépjen az **Egy PowerApp szerkesztése** panelre a jelen témakör korábbi [Beágyazott PowerApp szerkesztése](#editing-an-embedded-powerapp) részében írtak szerint. Győződjön meg róla, hogy az ablaktáblában az eltávolítani kívánt beágyazott PowerApp adatai láthatók, majd kattintson a **Törlés** gombra. 

- Mivel a beágyazott PowerApp mentése személyre szabási adatokként történik, az oldal személyre szabásának törlése az összes az oldalba beágyazott PowerApp-ot szintén eltávolítja. Vegye figyelembe, hogy a lap személyre szabása végleges, és nem vonható vissza. Ha el szeretné távolítani egy lap személyes beállításait, válassza a **Lehetőségek** elemet, majd kattintson a **Képernyő személyre szabása** elemre. A **Kezelés** menüben válassza a **Törlés** gombot. A böngésző frissítése után az oldal összes korábbi személyre szabási beállítása eltávolításra kerül. A lapok személyre szabással való optimalizációjával kapcsolatos további tudnivalókat lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).  

## <a name="appendix"></a>Melléklet 
### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Fejlesztői ellenőrzés afölött, hogy hova ágyazható be egy PowerApp
Alapértelmezés szerint a felhasználók minden lapon beágyazhatnak PowerApps alkalmazásokat vagy a PowerApps menügombbal, vagy közvetlenül az oldalon lap, gyorslap, lapát vagy munkaterület új szakasza formájában. Szükség esetén azonban a fejlesztők beállíthatják ezt a funkciót úgy is, hogy csak a PowerApp alkalmazások egyes oldalakon történő beágyazását engedélyezze az alábbi módszerek végrehajtásával: 

- **isPowerAppPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a PowerApps menügomb nem lesz látható, a felhasználók nem tudnak beágyazni PowerApps-t sehova ezen az oldalon, lapként sem. 

- **isPowerAppTabPersonalizationEnabled** – Ha ez a módszer hamis értéket ad vissza az egy adott oldalra, a felhasználók nem tudnak PowerApps-t beágyazni közvetlenül az oldalon sem lapként, sem gyorslapként, sem panorámaszakaszként. A felhasználók továbbra is beágyazhatják a PowerAppst a PowerApps menügombbal, ha az oldalon megengedett a beágyazás.  

A következő példa bemutat egy új osztályt a két konfigurálandó metódussal, ahol a PowerApps beágyazható.  

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{

    public static boolean isPowerAppPresonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPresonalizationEnabled(pageName);
        return true;
    }

    public static boolean isPowerAppTabPresonalizationEnabled(str pageName)   
    {
        var result = next isPowerAppTabPresonalizationEnabled(pageName);
        return true;
    }
    ```

}

