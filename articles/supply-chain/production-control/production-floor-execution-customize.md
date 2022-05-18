---
title: A termelési üzem végrehajtási felületének testreszabása
description: Ez a témakör leírja, hogyan lehet kiterjeszteni az aktuális képernyőkat, illetve új képernyők és gombok létrehozása a termelési emelet végrehajtási felületére.
author: johanhoffmann
ms.date: 05/04/2022
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ad5037442f27a5068b38613655591f1298808eac
ms.sourcegitcommit: 28537b32dbcdefb1359a90adc6781b73a2fd195e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712943"
---
# <a name="customize-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének testreszabása

[!include [banner](../includes/banner.md)]

A fejlesztők bővíthetnek az aktuális képernyőt, vagy létrehozhatják a saját képernyőiket és gombjaikat a termelési emelet végrehajtási felületére. Miután hozzáadta az új elemek kódját, a rendszergazdák vagy az üzletvezetők egyszerűen hozzáadhatják őket a felülethez a szabványos konfigurációvezérlők segítségével.

Íme néhány példa a lehetséges megoldásokból, ha új oszlopokra van szükség a fő képernyőn:

- A képernyő kiterjesztése `JmgProductionFloorExecutionMainGrid` és a kívánt mezők hozzáadása.
- Hozzon létre egy új képernyőt, és adja hozzá új fő nézetként (lap).

## <a name="add-a-new-button-action"></a>Új gomb hozzáadása (művelet)

Ha új gombot (műveletet) szeretne hozzáadni, a következő lépésekkel hozzon létre egy osztályt, amely megvalósítja az egyéni műveletet.

1. Új nevű osztály létrehozása, ahol `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`:

    - `<ExtensionPrefix>` Egyedi módon azonosítja a megoldást, jellemzően a vállalat neve alapján.
    - `<ActionName>` az osztály egyedi neve. Általában azonosítja a művelet fajtáját.

1. Az új osztálynak ki kell bővítenie az osztályt `JmgProductionFloorExecutionAction`.
1. Minden szükséges metódus felülbírálása.

Például nézze meg a következő osztályok kódját:

- `JmgProductionFloorExecutionBreakAction`– egy egyszerű művelet osztálya, amely nem szükséges rekordokhoz.
- `JmgProductionFloorExecutionReportFeedbackAction`– olyan osztály, amely összetettebb funkciókat kínál.

Ha végzett, az új gomb (művelet) **automatikusan megjelenik a Microsoft Tervező lapjain** Dynamics 365 Supply Chain Management. Itt Ön (vagy rendszergazda vagy az emeleti vezető) egyszerűen hozzáadhatja az elsődleges vagy másodlagos eszköztárhoz, akár csak a szokásos gombokat. Az utasításokat lásd [a Termelés - emelet végrehajtási felületének tervezése.](production-floor-execution-tabs.md)

## <a name="add-a-new-main-view"></a>Új fő nézet hozzáadása

1. Hozzon létre egy új képernyőt, amely tartalmazza a kívánt elemeket és funkciókat. Ne feledje, hogy ez a képernyő egy új képernyő, nem kiterjesztés. A képernyő neve `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, ahol:

    - `<ExtensionPrefix>` Egyedi módon azonosítja a megoldást, jellemzően a vállalat neve alapján.
    - `<FormName>` A <a0/<a0/<a2/aki a képernyő egyedi neve.

1. Nevű menüelem létrehozása `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Hozzon létre egy névvel kiegészített `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension` kiterjesztést, `getMainMenuItemsList` ahol a módszer kibővíthető az új menüelemnek a listához való hozzáadásával. A következő kód egy példát mutat be.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionMenuItemProvider))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Ha végzett, **·** **az** új fő nézet automatikusan megjelenik az Ellátásilánc-kezelés Lap Tervezés lapján, a Fő nézet kombinált mezőben. Itt Ön (vagy rendszergazda vagy emeleti vezető) egyszerűen hozzáadhatja az új vagy meglévő lapokhoz, ahogy a szokásos fő nézeteket is hozzáadhatja. Az utasításokat lásd [a Termelés - emelet végrehajtási felületének tervezése.](production-floor-execution-tabs.md)

## <a name="add-a-details-view"></a>Részletes nézet hozzáadása

1. Hozzon létre egy új képernyőt, amely tartalmazza a kívánt elemeket és funkciókat. Ne feledje, hogy ez a képernyő új, nem bővítmény. A képernyő neve `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, ahol: 

    - `<ExtensionPrefix>` Egyedi módon azonosítja a megoldást, jellemzően a vállalat neve alapján.
    - `<FormName>` A <a0/<a0/<a2/aki a képernyő egyedi neve.

1. Nevű menüelem létrehozása `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Hozzon létre egy névvel kiegészített `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension` kiterjesztést, `getDetailsMenuItemList` ahol a módszer kibővíthető az új menüelemnek a listához való hozzáadásával.

Ha végzett, **·** **az** új részletek nézet automatikusan megjelenik az Ellátásilánc-kezelés Lap Tervezés lapján, a Részletek nézet kombinált listában. Itt Ön (vagy rendszergazda vagy emeleti vezető) könnyen hozzáadhatja az új vagy meglévő lapokhoz, akár csak úgy, ahogyan a szokásos részletek nézetét is hozzáadhatja. Az utasításokat lásd [a Termelés - emelet végrehajtási felületének tervezése.](production-floor-execution-tabs.md)

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Numerikus billentyűzet hozzáadása képernyőkhez vagy párbeszédpanelhez

Az alábbi példa bemutatja, hogyan lehet numerikus billentyűzeteket hozzáadni a képernyőkhez.

1. Az egyes képernyőket tartalmazó numerikus billentyűzetvezérlők számának meg kell egynie a képernyőn található numerikus billentyűzetek számával.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Állítsa be az egyes numerikus billentyűzetvezérlők viselkedését, és kapcsolja az egyes numerikus billentyűzetvezérlőket egy numerikus billentyűzet képernyőrészhez.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Numerikus billentyűzet használata előugró párbeszédpanelként

A következő példa egy, az előugró párbeszédpanelen használható numerikus billentyűzetvezérlő beállítását mutatja be.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

A következő példa bemutatja az egyik módja a numerikus billentyűzet előugró párbeszédpanelének hívását.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="add-a-date-and-time-controls-to-a-form-or-dialog"></a>Dátum- és idővezérlők hozzáadása képernyőhöz vagy párbeszédpanelhez

Ez a szakasz bemutatja, hogyan lehet dátum- és idő vezérlőelemeket hozzáadni egy képernyőhöz vagy párbeszédpanelhez. A felhasználóbarát dátum- és idővezérlők segítségével a dolgozók megadhatják a dátumokat és időpontokat. A következő képernyőképek mutatják, hogyan jelennek meg a vezérlőelemek az oldalon. Az idővezérlő 12 órás és 24 órás verziókat is biztosít; A megjelenő verzió annak a felhasználói fióknak a preferenciakészletét követi, amelyen a felület fut.

![Példa dátumellenőrzésre.](media/pfe-customize-date-control.png "Dátumellenőrzés – példa")

![Idő-ellenőrzési példa 12 órás órákkal.](media/pfe-customize-time-control-12h.png "Idő-ellenőrzési példa 12 órás órákkal")

![Idő-ellenőrzési példa 24 órás órákkal.](media/pfe-customize-time-control-24h.png "Idő-ellenőrzési példa 24 órás órákkal")

Az alábbi művelet egy példát mutat be arra, hogyan lehet dátum- és idővezérlőket hozzáadni egy képernyőhöz.

1. Adjon hozzá egy kontrollert a képernyőhöz minden olyan dátum- és idővezérlőhöz, amelybe a képernyőnek tartalmaznia kell. (A kontrollerek számának meg kell egynie a képernyő dátum- és idővezérlőinek számában.)

    ```xpp
    private JmgProductionFloorExecutionDateTimeController  dateFromController; 
    private JmgProductionFloorExecutionDateTimeController  dateToController; 
    private JmgProductionFloorExecutionDateTimeController  timeFromController; 
    private JmgProductionFloorExecutionDateTimeController  timeToController;
    ```

1. A szükséges változók (típus) deklarálva `utcdatetime`.

    ```xpp
    private utcdatetime fromDateTime;
    private utcdatetime toDateTime;
    ```

1. Olyan metódusok létrehozása, amelyekben a dátum-/idő frissítését a dátum-idő kontrollerek frissítik. A következő példa egy ilyen módszert mutat be.

    ```xpp
    private void setFromDateTime(utcdatetime _value)
        {
            fromDateTime = _value;
        }
    ```

1. Az egyes dátum-idő kontrollerek viselkedésének beállítása és az egyes vezérlők csatlakoztatása egy képernyőrészhez. Az alábbi példa bemutatja, hogyan lehet beállítani a "dátumtól" és az "időtől" vezérlők adatait. A program ad hozzá hasonló kódot a dátumhoz és az időhöz (nem jelenik meg).

    ```xpp
    /// <summary>
    /// Initializes all date and time controllers, defines their behavior, and connects them with the form parts.
    /// </summary>
    private void initializeDateControlControllers()
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        timeFromController = new JmgProductionFloorExecutionDateTimeController();
        timeFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        timeFromController.parmDateTimeValue(fromDateTime);
        
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, timeFromController);
        TimeFromFormPart.getPartFormRun().setTimeControlController(timeFromController, dateFromController);
        
        ...

    }
    ```

    Ha csak egy dátumellenőrzésre van szüksége, akkor átugorhatja az időellenőrzés beállításait, és ehelyett beállíthatja a dátumellenőrzést, amint azt az alábbi példa mutatja:

    ```xpp
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, null);
    }
    ```

## <a name="additional-resources"></a>További erőforrások

- [A termelési üzem végrehajtási felületének kialakítása](production-floor-execution-styles.md)
- [A termelési üzem végrehajtási felületének tervezése](production-floor-execution-tabs.md)
