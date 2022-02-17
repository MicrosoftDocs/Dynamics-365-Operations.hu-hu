---
title: A termelési üzem végrehajtási felületének testreszabása
description: Ez a témakör elmagyarázza, hogyan lehet kiterjeszteni a jelenlegi űrlapokat, illetve hogyan lehet új űrlapokat és gombokat létrehozni a termelési szint végrehajtási felületéhez.
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
ms.openlocfilehash: 67fb381cbef6f1673afcaa834666b4a859bdf4e6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066546"
---
# <a name="customize-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének testreszabása

[!include [banner](../includes/banner.md)]

A fejlesztők kiterjeszthetik a jelenlegi űrlapokat, vagy létrehozhatják saját űrlapjaikat és gombjaikat a termelési szint végrehajtási felületéhez. Miután hozzáadta ezekhez az új elemekhez a kódot, az adminisztrátorok vagy a műhelyvezetők a szabványos konfigurációs vezérlők segítségével könnyedén hozzáadhatják őket a felülethez.

Például itt van néhány lehetséges megoldás, ha új oszlopokra van szükség fő formában:

- Hosszabbítsa meg a`JmgProductionFloorExecutionMainGrid` űrlapot, és adja hozzá a kívánt mezőket.
- Hozzon létre egy új űrlapot, és adja hozzá új főnézetként (lapként).

## <a name="add-a-new-button-action"></a>Új gomb hozzáadása (művelet)

Új gomb (művelet) hozzáadásához kövesse az alábbi lépéseket az egyéni műveletet megvalósító osztály létrehozásához.

1. Hozzon létre egy új osztályt, amelynek neve`<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, ahol:

    - `<ExtensionPrefix>` egyedileg azonosítja a megoldást, jellemzően a vállalat nevével.
    - `<ActionName>` az osztály egyedi neve. Jellemzően a cselekvés típusát azonosítja.

1. Az új osztálynak ki kell terjesztenie a`JmgProductionFloorExecutionAction` osztály.
1. Minden szükséges módszer felülírása.

Példákért nézze meg a következő osztályok kódját:

- `JmgProductionFloorExecutionBreakAction`– Egy osztály egy egyszerű művelethez, amelyhez nincs szükség rekordokra.
- `JmgProductionFloorExecutionReportFeedbackAction`– Összetettebb funkcionalitást biztosító osztály.

Ha végzett, az új gomb (művelet) automatikusan megjelenik a listában **Tervezési lapok** oldal a Microsoftban Dynamics 365 Supply Chain Management. Ott Ön (vagy egy adminisztrátor vagy az emeleti menedzser) könnyedén hozzáadhatja az elsődleges vagy másodlagos eszköztárhoz, ahogy a szabványos gombokat is. Az utasításokat lásd [Tervezze meg a termelési szint végrehajtási felületét](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Új főnézet hozzáadása

1. Hozzon létre egy új űrlapot, amely rendelkezik a kívánt elemekkel és funkciókkal. Vegye figyelembe, hogy ez az űrlap új űrlap, nem kiterjesztés. Nevezze el az űrlapot`<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, ahol:

    - `<ExtensionPrefix>` egyedileg azonosítja a megoldást, jellemzően a vállalat nevével.
    - `<FormName>` az űrlap egyedi neve.

1. Hozzon létre egy menüelemet, amelynek neve `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Hozzon létre egy nevű bővítményt`<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, hol a`getMainMenuItemsList` módszer kibővül az új menüpont hozzáadásával a listához. A következő kód példát mutat.

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

Ha végzett, az új fő nézet automatikusan megjelenik a listában **Fő nézet** kombinált doboz a **Tervezési lapok** oldalon a Supply Chain Management oldalon. Itt Ön (vagy egy adminisztrátor vagy az emeleti menedzser) könnyedén hozzáadhatja új vagy meglévő lapokhoz, ahogyan a szabványos fő nézeteket is. Az utasításokat lásd [Tervezze meg a termelési szint végrehajtási felületét](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Részletek nézet hozzáadása

1. Hozzon létre egy új űrlapot, amely rendelkezik a kívánt elemekkel és funkciókkal. Vegye figyelembe, hogy ez az űrlap új, nem bővítmény. Nevezze el az űrlapot`<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, ahol: 

    - `<ExtensionPrefix>` egyedileg azonosítja a megoldást, jellemzően a vállalat nevével.
    - `<FormName>` az űrlap egyedi neve.

1. Hozzon létre egy menüelemet, amelynek neve `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Hozzon létre egy nevű bővítményt`<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, hol a`getDetailsMenuItemList` módszer kibővül az új menüpont hozzáadásával a listához.

Ha végzett, az új részletes nézet automatikusan megjelenik a listában **Részletek nézet** kombinált doboz a **Tervezési lapok** oldalon a Supply Chain Management oldalon. Itt Ön (vagy egy adminisztrátor vagy az emeleti menedzser) egyszerűen hozzáadhatja új vagy meglévő lapokhoz, ugyanúgy, mint a szabványos részletes nézeteket. Az utasításokat lásd [Tervezze meg a termelési szint végrehajtási felületét](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Számbillentyűzet hozzáadása egy űrlaphoz vagy párbeszédpanelhez

A következő példa bemutatja, hogyan lehet számbillentyűzeteket hozzáadni egy űrlaphoz.

1. Az egyes űrlapokon található számbillentyűzet-vezérlők számának meg kell egyeznie az adott űrlapon lévő numerikus billentyűzetek számával.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Állítsa be az egyes számbillentyűzet-vezérlők viselkedését, és csatlakoztassa az egyes számbillentyűzet-vezérlőket egy számbillentyűzet-alkatrészhez.

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

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Használjon számbillentyűzetet felugró párbeszédpanelként

A következő példa bemutatja a számbillentyűzet-vezérlő beállításának egyik módját egy felugró párbeszédpanelhez.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

A következő példa bemutatja a számbillentyűzet felugró párbeszédablak meghívásának egyik módját.

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
