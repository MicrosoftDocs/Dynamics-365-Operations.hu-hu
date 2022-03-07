---
title: Külső katalógus használatának engedélyezése a PunchOut e-beszerzés számára
description: Ez a témakör bemutatja, hogyan tud külső katalógusok segítségével igényléseket létrehozni és elküldeni.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b236a17a7f93bfeb60d64fa25745bd1b4cb1b34b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578032"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>Külső katalógus használatának engedélyezése a PunchOut e-beszerzés számára

[!include [banner](../includes/banner.md)]

Ha külső katalógusokat használ a PunchOut e-beszerzéssel, nem kell megőriznie a szállítók termékeivel kapcsolatos információkat a saját alapadataiban. Ehelyett a rendszer a szállító webhelyén levő bevásárlókocsit alakítja át az igénylési sorokká, amelyek a megfelelő termékinformációkkal rendelkeznek. 

Kerülje a szállító termékei leírásainak és árainak saját termék alapadataiban történő karbantartását. Ehelyett használjon külső katalógusokat a PunchOut e-beszerzéssel. Ezután amikor az alkalmazottak igénylésekethoznak létre, „blokkolhatják” ezeket a szállító külső katalógusának helyéhez (vagyis elhagyják a rendszerét és a szállítói webhelyre lépnek). A bevásárlókocsihoz a szállító webhelyén hozzáadott termékek ezután igénylési sorokká konvertálhatók. Ennek megfelelően helyes termékinformációkat kap a termékazonosító, a név, az ár stb. tekintetében.

Külső katalógusok használatához egy alkalmazottnak létre kell hoznia egy igénylést a **Saját beszerzési igénylések** lapon.

Az igénylést létrehozó alkalmazottat az igénylés készítőjének nevezik. Készítőként a következő műveleteket végezheti el:

A **Külső katalógusok** sorművelet segítsésével nyisson meg egy olyan lapot, amely tartalmazza a megadott kérelmező, vevő jogi személy és fogadó üzemi egység rendelkezésére álló összes külső katalógust.

Az engedélyektől függően módosítsa a kérelmezőt, a vevő jogi személyt vagy a fogadó üzemi egységet. Az ilyen értékek módosítása megváltoztathatja a kérelmező számára elérhető külső katalógusok listáját. A rendelkezésre álló külső katalógusok a vevő jogi személy vagy a bevételező üzemi egység aktuális aktív beszerzési irányelveitől függnek. Ezek az irányelvek engedélyezhetik vagy megakadályozhatják a konkrét beszerzési kategóriákhoz való hozzáférést. Ezért ez befolyással lehet az ilyen beszerzési kategóriákhoz leképezett külső katalógusok listájára.

Az irényelvekkel kapcsolatos további információ: [Beszerzési irányelvek – áttekintés](../procurement/purchase-policies.md).

- Az egyes beszerzési kategóriákhoz tartozó külső katalógusok kereséséhez írjon be szöveget a katalóguskeresési mezőbe.
- A szállító weboldalán található termékek külső szállítói katalógusából történő hozzáadásához kattintson a külső katalógusra. Ezután adjon termékeket a bevásárlókocsihoz, majd fizessen. A bevásárlókocsi sorai átkerülnek a Microsoft Dynamics 365 rendszerbe.

Ha a beszerzési kategóriákhoz több lehetőség is van, válassza ki a megfelelő beszerzési kategóriát, mielőtt hozzáadná a sorokat az igényléshez.
Miután sorokat adtak hozzá egy igénybevételhez, további sorokat is hozzáadhat külső katalógusok használata nélkül. Alternatívaként továbbra is használhat külső katalógusokat sorok hozzáadására.

Amikor az igénylés készen áll, használja a **Munkafolyamat** > **Küldés** műveletet a jóváhagyásra küldéshez.

### <a name="additional-resources"></a>További erőforrások

- [Külső katalógus beállítása a PunchOut e-beszerzés számára](set-up-external-catalog-for-punchout.md)
- [Beszerzési cXML-fejlesztések](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]