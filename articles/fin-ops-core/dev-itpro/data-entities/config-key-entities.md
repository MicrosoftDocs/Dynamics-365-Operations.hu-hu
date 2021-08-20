---
title: Konfigurációs kulcsok és adatentitások
description: Ez a témakör bemutatja a konfigurációs kulcsok és az entitások közötti kapcsolatot.
author: Sunil-Garg
ms.date: 05/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 72204c0a454c9893b05f2cf37a3d43c49f06532faba48f344644ba83e3351110
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737851"
---
# <a name="configuration-keys-and-data-entities"></a>Konfigurációs kulcsok és adatentitások

[!include [banner](../includes/banner.md)]

Mielőtt adatentitásokat használna az adatok importálására vagy exportálására, javasoljuk, hogy először határozza meg a konfigurációs kulcsok hatását a használni kívánt adatentitásokra.

Ha szeretne többet megtudni a konfigurációs kulcsokról, lásd: [Licenckódok és konfigurációskulcs-jelentések](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Konfigurációs kulcsok hozzárendelése
Konfigurációs kulcsok a következő műtermékek egyikéhez vagy mindegyikéhez is hozzárendelhetők.

- Adatentitások
- Adatforrásként használt táblák
- Táblamezők
- Adatentitás-mezők

Az alábbi táblázat összefoglalja, hogy az objektum alapjául szolgáló különböző műtermékek konfigurációs kulcs-értékei hogyan változtatják meg az objektum várható viselkedését.

| Adatentitás konfigurációskulcs-beállítása | Tábla konfigurációskulcs-beállítása | Táblamező konfigurációskulcs-beállítása | Adatentitás-mező konfigurációs kulcsa | Várható viselkedés |
|-----------------------------------------|------------------------------------|------------------------------------------|----------------------------------------|------------------|
| Letiltva                                | Nem kiértékelt                      | Nem kiértékelt                            | Nem kiértékelt                          | Ha az adatentitás konfigurációs kulcsa le van tiltva, akkor az adatentitás nem fog működni. Nem számít, hogy a mögöttes táblák és mezők konfigurációs kulcsai engedélyezve vagy tiltva vannak-e. |
| Engedélyezett                                 | Letiltva                           | Nem kiértékelt                            | Nem kiértékelt                          | Ha az adatentitáshoz tartozó konfigurációs kulcs engedélyezve van, akkor az adatkezelési keretrendszer ellenőrzi minden egyes mögöttes táblán ellenőrzi a konfigurációs kulcsot. Ha egy táblához tartozó konfigurációs kulcs le van tiltva, akkor az adott tábla nem lesz elérhető az adatentitásban való felhasználásra. Ha egy tábla konfigurációs kulcsa le van tiltva, a tábla és az adatentitás konfigurációskulcs-beállításait a rendszer nem veszi figyelembe. Ha az entitás elsődleges táblájának konfigurációs kulcsa le van tiltva, a rendszer úgy jár el, mintha az entitás konfigurációs kulcsa lenne letiltva. |
| Engedélyezett                                 | Engedélyezett                            | Letiltva                                 | Nem kiértékelt                          | Ha egy adatentitáshoz tartozó konfigurációs kulcs engedélyezve van, és az alapul szolgáló táblák konfigurációs kulcsai engedélyezve vannak, akkor az adatkezelő keretrendszer ellenőrzi a táblák mezőinek konfigurációs kulcsát. Ha egy mező konfigurációs kulcsa le van tiltva, ez a mező akkor sem lesz elérhető az adatentitásban való felhasználásra, ha a megfelelő adatentitás-mezőnél a konfigurációs kulcs engedélyezve van. |
| Engedélyezett                                 | Engedélyezett                            | Engedélyezett                                  | Letiltva                               | Ha a konfigurációs kulcs minden más szinten engedélyezve van, de az entitásmező konfigurációs kulcsa nincs engedélyezve, akkor a mező nem lesz elérhető az adatentitásban. |

> [!NOTE]
> Ha egy entitás egy másik entitást használ adatforrásként, akkor a fenti szemantika rekurzív módon kerül alkalmazásra.

### <a name="entity-list-refresh"></a>Entitáslista frissítése
Az entitáslista frissítésekor az adatkezelő keretrendszer létrehozza a konfigurációskulcs-metaadatokat a futásidejű használathoz. Ezen metaadatok létrehozása a fent leírt logikával történik. Mindenképpen javasoljuk, hogy várja meg, hogy az entitáslista frissítése befejeződjön, mielőtt az adatkezelő keretrendszerben feladatokat és entitásokat használna. Ha nem vár, a konfigurációskulcs-metaadatok elavultak lehetnek, ami nem várt eredményeket okozhat. Az entitáslista frissítésekor a következő üzenet jelenik meg az entitások listája oldalon.

![Entitáslista frissítése.](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Adatentitások listája oldal
Az adatentitások listája oldal az adatkezelési munkaterületen az entitások konfigurációskulcs-beállításait mutatja. Induljon ki erről az oldalról a konfigurációs kulcsok az adatentitásokra gyakorolt hatásának megértéséhez.

Ez az információ azon metaadatok használatával jelenik meg, amelyek az entitás frissítéskor jönnek létre. A konfigurációs kulcs oszlopban látható az adatentitással társított konfigurációs kulcs neve. Ha ez az oszlop üres, azt jelenti, hogy az adatentitáshoz nincs konfigurációs kulcs társítva. A konfigurációs kulcs állapota oszlop a konfigurációs kulcs állapotát mutatja. Ha be van jelölve, akkor a kulcs engedélyezve van. Ha üres, akkor a kulcs le van tiltva, vagy nincs társítva kulcs.

![Entitások listája oldal.](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Célmezők
A következő lépés leásni az adatentitásba a konfigurációs kulcsok táblázatokra és mezőkre gyakorolt hatásának megjelenítéséhez. Az adatentitáshoz tartozó célmezők képernyő mutatja a konfigurációs kulcsot és az adatentitáshoz tartozó táblák és mezők kulcsállapot-adatait. Ha az adatentitásnak magának a konfigurációs kulcsa le van tiltva, figyelmeztető üzenet jelenik meg arról, hogy az adott entitáshoz tartozó célmezők képernyőn lévő táblák és mezők egyáltalán nem lesznek elérhetők a konfigurációs kulcs állapotától függetlenül.

![Célmezők.](./media/Target_fields_1.png)

### <a name="child-entities"></a>Gyermekentitások 
Bizonyos entitások más entitásokat használnak adatforrásokként, vagy összetett adatentitások: ezeknek a entitásoknak a konfigurációskulcs-információit a Gyermekentitások képernyő tartalmazza. Ezt a képernyőt a fenti entitáslista oldalhoz hasonló módon kell használni. A gyermekentitásokhoz tartozó célmezők képernyő is úgy viselkedik, mint a fent leírtak.

![Célmezők.](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Adatentitások használata
A használni kívánt adatentitások esetleges konfigurációs kulcsai teljes hatásának megértését követően továbbléphet az adatentitások projektekhez hozzáadásával történő használatára. 

### <a name="run-time-validations-for-configuration-keys"></a>Konfigurációs kulcsok futásidejű ellenőrzése
Az entitáslista frissítése során létrehozott konfigurációskulcs-metaadatok használatával futásidejű ellenőrzésre kerül sor a következő esetekben.

- Ha egy adatentitás hozzáadódik egy feladathoz
- Amikor a felhasználó rákattint az „ellenőrzés” elemre az entitáslistában
- Amikor a felhasználó betölt egy adatcsomagot egy adatprojektbe
- Amikor a felhasználó betölt egy sablont egy adatprojektbe
- Meglévő adatprojekt betöltésénél
- Sablon betöltésénél egy adatprojektbe
- Exportálási/importálási feladat végrehajtása előtt (kötegelt, nem kötegelt, ismétlődő, OData)
- Amikor a felhasználó leképezést hoz létre
- Amikor a felhasználó mezőket képez le a leképezési felületen
- Amikor a felhasználó csak „importálható mezőket” ad hozzá

### <a name="managing-configuration-key-changes"></a>Konfigurációs kulcsok módosításainak kezelése
Valahányszor frissíti a konfigurációs kulcsokat az entitás, tábla vagy mező szintjén, frissíteni kell az adatkezelő keretrendszerben szereplő entitások listáját. Ez a folyamat biztosítja, hogy a keretrendszer a legutóbbi konfigurációskulcs-beállításokat használja. Az entitáslista frissítéséig a következő üzenet látható az entitások listája oldalon. A frissített konfigurációskulcs-módosítások az entitáslista frissítése után azonnal életbe lépnek. Javasoljuk, hogy ellenőrizze a meglévő adatprojekteket és feladatokat, és győződjön meg arról, hogy a konfigurációs kulcsok módosításainak alkalmazása után a várt módon működnek.

![Célmezők.](./media/Target_fields_3.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]