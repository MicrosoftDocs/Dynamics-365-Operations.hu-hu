---
title: Beágyazott képek és alakzatok az ER-rel generált dokumentumokban
description: Ez a cikk bemutatja, hogy hogyan használható az Elektronikus jelentéskészítő eszköz beágyazott képekkel és alakokkal kapcsolatos üzleti dokumentumok generálása.
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.custom: 27621
ms.assetid: ''
ms.search.form: EROperationDesigner, ERParameters
ms.openlocfilehash: 0bb652f245db93424aeadcaadf2ad393945e616b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280988"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Beágyazott képek és alakzatok az ER-rel generált dokumentumokban

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítő (ER) eszköz segítségével lehet olyan jelentéseket tervezni, amelyek futtatásával elő lehet állítni a szükséges elektronikus dokumentumokat. A jelentések elrendezésének megadásához Microsoft Excel- vagy Microsoft Word-dokumentumokat használhat. Az ER-művelettervező segítségével az Excel- vagy Word-dokumentumot sablonként csatolhatja a jelentéshez. A csatolt sablonban a névvel ellátott elemek az ER-jelentés formátumelemeihez vannak társítva. A jelentés formátumelemei adatforrásokhoz vannak kötve. Ezek az elemek határozzák meg, hogy milyen adatok kerüljenek bele futásidőben a létrejövő dokumentumokba.

Ez az új funkció meghaladja a meglévő, a dokumentumok Microsoft Office-formátumban való létrehozásával kapcsolatos ER-képességeket. További információért játssza le az alábbi feladat-útmutatókat. Ezek a feladat-útmutatók a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamatában találhatóak.

- ER – Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése
- ER A Microsoft WORD-formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése

## <a name="embed-an-image-in-an-excel-document"></a>Kép beágyazása egy Excel-dokumentumba

### <a name="embed-an-image-in-an-excel-worksheet"></a>Kép beágyazása egy Excel-munkalapra

Először adja hozzá a kép helyőrzőjét az Excel-dokumentumhoz. Nyisson meg egy Excel-munkafüzetet, és adjon hozzá egy képet helyőrzőként a később hozzáadni kívánt képhez. Ezután az ER eszköz segítségével adjon meg egy olyan új ER-formátumkonfigurációt, amely tartalmazza a tervezés alatt álló jelentést. Csatolja az Excel-munkafüzetet sablonként a jelentés formátumához, majd importálja a munkafüzet tartalmát az ER-formátumba. A formátumdefiníció automatikusan létrejön. A hozzáadott képhelyőrző **CELLA** elemként fog szerepelni az ER-formátumdefinícióban.

> [!NOTE]
> Importálás helyett kézzel is megadhatja a formátumdefiníciót. A módosítások mentésekor a rendszer ellenőrzi a formátumot.

Ezután kösse az ER-formátum **CELLA** elemét a formátum adatforrásából származó azon mezőhoz, amely futásidőben bináris formátumban szolgáltatja a kép adatait. Ha ER-adatmodellt használ a formátum adatforrásként, a mező adattípusa kötelezően [Tároló](er-formula-supported-data-types-composite.md#container). Jelenleg egy [Tároló](er-formula-supported-data-types-composite.md#container) adattípusú ER-adatmodellmezőt több olyan adatforráshoz is lehet kötni, amelyek bináris formátumú képeket adnak vissza. Az adattáblák mezőit és az adattábla rekordjához csatolt fájlokat a Dokumentumkezelési keretrendszer használatával lehet elérni.

> [!IMPORTANT]
> - Ha az Excel-sablon segítségével létrehozott dokumentumban szeretné kitölteni a kép helyőrzőjét, az ER-formátumnak tartalmaznia kell azt a **CELLA** elemet, amely az Excel-sablon elnevezett képelemére hivatkozik. Ellenkező esetben nem jelenik meg képhelyőrző a jelentés kimenetében. Ha a **CELLA** elem kötése futásidőben nem ad vissza adatokat, akkor a létrehozott dokumentum a sablonból származó képhelyőrzőt fogja tartalmazni. Ha el szeretne rejteni egy képet az előállított dokumentumban, definiáljon egy **CELLA** elemet, és adja meg, hogy az **Engedélyezés** kifejezés értéke **HAMIS** legyen.
> - Az Excel-sablonban minden elemhez használjon egyedi nevet. Ilyen elemek a képek és a cellák. Ha egy elemnév ismétlődik, a létrehozott jelentés tartalma zavaros és kétértelmű lesz.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Képek beágyazása egy Excel-munkalap fejlécébe és láblécébe

Használja az Excel-munkafüzet dokumentumát sablonként a jelentés elrendezésének megadásához. A munkafüzet több munkalapot tartalmazhat, amelyek mindegyikét úgy lehet megtervezni, hogy fejléce és lábléce is legyen. Az Excel legfeljebb három képet támogat minden munkalap fejlécében és láblécében. A képek balra, jobbra vagy középre igazíthatók.

A Finance 10.0.21-es kiadásában kezelheti az Excel-sablonnal rendelkező ER-megoldás által generált fejléc- és láblécképeket.

Ha azt szeretné, hogy a generált dokumentum fejlécében vagy láblécében egy alapértelmezett kép jelenjen meg, hozzáadhat egy képet az ER-sablon munkalapjának fejlécéhez vagy láblécéhez. A kép ER-formátumban való eléréséhez a formátum [Fejléc](er-fillable-excel.md#header-component) vagy [Lábléc](er-fillable-excel.md#footer-component) összetevője alatt fel kell vennie a **Kép** összetevőt. Állítsa be a **Kép** összetevő igazítását szükség szerint. 

A **Kép** összetevő használatával is elhelyezhet képet a létrehozott dokumentum fejlécében vagy láblécében futásidőben – még akkor is, ha a sablon nem tartalmaz alapértelmezett képet. A létrehozott dokumentum fejlécében vagy láblécében elhelyezendő médiatartalom új képként vagy az alapértelmezett kép helyettesítőjeként való megadásához a **Kép** összetevőt egy bináris formátumú képet képviselő, [Tároló](er-formula-supported-data-types-composite.md#container) típusú adatforráshoz kell kötnie.

Minden **Fejléc** vagy **Lábléc** összetevő egyetlen **Kép** összetevőt tartalmazhat minden egyes támogatott igazításhoz: **Balra**, **Középre** és **Jobbra**.

A **Kép** összetevő **Magasság méretezése** tulajdonságának segítségével a konfigurált kötést használva szabályozhatja a képek méretét:

- Válassza az **Eredeti** lehetőséget, ha meg szeretné tartani a kép kiindulási méretét.
- Válassza a **Relatív** lehetőséget, ha a kép magasságát a képet tartalmazó fejléc vagy lábléc magasságával arányosan szeretné átméretni.

    - Ebben az esetben a kép magasságát a szülő fejléc vagy lábléc százalékában kell meghatározni.
    - Ha a méretezés értéke meghaladja a 100 százalékot, akkor a kép átfedésben lehet a kapcsolódó munkalap adatterületével.
    - Ha a méretezés alkalmazásakor módosul a kép magassága, akkor a szélessége is módosul, hogy megmaradjon a kép eredeti oldalaránya.

- Válassza az **Abszolút** lehetőséget, ha a képet a tervezéskor (képpontban) megadott magassági és szélességi értékek szerint szeretné átméretezni.

    - Ha a megadott magasság meghaladja a szülőfejléc vagy -lábléc magasságát, a kép átfedésben lehet a kapcsolódó munkalap adatterületével.

A **Kép** összetevő **Engedélyezve** tulajdonságával szabályozható a létrehozott dokumentumba ezzel az összetevővel beillesztett kép láthatósága.

> [!NOTE]
> Az ER-formátumtervezővel kell hozzáadnia egy **Kép** összetevőt a szerkeszthető ER-formátumhoz. Nem adhatja hozzá az összetevőt, ha az [Üzleti dokumentumok kezelése](er-business-document-management.md) munkaterület használatával szerkeszti az üzleti dokumentumok sablonját.

Ha többet szeretne tudni erről a funkcióról, kövesse az [ER-formátum megtervezése az oldalfejlécben vagy láblécben beágyazott képeket tartalmazó Excel-formátumú jelentés létrehozásához](er-embed-images-header-footer-excel-reports.md) című cikk lépéseit.

## <a name="embed-a-shape-in-an-excel-document"></a>Alakzat beágyazása egy Excel-dokumentumba

Először adja hozzá az alakzat helyőrzőjét az Excel-dokumentumhoz. Nyisson meg egy Excel-munkafüzetet, és válassza az **Alakzat**, a **Szövegdoboz** vagy a **WordArt** lehetőséget az alakzat helyőrzőjeként. Ezután az ER eszköz segítségével adjon meg egy olyan új ER-formátumkonfigurációt, amely tartalmazza a tervezés alatt álló jelentést. Csatolja az Excel-munkafüzetet sablonként a jelentés formátumához, majd importálja a munkafüzet tartalmát az ER-formátumba. A formátumdefiníció automatikusan létrejön. Az alakzat hozzáadott helyőrzője olyan **CELLA** elemként fog bekerülni az ER-formátumdefinícióba, amely a névvel ellátott Excel-alakzatelemre hivatkozik.

> [!NOTE]
> Importálás helyett kézzel is megadhatja a formátumdefiníciót. A módosítások mentésekor a rendszer ellenőrzi a formátumot.

Ezután kösse az ER-formátum **CELLA** elemét a formátum adatforrásából származó azon mezőhoz, amely futásidőben szolgáltatja az adatokat. Ezek az adatok szöveges karakterlánccá konvertálhatók. Amikor az ER-formátum **CELLA** eleme az Excel-sablonban található olyan alakzatelemre hivatkozik, amely támogatja a szöveget, akkor a kötésen keresztül futásidőben megadott szöveg egy alakzatban fog megjelenni a létrehozott dokumentumban.

> [!IMPORTANT]
> - Ha az új dokumentum létrehozásához az alakzat helyőrzőjét tartalmazó Excel-sablont szeretné használni, az ER-formátumnak tartalmaznia kell egy olyan **CELLA** elemet, amely az Excel-alakzatelemre hivatkozik. Ellenkező esetben nem jelenik meg alakzathelyőrző a jelentés kimenetében. Ha a névvel ellátott Excel-alakzatelemre hivatkozó **CELLA** elem kötése futásidőben nem ad vissza adatokat, akkor a létrehozott dokumentum az Excel-sablonban található alakzathelyőrző szövegét jeleníti meg. Ha el szeretne rejteni egy alakzatot az előállított dokumentumban, definiáljon egy, a névvel ellátott Excel-alakzatelemre hivatkozó **CELLA** elemet, és adja meg, hogy az **Engedélyezés** kifejezés értéke **HAMIS** legyen.
> - Az Excel-sablonban minden elemhez használjon egyedi nevet. Ilyen elemek az alakzatok és a cellák. Ha egy elemnév ismétlődik, a létrehozott jelentés tartalma zavaros és kétértelmű lesz.

## <a name="embed-an-image-in-a-word-document"></a>Kép beágyazása egy Word-dokumentumba
> [!IMPORTANT]
> Az Excel-sablont használó ER-formátum újra felhasználható beágyazott képeket tartalmazó dokumentumok létrehozásához. Az ER-formátumban győződjön meg róla, hogy olyan név van megadva a **CELLA** elemhez, amely egy elnevezett képelemre hivatkozik az Excel programban, és amely olyan adatforráshoz van kötve, amely futásidőben visszaad egy képet.

Először be kell állítania a Word-dokumentum elrendezését. A **Képtartalom** vezérlő használatával hozzon létre helyőrzőt a beágyazott képhez. A vezérlő eléréséhez először láthatóvá kell tenni a **Fejlesztő** lapot a Word menüszalagján.

Ezután törölje az Excel-sablont az ER-formátumból, és csatolja a Word-sablondokumentumot. Frissítse a sablonra mutató hivatkozást, és mentse a módosításokat. A jelenlegi ER-formátum szerkezetét a Word-sablonba menti a rendszer új egyéni, **Jelentés** nevű XML-részként.

Ezután mentse a helyi számítógépre a jelenlegi ER-formátum Word-sablonját. Nyissa meg a sablont, majd nyissa meg az **XML-leképezés** panelt. Keresse meg a **Jelentés** nevű egyéni XML-részt, majd mutasson azon ER-jelentés **CELLA** elemére, amely egy bináris formátumú képet eredményül adó adatforráshoz van kötve. Képezze le ennek az XML-résznek az elemét a kijelölt **Képtartalom** vezérlőre, és mentse a módosításokat.

[![képek beágyazása.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Végül törölje a Word-sablont az ER-formátumból, és csatolja a hozzárendelt egyéni XML-részeket tartalmazó Word-dokumentumot. Frissítse a formátumhivatkozást a sablonra, és mentse az ezen az ER-formátumon végzett módosításokat.

## <a name="more-information"></a>További információ
A funkció részleteinek megismerése érdekében játssza le az **ER – Jelentések létrehozása Microsoft Office-formátumokban** csoport feladat-útmutatóit. Ezek a feladat-útmutatók bemutatják, hogyan lehet beágyazni a vállalati embléma és egy jogosult személy aláírásának a képeit az ER eszközzel Excel- és Word-dokumentumként létrehozott fizetési csekkekre.

Az alábbi táblázat tartalmazza azokat a fájlokat, amelyekre az **ER – Jelentések létrehozása Microsoft Office-formátumokban** feladat-útmutatók elvégzéséhez szükség van. Töltse le és mentse a fájlt a helyi számítógépére.

| Leírás                                          | Fájlnév                   |
|------------------------------------------------------|-----------------------------|
| ER-adatmodell konfigurációja                          | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER-formátum konfigurációja                              | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Vállalati embléma képe                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Aláírás képe                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Alternatív aláírási kép                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Microsoft Word sablon a kifizetési csekkek nyomtatásához  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Microsoft Excel sablon a kifizetési csekkek nyomtatásához | [Cheque template.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

Az alábbi ábra egy Excel-sablonból létrehozott kifizetési csekk tesztnyomatára mutat példát.

[![Fizetési csekk tesztnyomata.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
