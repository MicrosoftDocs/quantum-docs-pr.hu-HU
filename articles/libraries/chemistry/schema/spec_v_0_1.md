---
title: Broombridge séma specifikációja
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185358"
---
# <a name="broombridge-specification-v01"></a>Broombridge-specifikáció – v 0.1 #

A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.

A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.

## <a name="introduction"></a>Introduction (Bevezetés) ##

Ez a szakasz tájékoztató jellegű.

A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.

## <a name="serialization"></a>Szerializálási ##

Ez a szakasz a normatív.

Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.
A YAML szerializált objektumnak olyan tulajdonsággal kell rendelkeznie, `"$schema"` amelynek értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, és érvényesnek kell lennie a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján.

A specifikáció hátralévő részében a "The Broombridge Object" kifejezés a Broombridge YAML-dokumentumból deszerializált JSON-objektumra hivatkozik.

Hacsak másként nincs jelezve, az objektumok nem rendelkezhetnek a jelen dokumentumban explicit módon megadott további tulajdonságokkal.

## <a name="additional-definitions"></a>További definíciók ##

Ez a szakasz a normatív.

### <a name="quantity-objects"></a>Mennyiségi objektumok ###

Ez a szakasz a normatív.

A _mennyiségi objektum_ egy JSON-objektum, és rendelkeznie kell egy tulajdonsággal `units` amelynek értéke az 1. táblázatban felsorolt engedélyezett értékek egyike.

A mennyiségi objektum egy _egyszerű mennyiségi objektum_ , ha a `units` tulajdonságán felül egyetlen tulajdonság `value` van.
A `value` tulajdonság értékének számnak kell lennie.

A mennyiségi objektum egy _körülhatárolt mennyiségi objektum_ , ha a tulajdonsága `lower` és `upper` a `units` tulajdonság mellett.
A `lower` és az `upper` tulajdonság értékének számnak kell lennie.
A kötött mennyiség objektum rendelkezhet olyan tulajdonsággal, `value` amelynek értéke egy szám.

A mennyiségi objektum egy _ritka tömbbeli mennyiségű objektum_ , ha a tulajdonsága `format` és egy tulajdonság `values` a `units` tulajdonságán felül.
`format` értékének a karakterláncnak `sparse`nak kell lennie.
A `values` tulajdonság értékének tömbnek kell lennie.
`values` minden elemének olyan tömbnek kell lennie, amely a ritka tömb mennyiségének indexeit és értékét jelöli.

A ritka tömb mennyiségi objektumának minden eleméhez egyedi indexeket kell megadni a teljes ritka tömb mennyiségi objektumán.
Ha egy index `0`értékkel rendelkezik, akkor az elemzőnek a ritka tömb mennyiségi objektumát azonos módon kell kezelnie egy olyan ritka tömbbeli mennyiség objektummal, amelyben az index egyáltalán nem szerepel.


Egy mennyiségi objektumnak a következők egyikének kell lennie

- egy egyszerű mennyiségi objektum,
- egy kötött mennyiségi objektum, vagy
- egy ritka tömb mennyiségi objektuma.


### <a name="examples"></a>Példák ###

Ez a szakasz tájékoztató jellegű.

Egy egyszerű mennyiség, amely A $1.9844146837\,\mathrm{Ha} $ értéket jelöli:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Egy kötött mennyiség, amely egységes eloszlást képvisel a $ [-7,-6]\,\mathrm{Ha} $ intervallumban:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Az alábbiakban egy olyan ritka tömbbeli mennyiség szerepel, amely `[1, 2]` egyenlő `hello` és egy elem `[3, 4]` `world`:

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

A Broombridge objektumnak olyan tulajdonsággal kell rendelkeznie, `format` amelynek értéke egy `version`nevű tulajdonságú JSON-objektum.
A `version` tulajdonságnak `"0.1"`értékűnek kell lennie.

### <a name="example"></a>Példa ###

Ez a szakasz tájékoztató jellegű.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Beépített készletek szakasz ##

Ez a szakasz a normatív.

A Broombridge objektumnak rendelkeznie kell egy olyan tulajdonsággal, `integral_sets` amelynek értéke JSON-tömb.
A `integral_sets` tulajdonság értékében szereplő összes elemnek egy olyan JSON-objektumnak kell lennie, amely az adott szakasz hátralévő részében leírtak szerint egy egységes készletet tartalmaz.
A szakasz hátralévő részében az "integrált készlet objektum" kifejezés a Broombridge objektum `integral_sets` tulajdonságának értékében található elemre hivatkozik.

Minden szerves set objektumnak rendelkeznie kell egy olyan tulajdonsággal, `metadata` amelynek értéke JSON-objektum.
`metadata` értéke lehet az üres JSON-objektum (azaz `{}`), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.

### <a name="hamiltonian-section"></a>Hamilton szakasz ###

#### <a name="overview"></a>Áttekintés ####

Ez a szakasz tájékoztató jellegű.

Az egyes integrált Hamilton `hamiltonian` tulajdonsága egy adott kvantum-kémiai probléma esetén ismerteti az egy-és kéttörzsű kifejezéseket, amelyek valós számok ritka tömbjét jelentik.
Az egyes integrált Hamilton-kezelők a következő űrlapot írják be:

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i \sigma} egy ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.

Az egyértelműség érdekében az egyelektronos kifejezés a következő:

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

a két elektron kifejezés pedig

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).
$$

Ahogy a `integral_sets` tulajdonság egyes elemeinek [`basis_set` tulajdonságának](#basis-set-object) leírásában is látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.
Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Tartalom ####

Ez a szakasz a normatív.

Minden szerves készletnek rendelkeznie kell egy olyan tulajdonsággal, `hamiltonian` amelynek értéke JSON-objektum.
A `hamiltonian` tulajdonság értéke Hamilton-objektumként ismert, és a tulajdonságok `one_electron_integrals` és `two_electron_integrals` a szakasz hátralévő részében leírtak szerint kell megadni.
Egy Hamilton objektumhoz `particle_hole_representation`tulajdonság is TARTOZHAT.
Ha van ilyen, `particle_hole_representation` értékének a szakasz hátralévő részében ismertetett formátumot kell követnie.

##### <a name="one-electron-integrals-object"></a>Egy elektronos szerves objektum #####

Ez a szakasz a normatív.

A Hamilton objektum `one_electron_integrals` tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.
Minden kifejezésnek tartalmaznia kell indexekkel `[i, j]`, ahol `i >= j`.

> Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.


###### <a name="example"></a>Példa ######

Ez a szakasz tájékoztató jellegű.

A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 \downarrow} egy\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
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


##### <a name="two-electron-integrals-object"></a>Két elektronos szerves objektum #####

Ez a szakasz a normatív.

A Hamilton objektum `two_electron_integrals` tulajdonságának olyan ritka tömb mennyiségnek kell lennie, amely egy `index_convention`nevű további tulajdonsággal rendelkezik.
`two_electron_integrals` értékének minden eleméhez négy indexnek kell tartoznia.

Minden `two_electron_integrals` tulajdonságnak rendelkeznie kell `index_convention` tulajdonsággal.
A `index_convention` tulajdonság értékének az 1. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.
Ha a `index_convention` értéke `mulliken`, akkor a `two_electron_integrals` ritka tömb mennyiségének minden egyes eleméhez egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton kifejezést kell létrehoznia, amely a kételektronos operátor $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , ahol a $i $, $j $, $k $, és $l $ értéknek a befogadó tartomány egész számának kell lennie, amely 1 és az integrált készlet objektum `n_electrons` tulajdonsága által meghatározott elektronok száma, valamint ahol $h _ {i, j, k, l} $ a ritka tömb mennyiségének `[i, j, k, l, h(i, j, k, l)]` eleme.

###### <a name="symmetries"></a>Symmetries ######

Ez a szakasz a normatív.

Ha egy `two_electron_integrals` objektum `index_convention` tulajdonsága egyenlő `mulliken`, akkor ha van olyan elem, amely indexekkel `[i, j, k, l]`, akkor a következő indexek nem lehetnek jelen, kivéve, ha `[i, j, k, l]`egyenlőek:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Mivel a `index_convention` tulajdonság ritka mennyiségű objektum, a különböző elemeken nem lehet megismételni az indexeket.
> Ha a `[i, j, k, l]` indexekkel rendelkező elemek jelen vannak, akkor előfordulhat, hogy más elem nem rendelkezik ezekkel az indexekkel.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Példa #######

Ez a szakasz tájékoztató jellegű.

A következő objektum határozza meg a Hamilton

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 \sigma} egy ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 \sigma} egy ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
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

A részecske – Hole reprezentációs objektum azt adja meg, hogy a tárolt alapértékek meghatározása a részecske-furat ábrázolására vonatkozik, amelyben a létrehozási és a megsemmisítési operátorok leírják a használt hivatkozási állapottól (például Hartree) származó izgalomokat. Fock állapota.
Az objektum nem kötelező.
Ha az objektum nincs megadva, a Hamilton úgy kell értelmezni, hogy a rendszer ne adja meg a részecske-furatos ábrázolásban.
Ha van, akkor a `particle_hole_representation` értékének olyan ritka tömb mennyiségű objektumnak kell lennie, amelynek indexei négy egész szám, és amelynek értéke egy szám és egy sztring.
Az egyes elemek értékének karakterlánc-része csak a `'+'` és `'-'` karaktereket tartalmazza, amely megadja, hogy a kifejezésben megadott tényező egy létrehozási vagy megsemmisülési operátor a részecske – Hole ábrázolásban.  Például a `"-+++"` a (z) $i $ helyen létrehozott lyukra reagál, és a $j, a k $ és a $l $ helyen létrehozott részecskéket hozza létre.

> [!NOTE]
> Mivel a `particle_hole_representation` értéke ritka tömb mennyiségű objektum, meg kell adni a `unit` és `format` tulajdonságokat.
> Az elfogadható egységeket az 1. táblázat tartalmazza.
> A `format` tulajdonság megadása kötelező, és azt jelzi, hogy a Hamilton-együtthatók meg vannak-e adva sűrű vagy ritka tömbként.
> A jelenlegi verzióban csak a ritka tömbök támogatottak, és az értelmezés szerint az összes meghatározatlan elem $0 $, de a jövőbeli verziók támogatják a `format` tulajdonság további értékeit is.

### <a name="initial-state-section"></a>Kezdeti állapot szakasz ###

A initial_state_suggestion objektum a megadott Hamilton tartozó kezdeti kvantum-állapotokat határozza meg. Az objektumnak JSON-`state` objektumok tömbjét kell tartalmaznia.

#### <a name="state-object"></a>Állapot objektum ####

Az egyes állapotok a megszállt pályák felhelyezését jelentik. Minden állapot-objektumnak rendelkeznie kell egy karakterláncot tartalmazó `label` tulajdonsággal. Minden állapot objektumnak rendelkeznie kell egy olyan `superposition` tulajdonsággal, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.

Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0} $ $ képviselő
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

Az összes szerves set objektum rendelkezhet `basis_set` tulajdonsággal.
Ha van, akkor a `basis_set` tulajdonság értékének olyan objektumnak kell lennie, amelynek két tulajdonsága van, `type` és `name`.

A `basis_set` tulajdonság értéke alapján azonosított függvényeknek valós értékűnek kell lenniük.

> [!NOTE]
> Ennek a specifikációnak a jövőbeli verzióiban a teljes körű függvények valós értékűek lehetnek.

## <a name="tables-and-lists"></a>Táblák és felsorolások ##

### <a name="table-1-allowed-physical-units"></a>1\. táblázat. Engedélyezett fizikai egységek ###

Ez a szakasz a normatív.

Az egységet megadó összes sztringnek a következők egyikének kell lennie:

- `hartree`
- `ev`

Az elemzőknek és a termelőknek egyenértékűnek kell lenniük a következő egyszerű mennyiségi objektumokkal:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>2\. táblázat Engedélyezett indexelési konvenciók ###

Ez a szakasz a normatív.

A tárgymutató-konvenciót megadó összes karakterláncnak a következők egyikének kell lennie:

- `mulliken`

Ez a szakasz tájékoztató jellegű.

A specifikáció későbbi verzióiban további indexelési konvenciók is bevezethetők.

#### <a name="interpretation-of-index-conventions"></a>Az index konvencióinak értelmezése ####

Ez a szakasz tájékoztató jellegű.
