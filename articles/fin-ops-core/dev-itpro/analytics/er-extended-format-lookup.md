---
title: Elektronikus jelentéskészítés (ER) – kiterjesztett formátumkeresés
description: Ez a témakör azt mutatja be, hogyan állíthat be ER-formátumhivatkozásokat az ER-formátumkeresésben, ha a kívánt formátum a globális tárházban található.
author: NickSelin
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 59b2cc1dae5774322d47f76e1213f0e8c8a0b8b244a68c113e34484c1e59b209
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767218"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>A felhasználók számára a Globális tárházban tárolt formátumot lekérő formátumreferencia beállításának engedélyezése

[!include [banner](../includes/banner.md)]

Az [Elektronikus jelentéstételi](general-electronic-reporting.md) (ER) keretrendszer segítségével a különböző országok/régiók jogi követelményeinek megfelelően konfigurálható az elektronikus dokumentumok [formátuma](general-electronic-reporting.md#FormatComponentOutbound). Az ER-keretrendszerrel ezenfelül konfigurálhatja a bejövő dokumentumok elemzésének [formátumát](general-electronic-reporting.md#FormatComponentInbound), és a dokumentumokból származó adatokat hozzáfűzheti az alkalmazás adataihoz, vagy frissítheti azokat. Mindegyik formátum használható a Dynamics 365 Finance példányában a bejövő vagy kimenő üzleti dokumentumok bizonyos üzleti folyamatok részeként történő kezeléséhez.

Általában meg kell adnia, hogy egy bizonyos üzleti folyamatban milyen ER formátumot kell használni. Ehhez válasszon ki egy adott ER-formátumot a keresési mezőben, amely az üzleti folyamatspecifikus paraméterek részeként be van állítva. Ezeket a keresési mezőket általában az ER-keretrendszer megfelelő API-ja segítségével valósítják meg. További tudnivalókért láss: [ER-keretrendszer API – a formátumleképezési keresés megjelenítéséhez szükséges kód](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

Például a [Külkereskedelmi paraméterek](../../../finance/localizations/emea-intrastat.md#set-up-foreign-trade-parameters) konfigurálásakor be kell állítani az Intrastat-bevallás és az Intrastat-bevallás ellenőrzési jelentésének előállításához használt egyéni ER-formátumokra mutató hivatkozásokat is. Az alábbi képernyőképek azt mutatják be, hogy hogyan néz ki az ER-formátumkeresési mező a **Külkereskedelmi paraméterek** oldalon.

Ha az aktuális Finance példány nem tartalmaz Intrastat üzleti folyamatokkal kapcsolatos ER-formátumokat, akkor ez a keresési mező üresen marad.

[![Külkereskedelmi paraméterek oldal.](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Ha az aktuális Finance-példány tartalmaz Intrastat üzleti folyamatokkal kapcsolatos ER-formátumokat, akkor ez a keresési mező ER-formátumokat ajánl fel.

[![Külkereskedelmi paraméterek oldal.](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

Ez a keresés csak az aktuális Finance-példányba már importált ER-formátumokat kínálja fel. Ha az aktuális Financeapéldánybe ER-megoldásokat szeretne [importálni](./tasks/er-import-configuration-lifecycle-services.md), rendelkeznie kell jogosultsággal az olyan ER-keretrendszer megfelelő funkciójának futtatásához, amely támogatja az ER-formátumokat tartalmazó megoldások [életciklusát](general-electronic-reporting-manage-configuration-lifecycle.md).

A Finance 10.0.9 verziójával (2020. áprilisi kiadás) kezdődően az ER-formátumkereseés felhasználói felületét (amelyet az ER-keretrendszer API-jával hoztunk létre) kiterjesztettük. Továbbra is kiválaszthatja a meglévő ER- formátumokat, amelyek a **Válassza ki a formátumkonfigurációt** gyorslapon találhatóak. Ezenkívül a kiterjesztett keresés az új lehetőséget kínál a globális tárházban (GR) való keresésre, hogy konkrét ER-formátumokat találhasson. A GR összes ER-formátuma felkínálható az **Importálás a globális tárházból** gyorslapon.

[![Külkereskedelmi paraméterek oldal.](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

A **Válassza ki a formátumkonfigurációt** gyorslaphoz hasonlóan az **Importálás a globális tárházból** gyorslapról történő importálás csak azokat az ER-formátumokat jeleníti meg, amelyek arra az üzleti folyamatra vonatkoznak, amelyekhez a keresési mezőben be van jelölve az ER-formátum. Ebben a példában egy Intrastat-bevallás generálása látható. Az ER-formátum attól függően alkalmazható a vállalat esetén, amelyhez a felhasználó pillanatnyilag be van jelentkezve, hogy a vállalat országa milyen környezetben van.

Amikor az **Importálás a globális tárházból** gyorslapjon kijelöl egy ER-formátumot, a program a GR-ből az aktuális Finance-példányba importálja a kiválasztott ER-formátum[konfigurációt](general-electronic-reporting.md#Configuration).

[![Külkereskedelmi paraméterek oldal.](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Ezt követően, ha az importálás sikeresen befejeződött, a program a keresési mezőben tárolja az importált értékre mutató hivatkozást. Amikor első alkalommal nyitja meg a GR-t, követnie kell a megadott hivatkozást, hogy feliratkozzon a GR-tárolóhoz való hozzáférés kezelésére használt [Regulatory Configuration Service](https://aka.ms/rcs) szolgáltatásra (RCS).

[![Külkereskedelmi paraméterek oldal.](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Alapértelmezetten az **Importálás a globális tárházból** gyorslap a teljesítmény javítása érdekében a GR-tartalom alapján automatikusan létrehozott ideiglenes tárolóból származó ER-formátumok listáját mutatja. Ez akkor fordulhat elő, ha az **Importálás a globális tárházból** gyorslapot első alkalommal nyitja meg, ami több másodpercig is eltarthat.

Ha nem látja a szükséges ER-formátumot az **Importálás a globális tárházból** gyorslapon, de biztos abban, hogy ez az ER-formátum a GR-területen található, akkor jelölje be a **Szinkronizálás** beállítást. Ez a lehetőség frissíti az ideiglenes tárolót, és szinkronizálja azt a GR aktuális tartalmával.

## <a name="feature-activation"></a>Funkció aktiválása

Ennek a funkciónak az elérhetőségét **A globális tárházból való lekérdezéseket lehetővé tevő ER-formátumok kiterjesztett keresése** funkció vezérli, amely a **Funkció kezelése** helyen található. Alapértelmezetten ez a paraméter engedélyezett.

[![Funkció kezelése oldal.](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Biztonsági megfontolások

A **Konfigurációs tárolók karbantartása** (**ERMaintainSolutionRepositories**) jogosultság szabályozza a GR-hez való hozzáférést olyan felhasználók számára, akik engedélyezték az **Importálás a globális tárházból** gyorslapot. Ha engedélyezni szeretné, hogy a felhasználók elérjék a GR-tartalmat az ER-formátumkeresésekből, módosítania kell a biztonsági beállításokat: adja meg az **ERMaintainSolutionRepositories** jogosultságot a felhasználóknak közvetlenül, vagy már kiosztott szerepkörök és feladatkörök segítségével.

A következő képernyőkép azt mutatja be, hogyan lehet a jogosultságot a **Könyvelő** szerepkörrel rendelkező felhasználók számára biztosítani. Ez a szerepkör teszi lehetővé a felhasználók számára a Külkereskedelmi paraméterek konfigurálását a **Külkereskedelmi paraméterek** oldalon az ER-formátumokra mutató hivatkozások beállítását a **Fájlformátum-hozzárendelés** és a **Jelentésformátum-hozzárendelés** mezőkben.

[![Biztonsági konfiguráció oldal.](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Korlátozások

A GR-hez való hozzáférés az ER-formátumkeresés közben jelenleg csak a kimenő dokumentumok létrehozásához használt ER-formátumok esetében támogatott.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>Miért nem tudom elérni a globális tárházat az ER-formátumkeresésből?

Ha a **Funkció kezelése** oldalon engedélyezte **A globális tárházból való lekérdezéseket lehetővé tevő ER-formátumok kiterjesztett keresése** funkciót, de a felhasználók nem látnak ER-formátumokat az **Importálás a globális tárházból** gyorslapon, és a **Szinkronizálás** lehetőség látható, de tiltva van, győzőjön meg arról, hogy a felhasználó rendelkezzen a **Konfigurációs tárolók karbantartása** (**ERMaintainSolutionRepositories**) jogosultsággal. Ezt a jogosultságot a rendszergazdától kérheti.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéstételi (ER) keretrendszer API](er-apis-app73.md)
- [Elektronikus jelentéstételi (ER) konfiguráció életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]