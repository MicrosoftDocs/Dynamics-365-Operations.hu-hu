---
title: Jövőben esedékes csekkek beállítása
description: Ez a témakör bemutatja, hogyan állíthatja be, miként legyenek feladva a jövőben esedékes csekkek naplóbejegyzési, és melyik feladási naplókat kell használni elszámolási tételekhez és szállítói kifizetésekhez.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc1798836d9b905d991adb4c87d55ddce41d260bdbfdad6bf0c4b4feb846ee57
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743073"
---
# <a name="set-up-postdated-checks"></a>Jövőben esedékes csekkek beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthatja be, miként legyenek feladva a jövőben esedékes csekkek naplóbejegyzési, és melyik feladási naplókat kell használni elszámolási tételekhez és szállítói kifizetésekhez. Emellett beállíthat elszámolószámokat a kiállított csekkekhez, a fogadott csekkekhez és az adóelőleghez is. Jövőben esedékes csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítottak ki. Megadhatja, hogy a csekk szerepeljen-e a számviteli könyvekben az esedékesség dátuma előtt.



Ezen eljárás szerepköre: Pénztáros. Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-postdated-checks"></a>Jövőben esedékes csekkek beállítása
1. Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.
2. Kattintson a Jövőben esedékes csekkek fülre.
3. Jelölje be a Jövőben esedékes csekkek jelölőnégyzetet, vagy törölje a jelet a jelölőnégyzetből.
4. Jelölje be, vagy törölje a jelet jelölőnégyzetből a Jövőben esedékes csekkekhez naplóbejegyzések feladása mellett.
5. Az Elszámolási számla a kiállított csekkekhez mezőben adja meg a kívánt értékeket.
6. Az Elszámolási számla a kapott csekkekhez mezőben adja meg a kívánt értékeket.
7. Az Általános napló bejegyzések elszámolásához mezőbe írjon be egy értéket.
8. A Jövőben esedékes csekkek átvezetése ebbe a szállítói kifizetési naplóba mezőbe írjon be egy értéket.
9. Az Adóelőleg-elszámolási számla mezőben adja meg a kívánt értékeket.
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.
12. Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.
13. Kattintson az Új lehetőségre.
14. Írjon be egy értéket a Fizetési mód mezőbe.
15. A Jövőben esedékes csekk elszámolási feladása lehetőség bejelölésével jelezheti, hogy a csekk összege elszámolószámlára lesz feladva.
16. A Fiók típusa mezőben válassza ki a „Bank” lehetőséget.
    * A fizetési módszer ellenszámlájának ellenőrzési módja egy bank lesz.  
17. A Fizetési számla mezőben adja meg a kívánt értékeket.
    * Válassza ki a számlaösszeg levonására szolgáló bankszámlát.  
18. Kattintson a Mentés gombra.
19. Zárja be a lapot.
> [!NOTE]
> Ahhoz, hogy a jövőben esedékes csekkeket fel tudja tenni egy bankszámlára, amikor a munkamenet dátuma az esedékességi dátumnál későbbi vagy azzal megegyező, engedélyeznie kell az **Esedékesség dátumának ellenőrzése a fizetési napló feladásakor későbbre dátumozott csekkekkel bankszámlához** funkciót. Ez a funkció lehetővé teszi, hogy fizetési naplókat adjon fel a jövőben esedékes csekkekkel szállítókhoz vagy vevőkhöz, ha a munkamenet dátuma megegyezik vagy később van, mint az esedékesség dátuma.
> 
> A **Fizetési mód** (**Kötelezettségek > Kifizetés beállítása > Fizetési módok**) beállításakor ne töltse ki az **Áthidaló számlát**. Ebben az esetben az ellenszámla van kitöltve a bankszámlával, amely a **Fizetési módban** van beállítva.
>  
> Ha a funkció engedélyezve van, és a munkamenet dátuma kisebb az esedékesség dátumánál, a fizetési napló feladása során a következő hibaüzenet jelenik meg: "Az esedékességi dátum nem lehet a munkamenet dátumával megegyező vagy korábbi, ha az ellenszámla Bank típusú". Ha a funkció nincs engedélyezve, akkor a jövőben esedékes csekkre vonatkozó fizetési naplót akkor lehet feladni, ha a munkamenet dátuma az esedékességi dátumnál korábbi.
> Ez a funkció elérhető a 10.0.21 vagy újabb verzióban.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
