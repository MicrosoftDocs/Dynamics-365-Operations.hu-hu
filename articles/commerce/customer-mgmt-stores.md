---
title: Vevők kezelése az üzletekben
description: Ez a cikk bemutatja, hogyan engedélyezhetik a kiskereskedők a vevőkezelési képességeket a pénztárnál (POS) a következőben:Microsoft Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 2928aa5c4e62611b54799fbe7c1bba25fe186bcd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282241"
---
# <a name="customer-management-in-stores"></a>Vevők kezelése az üzletekben

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan engedélyezhetik a kiskereskedők a vevőkezelési képességeket a pénztárnál (POS) a következőben:Microsoft Dynamics 365 Commerce

Fontos, hogy az üzlet munkatársai vevőrekordokat hozhassanak létre és szerkeszthessenek a pénztárban. Ily módon rögzíthetik a vevői adatok esetleges frissítéseit, például az e-mail-címet, a telefonszámot és a címet. Ez az információ hasznos az olyan alsóbb rétegbeli rendszerekben, mint a marketing, mivel ezeknek a rendszereknek a hatékonysága az ügyféladatok pontosságától függ.

Az értékesítési munkatársak két pénztári belépési pontból tudják aktiválni a vevő létrehozásának munkafolyamatát. Kiválaszthat egy, a **Vevő hozzáadása** nevű művelethez hozzárendelt gombot, vagy k Keresési eredmények oldalon az alkalmazássávon a **Vevő létrehozása** lehetőséget. Mindkét esetben megjelenik az **Új vevő** párbeszédpanel, ahol az értékesítési munkatárs megadhatja a vevő szükséges adatait, például a vevő nevét, e-mail-címét, telefonszámát, címét és az üzleti tevékenység számára esetleges további, releváns információkat. Ezek a kiegészítő információk a vevőhöz társított vevőattribútumok segítségével is rögzítethetők. A vevőattribútumokkal kapcsolatos további tudnivalókat lásd: [Vevőattribútumok](dev-itpro/customer-attributes.md).

Az értékesítési munkatárs másodlagos e-mail-címeket és telefonszámokat is rögzíthet. Ezenkívül rögzítheti, hogy a vevő a másodlagos e-mail-címek vagy telefonszámok egyikén fogad-e marketinginformációkat. A funkció engedélyezéséhez a kiskereskedőknek be kell kapcsolniuk a **Több e-mail és telefonszám rögzítése és a marketinghez való hozzájárulás ezen kapcsolatok esetén** funkciót a Commerce központi felületének **Funkciókezelés** munkaterületén (**Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés**).

## <a name="default-customer-properties"></a>Alapértelmezett vevőtulajdonságok

A kiskereskedők használhatják az **Összes üzlet** oldalt a Commerce központi felületén (**Retail és Commerce \> Csatornák \> Üzletek**) arra, hogy egy alapértelmezett vevőt társítsanak az egyes üzletekhez. A Commerce rendszer ezután átmásolja az alapértelmezett vevőhöz meghatározott tulajdonságokat az összes létrehozott új vevőrekordba. Például a **Vevő létrehozása** párbeszédpanelen azok a tulajdonságok jelennek meg, amelyek az üzlethez társított alapértelmezett vevőhöz vannak társítva. Ilyen tulajdonságok például a **vevő típusa**, a **vevőcsoport**, a **nyugta beállítása**, a **nyugtaként kapott e-mail**, a **pénznem** és a **nyelv**. A **fiókok** (vevői csoportok) is az alapértelmezett vevőtől öröklődnek. A **pénzügyi dimenziók** azonban attól a vevői csoporttól öröklődnek, amely az alapértelmezett vevőhöz van társítva, nem pedig magától az alapértelmezett vevőtől.

> [!NOTE]
> A **nyugtaként kapott e-mail** értékét csak akkor az alapértelmezett vevőtől másolja át a rendszer, ha az újonnan létrehozott vevőknél nem áll rendelkezésre a nyugtaként kapott e-mail azonosítója. Ez azt jelenti, hogy ha az alapértelmezett vevőnél megtalálható a nyugtaként kapott e-mail azonosítója, akkor az e-kereskedelmi webhelyről létrehozott valamennyi vevő a nyugtaként kapott e-mail ugyanazon azonosítóját fogja kapni, mivel a felhasználói felületen nem rögzíthető a nyugtaként kapott e-mail vevőtől származó azonosítója. Javasoljuk, hogy az üzlet alapértelmezett vevőjénél hagyja üresen a **nyugtaként kapott e-mail** mezőt. Csak olyan üzleti folyamat esetén használja ezt a mezőt, amelynél szükség van a nyugtához tartozó e-mail-címre. 

Az értékesítési munkatársak több címet is rögzíthetnek egy vevőhöz. A vevő neve és telefonszáma az egyes címekhez társított kapcsolattartási adatokból öröklődik. A vevőrekord **Címek** gyorslapja tartalmaz egy **Cél** mezőt, amelyet az értékesítési munkatársak módosíthatnak. Ha a vevő típusa **Személy**, az alapértelmezett érték a **Kezdőlap**. Ha a vevő típusa **Szervezet**, az alapértelmezett érték a **Vállalat**. A mező által támogatott egyéb értékek közé tartozik a **Kezdőlap**, az **Iroda** és a **Postaláda**. A cím **Ország** mezőjének értéke abból az elsődleges címből öröklődik, amely a Commerce központi felületében az **Üzemi egység** oldalon van megadva a **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek** pontban.



## <a name="additional-resources"></a>További erőforrások

[Aszinkron vevőlétrehozási mód](async-customer-mode.md)

[Aszinkron vevők átalakítása szinkron vevőkké](convert-async-to-sync.md)

[Vevőattribútumok](dev-itpro/customer-attributes.md)

[Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
