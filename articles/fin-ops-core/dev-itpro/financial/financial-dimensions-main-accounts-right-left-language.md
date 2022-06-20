---
title: Pénzügyi dimenziók és fő számlák a jobbról balra író nyelvek esetében
description: Ez a témakör olyan döntéseket ír le, amelyek a jobbról balra való nyelv használata esetén szükséges, valamint be kell állítani a pénzügyi dimenziókat és a fő számlákat.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b1e2c0ef5cd405232332847078c70af42f056e17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866760"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Pénzügyi dimenziók és fő számlák a jobbról balra író nyelvek esetében

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti azokat a megvalósítási döntéseket, amelyekre a jobbról balra való beállításnál figyelembe kell venni, és be kell állítani a pénzügyi dimenziókat és a fő számlákat.

A pénzügyi dimenziók és a fő számlák rendkívül alkotóelemek a megvalósítás tervezési szakaszában. Miután létrehozták a pénzügyi dimenziókat és a fő számlákat a rendszerben, ezek a következő oldalakon kerülnek felhasználásra: **Számlastruktúrák konfigurálása**, **Speciális szabálystruktúrák** és **Pénzügyi dimenzió konfigurációja alkalmazások integrálásához**. Az ezeken a lapokon meghatározott rendelés adatbevitelre és felhasználásra szolgál a rendszerben. A rendszer egyes helyein a pénzügyi dimenziók és a fő számlák külön mezőkben jelennek meg. Más helyeken, például naplókban, a pénzügyi dimenziók és a fő számlák egyetlen karakterláncként jelennek meg.

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Gyakorlati tanácsok a pénzügyi dimenziók és a fő számlák beállításához egy jobbról balra író rendszerben

- Amikor bejelöli a számlatükrök elválasztó karakterét, válasszon ki egyet a kettős elválasztási lehetőségek közül: dupla kötőjel (`--`), a dupla sáv (`||`) vagy két pont (`..`) vagy dupla aláhúzás (`\\`).
- Amikor létrehozza a pénzügyi dimenziók és a fő számla értékeit, csak számokat és jobbról balra irányú nyelvi karaktereket használjon.
- Ne használja a számlatükör kiválasztott elválasztó karakterét a pénzügyi dimenzió és a főszámla értékei esetében.

Ha követi ezeket a gyakorlati tanácsokat, azzal segít garantálni a felhasználó által meghatározott sorrend pontos betartását mindenhol a rendszerben..


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
