---
title: Új ER-megoldás tervezése ZPL-címkék nyomtatásához
description: Ez a cikk bemutatja, hogy hogyan lehet új elektronikus jelentéskészítő (ER) megoldást tervezni a ZPL-címkék nyomtatására.
author: kfend
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 7ef83cf4822ca129af3ca01fa6ddd05219fee0d7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271763"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Új ER-megoldás tervezése ZPL-címkék nyomtatásához

[!include [banner](../includes/banner.md)]


Ez a cikk bemutatja, hogy hogyan konfigurálhatja az elektronikus jelentéskészítő (ER) [keretrendszer paramétereit a rendszergazda,](general-electronic-reporting.md) az elektronikus jelentéskészítő fejlesztő vagy az elektronikus jelentéskészítő funkcionális tanácsadó szerepkörű felhasználó, hogyan tervezheti meg egy új ER-megoldás szükséges ER-konfigurációit [a](general-electronic-reporting.md#Configuration) raktárkezelő rendszer adatainak eléréséhez, és egyéni raktári helycímkéket hozhat létre a ZPL(ZPL) II formátumban. Ezeket a lépéseket a **USRT** vállalatban hajthatja végre.

## <a name="business-scenario"></a>Üzleti eset

Ön egy raktárkezelést megvalósító Microsoft Dynamics vállalat a 365 Pénzügyben. Minden raktári helyet egy vonalkódot tartalmazó, önfelfedő címkével kell címkézni. A raktári dolgozók kézi vonalkódolvasókat fognak használni a vonalkódok beolvasására.

Minden raktári hely címkéje az élő tevékenységek előzetes hatókörében van megcímkézve. A raktári helycímkéket azonban igény szerint ki kell nyomtatni, ha a meglévő címkék megsérülnek, vagy a raktári polcokat újrakonfigurálják. A legutóbb kiadott ER funkciók használatával olyan új ER-megoldást konfigurálhat, amellyel a raktárvezetők közvetlenül kinyomtatják a címkéket egy címkenyomtatóba.

## <a name="configure-the-er-framework"></a>ER-keretrendszer konfigurálása

Kövesse az [ER-keretrendszer konfigurálása](er-quick-start2-customize-report.md#ConfigureFramework) rész lépéseit az ER-paraméterek minimális készletének beállításához. Ezt a beállítást be kell fejeznie, mielőtt az ER keretrendszert használva új ER-megoldást tervez.

## <a name="design-a-domain-specific-data-model"></a>Tartományspecifikus adatmodell kialakítása

Új ER-konfiguráció létrehozása, amely a Raktárkezelési [tartomány adatmodell-összetevőjét](er-overview-components.md#data-model-component) tartalmazza. Ezt az adatmodellt fogja a program később adatforrásként használni, amikor a raktári helycímkék előállításához er-formátumot tervez.

### <a name="import-a-data-model-configuration"></a>Adatmodell-konfiguráció importálása

A következő lépések szerint importálhatja a szükséges adatmodellt a Microsoft által biztosított XML-fájlból. Arra is lehetőség van, hogy saját adatmodellt hozzon létre a következő szakaszban leírtak szerint.

1. Töltse le [a Raktár model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) fájlt, és mentse a helyi számítógépre.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. Válassza a **Konfigurációk lap** munkaablakában az **XML-fájlból való Adatcsere-betöltés** \> **lehetőséget.**
5. Válassza **a Tallózás** lehetőséget, majd keresse meg és válassza **ki a Raktár model.version.1.xml fájlt**.
6. A konfiguráció importálásához kattintson az **OK** gombra.

![Importált ER adatmodell-konfiguráció a Konfigurációk lapon.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Adatmodell-konfiguráció létrehozása

A Microsoft által biztosított adatmodellfájl importálása helyett létrehozhat egy adatmodellt az elsőből. A feladat befejezését mutatja be egy példaként: Új [adatmodell-konfiguráció létrehozása](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Az adatmodell áttekintése

A konfigurált adatmodell szerkeszthető változatát az Adatmodell-tervező **oldalon lehet** megtekinteni.

![Az ER-adatmodell szerkezete az Adatmodell-tervező oldalon.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Modell-leképezés tervezése a konfigurált adatmodellhez

Az Elektronikus jelentéskészítő fejlesztő szerepkör felhasználójaként létre kell hoznia egy új ER-konfigurációt, amely tartalmazza a [Raktár](er-overview-components.md#model-mapping-component) adatmodell modell-hozzárendelési összetevőjét. Ez az összetevő a Dynamics 365 Pénzügy konfigurált adatmodelljét valósítja meg, és az adott alkalmazásra vonatkozik. Konfigurálnia kell úgy, hogy megadja azokat az alkalmazásobjektumokat, amelyek a konfigurált adatmodell futásidőben való kitöltéséhez lesznek használva. A feladat végrehajtásához meg kell értenie, hogyan valósítja meg a Raktárkezelés üzleti tartomány adatszerkezetét a Pénzügyben.

### <a name="import-a-model-mapping-configuration"></a>Modellleképezés konfigurációjának importálása

A következő lépések szerint importálhatja a szükséges modellleképezéseket a Microsoft által biztosított XML-fájlból. Arra is lehetőség van, hogy saját modellleképezést hozzon létre a következő szakaszban leírtak szerint.

1. Töltse le [a Raktári modell mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) fájlt, és mentse a helyi számítógépre.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. Válassza a **Konfigurációk lap** munkaablakában az **XML-fájlból való Adatcsere-betöltés** \> **lehetőséget.**
5. Válassza **a Tallózás** lehetőséget, majd keresse meg és **válassza ki a Raktármodell mapping.version.1.1.xml fájlt**.
6. A konfiguráció importálásához kattintson az **OK** gombra.

![Importált ER modellleképezés konfigurációja a Konfigurációk lapon.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Modellleképezés konfigurációjának létrehozása

A Microsoft által megadott modellleképezési fájl importálása helyett létrehozhat egy modellleképezést az elsőből. A feladat befejezését mutatja be egy példaként: Új modellleképezés [létrehozása.](er-quick-start1-new-solution.md#CreateModelMapping)

### <a name="review-the-model-mapping"></a>A modell-leképezés áttekintése

A konfigurált modellleképezés szerkeszthető változatát a modellleképezés tervezőlapján **lehet** megtekinteni.

![Az ER modellleképezés szerkezete a modellleképezés tervezőlapján.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Formátum tervezése

Elektronikus jelentéskészítési funkció tanácsadója szerepkörű felhasználóként Önnek kell olyan új ER-konfigurációt létrehoznia, amely tartalmaz [formátum](er-overview-components.md#format-component) összetevőt. Ennek az összetevőnek a konfigurálása a ZPL II kód használatával határozza meg a raktári helycímke elrendezését.

### <a name="import-a-format-configuration"></a>Formátumkonfiguráció importálása

A következő lépések szerint importálhatja a szükséges formátumot a Microsoft által biztosított XML-fájlból. Arra is lehetőség van, hogy saját formátumot hozzon létre a következő szakaszban leírtak szerint.

1. Töltse le [a Raktár helycímkéit.1.1.xml fájlt](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml), és mentse a helyi számítógépre.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. Válassza a **Konfigurációk lap** munkaablakában az **XML-fájlból való Adatcsere-betöltés** \> **lehetőséget.**
5. Válassza **a Tallózás** lehetőséget, majd keresse meg és **válassza ki a Raktár helycímkéit.verzió.1.1.xml fájlt**.
6. A konfiguráció importálásához kattintson az **OK** gombra.

![Importált ER formátumkonfiguráció a Konfigurációk lapon.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Formátumkonfiguráció létrehozása

A Microsoft által megadott formátumfájl importálása helyett létrehozhatja a formátumot az akkreta alapján. A feladat befejezését mutatja be egy példaként: Új [formátumkonfiguráció létrehozása](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>A formátum áttekintése

A konfigurált formátum **szerkeszthető változatát a Formátumtervező lapon lehet** megtekinteni.

![Az ER-formátum szerkezete a Formátumtervező lapon.](./media/er-design-zpl-labels-format.png)

A `model.Location.Label` formátum adatforrása a következő információkat tartalmazó címkék előállítására van konfigurálva:

- A raktár címe szövegként
- A raktár címe vonalkódként
- A hely címe
- Ellenőrző számjegyek

Az adatforrás **képletszerkesztő** lapján a címkék generálása érdekében használt ER-képlet egy olyan funkciót tartalmaz, amely a `CONCATENATE` kívánt elrendezésben egyesíti az adatokat.

![Az adatforrás képlete a Képlettervező lapon.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> A címkeelrendezés úgy van kialakítva, hogy a hely címe és az ellenőrző számjegyek a címke közepéhez igazodnak. A ZPL II azonban nem támogatja a vonalkódok igazítását a középre. Ennek megfelelően az adatforrás képletét `model.Location.Warehouse.Alignment` használja a program a vonalkódnak a címke közepére igazítására. A képlet a raktár címében szereplő karakterek száma alapján számítja ki a vonalkód bal eltolási számát.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>A környezet előkészítése a létrehozott címkék előnézetének megtekintésére

A következő példa egy nyomtató-emulátor alkalmazása a ZPL-címkékhez a létrehozott címkék előzetes képének megjelenítése a képernyőn. A beállítás engedélyezéséhez kövesse az alábbi lépéseket.

1. Adja hozzá [az](er-destination-type-print.md) ER nyomtató célhelyet a Raktári **hely** ER formátumhoz, és állítsa be úgy, [hogy a generált címkéket a Pénzügy rendszerből küldje el a dokumentumirányítási ügynöknek (DRA).](install-document-routing-agent.md)
2. A DRA telepítése és konfigurálása a létrehozott címkéknek a Pénzügy rendszerből egy helyi nyomtatóra való leszállítva, amely az aktuális munkaállomásról érhető el.
3. Helyi nyomtató hozzáadása az aktuális munkaállomáshoz, és állítsa be úgy, hogy a generált címkéket átadja a DRA-tól egy nyomtatóemulátor alkalmazásnak.
4. Telepítsen egy nyomtató-emulátor alkalmazást a króm webböngésző kiterjesztéseként, és állítsa be úgy, hogy a generált címkéket a helyi nyomtatóról egy olyan webszolgáltatásnak adja át, amely megjeleníti a generált címkéket, és visszaadja őket előnézeti nézetként a nyomtató emulátorának.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>Er-jelentés</p>
<p>Nyomtatási cél</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Dokumentumirányítási ügynök</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Helyi nyomtató</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Nyomtató emulátora</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Webszolgáltatás megjelenítése</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Nyomtatóemulátor alkalmazás telepítése és konfigurálása

A ZPL-megjelenítő motor nyomtató-emulátoralkalmazásának hozzáadása a króm webböngészőhöz. Ez a példa a [címke ZPL webszolgáltatáson alapuló ZPL-nyomtató](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) emulátort [használja](http://labelary.com/service.html). A nyomtató emulátor alkalmazása át fogja adni a generált címkéket ZPL-formátumban a helyi nyomtatótól a webszolgáltatásnak, majd előnézeti képként visszaadja a címkéket PDF- vagy PNG-fájlként.

1. A Króm webtárban keresse meg és válassza ki a használni kívánt nyomtató-emulátor alkalmazást. Ezután a **Krómba való felvételhez válassza a Hozzáadás** a krómhoz lehetőséget.

    ![A nyomtató emulátoralkalmazásának hozzáadása a Króm webböngészőhöz a króm webáruházból](./media/er-design-zpl-labels-add-app.png)

2. Válassza **az Alkalmazás elindítása** lehetőséget a nyomtatóemulátor alkalmazásnak a króm webböngészőből való futtatásához.

    ![A nyomtató emulátoralkalmazásának futtatása a króm webböngészőből.](./media/er-design-zpl-labels-run-app.png)

3. A futó alkalmazás konfigurálása:

    1. A pályázat kikapcsolása.
    2. A nyomtatóbeállításoknál állítsa az állomást **127.0.0.1-re**.
    3. Állítsa a portot **9100-ra**.

        ![A nyomtatóemulátor alkalmazás konfigurálása](./media/er-design-zpl-labels-configure-app.png)

    4. Az alkalmazás újra bekapcsolva. Üzenetet kell kapnia, hogy a nyomtató a megadott állomáson és porton indult el.

        ![Nyomtatóemulátor alkalmazása bekapcsolva.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Mivel a nyomtató-emulátor alkalmazása, amely ebben a példában egy webszolgáltatáson alapul, címkék megjelenítésére, győződjön meg róla, hogy a biztonsági beállítások lehetővé teszik a szolgáltatás kommunikációját. Ellenkező esetben az alkalmazás nem kapja meg a megjelenített címkéket, és ezeknek a címkéknek az előnézete nem lesz elérhető.

### <a name="add-and-configure-a-local-printer"></a>Helyi nyomtató hozzáadása és konfigurálása

[Új helyi nyomtató hozzáadása](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b), amely segítségével az aktuális eszköz át tudja adni a generált címkéket a DRA-tól a nyomtatóemulátor alkalmazásnak.

1. A Windows rendszerben válassza a **Nyomtatók** \> **beállításai leolvasók** \> **·** \> **\& beállítását.**
2. Nyomtatóolvasók **\& beállításainak kiválasztása**.
3. Nyomtató **vagy leolvasó hozzáadásához** válassza az Eszköz **hozzáadása lehetőséget**.
4. Ha **a nyomtató nem szerepel a** listában, válassza a Manuális hozzáadás **lehetőséget**.
5. A Nyomtató **megkerese más** beállítások szerint mezőben **válassza a Helyi nyomtató hozzáadása, illetve a hálózati nyomtató kézi beállításokkal való beállítását**.
6. A Nyomtatóport **kiválasztása** mezőben válassza az Új **port létrehozása** lehetőséget, majd hajtsa végre a következő lépéseket:

    1. A Port **típusa mezőben** válassza a Szabványos **TCP/IP-port lehetőséget**.
    2. Az Állomásnév **vagy IP-cím mezőbe** írja **be a 127.0.0.1 nevet**.
    3. A Port **neve mezőbe** írja be a **ZPL-t**.
    4. Várjon, amíg **a TCP/IP-port** észlelési művelete be nem fejeződött.
    5. Az Eszköztípus **mezőben** válassza az Egyéni **lehetőséget**, majd a Beállítások **lehetőséget**.
    6. Győződjön meg a következő portbeállításokról:

        - **Port neve:** ZPL
        - **Nyomtató neve vagy IP-címe:** 127.0.0.1
        - **Protokoll:** nyers
        - **Port száma:** 9100

7. A Nyomtató-illesztőprogram **telepítése mezőben** válassza csak a **Generic / Text lehetőséget**.
8. A Nyomtató **neve mezőben** adja meg **azPrinter mezőt**.

![Helyi nyomtató hozzáadása az aktuális eszközhöz.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>A DRA telepítése és konfigurálása

A DRA előkészítése a létrehozott címkéknek a Pénzügy rendszerből a konfigurált helyi nyomtatónak való átadódra.

1. [Telepítse a DRA-t](install-document-routing-agent.md#install-the-document-routing-agent).
2. [A DRA konfigurálása](install-document-routing-agent.md#configure-the-document-routing-agent)
3. [Regisztrálja a helyi nyomtatót a](install-document-routing-agent.md#register-network-printers) DRA-ban.
4. [Aktiválja a helyi nyomtatót](install-document-routing-agent.md#administer-network-printers) a Pénzügyi környezetben.

![A DRA előkészítése a létrehozott címkék nyomtatására.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>ER-célhely konfigurálása

Az ersz. cél előkészítésével adja át a létrehozott címkéket a Pénzügy és a DRA számára.

1. Ugorjon a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési cél** részre.
2. Az Elektronikus jelentés **céloldalán**, a munkaablakban válassza az Új **lehetőséget**.
3. A Hivatkozás **mezőben** válassza ki a Raktár **helycímkéit**.
4. Válassza az **Új** lehetőséget a **Fájl célja** gyorslapon.
5. A Név **mezőben** adja meg a **Címkéket**.
6. A Fájlösszetevő **neve mezőben** válassza a Jelentés **lehetőséget**.
7. Válassza a **Beállítások** lehetőséget.
8. A Cél beállításai **párbeszédpanel** Nyomtató **lapján** **állítsa az Engedélyezett** beállítást Igen **beállításra**.
9. A Nyomtató **neve mezőben** válassza azPrinter **lehetőséget**.
10. Válassza a **ZPL-t a Dokumentum útvonaltípus** **mezőben**.
11. Válassza ki az **OK** lehetőséget.

![Az Elektronikus jelentés céloldalán található Raktári helycímkék formátumának er célhelyének konfigurálása](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Raktári helyek áttekintése

1. Ugrás a Raktárkezelés **beállítása raktári** \> **·** \> **helyekhez.** \> **·**
2. A Helyek **lapon** szűrővel csak az Ellenőrző számjegyek mezőben megadott **értékkel megadott helyeket lehet** megtekinteni.

![A Helyek lapon található raktári helyek áttekintése.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Raktári helycímkék nyomtatása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lapon**, a konfigurációs fában bontsa ki a Raktári **modellt**, és válassza a Raktár **helycímkéit**.
3. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
4. Az Elektronikus jelentés **paraméterei** párbeszédpanelen a **Beszúrni** kívánt rekordok lapon válassza a Szűrő **lehetőséget**.
5. A Tartomány **lapon** keresse meg azt a sort, **·** **·** **amelyben** a Tábla mező a Helyek, a Mező mezőben pedig a Hely **érték van beállítva.** A Feltételek **mezőben** adja meg az **LPEnabled mezőt**.
6. Válassza ki az **OK** lehetőséget.
7. Válassza ki az **OK** lehetőséget. A címke generálása és megjelenítése a nyomtató emulátoralkalmazásának előnézeti lapján.

![A Zpl-nyomtató emulátor alkalmazása előnézeti lapján létrehozott címke áttekintése](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Címke elrendezésének módosítása

A raktári helycímkék aktuális elrendezése megváltoztatható. A következő példa bemutatja, hogyan kell módosítani az elrendezést, hogy a generált címkék tartalmazzák a helyprofil azonosítóját.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A "Vázlatok **használata" állapotú**[ER felhasználói paraméter](electronic-reporting-destinations.md#applicability) beállítása Igen **beállításra**.
3. A Konfigurációk **lapon**, a konfigurációs fában bontsa ki a Raktári **modellt**, és válassza a Raktár **helycímkéit**.
4. Válassza a **Tervező** lehetőséget.
5. Válassza ki **az adatforrást** a **Formátumtervező** lap Hozzárendelés lapján`model.Location.Label`.
6. Az Adatforrás tulajdonságai párbeszédpanelen **válassza a Receptúra** **·**\> szerkesztése lehetőséget.**·**
7. A Receptúra **tervezőlap** **Receptúra mezőjében** ellenőrizze a címkék előállításához használt ER-képletet.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. A képlet frissítése a helyprofil azonosítójának a létrehozott címkékhez való hozzáadásához.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Válassza a **Mentés** lehetőséget.
10. Válassza ki az **OK** lehetőséget.
11. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
12. Az Elektronikus jelentés **paraméterei** párbeszédpanelen a **Beszúrni** kívánt rekordok lapon válassza a Szűrő **lehetőséget**.
13. A Tartomány **lapon** keresse meg azt a sort, **·** **·** **amelyben** a Tábla mező a Helyek, a Mező mezőben pedig a Hely **érték van beállítva.** A Feltételek mezőben **adja** meg a **Mintát**.
14. Válassza ki az **OK** lehetőséget.
15. Válassza ki az **OK** lehetőséget. A címke generálása és megjelenítése a nyomtató emulátoralkalmazásának előnézeti lapján.

![Egy generált címke áttekintése, amely tartalmazza a helyprofil azonosítóját a ZPL-nyomtató emulátor alkalmazása előnézeti lapján.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Kódolás

> [!NOTE]
> Szinkronizálni kell a szerkeszthető ER-formátum **Common\\File** összetevő kódolási beállítását és a tervezett címke megfelelő beállítását. A CommonFile **[...](er-suppress-bom-characters.md)** összetevő kódolási **Common\\File** mezőjének értéke nem szabad ellentétesnek lennie a címke kódolásának szabályozására használt ZPL-paranccsal (például `^CI` a parancssal). Az ER nem ellenőrzi, hogy ezek a beállítások szinkronizálva vannak-e.

## <a name="additional-resources"></a>További erőforrások

[Nyomtatási cél](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
