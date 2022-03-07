---
title: A termelési üzem végrehajtási felületének testreszabása
description: Ez a témakör leírja, hogyan lehet kiterjeszteni az aktuális képernyőkat, illetve új képernyők és gombok létrehozása a termelési emelet végrehajtási felületére.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 414fe5d6e16ad125bc2b9bb7ed427e5db5180ec9
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790974"
---
# <a name="customize-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének testreszabása

[!include [banner](../includes/banner.md)]

A fejlesztők bővíthetnek az aktuális képernyőt, vagy létrehozhatják a saját képernyőiket és gombjaikat a termelési emelet végrehajtási felületére. Miután hozzáadta az új elemek kódját, a rendszergazdák vagy az üzletvezetők egyszerűen hozzáadhatják őket a felülethez a szabványos konfigurációvezérlők segítségével.

Íme néhány példa a lehetséges megoldásokból, ha új oszlopokra van szükség a fő képernyőn:

- A képernyő `JmgProductionFloorExecutionMainGrid` kiterjesztése és a kívánt mezők hozzáadása.
- Hozzon létre egy új képernyőt, és adja hozzá új fő nézetként (lap).

## <a name="add-a-new-button-action"></a>Új gomb hozzáadása (művelet)

Ha új gombot (műveletet) szeretne hozzáadni, a következő lépésekkel hozzon létre egy osztályt, amely megvalósítja az egyéni műveletet.

1. Új nevű osztály `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action` létrehozása, ahol:

    - `<ExtensionPrefix>` Egyedi módon azonosítja a megoldást, jellemzően a vállalat neve alapján.
    - `<ActionName>`  Ez egy egyedi név az osztály számára. Általában azonosítja a művelet fajtáját.

1. Az új osztálynak ki kell bővítenie az `JmgProductionFloorExecutionAction` osztályt.
1. Minden szükséges metódus felülbírálása.

Például nézze meg a következő osztályok kódját:

- `JmgProductionFloorExecutionBreakAction`– egy egyszerű művelet osztálya, amely nem szükséges rekordokhoz.
- `JmgProductionFloorExecutionReportFeedbackAction`– olyan osztály, amely összetettebb funkciókat kínál.

Ha végzett, az új gomb (művelet) automatikusan megjelenik a **Microsoft Tervező** Dynamics 365 Supply Chain Management lapjain. Itt Ön (vagy rendszergazda vagy az emeleti vezető) egyszerűen hozzáadhatja az elsődleges vagy másodlagos eszköztárhoz, akár csak a szokásos gombokat. Az útmutatást lásd [a Termelési üzem végrehajtási felületének megtervezése](production-floor-execution-tabs.md) útmutatóban.

## <a name="add-a-new-main-view"></a>Új fő nézet hozzáadása

1. Hozzon létre egy új képernyőt, amely tartalmazza a kívánt elemeket és funkciókat. Ne feledje, hogy ez a képernyő egy új képernyő, nem kiterjesztés. A képernyő `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>` neve, ahol:

    - `<ExtensionPrefix>` Egyedi módon azonosítja a megoldást, jellemzően a vállalat neve alapján.
    - `<FormName>` A <a0/<a0/<a2/aki a képernyő egyedi neve.

1. Nevű menüelem `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>` létrehozása.
1. Hozzon létre egy névvel kiegészített kiterjesztést, ahol a módszer kibővíthető az új menüelemnek a `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension``getMainMenuItemsList` listához való hozzáadásával. A következő kód egy példát mutat be.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Ha végzett, az új fő nézet automatikusan megjelenik az Ellátásilánc-kezelés Lap Tervezés lapján, a Fő nézet **·** kombinált **·** mezőben. Itt Ön (vagy rendszergazda vagy emeleti vezető) egyszerűen hozzáadhatja az új vagy meglévő lapokhoz, ahogy a szokásos fő nézeteket is hozzáadhatja. Az útmutatást lásd [a Termelési üzem végrehajtási felületének megtervezése](production-floor-execution-tabs.md) útmutatóban.

## <a name="add-a-details-view"></a>Részletes nézet hozzáadása

1. Hozzon létre egy új képernyőt, amely tartalmazza a kívánt elemeket és funkciókat. Ne feledje, hogy ez a képernyő új, nem bővítmény. A képernyő `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail` neve, ahol: 

    - `<ExtensionPrefix>` Egyedi módon azonosítja a megoldást, jellemzően a vállalat neve alapján.
    - `<FormName>` A <a0/<a0/<a2/aki a képernyő egyedi neve.

1. Nevű menüelem `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail` létrehozása.
1. Hozzon létre egy névvel kiegészített kiterjesztést, ahol a módszer kibővíthető az új menüelemnek a `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension``getDetailsMenuItemList` listához való hozzáadásával.

Ha végzett, az új részletek nézet automatikusan megjelenik az Ellátásilánc-kezelés Lap Tervezés lapján, a Részletek nézet **·** kombinált **·** listában. Itt Ön (vagy rendszergazda vagy emeleti vezető) könnyen hozzáadhatja az új vagy meglévő lapokhoz, akár csak úgy, ahogyan a szokásos részletek nézetét is hozzáadhatja. Az útmutatást lásd [a Termelési üzem végrehajtási felületének megtervezése](production-floor-execution-tabs.md) útmutatóban.

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

## <a name="additional-resources"></a>További erőforrások

- [A termelési üzem végrehajtási felületének kialakítása](production-floor-execution-styles.md)
- [A termelési üzem végrehajtási felületének tervezése](production-floor-execution-tabs.md)
