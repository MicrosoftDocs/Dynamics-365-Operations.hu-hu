---
title: Folyamatútmutató-keretrendszer
description: Ez a témakör a raktári mobileszközfolyamatokat kiterjesztő a raktári folyamatokat X++ használatával bővítő folyamat-útmutatói keretrendszerével kapcsolatban tartalmaz tájékoztatást.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902046"
---
# <a name="process-guide-framework"></a>Folyamatútmutató-keretrendszer

[!include [banner](../includes/banner.md)]

Ez a témakör a raktári mobileszközfolyamatokat kiterjesztő a raktári folyamatokat X++ használatával bővítő folyamat-útmutatói keretrendszerével kapcsolatban tartalmaz tájékoztatást. A raktári mobil folyamatok a folyamatok kis lépésekre bonthatósága következtében bővíthetők. Az egyes lépések az üzleti logikáját és a felhasználói felület építését különálló osztályokba bontottuk, ami lehetővé teszi a bővíthetőséget.

## <a name="overview-of-the-existing-design"></a>Meglévő felépítés áttekintése

A raktári mobil végrehajtási folyamatok egyetlen egyéni szolgáltatási végponton keresztül érhetők el. A kérés XML-karakterlánc formájában érkezik a mobilalkalmazásból, amely a mobilalkalmazásban megjelenő felhasználói felület metaadatait, valamint a felhasználó által beírt értékeket tartalmazza.

A kérés beérkezette után az első lépés ennek az XML-kódnak a deszerializálása. A **WHSMobileAppServiceXMLTranslator** osztály tárolóvá alakítja az XML-t, amely mind a vezérlőadatokat, mind a munkamenetek adatait tartalmazza.

Ezt követően a rendszer a tárolóban található információk alapján levezeti, hogy melyik raktári folyamaton dolgozik a felhasználó, illetve áll indítás előtt áll (amit a **WHSWorkExecuteMode** enumeráció képvisel), és ennek megfelelően példányosít egy származtatott **WHSWorkExecuteDisplay** osztályt. Meghívja a **displayform()** metódust, amely aztán a következőt teszi:

-   A felhasználótól származó adatokat dolgozza fel (a **WHSRFControlData** osztálynak delegálva), de egyes folyamatok a **processControl()** metódus felülbírálásával konkrét logikát valósítanak meg.

-   Üzleti logikát hajt végre.

-   Lépteti a lépést.

-   Az új felhasználói felületet (általában **build…()** metódus) képviselő tárolót kiépíti.

A tárolót ezután visszaadja a fordítónak, amely szerializálja az XML-adatokat, és visszaküldi a mobileszközre adott válaszként.

A következő folyamatábrán látható a végrehajtási folyamat áttekintése. A diagram inkább sematikus áttekintés, és nem az aktuális kód 1:1-es ábrázolása.

![A folyamat sematikus áttekintése.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Az átdolgozás oka

A fenti kialakítás egy nagyon egyszerű keretrendszert kínál a mobilfolyamatokban használt folyamatok építéséhez. Ugyanakkor ahogy fent látható, a **displayform()** metódusok több felelősséget is átvesznek. Delegáltja azokat más metódusok és osztályok számára, de konkrét osztályon alapuló felelősségek hiányában az osztályok között inkonzisztens módon történik. Mivel a támogatott esetek száma folyamatosan és organikusan nő, ezek közül az osztályok közül egyesek nagyon bonyolultakká válhatnak. Hogy még érdekesebb legyen a helyzet, az osztályok/metódusok egy része felül van bírálva, és több módban újra fel van használva. Az eredmény több rendkívül hosszú ciklomatikusan komplex metódus. Ezek karbantartást problémákat okoztak korábban. A metódusokban a hibák kijavítása veszélyes és regresszíóra hajlamos volt.
Például a **WhsWorkExecuteDisplay** osztály **processWorkLine()** metódusát több folyamatból is lehet hivatkozni (alapvetően mindenhonnan, ahol a munkavégrehajtás történik).

Ha ezt bővíthetővé szeretné tenni, akkor az egyik lehetőség a **displayForm** metódusok kisebb metódusokká osztása, és további bővíthetőségi pontokat bevezetése. Az esetmátrix miatt azonban a partnerek számára a bővítmények megírása és a regresszív ellenőrzés kihívást jelentett volna. Nem elég, hogy a fent említett rendszerezett felelősségelosztás hiánya miatt a kód az idő múlásával kiszámíthatatlan módon nő, ami kihívást jelent a minőségi bővítmények kiépítése során.

Ennek eredményeképpen az újratervezés a megfelelő megoldás, amelynek célja, hogy egyértelműen meg legyenek határozva a független feladatkörrel rendelkező osztályok. Az osztályokhoz egy felelősségnek, egy módosítási oknak és egy kiterjesztési oknak kell tartoznia.

## <a name="design-overview"></a>Terv áttekintése

Az újratervezett keretrendszerben a alapstratégia két alapelv köré épül: a végrehajtás folyamatának felosztása egyedi összetevőkre, jól definiált felelősségi körökkel és az összetevők mindegyikében jól definiált kiterjesztési pontokkal.

Az új keretrendszer neve "ProcessGuide". Ennek oka, hogy ezeknek az osztályoknak az a célja, hogy végigvezessék a felhasználót egy üzleti folyamaton (szemen az összetett kilenssel, amely egy űrlapalapú élmény, ahol a felhasználó nagyobb rugalmasságot atektintetben, hogy hogyan lép interakcióba az adatokkal, és milyen sorrenden végzi el a feladatokat).

> [!NOTE]
> Fontos megjegyezni a "WHS" előtag szándékos kihagyását. Kezdetben a mobil folyamatokat raktárkezeléshez vezették be, majd átléptek határokat a különböző termelési és készletkezelési folyamatok támogatása érdekében. Emiatt a raktári hivatkozás ki lett hagyva a keretrendszer nevéből.

Az összetevők azonosításához az első lépés a Termelés kezdete folyamat (**WhsWorkExecuteDisplayProdStart** osztály) áttekintése. Itt a folyamat sémája.

![Sémafolyamat képe.](media/production-start-process-schematic.png)

A vezérlési folyamatot nézve a következő összetevőkre van szükség:

-   Vezérlő, amely végigvezet a teljes üzleti folyamaton.
-   A folyamat egy lépésének végrehajtásáért felelős lépés.
-   Egy lépés adatainak feldolgozását feldolgozó adatfeldolgozó.
-   Egy lépéshez tartozó felhasználói felület építéséért felelős oldalszerkesztő.
-   A lépésváltásért felelős navigációs ügynök.
-   Az üzleti folyamat végrehajtásáért felelős osztály.

A fenti folyamatábra: ha az 1. lépésnél megkezdi az előző lépés adatainak feldolgozását, majd a felhasználói felület építésével véget ér, a következő lépésben folytatódik az adatok feldolgozása. Emiatt az egymást követő lépések között szoros együttműködését vezeti be, ennek eredményeképpen az új, magas szintű séma a következőképpen néz ki:

![A magas szintű sémafolyamat képe.](media/high-level-schematic.png)

Az újratervezett folyamat fő összetevői a következők:

-   **ProcessGuideController** – Ez az osztály irányítja az üzleti folyamat általános végrehajtását. Meghatározza a lépés példányosító tényezőit, valamint a navigációs ügynökét, amelyek ezt követően a folyamat végrehajtását alkotják, valamint meghatározza a folyamat megszakítására vagy a kilépésére vonatkozó tisztítási logikát.

-   **ProcessGuideStep** – ez az osztály az üzleti folyamat egyetlen lépését képviseli. Ez az osztály a lapszerkesztők, műveletek és adatfeldolgozók példányosuló tényezőinek definícióját tartalmazza, és a helyes sorrendben való meghívásukért felelős.

-   **ProcessGuideNavigationAgent** – Ez az osztály a lépések közötti navigálásért felelős. Amikor egy lépés befejeződik, a navigációs ügynök felelős a következő lépés meghatározásáért, és az előző lépésből esetleg szükséges paramétereket átadja a következőnek.

-   **ProcessGuidePageBuilder** – Ez az osztály a felhasználói felület bemutatásáért felelős.

-   **ProcessGuideAction** – Ez az osztály egy műveletet jelent, amely a felhasználónak egy gombként jelenik meg.

-   **ProcessGuideDataProcessor** – Ez az osztály felelős a mezőben a felhasználó által megadott adatok feldolgozásáért.

## <a name="execution-flow"></a>Végrehajtási folyamat

A végrehajtási folyamat kiindulási pontja változatlan marad. Tehát a kérés továbbra is ugyanazon végpontokon érkezik, majd az XML deszerializálása történik a tárolóba. Ezt a tárolót ezután át kell adni a **getNextFormState()** számára.

Három fontos osztályt kell megjegyezni:

-  **ProcessGuideSessionState** – a munkamenet állapotinformációit – a módot, az átadsát, a vezérlőt, a végrehajtandó lépést stb. tartalmazza.

-  **ProcessGuidePage** – A felhasználói felület erősen tipizált ábrázolását tartalmazza.

-  **ProcessGuideRequest** – a fenti két tag tagból áll, és a mobileszközről kapott kérés erősen tipizált ábrázolása.

Ezek az osztályok a tárolóadatok (az állapot- és a felhasználó által megadott vezérlőadatok) használatával jönnek létre. Ezzel a módszerrel típusbiztonságos módon lehet elérni és módosítani az értékeket. A folyamat során a tároló ismétlődő elérésével összehasonlítva ez mind az olvashatóság, mind a teljesítmény szempontjából előnyös.

A munkamenet állapotinformációi a helyes **ProcessGuideController** osztály ábrázolására használatosak. A példányosítás után a **ProcessGuideController** osztály **createResponse()** metódusát hívja meg a rendszer. Ez a metódus a folyamatvezetői logika belépési pontja, és a végrehajtás után a válasszal érkezik vissza (a **ProcessGuideResponse** osztályban jelenik meg). A válasz ezt követően tárolóban lesz visszaalakítva, és az örökölt logikának lesz visszaadva, amely aztán szerializálja az XML-fájlba, és elküldi a választ a mobileszköznek.

Ezután a vezérlőnek meg kell találnia a következő végrehajtandó lépést. Ha ez egy új folyamat kezdete, a vezérlő meghívja az **initialStep()** metódust, hogy a folyamat első lépését lehívja. Ezt követően hívja meg az **execute()** metódust a **ProcessGuideStep** elemben. Ezzel a metódus példányosít egy **ProcessGuidePageBuilder** osztályt, és meghívja a **buildPage()** metódust, amely egy **ProcessGuidePage** objektummal tér vissza, és ez a felhasználói felület virtuális ábrázolása, amely a felhasználó számára meg lesz jelenítve. A lépés ezt követően visszaküldi az eredményt a vezérlőnek, amely menti az aktuális munkamenet állapotát, és az eredményt visszaadja a **ProcessGuideResponse** osztály formájában a **getNextFormState()** metódusának. Ezt követően a válasz vissza lesz alakítva tárolóvá, és ezt követően XML-formátumra szerializálja, és visszaküldi a választ a mobileszköznek.

A következő folyamatábra bemutatja a vezérlésfolyamot. Ne feledje, hogy ez a leggyakoribb vezérlésfolyam, amely egyszerűsítve lett a tervezés magyarázatához.

![A vezérlésfolyam leegyszerűsítve.](media/control-flow.png)

Amikor a felhasználó egy gombra kattintva (vagy egy érték beolvasásával– amely általában az alapértelmezett műveletet indítja el) a mobileszközön műveletet indít el– a kérés ugyanannak az útvonalnak a **createResponse()** metódusához érkezik meg a **ProcessGuideController** osztályban. Ez alkalommal azonban a vezérlő tudja a munkamenet-állapotból, hogy melyik lépésben van a felhasználó. Ennek megfelelően példányosítja a megfelelő **ProcessGuideStep** osztály, és meghívja a végrehajtási metódust. A **ProcessGuideStep** beolvassa a felhasználó által meghívott műveletnevet, majd példányosítja a megfelelő **ProcessGuideAction** osztályt és a meghívja az **execute()** metódust.

A **ProcessGuideAction** osztály felelős az adott művelet végrehajtásáért, de két fontos kivétel van.

Az első a **ProcessGuideOKAction** osztály. Ez a művelet azt feltételezi, hogy a felhasználó megerősíteni szeretne, majd előre szeretne lépni a folyamatban. Ezzel összhangban – ez a metódus ténylegesen visszahívja a ProcessGuideStep osztályt, ami azt jelenti, hogy a lépés meghívja a **processData()** metódust a **ProcessGuideDataProcessor** osztályban. Ez feldolgozza a felhasználó által bevitt adatokat, majd frissíti a lépés állapotát, és az eredményt visszaküldi a vezérlőnek. A feldolgozó eredményétől függően a lépés az oldalszerkesztőt hívja meg a megfelelő felhasználói felület felépítéséhez, vagy befejezettként állítja be a lépés állapotát. Ez az alábbi folyamatábra felső részén jelenik meg.

A másik kivétel a visszavonás művelet, amely a **ProcessGuideCancelResetProcessAction** és **ProcessGuideCancelExitProcessAction** osztályokban van megvalósítva. Ezek a műveletek olyan célokat képviselnek, amelyek célja a folyamat megszakítása és vagy a folyamat kezdetére való visszalépés, vagy kilépés teljesen a folyamatból. Az **OK** művelethez hasonlóan ezek a műveletek visszahívási műveletet is végrehajtanak a lépéshez, amely jelzi a **ProcessGuideController** számára a szándékot. A kontroller ezután végrehajtja az állapotváltozók szükséges tisztítását, és vagy a folyamat első lépésekére lép át, vagy teljesen megszakítja a folyamatot.

Ha a lépés befejezése után a lépés állapota **Befejeződött** értékre van állítva, akkor a vezérlő példányosítja a **ProcessGuideNavigationAgent** függvényt, amely a következő lépés nevét adja vissza. A vezérlő ezután példányosítja a lépést, és meghívja az **execute()** metódust – és a ciklus folytatódik. Az új lépés leggyakrabban a megfelelő **ProcessGuidePageBuilder** metódust hívja meg, hogy a következő, a felhasználónak megjelenő képernyő számára építse fel a felhasználói felületet, amely vissza lesz küldve. Ez a folyamat az alábbi folyamatábra alsó részén jelenik meg.

![folyamatábra.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Új folyamat létrehozása a ProcessGuide keretrendszer használatával

A legjobb mód a vezérlésfolyam magyarázatára az alkalmazásban – a termelés indítási folyamatában – létező példának használata.

## <a name="overview-of-the-production-start-process"></a>A gyártási indítása folyamat áttekintése

Először a folyamatábrát értelmezzük. Az első lépésben a rendszer rákérdez a felhasználónál a termelési rendelés azonosítójára.

![Rákérdezés a termelésazonosítóra.](media/production-id-prompt.png)

Amikor a felhasználó beírja a termelési rendelés azonosítóját, a rendszer ellenőrzi a rendelés számát. A futtatott ellenőrzések egy része annak alapján történik, hogy a rendelés ugyanabban a raktárban van-e, mint ahol a felhasználó be van jelentkezve, valamint a rendelés állapota. Ha az ellenőrzés sikertelen, a felhasználó hibaüzenetet kap. Ha az ellenőrzés sikeres, akkor a felhasználó számára megjelennek a termelési rendelés és a cikk adatai.

A felhasználó vagy megszakíthatja a műveletet, hogy visszalépjen a folyamat elejére, vagy az **OK** gombra kattintva megerősítheti azt. Az utóbbi esetben a termelési rendelés **Elindítva** állapotra van állítva, a megfelelő naplókat feladja a rendszer, a vezérlő visszalép az első lépésre, és a felhasználó számára megjelenik a "Munka befejezve" üzenet.


## <a name="creating-the-controller"></a>A vezérlő létrehozása

Az üzleti folyamat létrehozásának első lépése a vezérlőosztály létrehozása, amely a Vezérlők alapértelmezett viselkedését megvalósító **ProcessGuideController** absztrakt osztályra bővíti a folyamatot. Az új osztálynév a **ProdProcessGuideProductionStartController**, és a **StartProdOrder** **WHSWorkExecuteMode** értékével van jelölve. A **WHSWorkExecuteDisplay** osztályokban használt ugyanazon **SysExtension** alapú példányosítás használatos, amely lehetővé teszi a kontroller példányosítását abban az esetben, amikor a felhasználó végrehajt egy menüelemet ehhez a módhoz.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> Az osztály elnevezési mintája **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Vezérlő**. Ez a vezérlőosztályok által használt és a többi osztályra is kibővülő minta.


## <a name="building-the-first-step"></a>Az első lépés létrerhozása

Ezután hozza létre a **ProdProcessGuidePromptProductionIdStep** osztályt a **ProcessGuideStep** osztályból kibővítve az első lépés meghatározásához.

Az osztály példányosulatának feladata egy lépésgyárhoz van delegálva, amelyet a **ProcessGuideController** alaposztály hív meg. A gyár alapértelmezett implementációja a név alapján példányosítja a lépést. Ezért a **ProdProcessGuidePromptProductionIdStep** példányosításához a vezérlő első lépéseként, két dolgot kell megtennie:

-   Rendelje hozzá a **ProdProcessGuidePromptProductionIdStep** osztályhoz a **ProcessGuideStepName** attribútumot.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   A vezérlőosztályban implementálja az **initialStepName()** absztrakt metódust a lépés nevének visszaküldése érdekében.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> A **ProcessGuideStepName** attribútumban megadott értéknek nem kell pontosan egyeznie az osztálynévvel, amint az fent látható. Ugyanakkor ennek megvalósítása lehetővé teszi az osztály használata során a kereszthivatkozások egységességét és típusbiztonságát. Ezen elnevezési konvenció használata ajánlott.
>
> A **ProcessGuideStepName** alapú példányosítás a lépésben a **ProcessGuideStepDefaultFactory** osztályban van megvalósítva. Abban a ritka esetben, amikor más stratégia szükséges a lépés példányosodása érdekében, a következőket kell tenni:
> -   A **ProcessGuidStepAbstractFactory** osztálytól örökölt új gyárosztály létrehozása.
> -   Másik lehetőségként hozzon létre egy új paraméterosztályt, amely végrehajtja a **ProcessGuideIStepCreationParameters** felületet, amely tartalmazza a gyár számára szükséges paramétereket.
> -   A vezérlőosztályban bírálja felül a **stepFactory()** és a **stepCreationParameters()** metódusokat a fenti gyár és paraméterek visszaadása érdekében.

A következő lépés a **ProdProcessGuidePromptProductionIdStep** osztály funkcionalitásának megvalósítása. A felhasználói felület létrehozásához, a felhasználó által megadott adatok feldolgozásához és a lépés befejezésének meghatározásához meg kell valósítani a logikát.

### <a name="building-the-user-interface-for-the-first-step"></a>A felhasználói felület kiépítése az első lépéshez

A felhasználói felület a **ProcessGuidePageBuilder** absztrakt osztálytól örökölt osztállyal történik. A lépéshez nevezze el azt az osztályt, úgy, hogy képviselje a feladatát – **ProdProcessGuidePromptProductionIdPageBuilder**.

Az osztály példányosítási mechanizmusa hasonlít arra, ahogyan történt a lépés példányosítása a vezérlőből. 

-   Rendelje hozzá a **ProdProcessGuidePromptProductionIdPageBuilder** osztályhoz a **ProcessGuidePageBuilderName** attribútumot.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   A **ProdProcessGuidePromptProductionIdStep** osztályban implementálja a **pageBuilderName()** absztrakt metódust a név visszaadása érdekében.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> A lépésgyárhoz hasonlóan van egy absztrakt gyárminta is, amely a lapszerkesztő gyárához van megvalósítva. Tehát abban a ritka esetben, amikor más stratégia szükséges az oldalszerkesztő példányosodása érdekében, a következőket lehet tenni:
> - A **ProcessGuidePageBuilderAbstractFactory** osztálytól örökölt új gyárosztály létrehozása.
> - Másik lehetőségként hozzon létre egy új paraméterosztályt, amely végrehajtja a **ProcessGuideIPageBuilderCreationParameters** felületet, amely tartalmazza a gyár számára szükséges paramétereket.
> - A lépsosztályban bírálja felül a **pageBuilderFactory()** és a **pageBuilderCreationParameters()** metódusokat a fenti gyár és paraméterek visszaadása érdekében.

A felhasználói felület megvalósításához egy külön szövegmezővel rendelkező oldalon kell megadni a termelési rendelés azonosítóját, valamint egy **OK** gomb és egy **Mégse** gomb is szükséges. A **Mégse** gombnak ki kell lépnie a folyamatból.

Ennek megvalósításához felül kell bírálni két metódust a **ProdProcessGuidePromptProductionIdPageBuilder** osztályban:

-   Az **addDataControls()** metódussal adja hozzá a szövegmezőt.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Az **OK** és a **Mégse** gombok hozzáadására használja az **addActionControls()** metódust.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Így hozzáadja az adatvezérlőket, majd a gombokat. Ha azonban olyan képernyőt szeretne felépíteni, amely beékelt adatvezérlőt és gombot tartalmaz, a rugalmasság érdekében felülbírálhatja az **addControls()** metódust.

Egy másik megfontolandó eset, hogy ellenőrzési hibák esetén hogyan legyen újraépítve az oldal, például ha a felhasználó helytelenül adja meg a termelési rendelés azonosítóját. A **ProcessGuidePageBuilder** alaposztály megvalósítja az alapértelmezett viselkedést, amely újraépíti a felhasználói felületet, törli a beolvasott értéket, és hozzáadja a hibavezérlőt a hibaüzenettel. Mivel ezt az alapértelmezett viselkedést szeretné használni, nem kell kódot hozzáadnia a kezelési hibák kezelésére.

> [!TIP]
> Ha egyéni felhasználói felületi viselkedést szeretné megvalósítani a hibahelyzetekben, felülbírálhat egy vagy több **rebuildFromRequestPage()**, **isErrorState()** metódust, és a **reuseRequestPageOnError()** metódust.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>A felhasználó által az első lépésben bevitt adatok feldolgozása

Az adatok feldolgozása a **ProcessGuideDataProcessorDefault** osztályban történik, amely a régi **WhsRfControlData** osztályt hívja meg. Ehhez az alapértelmezett viselkedéshez nincs szükség változtatásra, és a **WhsRfControlData** már rendelkezik a **ProdId** mező érvényességének ellenőrzésével kapcsolatos logikával, így a kezeléséhez nem kell semmilyen logikát írni. Az ellenőrzési logikabővítésének szükségessége esetén célszerű a **WhsControl** alapú kiterjesztési mechanizmust használni.

### <a name="determine-if-the-first-step-is-complete"></a>Annak meghatározása, hogy az első lépés befejeződött-e

Ha az ellenőrzés sikeres, itt az idő, hogy a lépést készként jelöljük. Ez az alaposztályban történik, de a lépés befejezésének meghatározásához implementálnia kell a feltételt. A következő felülbírált módszer teszi meg ezt.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>2. lépés: A rendelés részleteinek megtekintése és megerősítése

A folyamat második lépésekében a felhasználó számára megjelenik egy képernyő, amely tartalmazza a rendelés részletes adatait. A felhasználó vagy az **OK** gombra kattintva megerősítheti a termelési rendelés kezdését, vagy a **Mégse** gombra kattintva visszatérhet a folyamat elejére. Például nevezze el a **ProdProcessGuideConfirmProductionOrderStep** lépést és az oldalszerkesztő osztályt: **ProdProcessGuideConfirmProductionOrderPageBuilder** néven.

A ProdProcessGuideConfirmProductionOrderStep osztály a következőképpen néz ki.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Mivel a felhasználó nem ad meg itt értéket, nem kell felülbírálni az **isComplete()** metódust. A lépés akkor fejeződik be, ha a felhasználó az **OK** gombra kattint.

Az oldalszerkesztő osztálya felülbírálja az **addDataControls()** metódust három címke hozzáadásához. Az első címkén a termelési rendelés azonosítója látható, a másodikban a cikk adatai (például a cikk azonosítója, a méretek vagy a leírás), a harmadik pedig a mennyiséget és a mértékegységet tartalmazza.

Az **addActionControls()** vezérlő ezt követően felül lesz bírálva, hogy hozzáadja a 2 gombot – az **OK** gombot és a **Mégse** gombot a folyamat megszakításához és a folyamat elejére való ugráshoz.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Az X++ metódusok forráskódja az Alkalmazásböngészővel található meg ebben a témakörben. Szűrjön az osztály nevére, majd kattintson a jobb gombbal az osztály nevére, és válassza a **Kód megtekintése** lehetőséget.

### <a name="step-3-start-the-production-order"></a>3. lépés: A termelési rendelés indítása

A harmadik lépés az, hogy végrehajtja a termelési rendelés indításának üzleti logikáját. Ez a lépés teljesen különbözik az előző lépésektől, ebben a lépésben nincs felhasználói felület. A rendszer a háttérben végrehajtja ezt a lépést, amikor a felhasználó az előző lépésben az **OK** gombra kattint.

A **ProcessGuideStepWithoutPrompt** absztrakt osztály implementálja az ilyen lépések alapértelmezett viselkedését. Az aktuális lépésben ezért ki kell bővítenie a **ProcessGuideStepWithoutPrompt** osztályt, és felül kell bírálni a **doExecute()** metódust.

Az alábbi példakód mutatja be az osztály és a **doExecute()** metódus implementációját. A metódus egyszerűen beolvassa a rendelésazonosítót és a felhasználói azonosítót a munkamenet-állapotából, és meghívja a termelési rendelés indítási módszerét.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

Kivétel esetén a keretrendszer kivételkezelési logikája gondoskodik arról, hogy a folyamat visszagördüljön az előző lépésre.

> [!NOTE]
> Az **addProcessCompletionMessage()** metódus meghívása hozzáadja a "Munka befejezve" üzenetet a navigációs paraméterekhez. A következő lépés (amennyiben van felhasználói felülete) megjeleníti ezt az üzenetet. Az alaposztályok kezelik ezt a logikát, és ennek a viselkedésnek a megvalósításához nem kell specifikus kódot adni a folyamatosztályhoz.


### <a name="building-the-navigation-through-the-steps"></a>A navigálás kiépítése a lépéseken keresztül

A **ProcessGuideController** alaposztály példányosítja a **ProcessGuideNavigationAgentDefault** osztályt, amely egy előre meghatározott navigációs útvonalon alapul, amely a forrás- és cél lépések egyszerű leképezése. A termelés kezdése forgatókönyvnél, mivel nincs feltételes elágazás, ez a megvalósítás elegendő lenne. Emiatt a navigációs útvonal definiálása érdekében csak az **initializeNavigationRoute()** metódust kell felülbírálni.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Vannak folyamatok, ahol feltételes elágazás lesz (felhasználói műveletek vagy bármilyen egyéb feltétel alapján). Az ilyen folyamatoknak a következőket kell tenniük:

-   A **ProcessGuideNavigationAgent** osztályból örökölt konkrét navigációs ügynökök implementálása.

-   A **ProcessGuideNavigationAgentAbstractFactory** osztályból örökölt, a navigációs ügynök aktuális lépés, munkamenet-állapot, felhasználói művelet vagy más logika alapján példányosítási logikáját tartalmazó konkrét navigációs ügynökgyár implementálása.

-   Opcionálisan a megfelelő paraméterek megadása érdekében felülbírálhatja a **navigationAgentCreationParameters()** paramétert a vezérlőosztályban.

-   A **navigationAgentFactory()** felülbírálása a vezérlőben a fent létrehozott navigációs ügynöki gyár példányosításának érdekében.

### <a name="action-classes"></a>Műveletosztályok

A műveletosztályok a felhasználói műveleteket képviselik, ezért ez a példa az **OK** művelet segítségével mutatja meg a műveletek létrehozásának módszerét.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

Az osztálynak 2 absztrakt metódust kell implementálnia:

-   **label()** – amely a művelethez kötött gombvezérlőben megjelenítendő címkét adja vissza.

-   **doExecute()**, amely a műveletet végrehajtja. Amint korábban említettük, az **OK** gomb egyszerűen visszahívást hajt végre a lépéshez. Más műveletek azonban ennél összetettebb logikát is tartalmaznak.

A műveletek a **SysExtension** keretrendszer használatával, a **ProcessGuideActionName** attribútum alapján vannak példányosítva. Az oldalszerkesztők példányosításához hasonlóan a lépésosztály implementálja az alapértelmezett műveletgyárat, és ez felülbírálható. Az oldalszerkesztő hozzáad egy ilyen gombvezérlőt.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

Ennek során megkéri a lépést, hogy hozzon létre egy műveletosztályt az átadott névhez, és a műveletet a gombhoz köti.

### <a name="summary"></a>Összegzés

Az ebben a témakörben ismertetekkel kapcsolatos információk összegzése érdekében itt találja a folyamathoz szükséges kódok átfogó összefoglalását:

1.  **ProdProcessGuideProductionStartController**

    1.  Az **initialStepName()** felülbírálása az első lépés nevének a beállításának érdekében.
    2.  Az **initializeNavigationRoute()** felülbírálása a navigációs térkép felépítéséhez.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Az **isComplete()** felülbírálása annak megadásához, hogy mikor tekintendő késznek a lépés.
    2.  A **pageBuilderName()** felülbírálása a használni kívánt lapszerkesztő megadásához.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Az **addDataControls()** felülbírálása a **Termelésazonosító** szövegmező hozzáadásához.
    2.  Az **OK** és a **Mégse** gombok hozzáadásához az **addActionControls()** felülbírálása.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  A **pageBuilderName()** felülbírálása a használni kívánt lapszerkesztő megadásához.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Az **addDataControls()** felülbírálása a rendelési, cikk- és mennyiségi adatcímkék hozzáadásához.

    2.  Az **OK** és a **Mégse** gombok hozzáadásához az **addActionControls()** felülbírálása.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > A **generateItemInfoForProdId()** metódus, amely a cikk-információs címkék létrehozásához használatos, ki van hagyva ebből a témakörből. Ezzel a metódussal néhány táblát le lehetkérdezni a cikkazonosító, a leírás és a dimenziók lekéréséhez. Ha jobban meg szeretné érteni a **generateItemInfoForProdId()** elemet, nézze meg a forráskódot.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  A **doExecute()** felülbírálása a termelés indítási folyamatának végrehajtásához és a folyamat befejezése üzenet hozzáadásához.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Sok gyakori mintázat (a felhasználói felület újragenerálása hiba esetén, a folyamat befejezésének üzenete, az **OK** és a **Mégse** viselkedés) átkerültek a keretrendszerbe – így az alkalmazásfejlesztőnek nem kell ismétlődő kódokat írnia, ami hibákat okozta, és a folyamatok inkonzisztens viselkedését okozhatja. Ahol azonban a forgatókönyvnek a gyakori útvonaltól el kell térni, az alkalmazásfejlesztőnek lehetősége van a megfelelő metódusok felülbírálatára, de ez mind explicit, mind nyomon követhető szándékos eltérés.


### <a name="extending-a-business-process"></a>Üzleti folyamat kibővítése

Ez a témakör eddig bemutatta, hogyan lehet egy új folyamatot felépíteni a **ProcessGuide** keretrendszer használatával. Ebben az utolsó szakaszban néhány példát talál arra, hogyan lehet kibővíteni ezt az üzleti folyamatot.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Lépés hozzáadása egy folyamathoz (a ProcessGuideNavigationAgentDefault használatával)

Hol bővítendő:

-   A **ProcessGuideController** osztály gyermeke a folyamathoz.

A bővítés módja:

-   Bővítse az **initializeNavigationRoute()** metódust a vezérlőosztályban, és hívja meg a **ProcessGuideNavigationRoute** osztály **addFollowingStep()** metódusát.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Lépés hozzáadása egy folyamathoz (egyéni navigációs ügynök használatával)

Hol bővítendő:

-   A **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent** gyermeke.

A bővítés módja:

-   A **ProcessGuideNavigationAgent** egy új gyermekosztályának létrehozása, amely a kívánt lépésnevet adja eredményül.

-   Hozzon létre egy új osztályt, amely a **ProcessGuideNavigationAgentFactory** osztályból származik, amely feltételesen visszaadja a fent létrehozott navigációs ügynököt.

-   Bővítse a **navigationAgentFactory()** metódust a vezérlőosztályban a fent létrehozott gyár visszaküldése érdekében.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Új vezérlőelem hozzáadása egy meglévő lépés felhasználói felületéhez 

Hol bővítendő:

-   A **ProdProcessGuidePageBuilder** gyermeke a lépéshez.

A bővítés módja:

-   Bővítse az **addDataControls()** metódust, és adja hozzá a további vezérlőt.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>A felhasználói felület teljes átalakítása egy meglévő lépésben

Hol bővítendő:

-   A **ProdProcessGuideStep** gyermeke.

A bővítés módja:

-   A **ProdProcessGuidePageBuilder** osztály új gyermekosztályának létrehozása és a kívánt felhasználói felület megvalósítása.

-   A lépésosztály **pageBuildeName()** metódusának kiterjesztése a **ProcessGuidePageBuilderNameAttribute** attribútum visszaadása érdekében a fent létrehozott osztályhoz.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>A logika megváltoztatása egy lépés késznek minősítésekor

Hol bővítendő:

-   A **ProdProcessGuideStep** gyermeke.

A bővítés módja:

-   Az **isComplete()** metódus kiterjesztése a további logika felépítéséhez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]