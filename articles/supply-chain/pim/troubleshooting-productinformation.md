---
title: Termékinformációk – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani a termékinformáció használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a05e9957363ef6a659e25ceba84a168507cd641a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841527"
---
# <a name="troubleshoot-product-information"></a>Termékinformációk – hibaelhárítás

Ez a témakör azt mutatja be, hogyan lehet javítani a termékinformáció használata során felmerülő problémákat.

## <a name="i-cant-delete-a-released-product"></a>Nem tudok törölni egy kiadott terméket.

### <a name="issue-description"></a>Probléma leírása

A kiadott termékeket és annak összes változatát csak akkor törölheti, ha a kiadott termékhez nem kapcsolódnak tranzakciók.

### <a name="issue-resolution"></a>Probléma megoldása

A kiadott termék vagy alaptermék törléséhez kövesse az alábbi lépéseket.

1. A cikkek összes nyitott tranzakciójának lezárása.
1. Csökkentse a készletet 0-ra (nulla).
1. Készletzárás végrehajtása.
1. Törölje a törölni kívánt alaptermék összes termékváltozatát.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>Módosíthatom a kiadott termék cikkszámát?

A legtöbb esetben nem szerkesztheti a kiadott termékek cikkszámait, mert ez a módosítás az adatok sérülését okozza. A cikkszámot csak akkor szerkesztheti, ha ki kell javítania azokat az adatsérüléseket, amelyeket a kiadott termék elsődleges kulcsának korábbi átnevezése okozott, ahogy az az [eltávolított vagy elavult Finance and Operations 10.0.0-s platformfrissítés 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24) funkciók listájában szerepel.

Ha azt szeretné, hogy képes legyen a kiadott termékek cikkszámainak szerkesztésére, [szavazzon erre az ötletre az Ideas portálon](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>A termék alapértelmezett ürítési elve nem kerül be az anyagjegyzéksorba.

### <a name="issue-description"></a>Probléma leírása

Amikor cikket ad hozzá egy anyagjegyzéksorhoz, a rendszer nem használja a cikkhez beállított alapértelmezett ürítési elv adatokat. Más szóval a cikk ürítési elve nem jelenik meg az **anyagjegyzéksor** oldalán.

### <a name="issue-resolution"></a>Probléma megoldása

Ha egy anyagjegyzéksorban ürítési elvet ad meg, az az adott anyagjegyzéksorra vonatkozik. Ha azonban az ürítési elv üres, vagy nincs beállítva anyagjegyzéksorhoz, akkor a cikken beállított ürítési elv továbbra is érvényes lesz az adott anyagjegyzéksorra, még akkor is, ha az nem jelenik meg az anyagjegyzéksorban.

A Microsoft Dynamics 365 Supply Chain Management egyéb funkcióinak alapértelmezett logikája általában nem így működik. A jelenlegi viselkedés azonban nem módosítható. Ellenkező esetben előfordulhat, hogy egyes meglévő testreszabások, amelyek támaszkodnak rá, megszakadnak.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>A rendszer lehetővé teszi, hogy ismétlődő vonalkódokat mentsek különböző cikkekhez vagy ugyanarra a különböző méretű cikkre.

A rendszer jelenleg nem kényszeríti ki az egyedi vonalkódokat, és a korlátozás hozzáadása kompatibilitástörő változás lenne. Valójában a Microsoftnak bizonyítéka van arra, hogy néhány meglévő ügyféltelepítést megtörne ez a változás. Azonban megfontoljuk a szélesebb körű tervezési változtatást, hogy a jövőben lehetővé tegyék ezt a funkciót.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Cikkbejegyzés-sablonok szerkesztéseknél a következő hibaüzenet jelenik meg: ”A raktár helye nem hozható létre, mert a cikk nincs raktáron. Cikkek készletezéséhez a kapcsolódó cikkmodellcsoport Készleten lévő termékbeállítását kell kiválasztani.”

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordul elő, ha az alábbi lépésekkel próbál sablont létrehozni egy nem raktározott cikkhez.

1. Nyisson meg egy nem raktározott, kiadott terméket.
1. A Művelet panel **Lehetőségek** fülön válassza a **Rekord infó** menüpontot.
1. A **Rekordinformáció** párbeszédpanelen válassza a **Vállalati számlák sablon** lehetőséget.

Ebben az esetben az alábbi hibaüzenetet kapja:

> A raktár nem hozható létre, mert a cikk nincs raktáron. Cikkek készletezéséhez a kapcsolódó cikkmodellcsoport Készleten lévő termékbeállítását kell kiválasztani.

### <a name="issue-resolution"></a>Probléma megoldása

A terméksablonok létrehozásának folyamata további termékspecifikus logikát igényel. Ezért erre a célra nem használhatja az általános **Vállalati számlák sablon** gombot. Ehelyett kövesse az alábbi lépéseket.

1. Nyisson meg egy kiadott terméket.
1. A Művelet panelen a **Termék** fülön az **Új** csoportban válassza a **Sablon \> Megosztott sablon létrehozása** lehetőséget.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>A termékattribútumokban hozzáadott alapértelmezett súgószöveg nem kerül be a kiadott termékbe.

A termékattribútumokban hozzáadott leírás és súgószöveg nem látható, és alapértelmezés szerint nem szerepel a kiadott termékekben. Ez szándékosan van.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>A megadott alapértelmezett mennyiség akkor változik, ha az anyagjegyzékből, és ha az anyagjegyzék-verzióból van regisztrálva.

### <a name="issue-description"></a>Probléma leírása

Alapértelmezés szerint, amikor cikket ad hozzá egy anyagjegyzékhez, a mennyiség 1-re van állítva a kiválasztott termék **Alapértelmezett rendelési beállítások** lapjának **Min. rendelési mennyisége** lehetőségben. Ha azonban egy anyagjegyzék-verzióból vesz fel cikket, és a cikk és a változat ki van jelölve, az alapértelmezés szerint megadott mennyiség figyelembe veszi az adott dimenziók alapértelmezett rendelési beállításaiban megadott minimális mennyiséget.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a viselkedés várható. Azonban az a tény, hogy a logika eltér az anyagjegyzékben és az anyagjegyzék-verzióban, az egy ismert probléma. Mindazonáltal ez a viselkedés nem változik, mert a módosítás számos különböző ügyfélforgatókönyvre hatással lehet.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>A kiadott termékrészletekben nem tudom módosítani a termékdokumentum mellékleteinek adatentitásból feltöltött csatolt képeket.

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordulhat elő, ha egy képet egy elemhez csatol a *Termékdokumentum mellékletek* adatentitás használatával. Ebben az esetben az elem képe jelenik meg az elemnél. Ha azonban a **Kép módosítása** lehetőséget választja, a feltöltött képek listájában semmi sem jelenik meg. Ezenkívül nem jelennek meg mellékletek az elemhez.

### <a name="issue-resolution"></a>Probléma megoldása

Az *EcoResProductDocumentAttachmentEntity* entitás (*Termékdokumentum-mellékletek*) importálja a *termékekhez* tartozó, de a *kiadott termékekhez* nem tartalmazó dokumentummellékleteket importál. (A kiadott termékeket *cikkeknek* is nevezik.) Ha egy elem mellékleteit a **Kiadott termék részletei** lapon szeretné megtekinteni, az *EcoResReleasedProductDocumentAttachmentEntity* entitást (*Kiadott termékdokumentum-mellékletek*) kell használnia.

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>Az Microsoft Flow összekötő a következő hibaüzenetet jeleníti meg: „Frissítés nem engedélyezett a „ProductNumber” mezőhöz”.

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordul elő, ha a **Termékszám** mezőt a *Kiadott termékek* entitás V2 és Microsoft Flow használatával próbálja frissíteni.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a viselkedés várható. A kiadott termék termékszámának szerkesztési lehetősége a Dynamics 365 Finance and Operations 10.0.0 verzióban a 24-es számú platformfrissítéssel lett eltávolítva az adatsérülés megelőzése érdekében. Kivételes esetekben ki kell javítania a kiadott termék elsődleges kulcsának egy korábbi átnevezése által okozott adatsérülést, kérdezze meg a Microsoft ügyfélszolgálatát a korlátozás ideiglenes eltávolításának kérése céljából.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>Nem tudok kiadott termékváltozatot létrehozni egy másik jogi személyben.

### <a name="issue-description"></a>Probléma leírása

Ha megpróbál kiadni egy alapterméket változatok nélkül, majd szükség szerint létrehozza az egyes jogi személy (vállalat) változatait, akkor a változatokat nem tudja kiadni változatjavaslatok használatával. A változatokat sem fogja tudni manuálisan létrehozni.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. Az alaptermék viszonyai és az alap által felvehető dimenziók megosztott szinten maradnak. Ezért nem hozhatja létre a rendelkezésre álló dimenziókat egy megosztott termékalaphoz egy adott jogi személynél, ahol ezeket a dimenziókat kiadta, és replikálja a folyamatot minden jogi személy, ahol a dimenziók szükségesek. Ehelyett módosítania kell a kiadási folyamatot, hogy az alkalmazkodjon a tervezett folyamathoz.

Itt van a termékek kiadásának folyamata.

1. Hozza létre a megosztott alapterméket és a jogi személyek számára kiadható dimenziókat.
1. Adja ki a termékeket a jogi személyeknek, vagy változatjavaslatok használatával, vagy manuálisan adja hozzá a kiadandó kombinációkat.

Azt is megteheti, hogy közvetlenül létrehozza a kiadott terméket.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>Amikor egy másik vállalatnál egy változatot kiadok, a következő hibaüzenet jelenik meg: „A megadott dimenziójú termékváltozat már létrejött.”

### <a name="issue-description"></a>Probléma leírása

Ha egy termékváltozat már megjelent egy „A” vállalatnál, és a „B” vállalatnál a **Kiadott termékváltozatok** lap **Új** gombjával próbálja meg kiadni, a következő hibaüzenet jelenik meg:

> A megadott dimenziókkal rendelkező termékváltozat már létrejött.

### <a name="issue-resolution"></a>Probléma megoldása

A **Kiadott termékváltozatok** lap **Új** gombja létrehozza a változatot, és vállalati környezetben adja ki azt. Ha a változat már létrejött, nem használhatja az **Új** gombot, hogy kiadja egy másik vállalatnál.

A probléma megoldásához nyissa meg az **Alaptermék** oldalt, és válassza a **Termék kiadása** lehetőséget a meglévő változat kiadásához a kívánt vállalatnál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]