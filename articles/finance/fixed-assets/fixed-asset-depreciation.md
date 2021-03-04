---
title: Tárgyi eszközök értékcsökkenése
description: Ez a témakör a tárgyi eszközök értékcsökkenéséről nyújt áttekintést.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1056dadab4294072cc064670f5cfcda239e22e19
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443960"
---
# <a name="fixed-asset-depreciation"></a>Tárgyi eszközök értékcsökkenése

[!include [banner](../includes/banner.md)]

Ez a témakör a tárgyi eszközök értékcsökkenéséről nyújt áttekintést.

Állítson be értékcsökkenést, ami egy ismétlődő tranzakció, és amely a mérlegszámlán csökkenti a tárgyi eszköz értékét, és a csökkenést kiadásként egy eredményszámlára terheli. Ezért általában a fő számla szolgál a mérlegszámla időszakos értékcsökkenése jóváírására. Az Ellenszámla pedig a a számlatükör eredményszámla részébe egy olyan számla.

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