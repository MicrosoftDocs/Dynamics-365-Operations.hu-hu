---
title: E-mail ER céltípusa
description: Ez a témakör bemutatja, hogyan kell konfigurálni egy e-mail-célt az Elektronikus jelentéskészítési (ER) formátumok egyes MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0a8ee5c16e2292481e24ada4853eed9a6824ef2d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562022"
---
# <a name="email-er-destination-type"></a>E-mail ER céltípusa

[!include [banner](../includes/banner.md)]

Egy Elektronikus jelentéskészítési (ER) formátum futtatásakor egy vagy több kimenő dokumentumot lehet létrehozni. A **Mappa** vagy **Fájl** formátumösszetevők a kimenő dokumentumok szerkezetének meghatározásához használatosak. Az ilyen típusú összetevők esetében beállíthatja, hogy a kimenő dokumentumok egy e-mail csatolmányként legyenek-e elküldve.

Az ER-formátum minden egyes **Mappa** vagy **Fájl** összetevője számára beállíthat egy e-mail célhelyet . Ebben az esetben az **egyes kimenő dokumentumok küldése egyenként történik**. A célhely ezen beállítása alapján a létrejövő dokumentumot a rendszer egy e-mail csatolmányaként küldi el. 

> [!NOTE]
> Ha nincs dokumentum létrehozva, mert a kapcsolódó **Fájl** **Engedélyezett** kifejezése úgy van beállítva, hogy **Hamis** logikai értéket adjon vissza, a program nem küld e-mailt, még akkor sem, ha egy e-mail célhely be van állítva, és engedélyezve van az összetevőhöz.

Több **Mappa** vagy **Fájl** is [csoportosítható](#grouping) együtt, majd a csoport minden összetevőjéhez beállíthat egy e-mail célhelyet. Ebben az esetben a csoporthoz tartozó összetevők által előállított kimenő dokumentumok **egyetlen e-mailben több mellékletként** lesznek elküldve. A célhely ezen beállítása alapján az egyes létrejövő dokumentumokat a rendszer egyetlen e-mail csatolmányaként küldi el.

> [!NOTE]
> Ha legalább egy dokumentumot egy összetevőcsoport **Fájl** összetevője hoz létre, akkor egy e-mail lesz küldve. Ha nincs dokumentum létrehozva a csoportosított összetevők által, mert az egyes **Fájl** összetevők **Engedélyezett** kifejezése úgy van beállítva, hogy **Hamis** logikai értéket adjon vissza, a program nem küld e-mailt, még akkor sem, ha egy e-mail célhely be van állítva, és engedélyezve van az összetevőcsoporthoz.
>
> Az **E-mail** az egyetlen olyan célhely, amely az összetevők egy csoportjához konfigurálható. Ha olyan dokumentumot szeretne kézbesíteni, amely egy csoport e-mail célhelye alapján e-mailben van elküldve, vegyen fel egy több célrekordot, válassza ki a kívánt összetevőt, majd konfiguráljon a rekordhoz egy másik célt.

Az összetevők több csoportja konfigurálható egyetlen ER formátumkonfigurációhoz. Ily módon egy e-mail célhelyet állíthat be az összetevők minden csoportjához és minden összetevőhöz egy e-mail célhelyet.

## <a name="configure-an-email-destination"></a>Egy e-mail-célhely konfigurálása

Kimeneti fájl vagy több kimeneti fájl e-mailben történő küldéséhez az **Elektronikus jelentéskészítés célja** lap **Fájl célhelye** gyorslapján a rácsban válassza ki az összetevőt vagy az összetevők csoportját, majd válassza ki a **Beállításokat**. A megjelenő **Célhely beállításai** párbeszédpanel **E-mail** lapján az **Engedélyezve** beállítást állítsa **Igen** értékre. Ezután megadhatja e-mail címzettjeit, és szerkesztheti a tárgyát és szövegét. Beállíthat állandó szöveget az e-mail tárgyaként és szövegeként, illetve használhat ER-[képleteket](er-formula-language.md) az e-mail szövegének dinamikus létrehozására.

Elektronikus jelentéstételhez e-mail-címeket két módon konfigurálhat. A konfiguráció ugyanúgy fejezhető be, mint a Nyomtatás kezelése funkció. Ezenfelül e-mail-címet megoldhat úgy is, hogy képlettel közvetlenül hivatkozik az ER-konfigurációra.

[![Az Engedélyezve beállítás Igen értékre állítása egy e-mail célhelyhez](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>E-mail-címek típusai

Ha a **Cél beállításai** párbeszédpanel **Címzett** vagy **Másolatot kap** mezője mellett a **Szerkesztés** lehetőséget választja , megjelenik az **E-mail címzettje** párbeszédpanel. Válassza a **Hozzáadás** lehetőséget, majd válassza ki a használandó e-mail-cím típusát. A jelenleg támogatott e-mail-típusok a **Konfigurációs e-mail** és a **Nyomtatás kezelése e-mail**.

[![Az e-mail cím típusának kiválasztása](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>Kezelési e-mail nyomtatása

Ha e-mail cím típusaként a **Nyomtatás kezelése e-mail** lehetőséget választja , a következő mezők beállításával megadhatja a rögzített E-mail címeket az **E-mail címzettje** párbeszédpanelen:

- Az **E-mail forrása** mezőben válassza a **Nincs** lehetőséget.
- A **További e-mail-címek „;”-el elválasztva** mezőben adja meg a rögzített e-mail-címeket.

Azt is megteheti, hogy az e-mail címeket annak a félnek a kapcsolattartási adataiból szerzik be, akinek kimenő dokumentumot hoz létre. Nem rögzített email-cím használatához az **E-mail forrása** mezőben válassza ki a fájl címzettjének [szerepkörét](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles). A következő szerepkörök támogatottak:

- Vevő
- Szállító
- Potenciális vevő
- Kapcsolat
- Versenytárs
- Dolgozó
- Pályázó
- Potenciális szállító
- Tiltott szállító

Ha például a szállítói kifizetések feldolgozására használt ER formátumhoz szeretne e-mail célt konfigurálni, válassza ki a **Szállító** szerepkört.

Miután kiválasztotta a kívánt szerepkört, válassza a **Kapcsolás** gombot (lánc szimbólum) az **E-mail forrásfiók** mező mellett a [Képlettervező](general-electronic-reporting-formula-designer.md) lap megnyitásához. Ezután ezen a lapon konfigurálhatja azt a képletet, amely visszaküldi a fél számlaszámát, amely hozzá van rendelve a konfigurált szerepkörhöz a feldolgozott dokumentumból az e-mail célhelyére.

> [!NOTE]
> A receptúrák ER-konfigurációspecifikusak.

A **Képlettervező** lap **Képlet** mezőjébe írja be a támogatott szerepkörhöz tartozó dokumentumspecifikus hivatkozást. A hivatkozás beírása helyett az **Adatforrás** ablaktáblában keresse meg és válassza ki azt az adatforrás-csomópontot, amely a konfigurált szerepkör számláját jelöli, majd válassza az **Adatforrás hozzáadása lehetőséget** a képlet frissítéséhez. Ha például a szállítói kifizetések feldolgozására használt **ISO 20022 átutalás** konfigurációhoz az e-mail célhelyet konfigurálja , akkor a szállítói számlát képviselő csomópont a következő: `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![E-mail-forrásfiók konfigurálása](./media/er_destinations-emaildefineaddresssource.gif)

Ha a konfigurált szerepkör számlaszáma egyedi az egész Microsoft Dynamics 365 Finance egész példányra vonatkozóan, akkor a **E-mail címzettje** párbeszédpanel **E-mail forrásának vállalata** mezője nem maradhat üresen.

Olyan helyzet is előfordulhat, amikor a [Globális címjegyzékben](../../fin-ops/organization-administration/overview-global-address-book.md) különböző feleket különböző vállalatokban ([jogi személyek](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) regisztráltak, olyan módon hogy minden felhasználó ugyanazt a számlaszámot használja a konfigurált szerepkör kitöltéséhez. Ebben az esetben a konfigurált szerepkör számlaszáma nem egyedi a teljes Finance példány esetében. Ennélfogva egy fél explicit kiválasztása esetén nem adható meg csak számlaszám. Meg kell adnia azt a vállalatot is, amelynél a fél regisztrálva van a konfigurált szerepkör kitöltéséhez. Válassza a **Kapcsolás** gombot (lánc szimbólum) az **E-mail címzettje** párbeszédpanel **E-mail forrás vállalata** mezőjét a [Képlettervező lap](general-electronic-reporting-formula-designer.md) megnyitásához. Ezután ezen a lapon konfigurálhatja azt a képletet, amely a program futási idején a megfelelő forrást tartalmazó vállalat kódját adja vissza.

> [!TIP]
> Ha vállalatkódot kell használnia egy ER-formátum futtatásához, de az ER-formátum nem szolgáltat olyan adatforrást, amelyből a vállalat kódja beszerezhető, akkor konfigurálja a `GetCurrentCompany()` képletet a beépített [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md) ER-függvény segítségével.

> [!NOTE]
> A receptúrák ER-konfigurációspecifikusak.

Ha meg szeretné adni, hogy milyen típusú e-mail címeket kell használni futásidőben, akkor az **E-mail címzettje** párbeszédpanelen válassza a **Szerkesztés** lehetőséget **Címzett** mező mellett az **E-mail cím hozzárendelése** legördülő párbeszédpanel megnyitásához. Majd, állítsa be a következő mezőket:

- A **Cél** mezőben válassza ki a kívánt célt. A program csak a felfedezett fél kapcsolattartóinak a kiválasztott célokból származó e-mail címeit fogja használni.
- Állítsa az **Elsődleges kapcsolattartó** beállítását **Igen** értékre az elsődleges e-mail címként a felfedezett fél számára konfigurált e-mail cím használatához.

> [!NOTE]
> Ha a **Cél** mezőben a célok vannak kiválasztva és az **Elsődleges kapcsolattartó** beállítás is **Igen** értékre van beállítva, akkor a program minden olyan e-mailt használ futásidőben, amely megfelel legalább egy konfigurált feltételnek.

### <a name="configuration-email"></a>Konfigurációs e-mail

Válassza a **Konfigurációs e-mail** e-mail-cím típust, ha a használt konfigurációnak van egy csomópontja az adatforrásokban, amely egyetlen e-mail címet vagy több, pontosvesszővel (;) elválasztott e-mail címet ad vissza. A képlettervezőben [adatforrások](general-electronic-reporting.md#FormatComponentOutbound) és [függvények](er-formula-language.md#functions) segítségével pontosan formázott e-mail címet vagy pontosvesszővel elválasztott e-mail címeket használhat. Ha például az **ISO 20022 átutalás** konfigurációt használja, akkor az a csomópont, amely a szállító elsődleges e-mail címét jelöli a szállító elérhetőségi adataiból, amelynek a kísérőlevelet el kell küldeni, a `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![E-mail-cím forrásának konfigurálása](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Csoportformátum-összetevők

A csoportformátumösszetevő-összetevők csoportosításához az **Elektronikus jelentés célja** lapon, a **Fájl célja** gyorslapon jelölje ki az összetevőket a rácsban, majd válassza a **Csoportosítás** lehetőséget.

Az **E-mail** az egyetlen korábban konfigurált célhely, amely továbbra is elérhető a kijelölt összetevők számára. Más, korábban konfigurált cél nem érhető el, mert az összetevők egy csoportja számára nem támogatottnak minősülnek. A változásokról szükség szerint értesítést kap.

A korábban hozzáadott rekord a létrehozott csoport fejlécének számít. Ez a fejlécrekord tartalmazza a csoport e-mail célbeállításait. A többi rekord olyan csoporttagokat tartalmaz, akik a csoport fejlécrekordjának e-mail célbeállításait fogják használni.

A formátumösszetevők csoportjának felbontásához a **Fájl célja** gyorslapon jelöljön ki egy, a csoporthoz tartozó rekordot, majd válassza a **Szétválasztás** lehetőséget.

- Ha fejlécrekordot jelöl ki, az egész csoport szét lesz választva.
- Ha tagbejegyzést jelöl ki, és az a csoport utolsó tagbejegyzése, az egész csoport szétválasztásra kerül.
- Ha olyan tagbejegyzést választ ki, amely nem a csoport utolsó tagbejegyzése, akkor a bejegyzés ki lesz zárva az aktuális csoportból.

A következő ábra egy olyan ER-formátum szerkezetét mutatja be, amely úgy lett beállítva, hogy egy fizetési felszólítást és megfelelő vevői számlákat tartalmazó, PDF formátumú tömörített kimenő fájlt készítsen.

[![Kimenő dokumentumokat létrehozó ER-formátum szerkezete](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

A következő ábra az egyes összetevők csoportosításának és az új csoport **E-mail** céljának engedélyezésének folyamatát mutatja be, hogy a rendszer a megfelelő vevői számlákkal együtt fizetési felszólítást küldjön e-mail mellékletként, ahogy az ebben a fejezetben be lett mutatva.

[![Az egyes összetevők csoportosítása és az E-mail cél engedélyezése](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
- [Képletszerkesztő elektronikus jelentésekhez (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]