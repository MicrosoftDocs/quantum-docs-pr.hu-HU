---
title: Broombridge séma specifikációja (0,1-es verzió)
description: A Broombridge Quantum kémia Schema v 0.1 specifikációinak részletei a Microsoft Quantum kémia Library-hez.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0a306f59a823e76ba0518d023a41f1f9d5670e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858196"
---
# <a name="broombridge-specification-v01"></a>Broombridge-specifikáció – v 0.1 #

A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.

A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.

## <a name="introduction"></a>Bevezetés ##

Ez a szakasz tájékoztató jellegű.

A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.

## <a name="serialization"></a>Szerializálás ##

Ez a szakasz a normatív.

Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.
A YAML szerializált objektumnak rendelkeznie kell egy olyan tulajdonsággal `"$schema"` , amelynek az értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` , és a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján érvényesnek kell lennie.

A specifikáció hátralévő részében a "The Broombridge Object" kifejezés a Broombridge YAML-dokumentumból deszerializált JSON-objektumra hivatkozik.

Hacsak másként nincs jelezve, az objektumok nem rendelkezhetnek a jelen dokumentumban explicit módon megadott további tulajdonságokkal.

## <a name="additional-definitions"></a>További definíciók ##

Ez a szakasz a normatív.

### <a name="quantity-objects"></a>Mennyiségi objektumok ###

Ez a szakasz a normatív.

A _mennyiségi objektum_ egy JSON-objektum, és rendelkeznie kell egy olyan tulajdonsággal, `units` amelynek értéke az 1. táblázatban felsorolt engedélyezett értékek egyike.

A mennyiségi objektum egy _egyszerű mennyiségi objektum_ , ha a `value` tulajdonsága mellett egyetlen tulajdonsággal rendelkezik `units` .
A tulajdonság értékének `value` számnak kell lennie.

A mennyiségi objektum egy _körülhatárolt mennyiségi objektum_ , ha a tulajdonságai és a `lower` `upper` tulajdonsága mellett is szerepel `units` .
A és a tulajdonság értékének `lower` `upper` számnak kell lennie.
A kötött mennyiségű objektum rendelkezhet olyan tulajdonsággal `value` , amelynek értéke egy szám.

A mennyiségi objektum egy _ritka tömbben lévő mennyiség objektum_ , ha a tulajdonsága és tulajdonsága mellett egy tulajdonság is szerepel `format` `values` `units` .
A értékének `format` a karakterláncnak kell lennie `sparse` .
A tulajdonság értékének `values` tömbnek kell lennie.
Minden elemnek `values` olyan tömbnek kell lennie, amely a ritka tömb mennyiségének indexeit és értékét jelöli.

A ritka tömb mennyiségi objektumának minden eleméhez egyedi indexeket kell megadni a teljes ritka tömb mennyiségi objektumán.
Ha egy index a értékkel van megadva `0` , az elemzőnek a ritka tömb mennyiségi objektumát azonos módon kell kezelnie egy olyan ritka tömbbeli mennyiség objektummal, amelyben az index egyáltalán nem szerepel.


Egy mennyiségi objektumnak a következők egyikének kell lennie

- egy egyszerű mennyiségi objektum,
- egy kötött mennyiségi objektum, vagy
- egy ritka tömb mennyiségi objektuma.


### <a name="examples"></a>Példák ###

Ez a szakasz tájékoztató jellegű.

Egy egyszerű mennyiség, amely A $1.9844146837 \Mathrm{ha} $ értéket jelöli \, :

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Egy kötött mennyiség, amely egységes eloszlást jelképez a $ [-7,-6] \, \mathrm{ha} $ intervallumban:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Az alábbiakban egy olyan ritka tömbbeli mennyiség szerepel, amelynek a eleme egyenlő a következővel `[1, 2]` `hello` `[3, 4]` `world` :

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Formázási szakasz ##

Ez a szakasz a normatív.

A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie `format` , amelynek értéke egy nevű JSON-objektum `version` .
A `version` tulajdonságnak értékkel kell rendelkeznie `"0.1"` .

### <a name="example"></a>Példa ###

Ez a szakasz tájékoztató jellegű.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Beépített készletek szakasz ##

Ez a szakasz a normatív.

A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie `integral_sets` , amelynek értéke JSON-tömb.
A tulajdonság értékének minden elemének `integral_sets` egy olyan JSON-objektumnak kell lennie, amely a szakasz hátralévő részében leírtak szerint egy egységes készletet ismertet.
A szakasz hátralévő részében az "integrált készlet objektum" kifejezés a `integral_sets` Broombridge objektum tulajdonságának értékében található elemre hivatkozik.

Minden szerves set objektumnak olyan tulajdonsággal kell rendelkeznie `metadata` , amelynek értéke JSON-objektum.
Az értéke lehet `metadata` az üres JSON-objektum (azaz `{}` ), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.

### <a name="hamiltonian-section"></a>Hamilton szakasz ###

#### <a name="overview"></a>Áttekintés ####

Ez a szakasz tájékoztató jellegű.

Az `hamiltonian` egyes beépített objektumok tulajdonsága egy adott Quantum kémiával kapcsolatos probléma Hamilton írja le azáltal, hogy az egy-és kéttörzsű kifejezéseket a valós számok ritka számaként sorolja fel.
Az egyes integrált Hamilton-kezelők a következő űrlapot írják be:

$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} h \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $

Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.

Az egyértelműség érdekében az egyelektronos kifejezés a következő:

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ * \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ A} {| x-x \_ A |}  \right) \psi \_ j (x), $ $

a két elektron kifejezés pedig

$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).
$$

Ahogy [ `basis_set` az a](#basis-set-object) tulajdonság egyes elemeinek leírásában is `integral_sets` látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.
Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Tartalom ####

Ez a szakasz a normatív.

Minden szerves készletnek rendelkeznie kell egy olyan tulajdonsággal `hamiltonian` , amelynek értéke JSON-objektum.
A `hamiltonian` tulajdonság értéke Hamilton objektum, és a `one_electron_integrals` `two_electron_integrals` szakasz hátralévő részében ISMERTETett tulajdonságokkal kell rendelkeznie.
Egy Hamilton objektum is rendelkezhet tulajdonsággal `particle_hole_representation` .
Ha van, akkor a értékének a `particle_hole_representation` szakasz hátralévő részében ismertetett formátumot kell követnie.

##### <a name="one-electron-integrals-object"></a>One-Electron szerves objektum #####

Ez a szakasz a normatív.

A `one_electron_integrals` Hamilton objektum tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.
Minden kifejezésnek tartalmaznia kell indexekkel, `[i, j]` ahol `i >= j` .

> Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.


###### <a name="example"></a>Példa ######

Ez a szakasz tájékoztató jellegű.

A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> A Broombridge 1 alapú indexelést használ.


##### <a name="two-electron-integrals-object"></a>Two-Electron szerves objektum #####

Ez a szakasz a normatív.

A `two_electron_integrals` Hamilton objektum tulajdonságának olyan ritka tömb mennyiségnek kell lennie, amely egy további nevű tulajdonsággal rendelkezik `index_convention` .
A értékének minden elemének `two_electron_integrals` négy indextel kell rendelkeznie.

Minden `two_electron_integrals` tulajdonságnak RENDELKEZNIE kell `index_convention` tulajdonsággal.
A tulajdonság értékének az `index_convention` 1. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.
Ha a értéke `index_convention` `mulliken` , akkor a `two_electron_integrals` ritka tömb mennyiségének minden eleme esetében egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton-kifejezést kell létrehoznia, amely a kételektronos operátorral egyenlő $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, ahol a $i $, $j $, $k $ és $l $ értéknek egész számnak kell lennie a befogadó tartomány 1 és a szerves készlet objektum tulajdonsága által meghatározott elektronok számával `n_electrons` , és ahol $h _ {i, j, k, l} $ a `[i, j, k, l, h(i, j, k, l)]` ritka tömb mennyiségének eleme.

###### <a name="symmetries"></a>Symmetries ######

Ez a szakasz a normatív.

Ha `index_convention` egy objektum tulajdonsága `two_electron_integrals` egyenlő `mulliken` , akkor ha az indexekkel rendelkező elem szerepel `[i, j, k, l]` , a következő indexek nem lehetnek jelen, kivéve, ha egyenlőek `[i, j, k, l]` :

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Mivel a `index_convention` tulajdonság egy ritka mennyiségű objektum, a különböző elemeken nem lehet megismételni az indexeket.
> Ha az indexekkel rendelkező elemek `[i, j, k, l]` jelen vannak, akkor előfordulhat, hogy nincs más elem az indexekkel.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Példa #######

Ez a szakasz tájékoztató jellegű.

A következő objektum határozza meg a Hamilton

$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} { \_ 6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} {1, \sigma} a ^ \_ {\dagger} { \_ 6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a>Részecske – Hole reprezentációs objektum #####

Ez a szakasz a normatív.

A részecske – Hole reprezentációs objektum azt adja meg, hogy a tárolt szerves adatok meghatározása a részecske-furatokra vonatkozik, amelyekben a létrehozási és a megsemmisítési operátorok leírják a használt hivatkozási állapottól, például a Hartree – Fock állapottal kapcsolatos izgalomokat.
Az objektum nem kötelező.
Ha az objektum nincs megadva, a Hamilton úgy kell értelmezni, hogy a rendszer ne adja meg a részecske-furatos ábrázolásban.
Ha van, akkor a értékének `particle_hole_representation` olyan ritka tömbbeli mennyiség típusú objektumnak kell lennie, amelynek indexei négy egész szám, és amelynek értéke egy szám és egy sztring.
Az egyes elemek értékének karakterlánc-részének csak a karaktereket kell tartalmaznia `'+'` , `'-'` amely meghatározza, hogy a kifejezésben megadott tényező egy létrehozási vagy megsemmisülési operátor a részecske – Hole ábrázolásban.  Például `"-+++"` egy, a (z) $i $ helyen létrehozott lyukra válaszol, és a (z) $j, k $ és $l $ helyen létrehozott részecskéket hozza létre.

> [!NOTE]
> Mivel a `particle_hole_representation` egy ritka tömbbeli mennyiség objektum értéke, `unit` meg kell adni a és a `format` tulajdonságokat.
> Az elfogadható egységeket az 1. táblázat tartalmazza.
> A `format` tulajdonság megadása kötelező, és azt jelzi, hogy a Hamilton-együtthatók egy sűrű vagy ritka tömbként vannak-e megadva.
> A jelenlegi verzióban csak a ritka tömbök támogatottak, és az értelmezés szerint az összes meghatározatlan elem $0 $, a későbbi verziók azonban a tulajdonság további értékeihez is hozzáadhatnak támogatást `format` .

### <a name="initial-state-section"></a>Kezdeti állapot szakasz ###

A initial_state_suggestion objektum a megadott Hamilton tartozó kezdeti kvantum-állapotokat határozza meg. Az objektumnak JSON-objektumok tömbje kell, hogy legyen `state` .

#### <a name="state-object"></a>Állapot objektum ####

Az egyes állapotok a megszállt pályák felhelyezését jelentik. Minden állapot objektumnak tartalmaznia kell egy `label` sztringet tartalmazó tulajdonságot. Minden állapot objektumnak rendelkeznie kell egy olyan `superposition` tulajdonsággal, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.

Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0.2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ a következőt képviseli:
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a>Alapul szolgáló set objektum ####

Ez a szakasz a normatív.

Az egyes szerves set objektumok rendelkezhetnek `basis_set` tulajdonsággal.
Ha van ilyen, a tulajdonság értékének `basis_set` két tulajdonsággal rendelkező objektumnak kell lennie, `type` és `name` .

A tulajdonság értékével azonosított alap függvényeknek `basis_set` valós értékűnek kell lenniük.

> [!NOTE]
> Ennek a specifikációnak a jövőbeli verzióiban a teljes körű függvények valós értékűek lehetnek.

## <a name="tables-and-lists"></a>Táblák és felsorolások ##

### <a name="table-1-allowed-physical-units"></a>1. táblázat Engedélyezett fizikai egységek ###

Ez a szakasz a normatív.

Az egységet megadó összes sztringnek a következők egyikének kell lennie:

- `hartree`
- `ev`

Az elemzőknek és a termelőknek egyenértékűnek kell lenniük a következő egyszerű mennyiségi objektumokkal:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>2. táblázat Engedélyezett indexelési konvenciók ###

Ez a szakasz a normatív.

A tárgymutató-konvenciót megadó összes karakterláncnak a következők egyikének kell lennie:

- `mulliken`

Ez a szakasz tájékoztató jellegű.

A specifikáció későbbi verzióiban további indexelési konvenciók is bevezethetők.

#### <a name="interpretation-of-index-conventions"></a>Az index konvencióinak értelmezése ####

Ez a szakasz tájékoztató jellegű.
