---
title: Új ER-konfiguráció tervezése Word-formátumú jelentések generálásához
description: Ez a témakör bemutatja, hogyan konfigurálhatnak a felhasználók egy új elektronikus jelentéskészítési (ER) formátumot jelentések létrehozásához Microsoft Word-dokumentumként.
author: NickSelin
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 4885caf017fa0f9d36d293fa32aad53c21d3f162
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753576"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Új ER-konfiguráció tervezése Word-formátumú jelentések generálásához

[!include [banner](../includes/banner.md)]

Ahhoz, hogy Microsoft Word-dokumentumként hozzon létre jelentéseket, meg kell terveznie egy sablont a jelentésekhez, például az asztali Word alkalmazás segítségével. A következő ábra az ellenőrző jelentés mintasablonját mutatja be, amely létrehozható a feldolgozott szállítói kifizetések részleteinek megjelenítéséhez.

![Mintasablon az asztali Word alkalmazásban használható ellenőrző jelentéshez](./media/er-design-configuration-word-image1.png)

Ha Word-dokumentumot kíván használni Word formátumú jelentések sablonjaként, egy új [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) [megoldást](er-quick-start1-new-solution.md) is konfigurálhat. Ennek a megoldásnak egy ER [konfigurációt](general-electronic-reporting.md#Configuration) kell tartalmaznia egy ER [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevővel.

> [!NOTE]
> Amikor új ER-formátumkonfigurációt hoz létre jelentések Word-formátumban való előállításához, vagy a **Word** formátumtípust kell kiválasztania a **Konfiguráció létrehozása** legördülő párbeszédpanelen, vagy üresen kell hagynia a **Formátumtípus** mezőt.

![Az egyéni formátumkonfiguráció létrehozása a Konfigurációk oldalon](./media/er-design-configuration-word-image2.gif)

A megoldás ER-formátum-összetevőjének tartalmaznia kell az **Excel\\Fájl** formátumelemet, és ezt a formátumelemet össze kell kapcsolni a Word dokumentummal, amelyet a futásidőben generált jelentések sablonjaként fog használni. Az ER-formátum összetevő konfigurálásakor meg kell nyitnia a létrehozott ER-konfiguráció [vázlat](general-electronic-reporting.md#component-versioning) verzióját az ER-formátumtervezőben. Ezután adja hozzá az **Excel\\Fájl** elemet, csatolja a Word-sablont a szerkeszthető ER-formátumhoz, és csatolja a sablont a hozzáadott **Excel\\Fájl** elemhez.

> [!NOTE]
> A sablon manuális csatolása esetén olyan [dokumentumtípust](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) kell használnia, amely korábban [konfigurálva](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) lett az ER-paraméterekben az ER-formátumok sablonjainak tárolására.

![Sablon csatolása a Formátumtervező oldalon](./media/er-design-configuration-word-image3.gif)

Az **Excel\\Fájl** elemhez hozzáadhatja az **Excel\\Tartomány** és **Excel\\Cella** beágyazott elemeket, hogy megadja a futásidőben generált jelentésekbe bevitt adatok szerkezetét. Ezután ezeket az elemeket hozzá kell kötnie a szerkeszthető ER-formátum adatforrásaihoz, hogy megadja a tényleges adatokat, amelyek a generált jelentésekbe futásidőben fognak bekerülni.

![Beágyazott elemek hozzáadása a Formátumtervező oldalon](./media/er-design-configuration-word-image4.gif)

Amikor a tervezés során menti az ER-formátum módosításait, a hierarchikus formátumszerkezet a csatolt Word-sablonban egy **Jelentés** nevű [egyéni XML-részként](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) tárolódik. A módosított sablonhoz hozzá kell férnie, le kell töltenie a Finance alkalmazásból, helyben kell tárolnia, majd meg kell nyitnia az asztali Word alkalmazásban. A következő ábra a **Jelentés** egyéni XML-részét tartalmazó ellenőrző jelentés helyileg tárolt mintasablonját mutatja be.

![A jelentéssablon mintájának előnézete az asztali Word alkalmazásban](./media/er-design-configuration-word-image5.gif)

Amikor futásidőben futtatja az **Excel\\Tartomány** és **Excel\\Cella** formátumelemek kötését, az össze kötés által előállított adatok a létrehozott Word-dokumentumba kerülnek, a **Jelentés** egyéni XML-rész egyedi mezőjeként. Ha egy generált dokumentumban meg szeretne adni az egyéni XML-rész mezőiben található értékeket, akkor hozzá kell adnia a megfelelő Word [tartalomvezérlőket](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) a Word-sablonhoz, hogy helyőrzőként szolgáljanak az olyan adatok számára, amelyek futásidőben ki lesznek töltve. A tartalomvezérlők kitöltésének megadásához minden tartalomvezérlőt le kell képezni kell a **Jelentés** egyéni XML-rész megfelelő mezőjére.

![Tartalomvezérlők hozzáadása és leképezése az asztali Word-alkalmazásban](./media/er-design-configuration-word-image6.gif)

Ezt követően le kell cserélnie a szerkeszthető ER-formátum eredeti Word-sablonját arra a módosított sablonra, amely most a **Jelentés** egyéni XML-rész mezőihez hozzárendelt Word-tartalomvezérlőket tartalmazza.

![Sablon cseréje a Formátumtervező oldalon](./media/er-design-configuration-word-image7.gif)

A konfigurált ER-formátum futtatásakor a csatolt Word-sablon használatával új jelentés generálható. A tényleges adatok egy **Jelentés** nevű egyéni XML-részként tárolódnak a Word-jelentésben. A létrehozott jelentés megnyitásakor a Word-tartalomvezérlőket a rendszer kitölti a **Jelentés** egyéni XML-rész adataival.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

**Kérdés:** Az ER-formátumot egy vállalati címet tartalmazó Word-dokumentum nyomtatására konfiguráltam. Az ER-formátum Word-sablonjába beszúrtam egy Rich Text-tartalomkezelőt a vállalati cím bemutásához. A Finance alkalmazásban többsoros szövegként adtam meg a vállalat címét, és az **Enter** gombbal adtam hozzá sortörést az egyes beírt sorokhoz. Ezért arra számítok, hogy a vállalat címe többsoros szövegként fog megjelenni a generált dokumentumokban. A cím azonban egyetlen szövegsorként jelenik meg, amely speciális szimbólumokat tartalmaz a sortörések helyett. Mi a hiba a beállításaimban?

**Válasz:** A Rich Text-tartalomvezérlő használata helyett egyszerű szöveges tartalomvezérlőt kell használnia, és a vezérlő tulajdonságai között ki kell választania a **Sortörés engedélyezése (több bekezdésbe)** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

- [ER-konfigurációk újrafelhasználása Excel-sablonokkal Word-formátumú jelentések generálásához](./tasks/er-design-configuration-word-2016-11.md)
- [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]