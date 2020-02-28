---
title: Broombridge séma specifikációja (0,2-es verzió)
description: A Broombridge Quantum kémia Schema v 0.2 specifikációit részletezi a Microsoft Quantum kémia Library-hez.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907273"
---
# <a name="broombridge-specification-v02"></a>Broombridge-specifikáció – v 0.2 #

A "kötelező", "nem", "REQUIREd", ",", "NOT", "nem", "nem", "NOT", "ajánlott", "MAY" és "OPTIONal" kulcsszót a dokumentumban [2119](https://tools.ietf.org/html/rfc2119)leírt módon kell értelmezni.

A "Megjegyzés", "" információ "vagy" figyelmeztetés "fejléceket tartalmazó oldalsávok informatív jellegűek.

## <a name="introduction"></a>Introduction (Bevezetés) ##

Ez a szakasz tájékoztató jellegű.

A Broombridge-dokumentumok a Quantum kémiában található szimulációs problémák példányainak közlésére szolgálnak a kvantum-szimuláció és a programozási eszközlánccal használatával történő feldolgozáshoz.

## <a name="serialization"></a>Szerializálási ##

Ez a szakasz a normatív.

Egy Broombridge-dokumentumot szerializálni kell egy JSON-objektumot képviselő [YAML 1,2-dokumentumként](http://yaml.org/spec/) , az [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2 szakaszban leírtak szerint.
A YAML szerializált objektumnak olyan tulajdonsággal kell rendelkeznie, `"$schema"` amelynek értéke `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, és érvényesnek kell lennie a JSON-séma draft-06 specifikációi [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] alapján.

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
A `version` tulajdonságnak `"0.2"`értékűnek kell lennie.

### <a name="example"></a>Példa ###

Ez a szakasz tájékoztató jellegű.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Probléma leírása szakasz ##

Ez a szakasz a normatív.

A Broombridge objektumnak rendelkeznie kell egy olyan tulajdonsággal, `problem_description` amelynek értéke JSON-tömb.
A `problem_description` tulajdonság értékében szereplő összes elemnek egy olyan JSON-objektumnak kell lennie, amely az adott szakasz hátralévő részében leírtak szerint egy egységes készletet tartalmaz.
A szakasz további részében a "probléma leírása objektum" kifejezés a Broombridge objektum `problem_description` tulajdonságának értékében található elemre hivatkozik.

Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `metadata` amelynek értéke JSON-objektum.
`metadata` értéke lehet az üres JSON-objektum (azaz `{}`), vagy a végrehajtó által meghatározott további tulajdonságokat is tartalmazhat.

### <a name="hamiltonian-section"></a>Hamilton szakasz ###

#### <a name="overview"></a>Áttekintés ####

Ez a szakasz tájékoztató jellegű.

Az egyes problémák Description objektum `hamiltonian` tulajdonsága egy adott kvantum-kémiai probléma Hamilton írja le azáltal, hogy az egy-és kéttörzsű kifejezéseket valós számú ritka tömbként sorolja fel.
Az egyes problémák Description objektuma által leírt Hamilton-operátorok az űrlapot

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} H\_{ijkl} a ^ \dagger\_{i \sigma} egy ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

Itt $h _ {ijkl} = (ij | KL) $ a Mulliken-egyezményben.

Az egyértelműség érdekében az egyelektronos kifejezés a következő:

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

a két elektron kifejezés pedig

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_(x\_2).
$$

Ahogy a `integral_sets` tulajdonság egyes elemeinek [`basis_set` tulajdonságának](#basis-set-object) leírásában is látható, explicit módon feltételezzük, hogy az alapul szolgáló függvények valós értékűek.
Ez lehetővé teszi, hogy a következő symmetries használja a feltételek között a Hamilton ábrázolásának tömörítéséhez.

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {KLIJ} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Tartalom ####

Ez a szakasz a normatív.

Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `hamiltonian` amelynek értéke JSON-objektum.
A `hamiltonian` tulajdonság értéke Hamilton-objektumként ismert, és a tulajdonságok `one_electron_integrals` és `two_electron_integrals` a szakasz hátralévő részében leírtak szerint kell megadni.

Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `coulomb_repulsion` amelynek értéke egyszerű mennyiségi objektum.
Minden probléma leírása objektumnak rendelkeznie kell egy olyan tulajdonsággal, `energy_offet` amelynek értéke egyszerű mennyiségi objektum.
> Megjegyzés A `coulomb_repulsion` és a `energy_offet` értékei együttesen rögzítik a Hamilton identitási idejét.

##### <a name="one-electron-integrals-object"></a>Egy elektronos szerves objektum #####

Ez a szakasz a normatív.

A Hamilton objektum `one_electron_integrals` tulajdonságának olyan ritka tömbbeli mennyiségnek kell lennie, amelynek indexei két egész szám, és amelyek értéke számok.
Minden kifejezésnek tartalmaznia kell indexekkel `[i, j]`, ahol `i >= j`.

> Megjegyzés Ez tükrözi azt a szimmetriát, amely $h _ {ij} = h_ {Ji} $, ami annak a ténynek a következménye, hogy a Hamilton Hermitian.


###### <a name="example"></a>Példa ######

Ez a szakasz tájékoztató jellegű.

A következő ritka tömb mennyisége a Hamilton $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} egy\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1, \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 \downarrow} egy\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
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
Ha a `index_convention` értéke `mulliken`, akkor a `two_electron_integrals` ritka tömb mennyiségének minden egyes eleméhez egy Broombridge-dokumentumot betöltő elemzőnek egy Hamilton-kifejezést kell létrehoznia, amely megegyezik a kételektronos operátorral $h _ {i, j, k, l} a ^ \ dagger_i a (z) ^ \ dagger_j a_k a_l $, ahol $i $, $j $, $k $ és $l $ értékének legalább 1 egész számnak kell lennie, és ahol $h _ {i, j, k, l} $ a ritka tömb mennyisége `[i, j, k, l, h(i, j, k, l)]` elem.

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

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} egy ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2 \rho} egy\_{3, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3 \sigma} egy ^ {\dagger}\_{2, \rho} a\_{1, \rho} egy\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{ha}.
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

### <a name="initial-state-section"></a>Kezdeti állapot szakasz ###

Ez a szakasz a normatív.

Az a `initial_state_suggestion` objektum, amelynek az értéke egy JSON-tömb, megadja a megadott Hamilton érdeklődésének kezdeti kvantum állapotait. A `initial_state_suggestion` tulajdonság értékének minden elemének egy kvantum-állapotot leíró JSON-objektumnak kell lennie, a szakasz hátralévő részében leírtak szerint.
A szakasz hátralévő részében az "állam objektum" kifejezés a Broombridge objektum `initial_state_suggestion` tulajdonságának értékében található elemre hivatkozik.

#### <a name="state-object"></a>Állapot objektum ####

Ez a szakasz a normatív.

Minden állapot-objektumnak rendelkeznie kell egy karakterláncot tartalmazó `label` tulajdonsággal. Minden állapot objektumnak rendelkeznie kell `method` tulajdonsággal. A `method` tulajdonság értékének a 3. táblázatban felsorolt engedélyezett értékek egyikének kell lennie.
Minden állapot objektum rendelkezhet olyan tulajdonsággal, `energy` amelynek értéke csak egyszerű mennyiség objektum lehet.

Ha a `method` tulajdonság értéke `sparse_multi_configurational`, az állapot objektumnak olyan `superposition` tulajdonsággal kell rendelkeznie, amely az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.

Például a kezdeti állapotok $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}, $ $, ahol a $ \ket{E} $ rendelkezik Energy $0,987 \textrm{Ha} $ azonosítóval, amelyet a
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

Ha a `method` tulajdonság értéke `unitary_coupled_cluster`, az állapot objektumnak olyan `cluster_operator` tulajdonsággal kell rendelkeznie, amelynek értéke JSON-objektum.
A JSON-objektumnak olyan `reference_state` tulajdonsággal kell rendelkeznie, amelynek értéke egy alap állapot.
A JSON-objektum rendelkezhet olyan `one_body_amplitudes` tulajdonsággal, amelynek értéke az egytörzsű fürtözött operátorok tömbje és az amplitúdójuk.
A JSON-objektum rendelkezhet olyan `two_body_amplitudes` tulajdonsággal, amelynek értéke a kéttörzsű fürtcsomópontok tömbje és az amplitúdójuk.
az alapul szolgáló állapotok tömbjét és a nem normalizált amplitúdókat tartalmazza.

Például a $ $ \ket{\text{Reference}} = (^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0}, $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dagger}\_{3, \uparrow}a\_{2, \downarrow} + 0,2 a ^ {\dagger}\_{2, \uparrow}a\_{2, \downarrow}-0,3 a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \downarrow}a\_{3, \uparrow}a\_{2, \downarrow} $ $ jelölője:
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a>Alapul szolgáló set objektum ####

Ez a szakasz a normatív.

Az egyes problémák leírási objektumai rendelkezhetnek `basis_set` tulajdonsággal.
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

### <a name="table-3-allowed-state-methods"></a>3\. táblázat. Engedélyezett állapotú metódusok ###

Ez a szakasz a normatív.

Az állapot-metódust megadó összes karakterláncnak a következők egyikének kell lennie:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Ez a szakasz tájékoztató jellegű.

További állapot-módszerek is bevezethetők a specifikáció jövőbeli verzióiban.
