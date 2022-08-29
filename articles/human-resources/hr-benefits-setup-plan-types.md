---
title: Tervtípus áttekintése
description: A konstrukciótípus a Microsoft Dynamics 365 Human Resources alkalmazásban a meghatározott típusú juttatások magas szintű csoportosítása.
author: twheeloc
ms.date: 08/24/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6ca14156c165ca3f536fc0120ebd03883284eb18
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337305"
---
# <a name="plan-type-overview"></a>Tervtípus áttekintése

[!include [banner](../includes/preview-banner.md)]

A konstrukciótípus a meghatározott típusú juttatások magas szintű csoportosítása. Minden konstrukciótípusnak van egy terv konstrukciótípus-kódja, amely meghatározza a konstrukció típusának szabályait. Például az **Alapélettartam** konstrukciótípushoz az **Élettartam** konstrukciótípus-kód lesz szükséges, mivel ez egyfajta életbiztosítás típusú konstrukció, amelyeknek meg kell felelniük az **Élettartam** konstrukciótípus-kódhoz meghatározott szabályoknak. Egy másik tervtípus lehet **Kiegészítő élettartam**. Ennek a tervtípusnak is **Élet** terv típuskódja lesz.

Mindegyik konstrukciótípus jelzi, hogy egy alkalmazott regisztrálhat-e egy vagy több ilyen típusú konstrukcióra. Például egy alkalmazott valószínűleg képes regisztrálni az **Alapélettartam** és a **Kiegészítő élettartam** biztosításokra az Élettartam konstrukciótípusból. Egy alkalmazott valószínűleg csak egy Orvosi típusú biztosításra regisztrálhat.

Ha egy konstukciótípus kapcsolattartókat tartalmaz, akkor a konstrukciótípus jelzi, hogy a kapcsolattartók kedvezményezettek vagy függő felek-e. Például egy **Alapélettartam** konstrukciótípushoz tartozhatnak kedvezményezettek, míg egy Alap orvosi konstukciótípushoz csak függő felek tartozhatnak. Bizonyos esetekben előfordulhat, hogy egy konstrukció nem rendelkezik személyes kapcsolattartókkal. Például egy Rugalmas kiadási számla vagy Parkolási támogatás.


A konstrukciótípus meghatározhatja a fedezeti beállításokat. A fedezeti opciókat a **Fedezeti opciók** lapon lehet meghatározni. A fedezeti beállítások határozzák meg a juttatás összegét, illetve azokat a kapcsolattartókat, akik jogosultak a konstrukciótípusra. Ha például a kapcsolattartó típusa **Kedvezményezett**, a fedezeti beállításnak meg kell határoznia, hogy a kedvezményezett milyen feltételekkel kaphat juttatást annak igénybevétele esetén. Ha a kapcsolattartó típusa **Függő fél**, a fedezeti beállításnak meg kell határoznia a függő fél és az alkalmazott közötti kapcsolatot. 

> [!IMPORTANT]
> A **Konstrukciótípusok** oldal olyan kulcsfontosságú adatokat tartalmaz, amelyek befolyásolják az új juttatási terv létrehozásakor rendelkezésre álló lehetőségeket:
>
> - **Terv típuskódja** – ez a mező azt befolyásolja, hogy mi jelenik meg a **Konfiguráció** lapon a tényleges juttatás beállításakor.  
> - **Párhuzamos regisztráció** – ez a mező határozza meg, hogy engedélyezve van-e több regisztráció. (Egy egészségügyi konstrukciónál ez a mező jellemzően a **Egy beléptetés**.)
> - **Kapcsolattartó típusa** – ez a mező lehetővé teszi, hogy eltartottak vagy kedvezményezettek hozzáadását a tervhez. Ha a beállítás **Nincs**, a juttatásokra jogosult alkalmazottak nem választhatják ki a kedvezményezettet vagy az eltartottat.
> - **Fedezeti beállítások** – ezzel a mezővel kapcsolhatják a fedezeti beállításokat a konstrukciótípusokhoz. Meghatározza, hogy az adott tervtípusban kinek legyen fedezete vagy azokat a fedezeti összegeket, amelyek erre a tervtípusra rendelkezésre állnak. Megadhatja például, hogy egy egészségügyi tervtípus fedezete csak az alkalmazott, az alkalmazott és egy másik személy, illetve az alkalmazott és a családja számára legyen elérhető.

## <a name="create-plan-types"></a>Költségvetési terv típusai

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Konstrukciótípusok** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció típusa** | A konstrukciótípust azonosító egyedi név. |
   | **Leírás** | A konstrukciótípus leírása. |
   | **Konstrukció típuskódja** | Válasszon egy konstrukciótípus-kódot az értékek legördülő listájából. A konstrukciótípus-kód listája megjeleníti az aktuális verzióban támogatott összes konstrukciótípust. |
   | **Párhuzamos regisztráció** | Megadja, hogy az alkalmazott több ugyanolyan konstrukciótípusú juttatási konstrukciót is regisztrálhat-e, vagy csak egy juttatási konstrukciót konstrukciótípusonként. |
   | **Névjegy típusa** | Megadja a személyes kapcsolattartó szerepét. Az érték üres, Függő fél és Kedvezményezett lehet. A **Kapcsolattartó típusa** elemet üresen hagyhatja, ha a konstrukciótípus nem igényel függő felet vagy kedvezményezettet a fedezeti beállítás alapján. |

4. Az élettartam-esemény beállításainak konfigurálásához válassza ki a **Műveletek** elemet, majd az **Élettartam-esemény beállításai** lehetőséget. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció típusa** | A konstrukciótípus, amely számára az élettartam-esemény beállításait konfigurálni kell. |
   | **Életesemény-típus azonosítója** | A élettartam-esemény típusának azonosítója. |
   | **Fedezeti beállítás módosítása** | Megadja, hogy az alkalmazott módosíthatja-e a fedezeti beállításokat az élettartam-esemény során. |
   | **Váltás új konstrukcióra** | Megadja, hogy az alkalmazott módosíthatja-e a konstrukciókat az élettartam-esemény során. |
   | **Jogosultsági ellenőrzés automatikus újranyitása** | Megadja, hogy a rendszer automatikusan nyissa-e újra a juttatási regisztrációra való jogosultsági ellenőrzése az életesemény során. |
   | **Életciklus-esemény beléptetési időszaka** | Megadja az életeseménnyel kapcsolatos jelentéskészítés időtartamát napokban. **Megjegyzés**: Ha nem ad meg összeget, akkor a rendszer nulla értékre állítja a jelentési ablakot, és nem dolgozza fel az élettartam-eseményt. |
   | **Csak a rendszergazdák szerkeszthetik** | Meghatározza, hogy az adminisztrátorok visszavonhatják vagy szerkeszthetik-e a terveket az élettartam eseménye során. Az alkalmazott nem tud változtatást eszközbe tenni **az alkalmazott önkiszolgáló munkaterületén**. |
   | **Konstrukció automatikus megszakítása** | Megadja, hogy egy élettartam eseménye esetén a terv automatikusan érvénytelenül törlődik-e. Az életesemény változásainak feldolgozása után az Automatikus **terv** visszavonása beállítás megtartja a tervkiválasztást. A rendszer csak **a Visszaigazolt** **vagy** a Kivett állapotot távolítja el. A terv továbbra is ki van választva. Emiatt azok az alkalmazottak, akik az élettartam esemény beléptetési időszaka alatt nem adnak meg tervkiválasztást, nem fogják elveszni a tervkiválasztást. 

5. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
