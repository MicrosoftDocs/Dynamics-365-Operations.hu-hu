---
title: A helyprofil nem engedélyezi a negatív készletet, de negatív aktuális készlet engedélyezett
description: A helyprofilhoz a Negatív készlet engedélyezése beállítása Nem, de a rendszer így is engedélyezi a negatív aktuális készletet.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 2a7345281301ee70a512dfadcd553cb4eb33003904d0dddf6967659b693f60d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742608"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>A helyprofil nem engedélyezi a negatív készletet, de negatív aktuális készlet engedélyezett

Tudásbáziscikk száma: 4613622

## <a name="symptoms"></a>Tünetek

A helyprofilhoz a **Negatív készlet engedélyezése** beállítása *Nem*, de a rendszer így is engedélyezi a negatív aktuális készletet.

## <a name="example-scenario"></a>Példaforgatókönyv

Állami szabályozású tranzakciók esetében a veszteség könyveléséhez a rendszernek képesnek kell lennie negatív készlet rögzítésére. Azt szeretné, hogy egy cikk negatív készletet mutathasson, de csak a megadott helyeken, például az önköltségi helyeken. Ha viszont a cikkmodellcsoport lehetővé teszi a negatív készletet, akkor úgy találja, hogy nem számít, hogy a helyen be van-e állítva a negatív készlet engedélyezése. Ha a cikk úgy van beállítva, hogy a negatív készlet nem megengedett, akkor a helyprofil beállítása sem számít.

## <a name="resolution"></a>Felbontás

A helyprofil **Negatív készlet engedélyezése** beállítása csak a raktári folyamatokra (például a kitárolásra) vonatkozik. A negatív készletre engedélyezésére beállított cikkmodellcsoportok ugyanakkor a Készletkezelés és Raktárkezelés modul minden folyamatát érintik, és a helyprofil nem bírálja felül a beállítást.

Szabályozhatja, hogy egy raktárnak megengedett-e a negatív készletet tárolni. A cikkmodellcsoportokat állítsa be a negatív fizikai készlet letiltására, és csak a megfelelő raktárakhoz állítsa be a negatív készlet engedélyezését.
