---
title: Beszedési folyamat automatizálási paramétereinek konfigurálása
description: Ez a témakör leírja az automatizált beszedési folyamatokat befolyásoló paramétereket, és útmutatást ad a beállításukhoz, hogy az automatizált folyamat megfeleljen a szándékokainak és a várakozásainak.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e7a7e048a371fc90456368206b91c29c4b1264d5
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734396"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Beszedési folyamat automatizálási paramétereinek konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör leírja az automatizált beszedési folyamatokat befolyásoló paramétereket, és útmutatást ad a beállításukhoz, hogy az automatizált folyamat megfeleljen a szándékokainak és a várakozásainak. A beszedési folyamatok automatizálásával kapcsolatos további tudnivalókat lásd: [Beszedési folyamat automatizálása](collections-process-automate.md).

## <a name="general"></a>Általános
Adjon meg egy számot az **Ügyfelek százaléka kötegelt feladatonként** helyen a kötegelt feladatok automatizálási folyamatonkénti számának meghatározásához. A **Fizetési felszólítások automatikus közzététele** beállítása legyen **Igen**, így a fizetési felszólítás művelettípusa az automatizálás során feladja a levelet. A **Tevékenységek automatikus létrehozása** elemet állítsa **Igen** beállításra a nem tevékenység művelettípusok létrehozásához és lezárásához, hogy megtekinthesse az összes, a fiókon végzett automatizálási lépést. Adja meg, hogy hány napig tárolja a rendszer a beszedési előzményeket a **A beszedési folyamatok automatizálása megtartása ennyi napig** helyen. Amikor egy számla eléri a beszedési folyamat utolsó lépését, a rendszer nem fogja használni a jövőbeli folyamatautomatizálási művelettípusok létrehozására, ha a **Számla kizárása az utolsó folyamatlépés aktiválása után** beállítása **Igen**. A következő legrégebbi számla meghatározza a következő folyamatautomatizálási lépést, hogy a beszedési folyamat automatizálási művelete folytatódjon. 

## <a name="payment-predictions"></a>Fizetési előrejelzések
A 10.0.21-es verziótól kezdve a Vevői kifizetések előrejelzései, a Finance Insights projektekben, amelyek azt jelzik, hogy a számlát időben, késve vagy nagyon késve fizetik-e ki. Ezeket a kategóriákat a Finance Insights alkalmazásban konfigurálhatja. Ha az előrejelzések szerint a számlák késve lesznek kifizetve, fontos, hogy a számla esedékessége előtt a beszedési folyamatot elindítani. Ezek az előrejelzések a beszedési tevékenységek létrehozására használhatók a Beszedési folyamatok automatizálásának futtatásakor. Állítsa a **Vevői fizetési előrejelzések engedélyezése** **Igen** értékre fizetési előrejelzések használatához beszedési tevékenységek létrehozásához, annak a valószínűsége alapján, hogy a számlát később fizetik ki. 

A vevői kifizetés előrejelzésekkel és a Finance Insights alkalmazással kapcsolatosan a [Vevői kifizetések előrejelzése](payment-insights-overview.md) nyújt további tájékoztatást.

A vevői fizetési előrejelzések futtatásakor hozzárendel egy százalékértéket az időbeni, késedelmesen vagy nagyon késve történő kifizetéshez. Ezeket az információkat felhasználhatja a beszedési tevékenységek automatikus indításához a Beszedési folyamat automatizálása segítségével, ha késedelmes fizetés várható. Ezeket a százalékokat a **Kifizetések előrejelzése vevőnként** vagy a **Kifizetések előrejelzése tranzakcióoldalanként** oldalakon tekintheti meg a **Követelések és beszedések > Beszedések** alatt. 

Ha a vevői számlára vonatkozó átlagos fizetési előrejelzés kisebb, mint a külső viszonyítási alap százalékos értéke, nem jön létre tevékenység. Ha a vevői számlára vonatkozó átlagos fizetési előrejelzés nagyobb vagy egyenlő, mint a külső viszonyítási alap százalékos értéke, egy tevékenység jön létre ügyfelenként. Az **Előrejelzés: Késés** elemnél adja meg, a **Külső viszonyítási alap százalékértékét**, hogy a beszedési folyamat automatizálása mikor hozzon létre beszedési tevékenységeket. Ez a késedelmes és a nagyon késedelmes összesített értéke. Válassza ki a létrehozott tevékenységhez használni kívánt **Üzletidokumentum-sablont**, vagy hozzon létre egy újat. Ez azonosítja a **Típust**, a **Célt** és a **Tevékenység fennmaradásáért fennmaradó napokat**. Beírhat bármilyen **Megjegyzést**, amelyek a tevékenység létrehozásakor alapértelmezett leírásként fognak megjelenni. Az **Előrejelzés: Nagyon késedelmes** elemnél adja meg, a **Külső viszonyítási alap százalékértékét**, hogy a beszedési folyamat automatizálása mikor hozzon létre beszedési tevékenységeket, amikor az előrejelzés szerint az ügyfél nagyon késedelmesen fizeti a számlát. Válassza ki a létrehozott tevékenységhez használni kívánt **Üzletidokumentum-sablont**. Ez azonosítja a **Típust**, a **Célt** és a **Tevékenység fennmaradásáért fennmaradó napokat**. Beírhat bármilyen **Megjegyzést**, amelyek a tevékenység létrehozásakor alapértelmezett leírásként fognak megjelenni. 

### <a name="example"></a>Példa
Ha a késedelem viszonyítási alapjának százalékos értéke 60%. A vevői fizetési előrejelzések futtatásakor az egyes számlákhoz a rendszer hozzárendel egy százalékértéket az időbeni, késedelmesen vagy nagyon késve történő kifizetéshez. Ha a számla késedelmes kifizetésének fizetési előrejelzése 59% vagy annál kevesebb, akkor az automatikus beszedési folyamat nem hoz létre beszedési tevékenységet a számlához. Ha egy számla vevői fizetési előrejelzése 60%-nál nagyobb vagy azzal egyenlő, akkor a beszedési folyamat automatizálása során létrejön egy beszedési tevékenység. 

> [!NOTE]
> A nagyon késedelmes előrejelzést a program a késedelmes előrejelzése előtt értékeli ki, mivel a nagyon késedelmes olyan számlákat is tartalmaz, amelyek várható kifizetése késedelmes lesz. A beszedési folyamat csak akkor generál egy tevékenységet, ha a számla a késedelmes és nagyon késedelmes viszonyítási alapra is esik. Ebben az esetben a rendszer a nagyon késedelmes tevékenységeket és üzleti dokumentumokat használja, mivel a nagyon késedelmes elemek prioritása magasabb. A már létrehozott egyéb műveleteket nem generálja második alkalommal a rendszer.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
