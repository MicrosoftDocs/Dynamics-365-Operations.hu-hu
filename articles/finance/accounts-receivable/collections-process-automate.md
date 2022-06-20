---
title: Beszedési folyamat automatizálása
description: Ez a cikk bemutatja a beszedési folyamat stratégiáit, amelyek automatikusan azonosítják azokat a vevői számlákat, amelyekhez e-mailben küldött emlékeztető, beszedési tevékenység vagy fizetési felszólítás szükséges.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 9ec749db197b4d04ee2e99ac7a16f4f2120c6707
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946178"
---
# <a name="collections-process-automation"></a>Beszedési folyamat automatizálása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a beszedési folyamat stratégiáit, amelyek automatikusan azonosítják azokat a vevői számlákat, amelyekhez e-mailben kell emlékeztetőt, beszedési tevékenységet (például telefonhívást) vagy fizetési felszólítást küldeni a vevőnek. 

A vállalatok gyakran jelentős időt töltenek az éves egyenlegjelentések, a vevői számlák és a nyitott számlák kutatására, hogy megtudják, hogy mely vevőkkel kell felvenni a kapcsolatot nyitott számlákkal vagy számlával kapcsolatos egyenleggel kapcsolatban. Ez a kutatás időt vesz igénybe a beszedési ügynököktől, hogy kommunikáljanak a vevőkkel, beszedjék a lejárt tartozásokat, vagy megoldják a számlákkal kapcsolatos vitákat. A beszedési folyamatok automatizálásával stratégián alapuló megközelítést állíthat be a beszedési folyamathoz. Ily módon a beszedési tevékenységeket következetesen alkalmazhatja a személyre szabott e-mailes emlékeztetőkkel, illetve a fizetési felszólítások küldésének programozott folyamatával. 

## <a name="collections-process-setup"></a>Beszedési folyamat beállítása
A **Beszedési folyamat beállítása** lap (**Követelések és beszedések > Beállítás > Beszedési folyamat beállítása**) segítségével létrehozható egy automatizált beszedési folyamat, amely a tevékenységeket, e-mailek küldését, valamint a vevői fizetési felszólítások létrehozását és feladását végzi. A folyamat lépései a kezdő vagy legrégebbi nyitott számlán alapulnak. Minden lépés ezt a számlát használja annak meghatározására, hogy milyen kommunikációt vagy tevékenységet kell végezni egy adott vevővel.  

A beszedési csoportok általában korai értesítést küldenek minden egyes függőben lévő számláról, így a vevő értesítést kap, amikor a számla esedékessé válik. Az **Előzetes fizetési felszólítás** lehetőséggel be lehet állítani, hogy minden folyamathierarchiában egy lépés legyen érvényes minden számlára, amikor a számla időzítése eléri az adott lépést.

### <a name="process-hierarchy"></a>Folyamathierarchia
A vevőgyűjtőket csak egy munkafolyamat-hierarchiához lehet hozzárendelni. Ennek a lépésnek a hierarchiaszintje határozza meg, hogy melyik folyamat fog elsőbbséget élvezni, ha a vevő egynél több olyan gyűjtőben szerepel, amelyhez van hozzárendelve munkafolyamat-hierarchia. A gyűjtő azonosítója határozza meg, hogy a folyamathoz melyik vevők lesznek hozzárendelve. Minden beállított hierarchia csak egy folyamatautomatizáláshoz rendelhető.

A csendes napok segítségével biztosítható, hogy a vevővel ne legyen túl gyakran felvéve a kapcsolat az automatizált eljárással. Ha például a csendes napok kettő értékre vannak állítva, akkor az automatizált folyamat veszi fel a kapcsolatot a vevővel legalább két napig, még sem, ha az eredeti vezető számlát teljes egészében kiegyenlítették. 

Ha ki szeretne zárni vevőket a folyamatautomatizálásból, ha a vevő korosítási egyenlege vagy a számla összege kisebb, mint egy definiált érték, válassza a **Vevő korosítási egyenlege kisebb, mint** vagy a **Számla összege kisebb, mint** lehetőséget a **Kihagyás a folyamatból** mezőben, és adja meg az összeget.

Jelölje be az **Előrejelzés használata** lehetőséget a beszedési tevékenységeknek a vevői fizetési előrejelzések használatával való létrehozásához. A létrehozott tevékenységek a **Fizetési előrejelzések** tevékenységsablonját fogják használni a **Kinnlévőségek paraméterei** oldal **Beszedési folyamat automatizálása** lapján. 

### <a name="process-details"></a>Folyamat részletei
Ha új folyamatadatokat szeretne hozzáadni a hierarchiához, kattintson az **Új** gombra. A **Leírás** a hierarchiában szereplő lépés céljának vagy nevének a meghatározására szolgál. Válassz a **Művelettípus** lehetőséget annak meghatározásához hogy a lépés egy tevékenységet hozzon létre, e-mailt küldjön vagy fizetési felszólítást hozzon létre. 

- Az **Üzleti dokumentum** a művelettípus létrehozásához használt sablont határozza meg. Ez a dokumentum lehet egy tevékenységsablon, egy e-mail-sablon vagy egy vevői fizetési felszólítás. A beszedési folyamat automatizálása csak vevőnként hoz létre fizetési leveleket, függetlenül attól, hogy hogyan vannak beállítva az egyéb beszedési paraméterek.
- A **MIkor** megadja azt a folyamatlépést, amely a nyitó (legrégebbi) számla esedékesség dátuma előtt vagy után történik, és a rendszer a **Napok a számla esedékességi dátumához képest** oszlopban látható számmal együtt használja. 
- Jelölje be az **Előzetes felszólítás** lehetőséget, ha a folyamathierarchia egy lépésében minden számlához létre kell hoznia egy műveletet. Az Előzetes felszólítás műveletek általában korai értesítést küldenek minden egyes függőben lévő számláról, így a vevő értesítést kap, amikor a számla esedékessé válik. Az előzetes felszólítást hierarchiánként csak egy tevékenységhez lehet megjelölni. Amikor kiválaszt egy e-mail műveleti típust, a címzett határozza meg, hogy a vevő, értékesítési csoport vagy a beszedési ügynök kapcsolattartója számára lesz-e e-mail küldve. 
- Az **Üzleti célú kapcsolattartó** határozza meg, hogy a vevő fiókjából melyik kapcsolattartó fogja kapni a kommunikációt.

### <a name="business-document-details"></a>Üzleti dokumentum részletei
Az üzleti dokumentum részletei a folyamat részleteinél kiválasztott művelettípus alapján változik. Ha a művelettípus egy tevékenység, akkor a program a műveletsablon adatait jeleníti meg. Ezek a részletek a műveletsablon nevét, a létrehozandó tevékenység típusát, a tevékenység célját, a tevékenység befejezéséhez ütemezett napok számát, valamint a tevékenység részleteit tartalmazzák. Ez a tevékenység ezt követően a vezető számlára hivatkozik, amely megadja a tevékenység teljesítéséhez szükséges művelet címzettjét.

Ha a művelettípus egy e-mailt a folyamat részletes adataiban, akkor ez a szakasz két gyorslapot fog tartalmazni. Az első a sablon azonosítójának, az e-mail leírásának, az alapértelmezett nyelvnek, az automatikusan elküldött e-mailekhez rendelt felhasználóneveknek, valamint a társított feladók e-mail címének a meghatározására szolgál. A második lehetővé teszi az e-mailek szövegtörzsének létrehozását, miután a **Nyelvi** és a **Tárgy** mezők értékeit a **Szerkesztés** gombra kattintva menti. Ekkor megnyílik egy ablak, amely lehetővé teszi a HTML-tartalom feltöltését. 

> [!Note]
> Az Outlook programban menteni lehet egy e-mail üzenetet, amely HTML formátumban tartalmazza a kommunikáció törzsszövegét. Ezután feltöltheti az üzenet tartalmát, hogy implementálja a sablont. <br> <br> Ha a fizetési felszólítás típusú művelet van kiválasztva, akkor a beállítási oldal nem tartalmaz üzleti dokumentum részletei szakaszt.

A **Beszedési folyamatok előzményei** gombra kattintva megtekintheti a kiválasztott folyamathierarchia legutóbbi előzményeit. 

A beszedési folyamathoz hozzárendelt vevők megtekintéséhez kattintson a **Beszedési folyamat hozzárendelése** műveletre. A **Vevői hozzárendelés előnézete** funkcióval megtekintheti az adott vevőhöz rendelt hierarchiát. A **Folyamat-hozzárendelés előnézete** futtatása a hierarchiához hozzárendelt vevők előnézetének megtekintésére használható. Egy folyamathoz kézzel hozzárendelt vevők megtekintése, illetve a folyamathoz hozzárendelendő vevők kiválasztásához kattintson a **Manuális hozzárendelés** lehetőségre.

Kattintson a **Folyamatszimuláció** lehetőségre azon műveletek előnézetéhez, amelyek akkor jönnek létre, ha a kiválasztott folyamatautomatizálás fut. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
