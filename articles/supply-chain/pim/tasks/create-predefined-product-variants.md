---
title: Az előre meghatározott termékváltozatok létrehozása
description: Ez az eljárás bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d3a4ae8efd438e01c263af1c0a1746d9484e491
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103098"
---
# <a name="predefined-product-variants"></a>Előre meghatározott termékváltozatok

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Példaforgatókönyv: Az előre meghatározott termékváltozatok létrehozása

Ez az példaforgatókönyv bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen forgatókönyv itt javasolt értékekkel való követéséhez a demóadatokat kell telepíteni, és az *USMF* demó jogi személyt kell használnia.

### <a name="step-1-create-a-product-master"></a>1. lépés: Alaptermék létrehozása

Alaptermék létrehozásához:

1. Ugorjon a **Termékinformációk kezelése > Termékek > Alaptermékek** lehetőségre.
1. Válassza az **Új** lehetőséget.
1. Ha a **Termékszám** mezőben még nem létezik szám, adjon meg egy értéket. Ez csak akkor szükséges, ha nem lett számsorozat beállítva ehhez a mezőhöz.
1. A **Termék neve** mezőbe írjon be egy nevet.
1. A **Termékdimenzió-csoport** mezőben válassza ki a *SizeCol* (Méret és Szín) termékdimenzió-csoportot.
1. Az új alaptermék létrehozásához és megnyitásához kattintson az **OK** gombra.

### <a name="step-2-add-product-dimensions"></a>2. lépés: Termékdimenziók hozzáadása

Ez a példa bemutatja, hogy hogyan lehet manuálisan megadni a termékdimenziókat. Arra is lehetősége van, hogy kiválassza a méretet, a színt és a stíluscsoportot, amely a használni kívánt termékdimenzió értékeket tartalmazza.

Termékdimenziók hozzáadásához:

1. Ha az új alaptermék még nyitva marad, válassza ki a **Termékdimenziókat** a műveleti ablaktáblán.
1. Ha új sort szeretne felvenni a rácsba, nyissa meg a **Méret** lapot, és válassza az eszköztár **Új** gombját. Az új sorhoz állítsa be a következőket:
    - **Méret:** Válasszon egy méretértéket.
    - **Név:** Adjon meg egy nevet a méretnek.
1. Válassza az eszköztár **Új** gombját, és adjon hozzá egy második méretet a rácshoz egy új **Méret** és **Név** használatával.
1. Ha új sort szeretne felvenni a rácsba, nyissa meg a **Színek** lapot, és válassza az eszköztár **Új** gombját. Az új sorhoz állítsa be a következőket:
    - **Szín:** Válasszon egy színértéket.
    - **Név:** Adjon meg egy nevet a színnek.
1. Válassza az eszköztár **Új** gombját, és adjon hozzá egy második színt a rácshoz egy új **Szín** és **Név** használatával.
1. Válassza a **Mentés** lehetőséget.
1. Az új alaptermékhez való visszatéréshez zárja be a lapot.

### <a name="step-3-generate-product-variants"></a>3. lépés: Termékváltozatok létrehozása

> [!NOTE]
> Ez a szakasz azt írja le, hogyan lehet termékváltozatokat generálni, ha nincs engedélyezve a *Változatjavaslatok oldal javításai* funkció. A következő szakaszban arról olvashat részletesen, hogy hogyan lehet termékváltozatokat generálni, ha ez a funkció elérhető.

Termékváltozatok létrehozásához:

1. Ha az új alaptermék még nyitva marad, válassza ki a **Termékváltozatokat** a műveleti ablaktáblán.
1. A Műveleti ablaktáblán válassza ki a **Változatjavaslatok** elemet.
1. A rendszer listát generál a termékhez megadott méretek és színek összes lehetséges kombinációjáról. Válassza at **Összes kijelölése** elemet az eszköztáron.
    - Az alábbi példában válassza ki az összes lehetséges változatot. Ha csak a lehetséges termékdimenzió-kombinációk egy részhalmazát szeretné használni, csak a szükséges jelölőnégyzeteket jelölje be.  
1. Válassza a **Létrehozása** lehetőséget.
1. Válassza a **Mentés** lehetőséget.

## <a name="improved-variant-suggestions"></a>Továbbfejlesztett változatjavaslatok

A *Változatjavaslatok oldal javításai* funkció javítja a **Változatjavaslatok** oldalt, így reagálva az olyan vállalatok teljesítmény- és használhatósági problémáira, amelyek nagy számú termékdimenzió-kombinációt használnak. Az olyan termékdimenzió-értékek kiválasztásának továbbfejlesztett folyamata, amelyekhez változatjavaslatokat kell létrehozni, felgyorsítja és megkönnyíti a termékváltozatok releváns halmazának beazonosítását és kiadását.

Ez a funkció a következő fejlesztéseket biztosítja:

- **Változatjavaslatok késleltetett létrehozása:** A **Változatjavaslatok** oldal már nem jelenít meg javaslatokat az első megnyitáskor. Ehelyett explicit módon ki kell választania, hogy milyen értékekre lesz szüksége, majd a kombinációk létrehozásához kattintson a **Javaslat** gombra. Így a folyamat láthatóvá és interaktívvá válik.
- **Dimenzióértékek kiválasztása**: Ha sok dimenzióértékkel rendelkezik, akkor általában csak néhányat tartalmazó változatjavaslatok létrehozása szükséges az Ön számára (például amikor új színeket vagy stílusokat vezet be). A továbbfejlesztett kialakítással kiválaszthatja azokat a dimenzióértékeket, amelyekhez termékváltozat-javaslatokat szeretne létrehozni. Ez nagy mértékben növeli a javasolt változatok relevanciáját, és javítja a rendszer teljesítményét és a felhasználói hatékonyságot.

### <a name="turn-the-variant-suggestions-page-improvements-feature-on-or-off"></a>A Változatjavaslatok lapjavítások funkció be- és kikapcsolása

Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy kapcsolhatják *be és kapcsolják ki ezt a funkciót, hogy a Funkciókezelés munkaterület Változatjavaslatok*[lapja](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) javítására keresnek rá.

### <a name="work-with-the-improved-variant-suggestions"></a>A továbbfejlesztett változatjavaslatok használata

A termékváltozat-javaslatok létrehozásához, ha engedélyezve van a *Változatjavaslatok oldal javításai* funkció:

1. Nyisson meg vagy hozzon létre egy alapterméket, és adja hozzá a szükséges termékdimenziókat az előző szakaszban leírtak szerint.
1. Ha az alaptermék még nyitva marad, válassza ki a **Termékváltozatokat** a műveleti ablaktáblán.
1. A Műveleti ablaktáblán válassza ki a **Változatjavaslatok** elemet.
1. Válassza ki a használni kívánt értékeket az egyes dimenziókhoz.
1. A felső eszköztáron válassza a **Javaslat** elemet.
1. A rendszer listát generál a kiválasztott méretek és színek összes lehetséges kombinációjáról. Jelölje be a **Javasolt változatok** gyorstáblán a használni kívánt termékdimenzió-kombinációk jelölőnégyzetét, vagy válassza az **Összes kijelölése** elemet az eszköztáron az összes kiválasztásához.  
1. Válassza a **Létrehozás** lehetőséget, ha a változatokat hozzá szeretne adni az aktuális alaptermékhez.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
