---
title: Közreműködő dokumentáció a Microsoft QDK
description: Ismerje meg, Hogyan járulhat hozzá a koncepcionális vagy API-tartalmakhoz a Microsoft Quantum dokumentációs készletében.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20e9f8126a290f52701b6b0e525d7669a605d4c9
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759679"
---
# <a name="improving-documentation"></a><span data-ttu-id="6a53b-103">A dokumentáció továbbfejlesztése</span><span class="sxs-lookup"><span data-stu-id="6a53b-103">Improving Documentation</span></span>

<span data-ttu-id="6a53b-104">A Quantum Development Kit dokumentációja számos különböző formát vesz igénybe, így az információk könnyen elérhetők a kvantum-fejlesztők számára.</span><span class="sxs-lookup"><span data-stu-id="6a53b-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="6a53b-105">A [dokumentumok kód szerinti](https://www.writethedocs.org/guide/docs-as-code/)alapelveit követve az összes Quantum Development Kit-dokumentáció kódként van formázva, és a git használatával felügyelhető ugyanúgy, mint a Quantum Development Kit felépítéséhez használt forráskód.</span><span class="sxs-lookup"><span data-stu-id="6a53b-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="6a53b-106">A legtöbb esetben a kód hátterének dokumentációja a [Markdown](https://daringfireball.net/projects/markdown/)különböző formáiból tevődik össze, és a parancssorban, az ide-ben és a Source Control használatával könnyen használható, formázatlan szöveges formátumú szöveg kiírására szolgáló nyelv.</span><span class="sxs-lookup"><span data-stu-id="6a53b-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="6a53b-107">Hasonlóképpen fogadjuk el a [MathJax](https://www.mathjax.org/) -függvénytárat, hogy a latex nyelv használatával formázza a matematika használatát a dokumentációban, az alább részletezett módon.</span><span class="sxs-lookup"><span data-stu-id="6a53b-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="6a53b-108">Így a dokumentáció minden formája némileg eltér a részletektől:</span><span class="sxs-lookup"><span data-stu-id="6a53b-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="6a53b-109">A **koncepcionális dokumentáció** a közzétett cikkekből áll, amelyek a kvantum- https://docs.microsoft.com/quantum számítástechnika alapjait ismertetik a Interchange formats technikai előírásai alapján.</span><span class="sxs-lookup"><span data-stu-id="6a53b-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="6a53b-110">Ezek a cikkek a [DocFX-stílusú Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a gazdag dokumentációs készletek létrehozásához használt Markdown-változatok.</span><span class="sxs-lookup"><span data-stu-id="6a53b-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="6a53b-111">Az **API-hivatkozás** az egyes Q# függvényekhez, műveletekhez és felhasználó által definiált típusokhoz tartozó lapok összessége https://docs.microsoft.com/qsharp/api/ .</span><span class="sxs-lookup"><span data-stu-id="6a53b-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="6a53b-112">Ezek az oldalak dokumentálják az összes meghívható bemenetet és műveletet, valamint példákat és további információkra mutató hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="6a53b-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="6a53b-113">Az API-referenciát a rendszer automatikusan Kinyeri a forráskódban lévő kis DFM-dokumentumokból az Q# egyes kiadások részeként.</span><span class="sxs-lookup"><span data-stu-id="6a53b-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="6a53b-114">Az egyes mintákhoz és Kata-hoz tartozó **readme <!----> . MD** fájlok azt írják le, hogyan használható a minta vagy a Kata, mit takar, és hogyan kapcsolódik a Quantum Development Kit további részeihez.</span><span class="sxs-lookup"><span data-stu-id="6a53b-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="6a53b-115">Ezek a fájlok a GitHub-stílusú [Markdown (GFM)](https://github.github.com/gfm/)használatával íródnak, amely egy egyszerűbb alternatíva a DFM, amely a dokumentáció közvetlen csatolásához használható a kódokhoz.</span><span class="sxs-lookup"><span data-stu-id="6a53b-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="6a53b-116">A fogalmi dokumentációhoz való hozzájárulás</span><span class="sxs-lookup"><span data-stu-id="6a53b-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="6a53b-117">A koncepcionális vagy a README dokumentációjának fejlesztéséhez, majd egy lekéréses kérelemmel kezdődik a [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), a [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)vagy a [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), a megfelelő módon.</span><span class="sxs-lookup"><span data-stu-id="6a53b-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="6a53b-118">Részletesebben ismertetjük a lekéréses kérelmeket, de most van néhány dolog, ami jó szem előtt tartani a dokumentáció tökéletesítése során:</span><span class="sxs-lookup"><span data-stu-id="6a53b-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="6a53b-119">Az olvasók rendkívül széles körben érkeznek a Quantum Development Kit dokumentációjában.</span><span class="sxs-lookup"><span data-stu-id="6a53b-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="6a53b-120">Mindenki a diákoknak, akik szeretnék megtanulni, hogy milyen új és izgalmas, hogy a kihasználatlan szakirányú oktatói képzésben részt vevő szakterületek elolvassák a dokumentációt.</span><span class="sxs-lookup"><span data-stu-id="6a53b-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="6a53b-121">A lehetséges mértékig ne Tételezzük fel, hogy az olvasók részéről nem vállalunk széleskörű ismeretet, mivel ezek csak most kezdik el. Ez a leghasznosabb, ha egyértelmű és hozzáférhető leírásokat is biztosít, vagy további információkra mutató hivatkozásokat is biztosíthat más erőforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="6a53b-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="6a53b-122">A dokumentációs készletek nem rendelkeznek például könyvekkel vagy dokumentumokkal, így az olvasók a "középső"-ként látszanak.</span><span class="sxs-lookup"><span data-stu-id="6a53b-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="6a53b-123">Előfordulhat például, hogy a keresőmotorok nem javasolják az indexet, vagy ha egy barátja olyan hivatkozást kapott, amely a segítségére tett kísérletet. Próbálja ki az olvasót úgy, hogy mindig egyértelmű kontextust biztosít, valamint a hivatkozásokat, ahol szükséges.</span><span class="sxs-lookup"><span data-stu-id="6a53b-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="6a53b-124">Egyes olvasók az absztrakt és a definíciókat is hasznosnak találják, míg a többi olvasó az adott példákból kikövetkeztetve a legjobban működik.</span><span class="sxs-lookup"><span data-stu-id="6a53b-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="6a53b-125">Az általános eset és a konkrét példák egyaránt segítenek abban, hogy az olvasók a lehető legtöbbet hozzanak ki a kvantum-programozásból.</span><span class="sxs-lookup"><span data-stu-id="6a53b-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="6a53b-126">Különösen, ha azt is írta, hogy a kód dokumentálva van, előfordulhat, hogy a dolgok nyilvánvalóak, hogy az olvasója egyáltalán nem látható.</span><span class="sxs-lookup"><span data-stu-id="6a53b-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="6a53b-127">Nincs a legjobb módszer a programhoz, így nem számít, hogy milyen okos vagy tapasztalt olvasó lehet, nem tudja kitalálni, hogy milyen tervezési mintákat talál a leghasznosabb, hogy kifejezzék ötleteit a kódban.</span><span class="sxs-lookup"><span data-stu-id="6a53b-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="6a53b-128">Egyértelművé teszi, hogy az olvasó Hogyan várhatja el a kód használatát, így biztosíthatja ezt a környezetet.</span><span class="sxs-lookup"><span data-stu-id="6a53b-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="6a53b-129">A kvantum-programozási Közösség számos tagja tudományos kutató, és elsősorban a Közösséghez való hozzájárulásuk alapján ismerik fel őket.</span><span class="sxs-lookup"><span data-stu-id="6a53b-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="6a53b-130">Amellett, hogy az olvasóknak további anyagokat is találnak, érdemes megadnia, hogy az oktatási segédanyagok, például a dokumentumok, a megbeszélések, a blogbejegyzések és a szoftveres eszközök megfelelően adják meg az oktatási közreműködőket, hogy a lehető legjobb munkát használják a Közösség fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="6a53b-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="6a53b-131">A Quantum programozási Közösség egy széles körű és csodálatosan sokszínű Közösség.</span><span class="sxs-lookup"><span data-stu-id="6a53b-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="6a53b-132">A harmadik féltől származó példákban (például: "Ha egy felhasználó...,...") a nem a Belefoglalás helyett a nemek közötti különbségeket is használhatja.</span><span class="sxs-lookup"><span data-stu-id="6a53b-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="6a53b-133">Ha a személyek neve szerepel az idézetek és a hivatkozások között, és a nem ASCII-karakterek megfelelő bevonása a Közösség sokféleségét szolgálja ki a tagjainak tiszteletben tartásával.</span><span class="sxs-lookup"><span data-stu-id="6a53b-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="6a53b-134">Hasonlóképpen, az angol nyelv számos szavát gyakran gyűlölködő módon használják, például hogy a technikai dokumentációban való használatuk az egyes olvasóknak és a Közösségnek is kárt okozhat.</span><span class="sxs-lookup"><span data-stu-id="6a53b-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="6a53b-135">Mintául szolgáló kód hivatkozása a koncepcionális cikkekből</span><span class="sxs-lookup"><span data-stu-id="6a53b-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="6a53b-136">Ha a [Samples adattárból](https://github.com/Microsoft/Quantum)szeretne kódot foglalni, ezt egy speciális, DocFX-stílusú Markdown paranccsal teheti meg:</span><span class="sxs-lookup"><span data-stu-id="6a53b-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="6a53b-137">Ez a parancs a [ `Game.qs` `chsh-game` mintából a fájl](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)4 – 8. sorait importálja a Q# szintaxis kiemelése céljából, kódként megjelölve.</span><span class="sxs-lookup"><span data-stu-id="6a53b-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="6a53b-138">Ezzel a paranccsal elkerülhető a kód duplikálása a koncepcionális cikkek és a minták tárháza között, így a dokumentációban található mintakód mindig a lehető legnaprakészebb.</span><span class="sxs-lookup"><span data-stu-id="6a53b-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="6a53b-139">Hozzájárulás az API-hivatkozásokhoz</span><span class="sxs-lookup"><span data-stu-id="6a53b-139">Contributing to the API References</span></span>

<span data-ttu-id="6a53b-140">Az API-referenciák fejlesztésének elősegítése érdekében célszerű a lekéréses kérelmeket közvetlenül a dokumentált kódban megnyitni.</span><span class="sxs-lookup"><span data-stu-id="6a53b-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="6a53b-141">Minden függvény, művelet vagy felhasználó által definiált típus támogatja a dokumentációs megjegyzést (a `///` helyett `//` ).</span><span class="sxs-lookup"><span data-stu-id="6a53b-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="6a53b-142">A Quantum Development Kit minden kiadásának fordításakor ezek a megjegyzések az API-referenciák előállítására szolgálnak https://docs.microsoft.com/qsharp/api/ , beleértve az egyes hívható bemenetek és kimenetek adatait, valamint az egyes meghívásos feltételezéseket és példákat a használatuk módjára.</span><span class="sxs-lookup"><span data-stu-id="6a53b-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a53b-143">Győződjön meg arról, hogy nem módosítja manuálisan a generált API-dokumentációt, mivel ezeket a fájlokat a rendszer felülírja az egyes új kiadásokkal.</span><span class="sxs-lookup"><span data-stu-id="6a53b-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="6a53b-144">Értékeljük a Közösséghez való hozzájárulását, és azt szeretnénk, hogy a módosítások továbbra is a kiadás után is elérhetők legyenek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="6a53b-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="6a53b-145">Vegyük például a függvényt `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="6a53b-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="6a53b-146">A dokumentációs megjegyzéseknek segíteniük kell a felhasználó számára, hogy megismerjék, hogyan értelmezhető `bits` és `oracle` milyen funkciói vannak.</span><span class="sxs-lookup"><span data-stu-id="6a53b-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="6a53b-147">Ezek a különböző információk a Q# fordítók számára a dokumentációs Megjegyzés speciális elnevezett Markdown szakaszában adhatók meg.</span><span class="sxs-lookup"><span data-stu-id="6a53b-147">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="6a53b-148">A példa a `ControlledOnBitString` következőhöz hasonló lehet:</span><span class="sxs-lookup"><span data-stu-id="6a53b-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

<span data-ttu-id="6a53b-149">A [ `ControlledOnBitString` függvény API-dokumentációjában](xref:microsoft.quantum.canon.controlledonbitstring)megtekintheti a fenti kód renderelt verzióját.</span><span class="sxs-lookup"><span data-stu-id="6a53b-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:microsoft.quantum.canon.controlledonbitstring).</span></span>

<span data-ttu-id="6a53b-150">A dokumentáció írásának általános gyakorlata mellett az API-dokumentációs megjegyzések írásakor a következő szempontokat is segít megőrizni:</span><span class="sxs-lookup"><span data-stu-id="6a53b-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="6a53b-151">Az egyes dokumentációs megjegyzések formátumának egyeznie kell azzal, amit a fordító arra vár, hogy a Q# dokumentáció helyesen jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="6a53b-151">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="6a53b-152">Bizonyos szakaszok, például a `/// # Remarks` szabadkézi tartalmak engedélyezése, míg a szakaszok (például a `/// # See Also` szakasz) szigorúbbak.</span><span class="sxs-lookup"><span data-stu-id="6a53b-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="6a53b-153">Az olvasó elolvashatja az API-dokumentációt a fő API-referenciát tartalmazó helyen, az egyes névterek összegzésén, vagy akár az IDE-n belül, a hover-információk használatával.</span><span class="sxs-lookup"><span data-stu-id="6a53b-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="6a53b-154">Győződjön meg arról, hogy a `/// # Summary` mondatok nem hosszabbak, így az olvasó gyorsan rendezheti, hogy szükség van-e további vagy máshol való keresésre, és segíthet a névtér-összegzések gyors vizsgálatában.</span><span class="sxs-lookup"><span data-stu-id="6a53b-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="6a53b-155">Előfordulhat, hogy a dokumentáció jóval hosszabb ideig tart, mint maga a kód, de ez rendben van.</span><span class="sxs-lookup"><span data-stu-id="6a53b-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="6a53b-156">Még egy kis kódrészlet is váratlan hatással lehet a felhasználókra, akik nem ismerik azt a kontextust, amelyben a kód létezik.</span><span class="sxs-lookup"><span data-stu-id="6a53b-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="6a53b-157">A konkrét példákkal és a egyértelmű magyarázatokkal segítheti a felhasználókat abban, hogy a lehető leghatékonyabban használják a számukra elérhető kódot.</span><span class="sxs-lookup"><span data-stu-id="6a53b-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
