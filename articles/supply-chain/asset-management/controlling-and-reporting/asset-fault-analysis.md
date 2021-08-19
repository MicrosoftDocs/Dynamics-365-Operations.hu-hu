---
title: Eszköz hibájának elemzése
description: Ez a cikk az Eszközkezelés hibás eszköz elemzésének költségét ismerteti.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 880ed35a9780185836218a5c2a7addb2a47eabd737d6bec99794ecb7a0959791
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779278"
---
# <a name="asset-fault-analysis"></a>Eszköz hibájának elemzése

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezeléssel elemezheti az eszközök hibaregisztrációit, hogy áttekintést kapjon egy adott időszakra vonatkozóan regisztrált hibák teljes számáról. A hibarögzítéseket különböző szempontok alapján lehet elemezni, például az eszközökre, eszközök típusára, funkcionális helyekre, hibatünetekre vagy hibatípusokra koncentrálva.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszköz hibájának elemzése**.

2. Az **Eszköz hibájának elemzése számítás** párbeszédpaneljén a **Szint** mező segítségével jelezheti, hogy milyen részletesen szeretné megjeleníteni az eszköz hibás sorait a funkcionális helyekre vonatkozóan. 

    Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a hibás eszköz minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. 
        
    Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely az eszközhiba minden sorát megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.

3. Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket, meghibásodási dátumokat, hibaokokat és hibamegoldásokat a **Szerepeltetni kívánt rekordok** gyorslapon.

4. Kattintson az **OK** gombra az számítás indításához.

5. Az **Eszköz hibájának elemzése** lapon kattintson a **Csoportosítás alapja** műveletlap csoport gombjaira a látni kívánt részletességi szint megjelenítéséhez. Az aktivált gombok ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a gombokat.

6. A képernyőn látható választások megjelenítéséhez kattintson a **Számítások frissítése** hivatkozásra. 

>[!NOTE]
>Minden alkalommal, amikor aktiválja vagy inaktiválja a **Csoportosítás alapja** gombot, ne felejtsen el a **Számítások frissítése** gombra kattintani. Erre azért van szükség, mert a rendszer nagy mennyiségű adatot dolgoz fel a hiba valószínűségének újraszámításakor.

## <a name="examples"></a>Példák

A hibaregisztrációk elemzésére számos mód van. Ebben a szakaszban öt példát láthat arra, hogy a különböző választások milyen módon tudnak betekintést és részleteket szolgáltatni az eszközhibák regisztrálásának elemzésekor.

### <a name="group-by-symptoms"></a>Csoportosítás tünetek szerint

A lenti képernyőfotón csak a **Tünet** gomb van kiválasztva.

- A hibaregisztrációk három hibatüneten történtek: „Légszivárgás”, „Kiégett biztosíték” és „Elakadtak berendezések”.  
- A **Valószínűség %** oszlopban a százalékos értékek 100%-ig adhatók. A valószínűség a hibaelemzés összes **Tünet** regisztrációján alapul.

![1. ábra](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a>Csoportosítás a tünetek és időszak szerint

A lenti képen az **Év** és a **Hónap** hozzáadódik annak a megjelenítéséhez, hogy hogyan lehet megtekinteni a hibák regisztrálását a kiválasztott időszakban.

- A hibatünetek most már éves/havi regisztrációkként jelennek meg.  
- Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban, akkor 100%-ot ad hozzá. A valószínűség az adott hibaelemzés **Tünet** regisztrációján alapul. Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatünetet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hiba miatti regisztrációk számát.

![2. ábra](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a>Csoportosítás több tünet és eszköz szerint

Az eszközök és az eszköztípus kombinációja az alábbi három képernyőfotón megjelenített számítások alapjaként használatos, ami növelni fogja a részletek szintjét.  

Általában a **Csoportosítás dátum szerint**, a **Csoportosítás eszköz szerint**, a **Csoportosítás munkavégzési helyszín szerint** műveletiablaktábla-csoportok, valamint a **Hiba** gomb (hibaazonosító), tartalmaz időszakokat vagy eszközkapcsolatokat. A **Hibajelenség**, a **Terület**, a **Típus**, az **Ok**, az **Orvoslás** gomb a hibakezeléshez használt kategóriák, amelyek az eszközhiba-regisztrációk elemzéséhez és a problématerületek lehatárolásához szükségesek.  

**Csoportosítás tünet, eszköz és eszköztípus szerint**

A lenti képernyőfotón hozzáadtuk az **Eszköz** és **Eszköztípus** elemeket, hogy több részletet kapjunk a hibák regisztrálásával kapcsolatban.

- A hiba tünetei most fel vannak osztva az **Eszköz** / **Eszköztípus** / **Tünet** kombinációkban.  
- Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációknak ebben a sorrendben, akkor mindegyik legfeljebb 100% lehet. A valószínűség az adott hibaelemzés **Tünet** regisztrációján alapul. Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatünetet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hiba miatti regisztrációk számát.

![3. ábra](media/08-controlling-and-reporting.png)

**Csoportosítás két tünet, eszköz és eszköztípus szerint**

A lenti képernyőfotón hozzáadtuk a **Terület** elemet a **Tünet**, **Eszköz** és **Eszköztípus** elemekhez, hogy több részletet kapjunk a hibák regisztrálásával kapcsolatban.

- Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációt az eszköznek, akkor mindegyik legfeljebb 100% lehet. A valószínűség az adott hibaelemzés **Tünet** és **Terület** kombinációján alapul. Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibaterületet jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hibaterület miatti regisztrációk számát.  

![4. ábra](media/09-controlling-and-reporting.png)

**Csoportosítás három tünet, eszköz és eszköztípus szerint**

A lenti képernyőfotón a **Típus** lett hozzáadva, és megjelenik a példaként használt legrészletesebb számítás.
 
- Ha minden hónap minden százalékát hozzáadja a **Valószínűség%** oszlopban az **Eszköz** / **Eszköztípus** / **Tünet** kombinációt az eszköznek, akkor mindegyik legfeljebb 100% lehet. A valószínűség az adott hibaelemzés **Tünet**, **Terület** és **Típus** kombinációján alapul. Ha egy eszköznek nagy számú sora van, de nagy százalék egy sorban jelenik meg, ezt a hibatípust jobban meg kell vizsgálni, hogy milyen módon korlátozhatja az adott hibatípus regisztrációinak számát.

![5. ábra](media/10-controlling-and-reporting.png)


>[!NOTE]
>A munkarendeléseken és a karbantartási kérelmeken létrehozott összes hibaregisztráció áttekintéséhez kattintson ide: **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Eszközhibák**. Az **Eszközhibák** oldalon válasszon ki egy eszközhiba-regisztrációt, és a **Kapcsolódó információ** ablaktábla kibontásával megtekintheti a kapcsolódó munkarendeléssel vagy karbantartási kérelemmel kapcsolatos információkat.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]