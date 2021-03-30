---
title: Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok
description: Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó. A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.
author: RichardLuan
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e591007a1330fe11b3f586185f9daca845798908
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218465"
---
# <a name="procurement-and-sourcing-workflows"></a>Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok

[!include [banner](../includes/banner.md)]

Egyes szervezetekben szükséges, hogy a beszerzési igényléseket és beszerzési rendeléseket jóváhagyja egy olyan felhasználó, aki más, mint a tranzakciót rögzítő felhasználó. A jóváhagyási folyamat beállításához munkafolyamatot hozhat létre.

A munkafolyamat egy üzleti folyamatot jelent. Meghatározza, hogy hogyan halad végig egy dokumentum a rendszeren keresztül, és megmutatja, kinek kell elvégznie a feladatot és jóváhagynia a dokumentumot. A munkafolyamat-rendszer használata számos előnnyel jár a szervezeténél:

- **Egységes folyamatok** — Meghatározhatja az egyes dokumentumok jóváhagyási folyamatát, például a beszerzési igénylésekét és költségjelentésekét. A munafolyamat-rendszer segítségével biztosítható, hogy a dokumentumok feldolgozása és jóváhagyása egységes és hatékony módon történjen.
- **A folyamat láthatósága** – Nyomon követheti egy meghatározott munkafolyamat-példány állapotát, előzményeit és teljesítmény metrikáit. Ennek segítségével meghatározhatja, hogy kell-e módosításokat végezni a munkafolyamatban a hatékonyság növelésének érdekében.
- **Központi munkalista** – A felhasználók megtekinthetik a központi munkalistát, hogy lássák a munkafolyamat-feladatokat és jóváhagyásokat, amelyek hozzájuk vannak rendelve, minden olyan munkafolyamat során, amelyben részt vesznek. Ez a Munkatételek lapon érhető el.

## <a name="the-types-of-workflows-that-you-can-create"></a> A létrehozható munkafolyamat-típusok

A következő munkafolyamat-típusok elérhetőek a Beszerzés és forrás modulhoz.

| Típus | Típus |
|---|---|
| Beszerzési igénylés ellenőrzése | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési igénylésekhez. |
| Beszerzési igénylési sor ellenőrzése | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésiigénylés-sorokhoz. |
| Beszerzési rendelés munkafolyamata | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzési rendelésekhez. |
| Beszerzésirendelés-sor munkafolyamata | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása beszerzésirendelés-sorokhoz. |
| Szállítói hozzáadás alkalmazás-munkafolyamata | Ellenőrzési és jóváhagyási munkafolyamatok létrehozása új szállítók hozzáadásához a szállítói kérelmeken keresztül. |

> [!IMPORTANT]
> Új munkafolyamat hozzáadásakor a következő elavult munkafolyamatok is megjelenhetnek a **Munkafolyamat létrehozása** párbeszédpanelen. Ezek a korábban a [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows) szolgáltatásban elérhető *bevételezés megerősítése* funkcióhoz kapcsolódtak, amelyek mostanra elavultak. Ezek a munkafolyamatok jelenleg nem támogatottak.
> 
> - Szállítási határidőkkel kapcsolatos értesítési munkafolyamat
> - A számla megérkezéséről értesítő munkafolyamat
> - A termékbevételezés során sikertelen volt az értesítési munkafolyamat.
> - Visszaigazolatlan termékbevételezés elutasításáról értesítő munkafolyamat

## <a name="creating-a-workflow"></a>Munkafolyamat létrehozása

Hogy létrehozzon egy munkafolyamatot lépjen a Beszerzés és forrás &gt; Beállítás &gt; Beszerzés és forrás munkafolyamatok elemre és hozzon létre egy új munkafolyamatot a készíteni kívánt munkafolyamat-típus kiválasztásával. 

A munkafolyamat vásznon behúzhatja a munkafolyamat elemeket a szerkesztőbe és bekapcsolhatja az elemeket egy folyamatba. A munkafolyamat-elemeket tanácsos konfigurálni. Jóváhagyás– és feladat munkafolyamat-elemekhez konfigurálhatja, hogy melyik résztvevőknek ajánlott cselekedniük.

## <a name="types-of-participants"></a>Résztvevőtípusok

Jóváhagyási lépéseket rendelhet a következő résztvevőcsoportokhoz.

| Felhasználócsoport | Leírás |
|---|---|
| Résztvevő | A jóváhagyási lépés hozzárendelése egy csoport vagy szerepkör tagjaihoz. |
| Hierarchia | A jóváhagyási lépés hozzárendelése egy meghatározott szervezeti hierarchiában lévő felhasználókhoz. |
| Munkafolyamat felhasználója | A jóváhagyási lépés hozzárendelése a munkafolyamatban lévő felhasználókhoz. |
| Várakozási sor | Rendelje hozzá a jóváhagyási lépést egy munkatétel-várólistához. |
| Felhasználó | Jóváhagyási lépés hozzárendelése adott felhasználókhoz. |

## <a name="additional-resources"></a>További erőforrások

- [Üzleti folyamatok munkafolyamatainak meghatározása beszerzési igénylések számára](https://www.microsoft.com/download/details.aspx?id=101821)
- [Beszerzési igénylési munkafolyamat](purchase-requisitions-workflow.md)
- [Szállítók felvétele](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]