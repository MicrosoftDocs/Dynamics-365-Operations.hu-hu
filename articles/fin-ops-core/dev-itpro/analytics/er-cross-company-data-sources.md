---
title: Több vállalatot érintő adatforrások az elektronikus jelentéskészítésben (ER)
description: Ez a témakör bemutatja, hogyan használható a több vállalatot érintő adatforrások elektronikus jelentés (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1a5c05b65c9022220056947471e95b703d923dc5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680830"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Több vállalatot érintő adatforrások az elektronikus jelentéskészítésben (ER)

[!include[banner](../includes/banner.md)]

Elektronikus jelentési (ER) formátumokat tervezhet kimenő dokumentumok többféle formátumú előállításához. A dokumentum létrehozásakor az ER formátum meghívja a megfelelő ER modell hozzárendelésben beállított adatforrásokat. Az alkalmazástáblákhoz való elérés rekordbeolvasáshoz való konfigurálásához a **Táblarekordok** típusú ER adatforrást használhatja. Amikor a hozzáféréstábla egy megosztott tábla (vagyis egy, az adatokat a vállalat azonosítója nélkül mentő tábla) ez az adatforrás visszaadja az összes rekordot. Ha az elérési tábla egy vállalatfüggő tábla (vagyis egy, az adatokat vállalatonként tároló tábla), ez az adatforrás csak az aktuális vállalathoz mentett rekordokat adja vissza (vagyis a vállalati környezet, amely alatt az ER formátum fut).

Minden adatforrás a **Táblarekordok** típusból a modell-hozzárendelésben most már több vállalatot érintő adatforrásként jelölhető meg. Ezért a **Táblarekordok** típusú adatforrásokat használhatja a több vállalatot érintő adatok eléréséhez az alkalmazástáblákban.

Ha bejelöli az adatforrást több vállalatot érintőként, a következő történik:

- Az adatforrás által hivatkozott megosztott táblák esetében, kivéve CompanyInfo, az adatforrás a hivatkozott táblában található összes rekordot adja vissza. 
- Ha egy adatforrás a CompanyInfo táblára hivatkozik, annak ellenére, hogy CompanyInfo adatforrás közös táblában van, az adatforrás eredményül ad rekordokat, amelyek tartalmazzák a definiált körből egy vállalat azonosítóját.
- Minden vállalatfüggő tábla esetében az adatforrás a hivatkozott tábla rekordjait adja vissza, amely tartalmazza a definiált köréből egy vállalat azonosítóját.

A rendszer lekérdezés párbeszédpanelen, ha a **Lekérdezés kérése** beállítás be van jelölve bármely több vállalatot érintőként megjelölt adatforrásra, manuálisan kiválaszthatja a szerepeltetni kívánt egy vagy több vállalatot a **Vállalati tartomány** lapon.

> [!IMPORTANT]
> Ahogy a többi szűrőnél, a vállalat szűrő megmarad a lekérdezésekhez az utoljára használt értékként ER formátum futtatásakor. A szűrő automatikusan nem változik, ha módosítja az adatforrásnál a több vállalatot érintő értéket. Egy másik adatforráshoz egy másik több vállalatot érintő érték használatához törölje a megfelelő felhasználóspecifikus kiválasztást.

Minden adatforrásnál, amely több vállalatot érintőként van megjelölve, jelölje be a használni kívánt rekordokat a **SZŰRŐ** és az **AHOL** funkciókkal az ER kifejezésekben. A **dataAreaID** mező is használható a vállalat azonosítójaként. Jelenleg a **dataAreaID** mező a következő típusú feltételekre korlátozódik, amikor a **SZŰRŐ** művelet van használatban:

- Csak azok a feltételek támogatottak, amelyeknek egyetlen **dataAreaID** mező-összehasonlítása van.
- Csak azok az összehasonlítások megengedettek, amelyeknek a kifejezései nem függenek a rekordlistaelemektől.

Emiatt a következő kifejezés érvényes.

```ER Expression
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

Alapértelmezés szerint a hatókör tartalmazza az aktuális alkalmazás összes vállalatát. Azonban ez korlátozható. Több vállalatot érintő adatelérés hatókörének korlátozásához egy ER formátumra, rendelje hozzá egy adott szervezeti hierarchiát a formátumhoz. Amikor egy hierarchiát ad meg egy ER formátumhoz, csak a hozzárendelt hierarchiában megtalálható jogi személyek rekordjai jelennek meg, annak ellenére, hogy a formátum meghívja a több vállalatot érintő adatforrásokat. Ha egy ER formátumhoz meg van adva egy hivatkozás egy hierarchiára, amely már nem létezik, a rendszer az alapértelmezett hatókört alkalmazza, és a formátum meghívja a több vállalatot érintő adatforrásokat. Ebben az esetben a rendszer minden alkalmazásvállalat rekordjait visszaadja.

Vegye figyelembe, hogy ha a **Vázlat használata** beállítás engedélyezve van az egyetlen ER-formátum szervezeti hierarchián, a jogi személyek a hierarchia piszkozatverzióját használja a program a több vállalatot érintő adatforrások hatókör azonosítására. Ha a vázlat verzió nem létezik, a jogi személyek a szervezeti hierarchia közzétett verzióból lesznek használva.

Vegye figyelembe, hogy ha a **Vázlat használata** beállítás engedélyezve van az egyetlen ER-formátum szervezeti hierarchián, a jogi személyeket a szervezeti hierarchia utolsó kiadott verziójából használja a program a több vállalatot érintő adatforrások hatókör azonosítására. Szervezeti hierarchiák dátum hatékonyságát az ER keretrendszer még nem támogatja.

A hierarchia a formátumhoz egy adott oldalon rendelhető hozzá, amely hozzáférhető az ER munkaterületről vagy a következő menüpont segítségével: **Szervezet felügyelete \> Elektronikus jelentés \> Jogi személy szűrője a formátumokhoz**. A lap eléréséhez a **Formátumok jogi személyi szűrőinek karbantartása** jogosultságot (ERMaintainFormatMappingLegalEntityFilters) meg kell adni a felhasználónak. A hierarchia-alapú jogi személyek hatókör-korlátozást formátumra a rendszer amellett a korlátozás mellett alkalmazza, amelyet a felhasználó manuálisan adhat meg a rendszerlekérdezés párbeszédpanelen. A megszorítások keresztezése lesz használatos a formátum futtatásakor.

Az ezzel a funkcióval kapcsolatos további tudnivalókért játssza le az **ER Vállalatfüggő táblák hozzáférési rekordjai több vállalatos módban** feladatútmutatót, amely része az 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamatnak, és letölthető innen: [Microsoft letöltőközpont](https://go.microsoft.com/fwlink/?linkid=874684). Ez a feladatútmutató végigvezeti egy ER modell leképezés és ER formátum konfigurálásán, a több vállalatot érintő módban alkalmazástáblák eléréséhez.

A feladatútmutató befejezéséhez töltse le a következő fájlokat:

- [ER modellkonfiguráció - CrossCompanyDataAccessModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [ER-formátumkonfiguráció - CrossCompanyDataAccessFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)
