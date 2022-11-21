---
title: Jövőben esedékes csekkek beállítása
description: Ez a cikk bemutatja, hogy fel kell-e adni a jövőben esedékes csekkek naplóbejegyzését, és hogy mely feladási naplókat kell használni a bejegyzések és a szállítói kifizetések elszámolására.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7172dd56113de23d841fe59ed9785471e90ed1f
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779609"
---
# <a name="set-up-postdated-checks"></a>Jövőben esedékes csekkek beállítása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogy fel kell-e adni a jövőben esedékes csekkek naplóbejegyzését, és hogy mely feladási naplókat kell használni a bejegyzések és a szállítói kifizetések elszámolására. Emellett beállíthat elszámolószámokat a kiállított csekkekhez, a fogadott csekkekhez és az adóelőleghez is. Jövőben esedékes csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítottak ki. Megadhatja, hogy a csekk szerepeljen-e a számviteli könyvekben az esedékesség dátuma előtt.



Ezen eljárás szerepköre: Pénztáros. Ez az eljárás az USMF bemutatócéget használja.


## <a name="set-up-postdated-checks"></a>Jövőben esedékes csekkek beállítása
1. A Készpénz- **és bankkezelés > beállítása > készpénz- és bankkezelési paraméterekhez**.
2. Kattintson a **Jövőben esedékes csekkek fülre**.
3. Jelölje be a Jövőben esedékes **csekkek engedélyezése jelölőnégyzetet, vagy törölje a** jelölést a jelölőnégyzetből.
4. Jelölje be a Naplóbejegyzések **feladása jelölőnégyzetet, vagy törölje a** jelölést a jövőben esedékes csekkek jelölőnégyzetből.
5. Adja meg **a kívánt értékeket az Elszámolószámla kiadott** csekkek mezőjében.
6. A kapott **csekkek elszámoló számláján** adja meg a kívánt értékeket.
7. A Főkönyvi **napló mezőben** adjon meg egy értéket.
8. Írjon be **egy értéket a Jövőben esedékes csekkek átvitele ebbe a szállítói** kifizetési naplóba mezőbe.
9. Adja meg **a kívánt értékeket az Adóelőleg-elszámolási** számla mezőben.
10. Kattintson a **Mentés** gombra.
11. Zárja be a lapot.
12. Ugrás a **Kötelezettségek > fizetési > fizetési módok beállításához**.
13. Kattintson az **Új** elemre.
14. Írjon be egy értéket a **Fizetési mód** mezőbe.
15. A jövőben esedékes **csekk elszámolási feladási beállításának** kiválasztásával jelezheti, hogy a csekk összege elszámoló számlára lett feladva.
16. A Számlatípus **mezőben** válassza a **Bank lehetőséget**.
    * A fizetési módszer ellenszámlájának ellenőrzési módja egy bank lesz.  
17. A Kifizetés **számla mezőjében** adja meg a kívánt értékeket.
    * Válassza ki a számlaösszeg levonására szolgáló bankszámlát.  
18. Kattintson a **Mentés** gombra.
19. Zárja be a lapot.
> [!NOTE]
> Ahhoz, hogy a jövőben esedékes csekkeket fel tudja tenni egy bankszámlára, amikor a munkamenet dátuma az esedékességi dátumnál későbbi vagy azzal megegyező, engedélyeznie kell az **Esedékesség dátumának ellenőrzése a fizetési napló feladásakor későbbre dátumozott csekkekkel bankszámlához** funkciót. Ez a funkció lehetővé teszi, hogy fizetési naplókat adjon fel a jövőben esedékes csekkekkel szállítókhoz vagy vevőkhöz, ha a munkamenet dátuma megegyezik vagy később van, mint az esedékesség dátuma.
> 
> A fizetési mód **beállításakor** (**kötelezettségek > fizetési** > beállításakor ne **töltse ki az áthidaló számlát**). Ebben az esetben az ellenszámla van kitöltve a bankszámlával, amely a **Fizetési módban** van beállítva.
>  
> Ha a funkció engedélyezve van, és a munkamenet dátuma kisebb az esedékesség dátumán, a fizetési napló feladása során a következő hibaüzenet jelenik meg, ha az esedékesség dátuma bank típusú, **vagy** a munkamenet dátumának meg kell egyednie vele. Ha a funkció nincs engedélyezve, akkor a jövőben esedékes csekkre vonatkozó fizetési naplót akkor lehet feladni, ha a munkamenet dátuma az esedékességi dátumnál korábbi.
> Ez a funkció elérhető a 10.0.21 vagy újabb verzióban.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
