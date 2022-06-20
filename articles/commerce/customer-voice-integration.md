---
title: A Customer Voice integrálása e-kereskedelmi webhelyek oldalaira
description: Ez a témakör azt mutatja be, hogyan lehet integrálni a Microsoftot Dynamics 365 Customer Voice az Dynamics 365 Commerce e-commerce webhelyoldalakba.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850330"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>A Customer Voice integrálása e-kereskedelmi webhelyek oldalaira

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet integrálni a Microsoftot Dynamics 365 Customer Voice az Dynamics 365 Commerce e-commerce webhelyoldalakba.

Az e-commerce [webhelybe integrálhatja a Vevői7](https://dynamics.microsoft.com/customer-voice/overview/) webhelyet, hogy összegyűjtse, elemezze és nyomon kövesse a valós idejű vevői visszajelzéseket. Az integráció első lépésekhez létre kell hoznia egy számlát, és ki kell választania egy Vevői projektsablont az összegyűjteni kívánt visszajelzés típusára.

## <a name="integrate-the-customer-voice-service"></a>Az Ügyfélszolgálat integrálása szolgáltatás

Vevői Számla létrehozásához menjen [a Vevő És vevőhöz](https://dynamics.microsoft.com/customer-voice/overview/), és kövesse a rá vonatkozó utasításokat.

Miután létrehozott egy Vevői Számla számlát, és bejelentkezik, a következő lépés az, hogy kiválaszt egy projektsablont a begyűjteni kívánt visszajelzéstípushoz.

A vevő Projekt projektsablonjának kiválasztásához kövesse ezeket a lépéseket.

1. Ugrás a Vevő [Projekt projektsablon-oldalára](https://customervoice.microsoft.com/Pages/ProjectPage.aspx)
1. Válassza az Első **lépések lehetőséget**.
1. Válassza ki az összegyűjteni kívánt visszajelzéstípus projektsablonját, **majd válassza a Tovább gombra**.
1. A Küldés **lap** Beágyazási formátum **kiválasztása** csoportjában válasszon ki egy beágyazási formátumot. A **Beágyazott kód** mező mutatja a Commerce webhelyszerkesztőben beágyazható kódot.

Az ebben a példában lévő példák az Időszakos vevői **felmérés** projektsablonját **és a Gomb beágyazási formátumot** használják.

A következő **példa bemutatja** az Időszakos vevői felmérés projektsablonjának lapját, **ahol** be van jelölve a Gomb beágyazási formátumának lehetősége, és a beállítás beágyazási kódja megjelenik a Beágyazott kód mezőben **.** Három különálló műveletre van szükség a megadott kódnak a webhelyoldalakba történő beágyazása érdekében, az alábbi szakaszokban leírtak szerint.

![Vevői időszakos vevői felmérés lap a Gomb beállítással.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>A külső parancsfájl URL-címének beágyazása

Minden olyan webhelyoldalon, amelyekben vevői Felmérésnek kell lennie, be kell ágyazni a Vevő Által megadott külső parancsfájl URL-címét a beágyazási kódba. A parancsfájlt úgy lehet több webhelyoldalba beágyazni, ha a külső parancsfájl URL-címét tartalmazó részletet hoz létre a webhelyszerkesztőben, és a darabot hozzáadja a megfelelő lapsablonhoz. A frissített sablon közzététele után a beágyazott külső parancsfájlkód hasonlít az érintett webhelyoldalakon a következő példához.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

A darabkával kapcsolatos tudnivalókat lásd [: Munka darabkával.](work-with-fragments.md)

> [!NOTE]
> Az URL-címet csak a részlethez kell hozzáadni. A külső parancsfájlmodul hozzáadja a másik parancsfájlkódot.

Ha a külső parancsfájl URL-címét egy részletbe szeretne beágyazni, kövesse ezeket a lépéseket.

1. A webhelyszerkesztőben hozzon létre egy részletet, amely a külső parancsfájlmodulon [alapul](script-module.md).
1. Az új részletben válassza ki az Alapértelmezett **külső parancsfájl-rést**.
1. Írja be **a** **külső parancsfájlok alapértelmezett tulajdonságait tartalmazó ablaktábla Parancsfájl** forrása mezőjébe a külső parancsfájl URL-címét, amint azt az alábbi példa mutatja.

    ![Külső parancsfájl URL-címe a Parancsfájl forrása mezőben az új részlethez](media/customer-voice-integration-2.png)

1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget a részlet közzétételéhez.

Az új részlet, amely a beágyazott külső parancsfájlblokkot tartalmazza, készen áll arra, hogy hozzá legyen adva a megfelelő lapsablonhoz.

### <a name="embed-the-external-style-sheet-code"></a>A külső stíluslap kódának beágyazása

Ezután minden olyan webhelyoldalon, amelyekben fel kell használni a Vevő felmérését, be kell ágyazni a Vevő Által megadott külső stíluslapkódot az beágyazási kódba. Az előző szakaszhoz képest a külső stíluslap kódját úgy lehet beágyazni több telephelyes lapokba, hogy létrehoz egy részletet a webhelyszerkesztőben, amely tartalmazza a stíluslap kódját, majd a részletet hozzáadja a megfelelő lapsablonhoz. A beágyazott külső stíluslapkód hasonlít a következő példakódra.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Ha a külső stíluslapkódot egy részletbe szeretne beágyazni, kövesse ezeket a lépéseket.

1. A helyszerkesztőben hozzon létre egy, a [Metatagok modulon alapuló részletet](metatags-module.md).
1. A részletben válassza ki az Alapértelmezett **metatagok beállítási lehetőséget**.
1. Az Alapértelmezett **metatagok** tulajdonságai **ablak Metacímkék** mezőjébe írja be a stíluslap kódját, amint azt az alábbi példa mutatja.

    ![Külső stíluslap kódja az új részlet Metacímkéi mezőjében.](media/customer-voice-integration-3.png)

1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget a részlet közzétételéhez.

Az új részlet, amely a beágyazott külső stíluslapkódot tartalmazza, készen áll arra, hogy hozzá legyen adva a megfelelő lapsablonhoz.

### <a name="embed-the-inline-script-code"></a>A inline parancsfájlkód beágyazása 

Ezután minden olyan webhelyoldalon, amelyekben fel kell függesnie a Vevői felmérésnek, be kell ágyazni azt a inline script-kódot, amit a Vevő Adott az beágyazási kódba. Ahogy az előző szakaszokban is, a legjobb mód arra, hogy több telephelyes lapokba beágyazza a inline parancsfájlkódot, az az, ha létrehoz egy kódot a helyszerkesztőben, amely tartalmazza a inline parancsfájl kódját, majd a részletet hozzáadja a megfelelő lapsablonhoz.

A következő példa a inline parancsfájlkódra, **a SURVEY\_ KEY** helyőrző. A SURVEY KEY **értékének\_** meg kell egyeznie a Vevő által az beágyazási kódban megadott tényleges felmérési kulccsal. Az utolsó sor úgy hívja meg a kódot, hogy egy másodperc után megjelenítsen egy felmérésgombot, hogy a parancsprogramnak elég ideje legyen a betöltésre. A kiválasztott felméréstől függően előfordulhat, hogy más metaadatokat is hozzá kell adni vagy frissítenie kell, például a vállalat nevét.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Ha a inline parancsfájl kódját egy részletbe szeretne beágyazni, kövesse ezeket a lépéseket.

1. A helyszerkesztőben hozzon létre egy részletet, amely [a Inline parancsfájlmodulon alapul](script-module.md).
1. A részletben válassza ki az alapértelmezett **inline parancsfájl-rést**.
1. Az Alapértelmezett inline **parancsfájl** **tulajdonságai ablaktábla Inline parancsfájl** mezőjébe írja be aline parancsfájl kódját, amint azt az alábbi példa mutatja.

    ![Az új részlet inline parancsfájlkódja a Inline parancsfájl mezőjében.](media/customer-voice-integration-4.png)

1. Válassza a **Mentés** parancsot, majd válassza a **Szerkesztés befejezése** elemet.
1. Válassza a **Közzététel** lehetőséget a részlet közzétételéhez.

Az új részlet, amely a beágyazott inline parancsfájlkódot tartalmazza, készen áll arra, hogy hozzá legyen adva a megfelelő oldalsablonhoz.

## <a name="add-fragments-to-a-template"></a>Részlet hozzáadása sablonhoz

Amikor befejezte a Beágyazott vevőkódot tartalmazó részletek létrehozását, azokat hozzá kell adni a használni kívánt webhelyoldalakhoz társított lapsablonhoz. A következő példa azt mutatja be, hogy a három példarészlet egy PDP-sablonhoz lett hozzáadva.

![Például a PDP-sablonhoz adott részlet.](media/customer-voice-integration-5.png)

A frissített sablon közzététele után a Vevői felmérés minden olyan oldalon megjelenik, amelyet a sablon szabályoz.

A sablonokkal kapcsolatos tudnivalókat lásd a [Sablonokkal kapcsolatos tudnivalókat](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Tartalom-biztonsági házirend konfigurálása

Alapértelmezés szerint a tartalom-biztonsági házirend (CSP) csak akkor engedélyezi a más szolgáltatásokhoz való hívásokat, ha nincs további konfiguráció. Ezért a frissített sablonok közzététele után valószínűleg nem sikerül betöltenie a felmérést a megfelelő webhelyoldalakra. A CSP-hez kapcsolódó hibák megtekintéséhez nyissa meg a webböngésző fejlesztői eszközeit (F12), majd egy olyan oldalra, amely a felmérést használja. A konzol kimenetében a CSP-hez kapcsolódó hibák jelennek meg.

A CSP-nek a webhelyszerkesztőben a hibák kijavítása érdekében való konfigurálásával hajtsa végre a következő lépéseket.

1. Ugrás a **Webhelybeállítások \> Bővítmények** pontra.
1. A Tartalom biztonsági házirend lapján **adja hozzá**`https://customervoice.microsoft.com/` a gyermekrc-irányelvet **.**
1. Hozzáadás `https://customervoice.microsoft.com/` a keretváról **szóló irányelvhez**
1. Hozzáadás `https://mfpembedcdnmsit.azureedge.net` és **.azureedge.net** hozzáadása az **img-src-irányelvhez**.

További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP)](manage-csp.md).

## <a name="additional-resources"></a>További erőforrások

[Külső parancsfájlmodul](script-module.md)

[Metacímkék modulja](metatags-module.md)

[Inline parancsfájlmodul](script-module.md)

[Tartalom-biztonsági házirend](manage-csp.md)

[Töredékek használata](work-with-fragments.md)

[Sablonok használata](work-with-templates.md)
