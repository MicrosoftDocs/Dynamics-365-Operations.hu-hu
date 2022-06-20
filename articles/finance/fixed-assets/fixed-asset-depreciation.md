---
title: Tárgyi eszközök értékcsökkenése
description: Ez a cikk a tárgyi eszközök értékcsökkenésének áttekintését nyújt.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4fedee481b4066c81671cf1fca3781c8c75aaeb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874523"
---
# <a name="fixed-asset-depreciation"></a>Tárgyi eszközök értékcsökkenése

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk a tárgyi eszközök értékcsökkenésének áttekintését nyújt.

Állítson be értékcsökkenést, ami egy ismétlődő tranzakció, és amely a mérlegszámlán csökkenti a tárgyi eszköz értékét, és a csökkenést kiadásként egy eredményszámlára terheli. Ezért általában a fő számla szolgál a mérlegszámla időszakos értékcsökkenése jóváírására. Az Ellenszámla pedig a a számlatükör eredményszámla részébe egy olyan számla.

A 10.0.24-es **·** **verziónak** megfelelő Könyvoldal pozitív értékcsökkenés könyv szerinti konfigurációjának használata esetén az értékcsökkenés a negatív könyv szerinti értékkel (követel) rendelkező tárgyi eszközök terhelését teszi lehetővé.

## <a name="depreciation-adjustment"></a>Értékcsökkenés helyesbítése
Általában csak egy már feladott értékcsökkenési tranzakció helyesbítése adható fel úgy, mint az. A fő számla és az ellenszámla beállításai így megegyeznek az értékcsökkenés számláival. Az értékcsökkenési kiigazítás pozitív és negatív összeg is lehet, de a fő számla (mint mérlegszámla) és az ellenszámla (általában mint eredményszámla) működése nem változik.

## <a name="extraordinary-depreciation"></a>Rendkívüli értékcsökkenés
A rendkívüli értékcsökkenés rendes értékcsökkenésként működik. Ebben az esetben a fő számla használatos az értékcsökkenési összeg mérlegszámlára történő jóváírására és a tárgyi eszköz értékének csökkentésére. Egy Ellenszámla típusú számlájára egy eredményszámla, ahol a pénzügyi időszakra kiszámított értékcsökkenés kiadásként. 

A Rendkívüli értékcsökkenés a rendes értékcsökkenéstől függetlenül működik. A külön tranzakciótípusnak számító különleges értékcsökkenés lehetővé teszi, hogy a rendes értékcsökkenésen kívül rendkívüli értékcsökkenést is feladhasson és jelenthessen.

## <a name="special-depreciation-allowance"></a>Különleges értékcsökkenési keret
A különleges értékcsökkenési keret segítségével különleges értékcsökkenési összegeket alkalmazhat egy eszköz üzembe helyezésének és értékcsökkenésének első évében. A különleges értékcsökkenési keretet a többi értékcsökkenési számítás előtt kell végrehajtani. Mivel a különleges értékcsökkenési keretek gyakran ismeretlenek a tárgyi eszköz élettartamának későbbi időpontjáig, célszerű ezt a típust nem a főkönyvbe feladott könyvvel használni. Használhatja a Főkönyvbe fel nem adott tranzakciók törlése időszakos funkciót ezen könyvek előzménytranzakcióinak törléséhez. Törölheti a tárgyieszköz-könyv értékcsökkenési előzményeit, feladhatja a különleges értékcsökkenési keretet (amikor ismert), valamint feladhatja az adott évre fennmaradó értékcsökkenési tranzakciókat. 

A létrehozható különleges értékcsökkenési keretekre vonatkozó rekordok száma korlátlan. Miután egy eszközcsoport könyvéhez társította a rekordokat, a program alkalmazza őket az eszköz könyvére. 

A különleges értékcsökkenési keretet százalékként vagy rögzített összegként kell megadni. Ha értékcsökkenési javaslatot ad fel, akkor a program az értékcsökkenés tranzakcióitól különálló tranzakciókként adja fel a különleges értékcsökkenési keret tranzakcióit a könyvbe.

## <a name="depreciation-calendars"></a> Értékcsökkenési naptárak
Mindegyik könyvhöz tartozik egy, a tárgyi eszközök értékcsökkenésénél használt naptár. A könyv a főkönyvi pénzügyi naptárat fogja használni alapértelmezés szerint, ha nem ad meg naptárat. Ha a könyvhöz kapcsolt értékcsökkenési profil pénzügyi értékcsökkenési évet használ, ki kell választani egy pénzügyi naptárat a könyvhöz. 

A Főkönyvben a **Pénzügyi naptárak** lapon megosztott naptárakat hozhat létre.

További tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](depreciation-methods-conventions.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
