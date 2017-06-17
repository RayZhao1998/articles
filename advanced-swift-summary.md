<hr>
    <div class="article-content">
<h1 id="介绍">介绍</h1>
<p><strong>《Swift 进阶》</strong>对一本书来说是一个很大胆的标题，所以我想我们应该先解释一下它意味着什么。</p>
<p>当我们开始本书第一版的写作的时候，Swift 才刚刚一岁。我们推测这门语言会在进入第二个年头的时候继续高速地发展，不过尽管我们十分犹豫，我们还是决定在 Swift 2.0 测试版发布以前就开始写作。几乎没有别的语言能够在如此短的时间里就能吸引这么多的开发者前来使用。</p>
<p>但是这留给了我们一个问题，你如何写出“符合语言习惯”的 Swift 代码？对某一个任务，有正确的做法吗？标准库给了我们一些提示，但是我们知道，即使是标准库本身也会随时间发生变化，它常常抛弃一切约定，又去遵守另一些约定。不过，在过去两年里，Swift 高速进化着，而优秀的 Swift 代码标准也日益明确。</p>
<p>对于从其他语言迁移过来的开发者，Swift 可能看起来很像你原来使用的语言，特别是它可能拥有你原来的语言中你最喜欢的那一部分。它可以像 C 一样进行低层级的位操作，但又可以避免许多未定义行为的陷阱。Ruby 的教徒可以在像是 <code>map</code> 或 <code>filter</code> 的轻量级的尾随闭包中感受到宾至如归。Swift 的泛型和 C++ 的模板如出一辙，但是额外的类型约束能保证泛型方法在被定义时就是正确的，而不必等到使用的时候再进行判定。灵活的高阶函数和运算符重载让你能够以 Haskell 或者 F# 那样的风格进行编码。最后 <code>@objc</code> 关键字允许你像在 Objective-C 中那样使用 selector 和各种运行时的动态特性。</p>
<p>有了这些相似点，Swift 可以去适应其他语言的风格。比如，Objective-C 的项目可以自动地导入到 Swift 中，很多 Java 或者 C# 的设计模式也可以直接照搬过来使用。在 Swift 发布的前几个月，一大波关于单子 (monad) 的教程和博客也纷至杳来。</p>
<p>但是失望也接踵而至。为什么我们不能像 Java 中接口那样将协议扩展 (protocol extension) 和关联类型 (associated type) 结合起来使用？为什么数组不具有我们预想那样的协变 (covariant) 特性？为什么我们无法写出一个“函子” (functor)？有时候这些问题的答案是 Swift 还没有来得及实现这部分功能，但是更多时候，这是因为在 Swift 中有其他更适合这门语言的方式来完成这些任务，或者是因为 Swift 中这些你认为等价的特性其实和你原来的想象大有不同。</p>
<blockquote>
<p>译者注：数组的协变特性指的是，包含有子类型对象的数组，可以直接赋值给包含有父类型对象的数组的变量。比如在 Java 和 C# 中 <code>string</code> 是 <code>object</code> 的子类型，而对应的数组类型 <code>string[]</code> 可以直接赋值给声明为 <code>object[]</code> 类型的变量。但是在 Swift 中，<code>Array&lt;Parent&gt;</code> 和 <code>Array&lt;Child&gt;</code> 之间并没有这样的关系。</p>
</blockquote>
<p>和其他大多数编程语言一样，Swift 也是一门复杂的语言。但是它将这些复杂的细节隐藏得很好。你可以使用 Swift 迅速上手开发应用，而不必知晓泛型，重载或者是静态调用和动态派发之间的区别这些知识。你可能永远都不会需要去调用 C 语言的代码，或者实现自定义的集合类型。但是随着时间的推移，无论是想要提升你的代码的性能，还是想让程序更加优雅清晰，亦或只是为了完成某项开发任务，你都有可能要逐渐接触到这些事情。</p>
<p>带你深入地学习这些特性就是这本书的写作目的。我们在书中尝试回答了很多“这个要怎么做”以及“为什么在 Swift 中会是这个结果”这样的问题，这种问题遍布各个论坛。我们希望你一旦阅读过本书，就能把握这些语言基础的知识，并且了解很多 Swift 的进阶特性，从而对 Swift 是如何工作的有一个更好的理解。本书中的知识点可以说是一个高级 Swift 程序员所必须了解和熟悉的内容。</p>
<h2 id="本书所面向的读者">本书所面向的读者</h2>
<p>本书面向的是有经验的程序员，你不需要是程序开发的专家，不过你应该已经是 Apple 平台的开发者，或者是想要从其他比如 Java 或者 C++ 这样的语言转行过来的程序员。如果你想要把你的 Swift 相关知识技能提升到和你原来已经熟知的 Objective-C 或者其他语言的同一水平线上的话，这本书会非常适合你。本书也适合那些已经开始学习 Swift，对这门语言基础有一定了解，并且渴望再上一个层次的新程序员们。</p>
<p>这本书不是一本介绍 Swift 基础的书籍，我们假定你已经熟悉这门语言的语法和结构。如果你需要完整地学习 Swift 的基础知识，最好的资源是 Apple 的 Swift 相关书籍 (在 <a href="https://itunes.apple.com/us/book/swift-programming-language/id1002622538">iBooks</a> 以及 <a href="https://developer.apple.com/swift/resources/">Apple 开发者网站</a>上均有下载)。如果你很有把握，你可以尝试同时阅读我们的这本书和 Apple 的 Swift 书籍。</p>
<p>这也不是一本教你如何为 macOS 或者 iOS 编程的书籍。不可否认，Swift 现在主要用于 Apple 的平台，我们会尽量包含一些实践中使用的例子，但是我们更希望这本书可以对非 Apple 平台的程序员也有所帮助。</p>
<h2 id="主题">主题</h2>
<p>我们按照基本概念的主题来组织本书，其中有一些深入像是可选值和字符串这样基本概念的章节，也有对于像是 C 语言互用性方面的主题。不过纵观全书，有一些主题可以为描绘出 Swift 给人的总体印象：</p>
<p><strong>Swift 既是一门高层级语言，又是一门低层级语言。</strong> 你可以在 Swift 中用 <code>map</code> 或者 <code>reduce</code> 来写出十分类似于 Ruby 和 Python 的代码，你也可以很容易地创建自己的高阶函数。Swift 让你有能力快速完成代码编写，并将它们直接编译为原生的二进制可执行文件，这使得性能上可以与 C 代码编写的程序相媲美。</p>
<p>Swift 真正激动人心，以及令人赞叹的是，我们可以<strong>兼顾</strong>高低两个层级。将一个数组通过闭包表达式映射到另一个数组所编译得到的汇编码，与直接对一块连续内存进行循环所得到的结果是一致的。</p>
<p>不过，为了最大化利用这些特性，有一些知识是你需要掌握的。如果你能对结构体和类的区别有深刻理解，或者对动态和静态方法派发的不同了然于胸的话，你就能从中获益。我们将在之后更深入地介绍这些内容。</p>
<p><strong>Swift 是一门多范式的语言。</strong>你可以用 Swift 来编写面向对象的代码，也可以使用不变量的值来写纯函数式的程序，在必要的时候，你甚至还能使用指针运算来写和 C 类似的代码。</p>
<p>这是一把双刃剑。好的一面，在 Swift 中你将有很多可用工具，你也不会被限制在一种代码写法里。但是这也让你身临险境，因为可能你实际上会变成使用 Swift 语言来书写 Java 或者 C 或者 Objective-C 的代码。</p>
<p>Swift 仍然可以使用大部分 Objective-C 的功能，包括消息发送，运行时的类型判定，以及 KVO 等。但是 Swift 还引入了很多 Objective-C 中不具备的特性。</p>
<p>Erik Meijer 是一位著名的程序语言专家，他在 <a href="https://twitter.com/headinthebox/status/655407294969196544">2015 年 10 月发推</a>说道：</p>
<blockquote>
<p>现在，相比 Haskell，Swift 可能是更好，更有价值，也更合适用来的学习函数式编程的语言。</p>
</blockquote>
<p>Swift 拥有泛型，协议，值类型以及闭包等特性，这些特性是对函数式风格的很好的介绍。我们甚至可以将运算符和函数结合起来使用。在 Swift 早期的时候，这门语言为世界带来了很多关于单子 (monad) 的博客。不过等到 Swift 2.0 发布并引入协议扩展的时候，大家研究的趋势也随之变化。</p>
<p><strong>Swift 十分灵活。</strong>在 <a href="http://www.paulgraham.com/onlisp.html">On Lisp</a> 这本书的介绍中，Paul Graham 写到：</p>
<blockquote>
<p>富有经验的 Lisp 程序员将他们的程序拆分成不同的部分。除了自上而下的设计原则，他们还遵循一种可以被称为自下而上的设计，他们可以将语言进行改造，让它更适合解决当前的问题。在 Lisp 中，你并不只是使用这门语言来编写程序，在开发过程中，你同时也在构建这门语言。当你编写代码的时候，你可能会想“要是 Lisp 有这个或者这个运算符就好了”，之后你就真的可以去实现一个这样的运算符。事后来看，你会意识到使用新的运算符可以简化程序的某些部分的设计，语言和程序就这样相互影响，发展进化。</p>
</blockquote>
<p>Swift 的出现比 Lisp 要晚得多，不过，我们能强烈感受到 Swift 也鼓励从下向上的编程方式。这让我们能轻而易举地编写一些通用可重用组件，然后你可以将它们组合起来实现更强大的的特性，最后用它们来解决你的实际问题。Swift 非常适合用来构建这些组件，你可以使它们看起来就像是语言自身的一部分。一个很好的例子就是 Swift 的标准库，许多你能想到的基本组件 - 像是可选值和基本的运算符等 - 其实都不是直接在语言本身中定义的，相反，它们是在标准库中被实现的。</p>
<p><strong>Swift 代码可以做到紧凑，精确，同时保持清晰。</strong>Swift 使用相对简洁的代码，这并不意味着单纯地减少输入量，还标志了一个更深层次目标。Swift 的观点是通过抛弃你经常在其他语言中见到的模板代码，而使得代码更容易被理解和阅读。这些模板代码往往会成为理解程序的障碍，而非助力。</p>
<p>举个例子，有了类型推断，在上下文很明显的时候我们就不再需要乱七八糟的类型声明了；那些几乎没有意义的分号和括号也都被移除了；泛型和协议扩展让你免于重复，并且把通用的操作封装到可以复用的方法中去。这些特性最终的目的都是为了能够让代码看上去一目了然。</p>
<p>一开始，这可能会对你造成一些困扰。如果你以前从来没有用像是 <code>map</code>，<code>filter</code> 和 <code>reduce</code> 这样的函数的话，它们可能看起来比简单的 <code>for</code> 循环要难理解。但是我们相信这个学习过程会很短，并且作为回报，你会发现这样的代码你第一眼看上去就能更准确地判断出它“显然正确”。</p>
<p><strong>除非你有意为之，否则 Swift 在实践中总是安全的。</strong>Swift 和 C 或者 C++ 这样的语言不同，在那些语言中，你只要忘了做某件事情，你的代码很可能就不是安全的了。它和 Haskell 或者 Java 也不一样，在后两者中有时候不论你是否需要，它们都“过于”安全。</p>
<p>C# 的主要设计者之一的 Eric Lippert 在他关于创造 C# 的 10 件后悔的事情中<a href="http://www.informit.com/articles/article.aspx?p=2425867">总结了</a>一些经验教训：</p>
<blockquote>
<p>有时候你需要为那些构建架构的专家实现一些特性，这些特性应当被清晰地标记为危险 — 它们往往并不能很好地对应其他语言中某些有用的特性。</p>
</blockquote>
<p>说这段话时，Eric 特别所指的是 C# 中的终止方法 (finalizer)，它和 C++ 中的析构函数 (destructor) 比较类似。但是不同于析构函数，终止方法的运行是不确定的，它受命于垃圾回收器，并且运行在垃圾回收的线程上。更糟糕的是，很可能终止方法甚至完全不会被调用到。但是，在 Swift 中，因为采用的是引用计数，<code>deinit</code> 方法的调用是可以确定和预测的。</p>
<p>Swift 的这个特点在其他方面也有体现。未定义的和不安全的行为默认是被避免的。比如，一个变量在被初始化之前是不能使用的，使用越界下标访问数组将会抛出异常，而不是继续使用一个可能取到的错误值。</p>
<p>当你真正需要的时候，也有不少“不安全”的方式，比如 <code>unsafeBitcast</code> 函数，或者是 <code>UnsafeMutablePointer</code> 类型。但是强大能力的背后是更大的未定义行为的风险。 比如下面的代码：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">someArray</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">]</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">uhOh</span> <span class="pyg-p">=</span> <span class="pyg-n">someArray</span><span class="pyg-p">.</span><span class="pyg-n">withUnsafeBufferPointer</span> <span class="pyg-p">{</span> <span class="pyg-n">ptr</span> <span class="pyg-k">in</span>
    <span class="pyg-c1">// ptr 只在这个 block 中有效</span>
    <span class="pyg-c1">// 不过你完全可以将它返回给外部世界：</span>
    <span class="pyg-k">return</span> <span class="pyg-n">ptr</span>
<span class="pyg-p">}</span>
<span class="pyg-c1">// 稍后...</span>
<span class="pyg-bp">print</span><span class="pyg-p">(</span><span class="pyg-n">uhOh</span><span class="pyg-p">[</span><span class="pyg-mi">10</span><span class="pyg-p">])</span>
</code></pre></div>
<p>这段代码可以编译，但是天知道它最后会做什么。方法名里已经警告了你这是不安全的，所以对此你需要自己负责。</p>
<p><strong>Swift 是一门独断的语言。</strong>关于“正确的” Swift 编码方法，作为本书作者，我们有着坚定的自己的看法。你会在本书中看到很多这方面的内容，有时候我们会把这些看法作为事实来对待。但是，归根结底，这只是我们的看法，你完全可以反对我们的观点。Swift 还是一门年轻的语言，许多事情还未成定局。更糟糕的是，很多博客或者文章是不正确的，或者已经过时 (包括我们曾经写过的一些内容，特别是早期就完成了的内容)。不论你在读什么资料，最重要的事情是你应当亲自尝试，去检验它们的行为，并且去体会这些用法。带着批判的眼光去审视和思考，并且警惕那些已经过时的信息。</p>
<h2 id="术语">术语</h2>
<blockquote>
<p>你用，或是不用，术语就在那里，不多不少。你懂，或是不懂，定义就在那里，不偏不倚。</p>
</blockquote>
<p>程序员总是喜欢说<a href="https://zh.wikipedia.org/wiki/行話">行话</a>。为了避免困扰，接下来我们会介绍一些贯穿于本书的术语定义。我们将尽可能遵守官方文档中的术语用法，使用被 Swift 社区所广泛接受的定义。这些定义大多都会在接下来的章节中被详细介绍，所以就算一开始你对它们一头雾水，也大可不必在意。如果你已经对这些术语非常了解，我们也还是建议你再浏览一下它们，并且确定你能接受我们的表述。</p>
<p>在 Swift 中，我们需要对值，变量，引用以及常量加以区分。</p>
<p><strong>值 (value)</strong> 是不变的，永久的，它从不会改变。比如，<code>1</code>, <code>true</code> 和 <code>[1,2,3]</code> 都是值。这些是<strong>字面量 (literal)</strong> 的例子，值也可以是运行时生成的。当你计算 5 的平方时，你得到的数字也是一个值。</p>
<p>当我们使用 <code>var x = [1,2]</code> 来将一个值进行命名的时候，我们实际上创建了一个名为 <code>x</code> 的<strong>变量 (variable)</strong> 来持有 <code>[1,2]</code> 这个值。通过像是执行 <code>x.append(3)</code> 这样的操作来改变 <code>x</code> 时，我们并没有改变原来的值。相反，我们所做的是使用 <code>[1,2,3]</code> 这个新的值来替代原来 <code>x</code> 中的内容。可能实际上它的内部实现真的只是在某段内存的后面添加上一个条目，并不是全体的替换，但是至少从<strong>逻辑</strong>上来说值是全新的。我们将这个过程称为变量的<strong>改变</strong> (mutating)。</p>
<p>我们还可以使用 <code>let</code> 而不是 <code>var</code> 来声明一个<strong>常量变量 (constant variables)</strong>，或者简称为常量。一旦常量被赋予一个值，它就不能再次被赋一个新的值了。</p>
<p>我们不需要在一个变量被声明的时候就立即为它赋值。我们可以先对变量进行声明 (<code>let x: Int</code>)，然后稍后再给它赋值 (<code>x = 1</code>)。Swift 是强调安全的语言，它将检查所有可能的代码路径，并确保变量在被读取之前一定是完成了赋值的。在 Swift 中变量不会存在未定义状态。当然，如果一个变量是用 <code>let</code> 声明的，那么它只能被赋值一次。</p>
<p>结构体 (struct) 和枚举 (enum) 是<strong>值类型 (value type)</strong>。当你把一个结构体变量赋值给另一个，那么这两个变量将会包含同样的值。你可以将它理解为内容被复制了一遍，但是更精确地描述的话，是被赋值的变量与另外的那个变量包含了同样的值。</p>
<p><strong>引用 (reference)</strong> 是一种特殊类型的值：它是一个“指向”另一个值的值。两个引用可能会指向同一个值，这引入了一种可能性，那就是这个值可能会被程序的两个不同的部分所改变。</p>
<p>类 (class) 是<strong>引用类型 (reference type)</strong>。你不能在一个变量里直接持有一个类的实例 (我们偶尔可能会把这个实例称作<strong>对象 (object)</strong>，这个术语经常被滥用，会让人困惑)。对于一个类的实例，我们只能在变量里持有对它的引用，然后使用这个引用来访问它。</p>
<p>引用类型具有<strong>同一性 (identity)</strong>，也就是说，你可以使用 <code>===</code> 来检查两个变量是否确实引用了同一个对象。如果相应类型的 <code>==</code> 运算符被实现了的话，你也可以用 <code>==</code> 来判断两个变量是否相等。两个不同的对象按照定义也是可能相等的。</p>
<p>值类型不存在同一性的问题。比如你不能对某个变量判定它是否和另一个变量持有“相同”的数字 2。你只能检查它们都包含了 2 这个值。<code>===</code> 运算符实际做的是询问“这两个变量是不是持有同样的引用”。在程序语言的论文里，<code>==</code> 有时候被称为<strong>结构相等</strong>，而 <code>===</code> 则被称为<strong>指针相等</strong>或者<strong>引用相等</strong>。</p>
<p>Swift 中，类引用不是唯一的引用类型。Swift 中依然有指针，比如使用 <code>withUnsafeMutablePointer</code> 和类似方法所得到的就是指针。不过类是使用起来最简单引用类型，这与它们的引用特性被部分隐藏在语法糖之后是不无关系的。你不需要像在其他一些语言中那样显式地处理指针的“解引用”。(我们会在稍后的<a href="#interoperability">互用性</a>章节中详细提及其他种类的引用。)</p>
<p>一个引用变量也可以用 <code>let</code> 来声明，这样做会使引用变为常量。换句话说，这会使变量不能被改变为引用其他东西，不过很重要的是，这并不意味着这个变量<strong>所引用</strong>的对象本身不能被改变。所以，当用常量的方式来引用变量的时候要格外小心，只有指向关系被常量化了，而对象本身还是可变的。(如果前面这几句话看起来有些不明不白的话，不要担心，我们在<a href="#structs-and-classes">结构体和类</a>还会详细解释)。这一点造成的问题是，就算在一个声明变量的地方看到 <code>let</code>，你也不能一下子就知道声明的东西是不是完全不可变的。想要做出正确的判断，你必须先<strong>知道</strong>这个变量持有的是值类型还是引用类型。</p>
<p>我们通过值类型是否执行<strong>深复制</strong>来对它们分类，判断它们是否具有<strong>值语义 (value semantics)</strong>。这种复制可能是在赋值新变量时就发生的，也可能会延迟到变量内容发生变更的时候。</p>
<p>这里我们会遇到另一件复杂的事情。如果我们的结构体中包含有引用类型，在将结构体赋值给一个新变量时所发生的复制行为中，这些引用类型的内容是不会被自动复制一份的，只有引用本身会被复制。这种复制的行为被称作<strong>浅复制 (shallow copy)</strong>。</p>
<p>举个例子，Foundation 框架中的 <code>Data</code> 结构体实际上是对引用类型 <code>NSData</code> 的一个封装。不过，<code>Data</code> 的作者采取了额外的步骤，来保证当 <code>Data</code> 结构体发生变化的时候对其中的 <code>NSData</code> 对象进行深复制。他们使用一种名为“写时复制” (copy-on-write) 的技术来保证操作的高效，我们会在<a href="#structs-and-classes">结构体和类</a>里详细介绍这种机制。现在我们需要重点知道的是，这种写时复制的特性并不是直接具有的，它需要额外进行实现。</p>
<p>Swift 中，像是数组这样的集合类型也都是对引用类型的封装，它们同样使用了写时复制的方式来在提供值语义的同时保持高效。不过，如果集合类型的元素是引用类型 (比如一个含有对象的数组) 的话，对象本身将不会被复制，只有对它的引用会被复制。也就是说，Swift 的数组只有当其中的元素满足值语义时，数组本身才具有值语义。在下一章，我们会讨论 Swift 中的集合类型与 Foundation 框架中 <code>NSArray</code> 和 <code>NSDictionary</code> 这些集合类型的不同之处。</p>
<p>有些类是完全不可变的，也就是说，从被创建以后，它们就不提供任何方法来改变它们的内部状态。这意味着即使它们是类，它们依然具有值语义 (因为它们就算被到处使用也从不会改变)。 但是要注意的是，只有那些标记为 <code>final</code> 的类能够保证不被子类化，也不会被添加可变状态。</p>
<p>在 Swift 中，函数也是值。你可以将一个函数赋值给一个变量，也可以创建一个包含函数的数组，或者调用变量所持有的函数。如果一个函数接受别的函数作为参数 (比如 <code>map</code> 函数接受一个转换函数，并将其应用到数组中的所有元素上)，或者一个函数的返回值是函数，那么这样的函数就叫做<strong>高阶函数 (higher-order function)</strong>。</p>
<p>函数不需要被声明在最高层级 — 你可以在一个函数内部声明另一个函数，也可以在一个 <code>do</code> 作用域或者其他作用域中声明函数。如果一个函数被定义在外层作用域中，但是被传递出这个作用域 (比如把这个函数被作为其他函数的返回值返回时)，它将能够“捕获”局部变量。这些局部变量将存在于函数中，不会随着局部作用域的结束而消亡，函数也将持有它们的状态。这种行为的变量被称为“闭合变量”，我们把这样的函数叫做<strong>闭包 (closure)</strong>。</p>
<p>函数可以通过 <code>func</code> 关键字来定义，也可以通过 <code>{ }</code> 这样的简短的<strong>闭包表达式 (closure expression)</strong>来定义。有时候我们只把通过闭包表达式创建的函数叫做“闭包”，不过不要让这种叫法蒙蔽了你的双眼。实际上使用 <code>func</code> 关键字定义的函数也是闭包。</p>
<p>函数是引用类型。也就是说，将一个通过闭合变量保存状态的函数赋值给另一个变量，并不会导致这些状态被复制。和对象引用类似，这些状态会被共享。换句话说，当两个闭包持有同样的局部变量时，它们是共享这个变量以及它的状态的。这可能会让你有点儿惊讶，我们将在<a href="#functions">函数</a>一章中涉及这方面的更多内容。</p>
<p>定义在类或者协议中的函数就是<strong>方法 (method)</strong>，它们有一个隐式的 self 参数。如果一个函数不是接受多个参数，而是只接受部分参数，然后返回一个接受其余参数的函数的话，那么这个函数就是一个<strong>柯里化函数 (curried function)</strong>。我们将在<a href="#functions">函数</a>中讲解一个方法是如何成为柯里化函数的。有时候我们会把那些不是方法的函数叫做<strong>自由函数 (free function)</strong>，这可以将它们与方法区分开来。</p>
<p>自由函数和那些在结构体上调用的方法是<strong>静态派发 (statically dispatched)</strong>的。对于这些函数的调用，在编译的时候就已经确定了。对于静态派发的调用，编译器可能能够<strong>内联 (inline)</strong>这些函数，也就是说，完全不去做函数调用，而是将这部分代码替换为需要执行的函数。静态派发还能够帮助编译器丢弃或者简化那些在编译时就能确定不会被实际执行的代码。</p>
<p>类或者协议上的方法可能是<strong>动态派发 (dynamically dispatched)</strong> 的。编译器在编译时不需要知道哪个函数将被调用。在 Swift 中，这种动态特性要么由 <a href="https://en.wikipedia.org/wiki/Virtual_method_table">vtable</a> 来完成，要么通过 selector 和 <code>objc_msgSend</code> 来完成，前者的处理方式和 Java 或是 C++ 中类似，而后者只针对 <code>@objc</code> 的类和协议上的方法。</p>
<p>子类型和方法<strong>重写 (overriding)</strong>是实现<strong>多态 (polymorphic)</strong> 特性的手段，也就是说，根据类型的不同，同样的方法会呈现出不同的行为。另一种方式是函数<strong>重载 (overloading)</strong>，它是指为不同的类型多次写同一个函数的行为。(注意不要把重写和重载弄混了，它们是完全不同的。)实现多态的第三种方法是通过泛型，也就是一次性地编写能够接受任意类型的的函数或者方法，不过这些方法的实现会各有不同。与方法重写不同的是，泛型中的方法在编译期间就是静态已知的。我们会在<a href="#generics">泛型</a>章节中提及关于这方面的更多内容。</p>
<h2 id="swift-风格指南">Swift 风格指南</h2>
<p>当我们编写这本书，或者在我们自己的项目中使用 Swift 代码时，我们尽量遵循如下的原则：</p>
<ul>
<li><p>对于命名，<strong>在使用时</strong>能清晰表意是最重要。因为 API 被使用的次数要远远多于被声明的次数，所以我们应当从使用者的角度来考虑它们的名字。尽快熟悉 <a href="https://swift.org/documentation/api-design-guidelines/">Swift API 设计准则</a>，并且在你自己的代码中坚持使用这些准则。</p></li>
<li><p>简洁经常有助于代码清晰，但是简洁本身不应该独自成为我们编码的目标。</p></li>
<li><p>务必为函数添加文档注释 — <strong>特别是</strong>泛型函数。</p></li>
<li><p>类型使用大写字母开头，函数、变量和枚举成员使用小写字母开头，两者都使用驼峰式命名法。</p></li>
<li><p>使用类型推断。省略掉显而易见的类型会有助于提高可读性。</p></li>
<li><p>如果存在歧义或者在进行定义的时候不要使用类型推断。(比如 <code>func</code> 就需要显式地指定返回类型)</p></li>
<li><p>优先选择结构体，只在确实需要使用到类特有的特性或者是引用语义时才使用类。</p></li>
<li><p>除非你的设计就是希望某个类被继承使用，否则都应该将它们标记为 <code>final</code>。</p></li>
<li><p>除非一个闭包后面立即跟随有左括号，否则都应该使用尾随闭包 (trailing closure) 的语法。</p></li>
<li><p>使用 <code>guard</code> 来提早退出方法。</p></li>
<li><p>避免对可选值进行强制解包和隐式强制解包。它们偶尔有用，但是经常需要使用它们的话往往意味着有其他不妥的地方。</p></li>
<li><p>不要写重复的代码。如果你发现你写了好几次类似的代码片段的话，试着将它们提取到一个函数里，并且考虑将这个函数转化为协议扩展的可能性。</p></li>
<li><p>试着去使用 <code>map</code> 和 <code>reduce</code>，但这不是强制的。当合适的时候，使用 <code>for</code> 循环也无可厚非。高阶函数的意义是让代码可读性更高。但是如果使用 <code>reduce</code> 的场景难以理解的话，强行使用往往事与愿违，这种时候简单的 <code>for</code> 循环可能会更清晰。</p></li>
<li><p>试着去使用不可变值：除非你需要改变某个值，否则都应该使用 <code>let</code> 来声明变量。不过如果能让代码更加清晰高效的话，也可以选择使用可变的版本。用函数将可变的部分封装起来，可以把它带来的副作用进行隔离。</p></li>
<li><p>Swift 的泛型可能会导致非常长的函数签名。坏消息是我们现在除了将函数声明强制写成几行以外，对此并没有什么好办法。我们会在示例代码中在这点上保持一贯性，这样你能看到我们是如何处理这个问题的。</p></li>
<li><p>除非你确实需要，否则不要使用 <code>self.</code>。在闭包表达式中，使用 <code>self</code> 是一个清晰的信号，表明闭包将会捕获 <code>self</code>。</p></li>
<li><p>尽可能地对现有的类型和协议进行扩展，而不是写一些全局函数。这有助于提高可读性，让别人更容易发现你的代码。</p></li>
</ul>
<h1 id="builtin-collections">内建集合类型</h1>
<p>在所有的编程语言中，元素的集合都是最重要的数据类型。在语言层面上对于不同类型的容器的良好支持，是决定编程效率和幸福指数的重要因素。Swift 在序列和集合这方面进行了特别的强调，标准库的开发者对于该话题的内容所投入的精力远超其他部分。正是有了这样的努力，我们能够使用到非常强大的集合模型，它比你所习惯的其他语言的集合拥有更好的可扩展性，不过同时它也相当复杂。</p>
<p>在本章中，我们将会讨论 Swift 中内建的几种主要集合类型，并重点研究如何以符合语言习惯的方式高效地使用它们。在<a href="#collection-protocols">下一章</a>中，我们会沿着抽象的阶梯蜿蜒而上，去探究标准库中的集合协议的工作原理。</p>
<h2 id="数组">数组</h2>
<h3 id="数组和可变性">数组和可变性</h3>
<p>在 Swift 中最常用的集合类型非数组莫属。数组是一系列相同类型的元素的有序的容器，对于其中每个元素，我们可以使用下标对其直接进行访问 (这又被称作随机访问)。举个例子，要创建一个数字的数组，我们可以这么写：</p>
<div class="highlight"><pre><code><span class="pyg-c1">// 斐波那契数列</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">fibs</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-mi">0</span><span class="pyg-p">,</span> <span class="pyg-mi">1</span><span class="pyg-p">,</span> <span class="pyg-mi">1</span><span class="pyg-p">,</span> <span class="pyg-mi">2</span><span class="pyg-p">,</span> <span class="pyg-mi">3</span><span class="pyg-p">,</span> <span class="pyg-mi">5</span><span class="pyg-p">]</span>
</code></pre></div>
<p>要是我们使用像是 <code>append(_:)</code> 这样的方法来修改上面定义的数组的话，会得到一个编译错误。这是因为在上面的代码中数组是用 <code>let</code> 声明为常量的。在很多情景下，这是正确的做法，它可以避免我们不小心对数组做出改变。如果我们想按照变量的方式来使用数组，我们需要将它用 <code>var</code> 来进行定义：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">mutableFibs</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-mi">0</span><span class="pyg-p">,</span> <span class="pyg-mi">1</span><span class="pyg-p">,</span> <span class="pyg-mi">1</span><span class="pyg-p">,</span> <span class="pyg-mi">2</span><span class="pyg-p">,</span> <span class="pyg-mi">3</span><span class="pyg-p">,</span> <span class="pyg-mi">5</span><span class="pyg-p">]</span>
</code></pre></div>
<p>现在我们就能很容易地为数组添加单个或是一系列元素了：</p>
<div class="highlight"><pre><code><span class="pyg-n">mutableFibs</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-mi">8</span><span class="pyg-p">)</span>
<span class="pyg-n">mutableFibs</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-n">contentsOf</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-mi">13</span><span class="pyg-p">,</span> <span class="pyg-mi">21</span><span class="pyg-p">])</span>
<span class="pyg-n">mutableFibs</span> <span class="pyg-c1">// [0, 1, 1, 2, 3, 5, 8, 13, 21]</span>
</code></pre></div>
<p>区别使用 <code>var</code> 和 <code>let</code> 可以给我们带来不少好处。使用 <code>let</code> 定义的变量因为其具有不变性，因此更有理由被优先使用。当你读到类似 <code>let fibs = ...</code> 这样的声明时，你可以确定 <code>fibs</code> 的值将永远不变，这一点是由编译器强制保证的。这在你需要通读代码的时候会很有帮助。不过，要注意这只针对那些具有值语义的类型。使用 <code>let</code> 定义的类实例对象 (也就是说对于引用类型) 时，它保证的是这个<strong>引用</strong>永远不会发生变化，你不能再给这个引用赋一个新的值，但是这个引用所指向的对象却是<strong>可以</strong>改变的。我们将在<a href="#structs-and-classes">结构体和类</a>中更加详尽地介绍两者的区别。</p>
<p>数组和标准库中的所有集合类型一样，是具有值语义的。当你创建一个新的数组变量并且把一个已经存在的数组赋值给它的时候，这个数组的内容会被复制。举个例子，在下面的代码中，<code>x</code> 将不会被更改：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">x</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">]</span>
<span class="pyg-kd">var</span> <span class="pyg-nv">y</span> <span class="pyg-p">=</span> <span class="pyg-n">x</span>
<span class="pyg-n">y</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-mi">4</span><span class="pyg-p">)</span>
<span class="pyg-n">y</span> <span class="pyg-c1">// [1, 2, 3, 4]</span>
<span class="pyg-n">x</span> <span class="pyg-c1">// [1, 2, 3]</span>
</code></pre></div>
<p><code>var y = x</code> 语句复制了 <code>x</code>，所以在将 <code>4</code> 添加到 <code>y</code> 末尾的时候，<code>x</code> 并不会发生改变，它的值依然是 <code>[1,2,3]</code>。当你把一个数组传递给一个函数时，会发生同样的事情；方法将得到这个数组的一份本地复制，所有对它的改变都不会影响调用者所持有的数组。</p>
<p>对比一下 Foundation 框架中 <code>NSArray</code> 在可变特性上的处理方法。<code>NSArray</code> 中没有更改方法，想要更改一个数组，你必须使用 <code>NSMutableArray</code>。但是，就算你拥有的是一个不可变的 <code>NSArry</code>，但是它的引用特性并<strong>不能</strong>保证这个数组不会被改变：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">a</span> <span class="pyg-p">=</span> <span class="pyg-bp">NSMutableArray</span><span class="pyg-p">(</span><span class="pyg-n">array</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">])</span>

<span class="pyg-c1">// 我们不想让 b 发生改变</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">b</span><span class="pyg-p">:</span> <span class="pyg-bp">NSArray</span> <span class="pyg-p">=</span> <span class="pyg-n">a</span>

<span class="pyg-c1">// 但是事实上它依然能够被 a 影响并改变</span>
<span class="pyg-n">a</span><span class="pyg-p">.</span><span class="pyg-bp">insert</span><span class="pyg-p">(</span><span class="pyg-mi">4</span><span class="pyg-p">,</span> <span class="pyg-n">at</span><span class="pyg-p">:</span> <span class="pyg-mi">3</span><span class="pyg-p">)</span>
<span class="pyg-n">b</span> <span class="pyg-c1">// ( 1, 2, 3, 4 )</span>
</code></pre></div>
<p>正确的方式是在赋值时，先手动进行复制：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">c</span> <span class="pyg-p">=</span> <span class="pyg-bp">NSMutableArray</span><span class="pyg-p">(</span><span class="pyg-n">array</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">])</span>

<span class="pyg-c1">// 我们不想让 d 发生改变</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">d</span> <span class="pyg-p">=</span> <span class="pyg-n">c</span><span class="pyg-p">.</span><span class="pyg-n">copy</span><span class="pyg-p">()</span> <span class="pyg-kc">as</span><span class="pyg-p">!</span> <span class="pyg-bp">NSArray</span>

<span class="pyg-n">c</span><span class="pyg-p">.</span><span class="pyg-bp">insert</span><span class="pyg-p">(</span><span class="pyg-mi">4</span><span class="pyg-p">,</span> <span class="pyg-n">at</span><span class="pyg-p">:</span> <span class="pyg-mi">3</span><span class="pyg-p">)</span>
<span class="pyg-n">d</span>  <span class="pyg-c1">// ( 1, 2, 3 )</span>
</code></pre></div>
<p>在上面的例子中，显而易见，我们需要进行复制，因为 <code>a</code> 的声明毕竟就是可变的。但是，当把数组在方法和函数之间来回传递的时候，事情可能就不那么明显了。</p>
<p>而在 Swift 中，相较于 <code>NSArray</code> 和 <code>NSMutableArray</code> 两种类型，数组只有一种统一的类型，那就是 <code>Array</code>。使用 <code>var</code> 可以将数组定义为可变，但是区别于与 <code>NS</code> 的数组，当你使用 <code>let</code> 定义第二个数组，并将第一个数组赋值给它，也可以保证这个新的数组是不会改变的，因为这里没有共用的引用。</p>
<p>创建如此多的复制有可能造成性能问题，不过实际上 Swift 标准库中的所有集合类型都使用了“写时复制”这一技术，它能够保证只在必要的时候对数据进行复制。在我们的例子中，直到 <code>y.append</code> 被调用的之前，<code>x</code> 和 <code>y</code> 都将共享内部的存储。在<a href="#structs-and-classes">结构体和类</a>中我们也将仔细研究值语义，并告诉你如何为你自己的类型实现写时复制特性。</p>
<h3 id="arrays-and-optionals">数组和可选值</h3>
<p>Swift 数组提供了你能想到的所有常规操作方法，像是 <code>isEmpty</code> 或是 <code>count</code>。数组也允许直接使用特定的下标直接访问其中的元素，像是 <code>fibs[3]</code>。不过要牢记在使用下标获取元素之前，你需要确保索引值没有超出范围。比如获取索引值为 3 的元素，你需要保证数组中至少有 4 个元素。否则，你的程序将会崩溃。</p>
<p>这么设计的主要原因是我们可以使用数组切片。在 Swift 中，计算一个索引值这种操作是非常罕见的：</p>
<ul>
<li><p>想要迭代数组？ <code>for x in array</code></p></li>
<li><p>想要迭代除了第一个元素以外的数组其余部分？ <code>for x in array.dropFirst()</code></p></li>
<li><p>想要迭代除了最后 5 个元素以外的数组？ <code>for x in array.dropLast(5)</code></p></li>
<li><p>想要列举数组中的元素和对应的下标？ <code>for (num, element) in collection.enumerated()</code></p></li>
<li><p>想要寻找一个指定元素的位置？ <code>if let idx = array.index { someMatchingLogic($0) }</code></p></li>
<li><p>想要对数组中的所有元素进行变形？ <code>array.map { someTransformation($0) }</code></p></li>
<li><p>想要筛选出符合某个标准的元素？ <code>array.filter { someCriteria($0) }</code></p></li>
</ul>
<p>Swift 3 中传统的 C 风格的 <code>for</code> 循环被移除了，这是 Swift 不鼓励你去做索引计算的另一个标志。手动计算和使用索引值往往可能带来很多潜在的 bug，所以最好避免这么做。如果这不可避免的话，我们可以很容易写一个可重用的通用函数来进行处理，在其中你可以对精心测试后的索引计算进行封装，我们将在<a href="#generics">泛型</a>一章里看到这个例子。</p>
<p>但是有些时候你仍然不得不使用索引。对于数组索引来说，当你这么做时，你应该已经深思熟虑，对背后的索引计算逻辑进行过认真思考。在这个前提下，如果每次都要对获取的结果进行解包的话就显得多余了 - 因为这意味着你不信任你的代码。但实际上你是信任你自己的代码的，所以你可能会选择将结果进行强制解包，因为你<strong>知道</strong>这些下标都是有效的。这一方面十分麻烦，另一方面也是一个坏习惯。当强制解包变成一种习惯后，很可能你会不小心强制解包了本来不应该解包的东西。所以，为了避免这个行为变成习惯，数组根本没有给你可选值的选项。</p>
<blockquote>
<p>无效的下标操作会造成可控的崩溃，有时候这种行为可能会被叫做<strong>不安全</strong>，但是这只是安全性的一个方面。下标操作在<strong>内存安全</strong>的意义上是完全安全的，标准库中的集合总是会执行边界检查，并禁止那些越界索引对内存的访问。</p>
</blockquote>
<p>其他操作的行为略有不同。<code>first</code> 和 <code>last</code> 属性返回的是可选值，当数组为空时，它们返回 <code>nil</code>。<code>first</code> 相当于 <code>isEmpty ? nil : self[0]</code>。类似地，如果数组为空时，<code>removeLast</code> 将会导致崩溃，而 <code>popLast</code> 将在数组不为空是删除最后一个元素并返回它，在数组为空时，它将不执行任何操作，直接返回 <code>nil</code>。你应该根据自己的需要来选取到底使用哪一个：当你将数组当作栈来使用时，你可能总是想要将 <code>empty</code> 检查和移除最后元素组合起来使用；而另一方面，如果你已经知道数组一定非空，那再去处理可选值就完全没有必要了。</p>
<p>我们会在本章后面讨论字典的时候再次遇到关于这部分的权衡。除此之外，关于<a href="#optionals">可选值</a>我们会有一整章的内容对它进行讨论。</p>
<h3 id="数组变形">数组变形</h3>
<h4 id="map">Map</h4>
<p>对数组中的每个值执行转换操作是一个很常见的任务。每个程序员可能都写过上百次这样的代码：创建一个新数组，对已有数组中的元素进行循环依次取出其中元素，对取出的元素进行操作，并把操作的结果加入到新数组的末尾。比如，下面的代码计算了一个整数数组里的元素的平方：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">squared</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-nb">Int</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-p">[]</span>
<span class="pyg-k">for</span> <span class="pyg-n">fib</span> <span class="pyg-k">in</span> <span class="pyg-n">fibs</span> <span class="pyg-p">{</span>
    <span class="pyg-n">squared</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-n">fib</span> <span class="pyg-o">*</span> <span class="pyg-n">fib</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>
<span class="pyg-n">squared</span> <span class="pyg-c1">// [0, 1, 1, 4, 9, 25]</span>
</code></pre></div>
<p>Swift 数组拥有 <code>map</code> 方法，这个方法来自函数式编程的世界。下面的例子使用了 <code>map</code> 来完成同样的操作：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">squares</span> <span class="pyg-p">=</span> <span class="pyg-n">fibs</span><span class="pyg-p">.</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-n">fib</span> <span class="pyg-k">in</span> <span class="pyg-n">fib</span> <span class="pyg-o">*</span> <span class="pyg-n">fib</span> <span class="pyg-p">}</span>
<span class="pyg-n">squares</span> <span class="pyg-c1">// [0, 1, 1, 4, 9, 25]</span>
</code></pre></div>
<p>这种版本有三大优势。首先，它很短。长度短一般意味着错误少，不过更重要的是，它比原来更清晰。所有无关的内容都被移除了，一旦你习惯了 <code>map</code> 满天飞的世界，你就会发现 <code>map</code> 就像是一个信号，一旦你看到它，就会知道即将有一个函数被作用在数组的每个元素上，并返回另一个数组，它将包含所有被转换后的结果。</p>
<p>其次，<code>squared</code> 将由 <code>map</code> 的结果得到，我们不会再改变它的值，所以也就不再需要用 <code>var</code> 来进行声明了，我们可以将其声明为 <code>let</code>。另外，由于数组元素的类型可以从传递给 <code>map</code> 的函数中推断出来，我们也不再需要为 <code>squared</code> 显式地指明类型了。</p>
<p>最后，创造 <code>map</code> 函数并不难，你只需要把 <code>for</code> 循环中的代码模板部分用一个泛型函数封装起来就可以了。下面是一种可能的实现方式 (在 Swift 中，它实际上是 <code>Sequence</code> 的一个扩展，我们将在之后关于<a href="#generics">编写泛型算法</a>的章节里继续 <code>Sequence</code> 的话题)：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">map</span><span class="pyg-p">&lt;</span><span class="pyg-n">T</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">transform</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">T</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">T</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-kd">var</span> <span class="pyg-nv">result</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-n">T</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-p">[]</span>
        <span class="pyg-n">result</span><span class="pyg-p">.</span><span class="pyg-n">reserveCapacity</span><span class="pyg-p">(</span><span class="pyg-bp">count</span><span class="pyg-p">)</span>
        <span class="pyg-k">for</span> <span class="pyg-n">x</span> <span class="pyg-k">in</span> <span class="pyg-kc">self</span> <span class="pyg-p">{</span>
            <span class="pyg-n">result</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-n">transform</span><span class="pyg-p">(</span><span class="pyg-n">x</span><span class="pyg-p">))</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-n">result</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p><code>Element</code> 是数组中包含的元素类型的占位符，<code>T</code> 是元素转换之后的类型的占位符。<code>map</code> 函数本身并不关心 <code>Element</code> 和 <code>T</code> 究竟是什么，它们可以是任意类型。<code>T</code> 的具体类型将由调用者传入给 <code>map</code> 的 <code>transform</code> 方法的返回值类型来决定。</p>
<blockquote>
<p>实际上，这个函数的签名应该是</p>
<p><code>func map&lt;T&gt;(_ transform: (Element) throws -&gt; T) rethrows -&gt; [T]</code></p>
<p>也就是说，对于可能抛出错误的变形函数，<code>map</code> 将会把错误转发给调用者。我们会在<a href="#error-handling">错误处理</a>一章里覆盖这个细节。在这里，我们选择去掉错误处理的这个修饰，这样看起来会更简单一些。如果你感兴趣，可以看看 GitHub 上 Swift 仓库的 <a href="https://github.com/apple/swift/blob/master/stdlib/public/core/Sequence.swift"><code>Sequence.map</code> 的源码实现</a>。</p>
</blockquote>
<h4 id="使用函数将行为参数化">使用函数将行为参数化</h4>
<p>即使你已经很熟悉 <code>map</code> 了，也请花一点时间来想一想 <code>map</code> 的代码。是什么让它可以如此通用而且有用？</p>
<p><code>map</code> 可以将模板代码分离出来，这些模板代码并不会随着每次调用发生变动，发生变动的是那些功能代码，也就是如何变换每个元素的逻辑代码。<code>map</code> 函数通过接受调用者所提供的变换函数作为参数来做到这一点。</p>
<p>纵观标准库，我们可以发现很多这样将行为进行参数化的设计模式。标准库中有不下十多个函数接受调用者传入的闭包，并将它作为函数执行的关键步骤：</p>
<ul>
<li><p><strong><code>map</code></strong> 和 <strong><code>flatMap</code></strong> — 如何对元素进行变换</p></li>
<li><p><strong><code>filter</code></strong> — 元素是否应该被包含在结果中</p></li>
<li><p><strong><code>reduce</code></strong> — 如何将元素合并到一个总和的值中</p></li>
<li><p><strong><code>sequence</code></strong> — 序列中下一个元素应该是什么？</p></li>
<li><p><strong><code>forEach</code></strong> — 对于一个元素，应该执行怎样的操作</p></li>
<li><p><strong><code>sort</code></strong>，<strong><code>lexicographicCompare</code></strong> 和 <strong><code>partition</code></strong> — 两个元素应该以怎样的顺序进行排列</p></li>
<li><p><strong><code>index</code></strong>，<strong><code>first</code></strong> 和 <strong><code>contains</code></strong> — 元素是否符合某个条件</p></li>
<li><p><strong><code>min</code></strong> 和 <strong><code>max</code></strong> — 两个元素中的最小/最大值是哪个</p></li>
<li><p><strong><code>elementsEqual</code></strong> 和 <strong><code>starts</code></strong> — 两个元素是否相等</p></li>
<li><p><strong><code>split</code></strong> — 这个元素是否是一个分割符</p></li>
</ul>
<p>所有这些函数的目的都是为了摆脱代码中那些杂乱无用的部分，比如像是创建新数组，对源数据进行 <code>for</code> 循环之类的事情。这些杂乱代码都被一个单独的单词替代了。这可以重点突出那些程序员想要表达的真正重要的逻辑代码。</p>
<p>这些函数中有一些拥有默认行为。除非你进行过指定，否则 <code>sort</code> 默认将会把可以作比较的元素按照升序排列。<code>contains</code> 对于可以判等的元素，会直接检查两个元素是否相等。这些行为让代码变得更加易读。升序排列非常自然，因此 <code>array.sort()</code> 的意义也很符合直觉。而对于 <code>array.index(of: &quot;foo&quot;)</code> 这样的表达方式，也要比 <code>array.index { $0 == &quot;foo&quot; }</code> 更容易理解。</p>
<p>不过在上面的例子中，它们都只是特殊情况下的简写。集合中的元素并不一定需要可以作比较，也不一定需要可以判等。你可以不对整个元素进行操作，比如，对一个包含人的数组，你可以通过他们的年龄进行排序 (<code>people.sort { $0.age &lt; $1.age }</code>)，或者是检查集合中有没有包含未成年人 (<code>people.contains { $0.age &lt; 18 }</code>)。你也可以对转变后的元素进行比较，比如通过 <code>people.sort { $0.name.uppercased() &lt; $1.name.uppercased() }</code> 来进行忽略大小写的排序，虽然这么做的效率不会很高。</p>
<p>还有一些其他类似的很有用的函数，可以接受一个闭包来指定行为。虽然它们并不存在于标准库中，但是你可以很容易地自己定义和实现它们，我们也建议你自己尝试着做做看：</p>
<ul>
<li><p><strong><code>accumulate</code></strong> — 累加，和 <code>reduce</code> 类似，不过是将所有元素合并到一个数组中，而且保留合并时每一步的值。</p></li>
<li><p><strong><code>all(matching:)</code></strong> 和 <strong><code>none(matching:)</code></strong> — 测试序列中是不是所有元素都满足某个标准，以及是不是没有任何元素满足某个标准。它们可以通过 <code>contains</code> 和它进行了精心对应的否定形式来构建。</p></li>
<li><p><strong><code>count(where:)</code></strong> — 计算满足条件的元素的个数，和 <code>filter</code> 相似，但是不会构建数组。</p></li>
<li><p><strong><code>indices(where:)</code></strong> — 返回一个包含满足某个标准的所有元素的索引的列表，和 <code>index(where:)</code> 类似，但是不会在遇到首个元素时就停止。</p></li>
<li><p><strong><code>prefix(while:)</code></strong> — 当判断为真的时候，将元素滤出到结果中。一旦不为真，就将剩余的抛弃。和 <code>filter</code> 类似，但是会提前退出。这个函数在处理无限序列或者是延迟计算 (lazily-computed) 的序列时会非常有用。</p></li>
<li><p><strong><code>drop(while:)</code></strong> — 当判断为真的时候，丢弃元素。一旦不为真，返回将其余的元素。和 <code>prefix(while:)</code> 类似，不过返回相反的集合。</p></li>
</ul>
<p>对于上面列表中的部分函数，我们在本书的其他地方进行了定义和实现。(<code>prefix(while:)</code> 和 <code>drop(while:)</code> 已经在添加到标准库的<a href="https://github.com/apple/swift-evolution/blob/master/proposals/0045-scan-takewhile-dropwhile.md">计划之中</a>，它们没有来得及被添加到 Swift 3.0 中，不过会在未来的版本中被添加。)</p>
<p>有时候你可能会发现你写了好多次同样模式的代码，比如想要在一个逆序数组中寻找第一个满足特定条件的元素：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">names</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;Paula&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;Elena&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;Zoe&quot;</span><span class="pyg-p">]</span>

<span class="pyg-kd">var</span> <span class="pyg-nv">lastNameEndingInA</span><span class="pyg-p">:</span> <span class="pyg-nb">String</span><span class="pyg-p">?</span>
<span class="pyg-k">for</span> <span class="pyg-n">name</span> <span class="pyg-k">in</span> <span class="pyg-n">names</span><span class="pyg-p">.</span><span class="pyg-n">reversed</span><span class="pyg-p">()</span> <span class="pyg-k">where</span> <span class="pyg-n">name</span><span class="pyg-p">.</span><span class="pyg-n">hasSuffix</span><span class="pyg-p">(</span><span class="pyg-s">&quot;a&quot;</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
    <span class="pyg-n">lastNameEndingInA</span> <span class="pyg-p">=</span> <span class="pyg-n">name</span>
    <span class="pyg-k">break</span>
<span class="pyg-p">}</span>
<span class="pyg-n">lastNameEndingInA</span> <span class="pyg-c1">// Optional(&quot;Elena&quot;)</span>
</code></pre></div>
<p>在这种情况下，你可以考虑为 <code>Sequence</code> 添加一个小扩展，来将这个逻辑封装到 <code>last(where:)</code> 方法中。我们使用闭包来对 <code>for</code> 循环中发生的变化进行抽象描述：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Sequence</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">last</span><span class="pyg-p">(</span><span class="pyg-k">where</span> <span class="pyg-n">predicate</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Bool</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">?</span> <span class="pyg-p">{</span>
        <span class="pyg-k">for</span> <span class="pyg-n">element</span> <span class="pyg-k">in</span> <span class="pyg-n">reversed</span><span class="pyg-p">()</span> <span class="pyg-k">where</span> <span class="pyg-n">predicate</span><span class="pyg-p">(</span><span class="pyg-n">element</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
            <span class="pyg-k">return</span> <span class="pyg-n">element</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-kc">nil</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>现在我们就能把代码中的 <code>for</code> 循环换成 <code>findElement</code> 了：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">match</span> <span class="pyg-p">=</span> <span class="pyg-n">names</span><span class="pyg-p">.</span><span class="pyg-bp">last</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span><span class="pyg-p">.</span><span class="pyg-n">hasSuffix</span><span class="pyg-p">(</span><span class="pyg-s">&quot;a&quot;</span><span class="pyg-p">)</span> <span class="pyg-p">}</span>
<span class="pyg-n">match</span> <span class="pyg-c1">// Optional(&quot;Elena&quot;)</span>
</code></pre></div>
<p>这么做的好处和我们在介绍 <code>map</code> 时所描述的是一样的，相较 <code>for</code> 循环，<code>last(where:)</code> 的版本显然更加易读。虽然 <code>for</code> 循环也很简单，但是在你的头脑里你始终还是要去做个循环，这加重了理解的负担。使用 <code>last(where:)</code> 可以减少出错的可能性，而且它允许你使用 <code>let</code> 而不是 <code>var</code> 来声明结果变量。</p>
<p>它和 <code>guard</code> 一起也能很好地工作，可能你会想要在元素没被找到的情况下提早结束代码：</p>
<div class="highlight"><pre><code><span class="pyg-k">guard</span> <span class="pyg-kd">let</span> <span class="pyg-nv">match</span> <span class="pyg-p">=</span> <span class="pyg-n">someSequence</span><span class="pyg-p">.</span><span class="pyg-bp">last</span><span class="pyg-p">(</span><span class="pyg-k">where</span><span class="pyg-p">:</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span><span class="pyg-p">.</span><span class="pyg-n">passesTest</span><span class="pyg-p">()</span> <span class="pyg-p">})</span>
    <span class="pyg-k">else</span> <span class="pyg-p">{</span> <span class="pyg-k">return</span> <span class="pyg-p">}</span>
<span class="pyg-c1">// 对 match 进行操作</span>
</code></pre></div>
<p>我们在本书后面会进一步涉及<a href="#collection-protocols">扩展集合类型</a>和<a href="#functions">使用函数</a>的相关内容。</p>
<h4 id="可变和带有状态的闭包">可变和带有状态的闭包</h4>
<p>当遍历一个数组的时候，你可以使用 <code>map</code> 来执行一些其他操作 (比如将元素插入到一个查找表中)。我们不推荐这么做，来看看下面这个例子：</p>
<div class="highlight"><pre><code><span class="pyg-n">array</span><span class="pyg-p">.</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-n">item</span> <span class="pyg-k">in</span>
    <span class="pyg-n">table</span><span class="pyg-p">.</span><span class="pyg-bp">insert</span><span class="pyg-p">(</span><span class="pyg-n">item</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>这将副作用 (改变了查找表) 隐藏在了一个看起来只是对数组变形的操作中。在上面这样的例子中，使用简单的 <code>for</code> 循环显然是比使用 <code>map</code> 这样的函数更好的选择。我们有一个叫做 <code>forEach</code> 的函数，看起来很符合我们的需求，但是 <code>forEach</code> 本身存在一些问题，我们一会儿会详细讨论。</p>
<p>这种做法和故意给闭包一个<strong>局部</strong>状态有本质不同。闭包是指那些可以捕获自身作用域之外的变量的函数，闭包再结合上高阶函数，将成为强大的工具。举个例子，方才我们提到的 <code>accumulate</code> 函数就可以用 <code>map</code> 结合一个带有状态的闭包来进行实现：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">accumulate</span><span class="pyg-p">&lt;</span><span class="pyg-n">Result</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">initialResult</span><span class="pyg-p">:</span> <span class="pyg-n">Result</span><span class="pyg-p">,</span> 
        <span class="pyg-kc">_</span> <span class="pyg-n">nextPartialResult</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Result</span><span class="pyg-p">,</span> <span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">Result</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">Result</span><span class="pyg-p">]</span> 
    <span class="pyg-p">{</span>
        <span class="pyg-kd">var</span> <span class="pyg-nv">running</span> <span class="pyg-p">=</span> <span class="pyg-n">initialResult</span>
        <span class="pyg-k">return</span> <span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-n">next</span> <span class="pyg-k">in</span>
            <span class="pyg-n">running</span> <span class="pyg-p">=</span> <span class="pyg-n">nextPartialResult</span><span class="pyg-p">(</span><span class="pyg-n">running</span><span class="pyg-p">,</span> <span class="pyg-n">next</span><span class="pyg-p">)</span>
            <span class="pyg-k">return</span> <span class="pyg-n">running</span>
        <span class="pyg-p">}</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>这个函数创建了一个中间变量来存储每一步的值，然后使用 <code>map</code> 来从这个中间值逐步创建结果数组：</p>
<div class="highlight"><pre><code><span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">,</span><span class="pyg-mi">4</span><span class="pyg-p">].</span><span class="pyg-n">accumulate</span><span class="pyg-p">(</span><span class="pyg-mi">0</span><span class="pyg-p">,</span> <span class="pyg-o">+</span><span class="pyg-p">)</span> <span class="pyg-c1">// [1, 3, 6, 10]</span>
</code></pre></div>
<p>要注意的是，这段代码假设了变形函数是以序列原有的顺序执行的。在我们上面的 <code>map</code> 中，事实确实如此。但是也有可能对于序列的变形是无序的，比如我们可以有并行处理元素变形的实现。官方标准库中的 <code>map</code> 版本没有指定它是否会按顺序来处理序列，不过看起来现在这么做是安全的。</p>
<h4 id="filter">Filter</h4>
<p>另一个常见操作是检查一个数组，然后将这个数组中符合一定条件的元素过滤出来并用它们创建一个新的数组。对数组进行循环并且根据条件过滤其中元素的模式可以用数组的 <code>filter</code> 方法表示：</p>
<div class="highlight"><pre><code><span class="pyg-n">nums</span><span class="pyg-p">.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-n">num</span> <span class="pyg-k">in</span> <span class="pyg-n">num</span> <span class="pyg-o">%</span> <span class="pyg-mi">2</span> <span class="pyg-p">==</span> <span class="pyg-mi">0</span> <span class="pyg-p">}</span> <span class="pyg-c1">// [2, 4, 6, 8, 10]</span>
</code></pre></div>
<p>我们可以使用 Swift 内建的用来代表参数的简写 <code>$0</code>，这样代码将会更加简短。我们可以不用写出 <code>num</code> 参数，而将上面的代码重写为：</p>
<div class="highlight"><pre><code><span class="pyg-n">nums</span><span class="pyg-p">.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">%</span> <span class="pyg-mi">2</span> <span class="pyg-p">==</span> <span class="pyg-mi">0</span> <span class="pyg-p">}</span> <span class="pyg-c1">// [2, 4, 6, 8, 10]</span>
</code></pre></div>
<p>对于很短的闭包来说，这样做有助于提高可读性。但是如果闭包比较复杂的话，更好的做法应该是就像我们之前那样，显式地把参数名字写出来。不过这更多的是一种个人选择，使用一眼看上去更易读的版本就好。一个不错的原则是，如果闭包可以很好地写在一行里的话，那么使用简写名会更合适。</p>
<p>通过组合使用 <code>map</code> 和 <code>filter</code>，我们现在可以轻易完成很多数组操作，而不需要引入中间数组。这会使得最终的代码变得更短更易读。比如，寻找 100 以内同时满足是偶数并且是其他数字的平方的数，我们可以对 <code>0..&lt;10</code> 进行 <code>map</code> 来得到所有平方数，然后再用 <code>filter</code> 过滤出其中的偶数：</p>
<div class="highlight"><pre><code><span class="pyg-p">(</span><span class="pyg-mf">1.</span><span class="pyg-p">.&lt;</span><span class="pyg-mi">10</span><span class="pyg-p">).</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">*</span> <span class="pyg-nv">$0</span> <span class="pyg-p">}.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">%</span> <span class="pyg-mi">2</span> <span class="pyg-p">==</span> <span class="pyg-mi">0</span> <span class="pyg-p">}</span> 
<span class="pyg-c1">// [4, 16, 36, 64]</span>
</code></pre></div>
<p><code>filter</code> 的实现看起来和 <code>map</code> 很类似：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">filter</span><span class="pyg-p">(</span><span class="pyg-kc">_</span> <span class="pyg-n">isIncluded</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Bool</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">Element</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-kd">var</span> <span class="pyg-nv">result</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-n">Element</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-p">[]</span>
        <span class="pyg-k">for</span> <span class="pyg-n">x</span> <span class="pyg-k">in</span> <span class="pyg-kc">self</span> <span class="pyg-k">where</span> <span class="pyg-n">isIncluded</span><span class="pyg-p">(</span><span class="pyg-n">x</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
            <span class="pyg-n">result</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-n">x</span><span class="pyg-p">)</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-n">result</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>如果你对在 <code>for</code> 中所使用的 <code>where</code> 感兴趣的话，可以阅读<a href="#optionals">可选值</a>一章。</p>
<p>一个关于性能的小提示：如果你正在写下面这样的代码，请不要这么做！</p>
<div class="highlight"><pre><code><span class="pyg-n">bigArray</span><span class="pyg-p">.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-n">someCondition</span> <span class="pyg-p">}.</span><span class="pyg-bp">count</span> <span class="pyg-o">&gt;</span> <span class="pyg-mi">0</span>
</code></pre></div>
<p><code>filter</code> 会创建一个全新的数组，并且会对数组中的每个元素都进行操作。然而在上面这段代码中，这显然是不必要的。上面的代码仅仅检查了是否有至少一个元素满足条件，在这个情景下，使用 <code>contains(where:)</code> 更为合适：</p>
<div class="highlight"><pre><code><span class="pyg-n">bigArray</span><span class="pyg-p">.</span><span class="pyg-bp">contains</span> <span class="pyg-p">{</span> <span class="pyg-n">someCondition</span> <span class="pyg-p">}</span>
</code></pre></div>
<p>这种做法会比原来快得多，主要因为两个方面：它不会去为了计数而创建一整个全新的数组，并且一旦匹配了第一个元素，它就将提前退出。一般来说，你只应该在需要所有结果时才去选择使用 <code>filter</code>。</p>
<p>有时候你会发现你想用 <code>contains</code> 完成一些操作，但是写出来的代码看起来很糟糕。比如，要是你想检查一个序列中的所有元素是否全部都满足某个条件，你可以用 <code>!sequence.contains { !condition }</code>，其实你可以用一个更具有描述性名字的新函数将它封装起来：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Sequence</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">public</span> <span class="pyg-kd">func</span> <span class="pyg-nf">all</span><span class="pyg-p">(</span><span class="pyg-n">matching</span> <span class="pyg-n">predicate</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Bool</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Bool</span> <span class="pyg-p">{</span>
        <span class="pyg-c1">// 对于一个条件，如果没有元素不满足它的话，那意味着所有元素都满足它：</span>
        <span class="pyg-k">return</span> <span class="pyg-o">!</span><span class="pyg-bp">contains</span> <span class="pyg-p">{</span> <span class="pyg-o">!</span><span class="pyg-n">predicate</span><span class="pyg-p">(</span><span class="pyg-nv">$0</span><span class="pyg-p">)</span> <span class="pyg-p">}</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>

<span class="pyg-kd">let</span> <span class="pyg-nv">evenNums</span> <span class="pyg-p">=</span> <span class="pyg-n">nums</span><span class="pyg-p">.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">%</span> <span class="pyg-mi">2</span> <span class="pyg-p">==</span> <span class="pyg-mi">0</span> <span class="pyg-p">}</span> <span class="pyg-c1">// [2, 4, 6, 8, 10]</span>
<span class="pyg-n">evenNums</span><span class="pyg-p">.</span><span class="pyg-n">all</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">%</span> <span class="pyg-mi">2</span> <span class="pyg-p">==</span> <span class="pyg-mi">0</span> <span class="pyg-p">}</span> <span class="pyg-c1">// true</span>
</code></pre></div>
<h4 id="reduce">Reduce</h4>
<p><code>map</code> 和 <code>filter</code> 都作用在一个数组上，并产生另一个新的、经过修改的数组。不过有时候，你可能会想把所有元素合并为一个新的值。比如，要是我们想将元素的值全部加起来，可以这样写：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">total</span> <span class="pyg-p">=</span> <span class="pyg-mi">0</span>
<span class="pyg-k">for</span> <span class="pyg-n">num</span> <span class="pyg-k">in</span> <span class="pyg-n">fibs</span> <span class="pyg-p">{</span>
    <span class="pyg-n">total</span> <span class="pyg-p">=</span> <span class="pyg-n">total</span> <span class="pyg-o">+</span> <span class="pyg-n">num</span>
<span class="pyg-p">}</span>
<span class="pyg-n">total</span> <span class="pyg-c1">// 12</span>
</code></pre></div>
<p><code>reduce</code> 方法对应这种模式，它把一个初始值 (在这里是 0) 以及一个将中间值 (<code>total</code>) 与序列中的元素 (<code>num</code>) 进行合并的函数进行了抽象。使用 <code>reduce</code>，我们可以将上面的例子重写为这样：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">sum</span> <span class="pyg-p">=</span> <span class="pyg-n">fibs</span><span class="pyg-p">.</span><span class="pyg-bp">reduce</span><span class="pyg-p">(</span><span class="pyg-mi">0</span><span class="pyg-p">)</span> <span class="pyg-p">{</span> <span class="pyg-n">total</span><span class="pyg-p">,</span> <span class="pyg-n">num</span> <span class="pyg-k">in</span> <span class="pyg-n">total</span> <span class="pyg-o">+</span> <span class="pyg-n">num</span> <span class="pyg-p">}</span> <span class="pyg-c1">// 12</span>
</code></pre></div>
<p>运算符也是函数，所以我们也可以把上面的例子写成这样：</p>
<div class="highlight"><pre><code><span class="pyg-n">fibs</span><span class="pyg-p">.</span><span class="pyg-bp">reduce</span><span class="pyg-p">(</span><span class="pyg-mi">0</span><span class="pyg-p">,</span> <span class="pyg-o">+</span><span class="pyg-p">)</span> <span class="pyg-c1">// 12</span>
</code></pre></div>
<p><code>reduce</code> 的输出值的类型可以和输入的类型不同。举个例子，我们可以将一个整数的列表转换为一个字符串，这个字符串中每个数字后面跟一个空格：</p>
<div class="highlight"><pre><code><span class="pyg-n">fibs</span><span class="pyg-p">.</span><span class="pyg-bp">reduce</span><span class="pyg-p">(</span><span class="pyg-s">&quot;&quot;</span><span class="pyg-p">)</span> <span class="pyg-p">{</span> <span class="pyg-n">str</span><span class="pyg-p">,</span> <span class="pyg-n">num</span> <span class="pyg-k">in</span> <span class="pyg-n">str</span> <span class="pyg-o">+</span> <span class="pyg-s">&quot;</span><span class="pyg-si">\(</span><span class="pyg-n">num</span><span class="pyg-si">)</span><span class="pyg-s"> &quot;</span> <span class="pyg-p">}</span> 
<span class="pyg-c1">// 0 1 1 2 3 5 </span>
</code></pre></div>
<p><code>reduce</code> 的实现是这样的：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">reduce</span><span class="pyg-p">&lt;</span><span class="pyg-n">Result</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">initialResult</span><span class="pyg-p">:</span> <span class="pyg-n">Result</span><span class="pyg-p">,</span> 
        <span class="pyg-kc">_</span> <span class="pyg-n">nextPartialResult</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Result</span><span class="pyg-p">,</span> <span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">Result</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">Result</span>
    <span class="pyg-p">{</span>
        <span class="pyg-kd">var</span> <span class="pyg-nv">result</span> <span class="pyg-p">=</span> <span class="pyg-n">initialResult</span>
        <span class="pyg-k">for</span> <span class="pyg-n">x</span> <span class="pyg-k">in</span> <span class="pyg-kc">self</span> <span class="pyg-p">{</span>
            <span class="pyg-n">result</span> <span class="pyg-p">=</span> <span class="pyg-n">nextPartialResult</span><span class="pyg-p">(</span><span class="pyg-n">result</span><span class="pyg-p">,</span> <span class="pyg-n">x</span><span class="pyg-p">)</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-n">result</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>另一个关于性能的小提示：<code>reduce</code> 相当灵活，所以在构建数组或者是执行其他操作时看到 <code>reduce</code> 的话不足为奇、比如，你可以只使用 <code>reduce</code> 就能实现 <code>map</code> 和 <code>filter</code>：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">map2</span><span class="pyg-p">&lt;</span><span class="pyg-n">T</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">transform</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">T</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">T</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-k">return</span> <span class="pyg-bp">reduce</span><span class="pyg-p">([])</span> <span class="pyg-p">{</span>
            <span class="pyg-nv">$0</span> <span class="pyg-o">+</span> <span class="pyg-p">[</span><span class="pyg-n">transform</span><span class="pyg-p">(</span><span class="pyg-nv">$1</span><span class="pyg-p">)]</span>
        <span class="pyg-p">}</span>
    <span class="pyg-p">}</span>

    <span class="pyg-kd">func</span> <span class="pyg-nf">filter2</span><span class="pyg-p">(</span><span class="pyg-kc">_</span> <span class="pyg-n">isIncluded</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Bool</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">Element</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-k">return</span> <span class="pyg-bp">reduce</span><span class="pyg-p">([])</span> <span class="pyg-p">{</span>
            <span class="pyg-n">isIncluded</span><span class="pyg-p">(</span><span class="pyg-nv">$1</span><span class="pyg-p">)</span> <span class="pyg-p">?</span> <span class="pyg-nv">$0</span> <span class="pyg-o">+</span> <span class="pyg-p">[</span><span class="pyg-nv">$1</span><span class="pyg-p">]</span> <span class="pyg-p">:</span> <span class="pyg-nv">$0</span>
        <span class="pyg-p">}</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>这样的实现符合美学，并且不再需要那些啰嗦的命令式的 <code>for</code> 循环。但是 Swift 不是 Haskell，Swift 的数组并不是列表 (list)。在这里，每次执行 <code>combine</code> 函数都会通过在前面的元素之后附加一个变换元素或者是已包含的元素，并创建一个全新的数组。这意味着上面两个实现的复杂度是 <span class="math inline"><em>O</em>(<em>n</em><sup>2</sup>)</span>，而不是 <span class="math inline"><em>O</em>(<em>n</em>)</span>。随着数组长度的增加，执行这些函数所消耗的时间将以平方关系增加。</p>
<h4 id="flatmap">flatMap</h4>
<p>有时候我们会想要对一个数组用一个函数进行 <code>map</code>，但是这个变形函数返回的是另一个数组，而不是单独的元素。</p>
<p>举个例子，假如我们有一个叫做 <code>extractLinks</code> 的函数，它会读取一个 Markdown 文件，并返回一个包含该文件中所有链接的 URL 的数组。这个函数的类型是这样的：</p>
<div class="highlight"><pre><code><span class="pyg-kd">func</span> <span class="pyg-nf">extractLinks</span><span class="pyg-p">(</span><span class="pyg-n">markdownFile</span><span class="pyg-p">:</span> <span class="pyg-nb">String</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">URL</span><span class="pyg-p">]</span>
</code></pre></div>
<p>如果我们有一系列的 Markdown 文件，并且想将这些文件中所有的链接都提取到一个单独的数组中的话，我们可以尝试使用 <code>markdownFiles.map(extractLinks)</code> 来构建。不过问题是这个方法返回的是一个包含了 URL 的数组的数组，这个数组中的每个元素都是一个文件中的 URL 的数组。为了得到一个包含所有 URL 的数组，你还要对这个由 <code>map</code> 取回的数组中的每一个数组用 <code>joined</code> 来进行展平 (flatten)，将它归并到一个单一数组中去：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">markdownFiles</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-nb">String</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-c1">// ...</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">nestedLinks</span> <span class="pyg-p">=</span> <span class="pyg-n">markdownFiles</span><span class="pyg-p">.</span><span class="pyg-bp">map</span><span class="pyg-p">(</span><span class="pyg-n">extractLinks</span><span class="pyg-p">)</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">links</span> <span class="pyg-p">=</span> <span class="pyg-n">nestedLinks</span><span class="pyg-p">.</span><span class="pyg-n">joined</span><span class="pyg-p">()</span>
</code></pre></div>
<p><code>flatMap</code> 将这两个操作合并为一个步骤。<code>markdownFiles.flatMap(links)</code> 将直接把所有 Markdown 文件中的所有 URL 放到一个单独的数组里并返回。</p>
<p><code>flatMap</code> 的实现看起来也和 <code>map</code> 基本一致，不过 <code>flatMap</code> 需要的是一个能够返回数组的函数作为变换参数。另外，在附加结果的时候，它使用的是 <code>append(contentsOf:)</code> 而不是 <code>append(_:)</code>，这样它将能把结果展平：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">flatMap</span><span class="pyg-p">&lt;</span><span class="pyg-n">T</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">transform</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">T</span><span class="pyg-p">])</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">T</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-kd">var</span> <span class="pyg-nv">result</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-n">T</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-p">[]</span>
        <span class="pyg-k">for</span> <span class="pyg-n">x</span> <span class="pyg-k">in</span> <span class="pyg-kc">self</span> <span class="pyg-p">{</span>
            <span class="pyg-n">result</span><span class="pyg-p">.</span><span class="pyg-n">append</span><span class="pyg-p">(</span><span class="pyg-n">contentsOf</span><span class="pyg-p">:</span> <span class="pyg-n">transform</span><span class="pyg-p">(</span><span class="pyg-n">x</span><span class="pyg-p">))</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-n">result</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p><code>flatMap</code> 的另一个常见使用情景是将不同数组里的元素进行合并。为了得到两个数组中元素的所有配对组合，我们可以对其中一个数组进行 <code>flatMap</code>，然后对另一个进行 <code>map</code> 操作：</p>
<p><embed src="artwork/suits.pdf" /> </p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">ranks</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;J&quot;</span><span class="pyg-p">,</span><span class="pyg-s">&quot;Q&quot;</span><span class="pyg-p">,</span><span class="pyg-s">&quot;K&quot;</span><span class="pyg-p">,</span><span class="pyg-s">&quot;A&quot;</span><span class="pyg-p">]</span>

<span class="pyg-kd">let</span> <span class="pyg-nv">result</span> <span class="pyg-p">=</span> <span class="pyg-n">suits</span><span class="pyg-p">.</span><span class="pyg-n">flatMap</span> <span class="pyg-p">{</span> <span class="pyg-n">suit</span> <span class="pyg-k">in</span>
    <span class="pyg-n">ranks</span><span class="pyg-p">.</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-n">rank</span> <span class="pyg-k">in</span>
        <span class="pyg-p">(</span><span class="pyg-n">suit</span><span class="pyg-p">,</span> <span class="pyg-n">rank</span><span class="pyg-p">)</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<h4 id="使用-foreach-进行迭代">使用 <code>forEach</code> 进行迭代</h4>
<p>我们最后要讨论的操作是 <code>forEach</code>。它和 <code>for</code> 循环的作为非常类似：传入的函数对序列中的每个元素执行一次。和 <code>map</code> 不同，<code>forEach</code> 不返回任何值。技术上来说，我们可以不暇思索地将一个 <code>for</code> 循环替换为 <code>forEach</code>：</p>
<div class="highlight"><pre><code><span class="pyg-k">for</span> <span class="pyg-n">element</span> <span class="pyg-k">in</span> <span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
    <span class="pyg-bp">print</span><span class="pyg-p">(</span><span class="pyg-n">element</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>

<span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">].</span><span class="pyg-n">forEach</span> <span class="pyg-p">{</span> <span class="pyg-n">element</span> <span class="pyg-k">in</span>
    <span class="pyg-bp">print</span><span class="pyg-p">(</span><span class="pyg-n">element</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>这没什么特别之处，不过如果你想要对集合中的每个元素都调用一个函数的话，使用 <code>forEach</code> 会比较合适。你只需要将函数或者方法直接通过参数的方式传递给 <code>forEach</code> 就行了，这可以改善代码的清晰度和准确性。比如在一个 view controller 里你想把一个数组中的视图都加到当前 view 上的话，只需要写 <code>theViews.forEach(view.addSubview)</code> 就足够了。</p>
<p>不过，<code>for</code> 循环和 <code>forEach</code> 有些细微的不同，值得我们注意。比如，当一个 <code>for</code> 循环中有 <code>return</code> 语句时，将它重写为 <code>forEach</code> 会造成代码行为上的极大区别。让我们举个例子，下面的代码是通过结合使用带有条件的 <code>where</code> 和 <code>for</code> 循环完成的：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-k">where</span> <span class="pyg-n">Element</span><span class="pyg-p">:</span> <span class="pyg-nb">Equatable</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">index</span><span class="pyg-p">(</span><span class="pyg-n">of</span> <span class="pyg-n">element</span><span class="pyg-p">:</span> <span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Int</span><span class="pyg-p">?</span> <span class="pyg-p">{</span>
        <span class="pyg-k">for</span> <span class="pyg-n">idx</span> <span class="pyg-k">in</span> <span class="pyg-kc">self</span><span class="pyg-p">.</span><span class="pyg-bp">indices</span> <span class="pyg-k">where</span> <span class="pyg-kc">self</span><span class="pyg-p">[</span><span class="pyg-n">idx</span><span class="pyg-p">]</span> <span class="pyg-p">==</span> <span class="pyg-n">element</span> <span class="pyg-p">{</span>
            <span class="pyg-k">return</span> <span class="pyg-n">idx</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-kc">nil</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>我们不能直接将 <code>where</code> 语句加入到 <code>forEach</code> 中，所以我们可能会用 <code>filter</code> 来重写这段代码 (实际上这段代码是错误的)：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Array</span> <span class="pyg-k">where</span> <span class="pyg-n">Element</span><span class="pyg-p">:</span> <span class="pyg-nb">Equatable</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">index_foreach</span><span class="pyg-p">(</span><span class="pyg-n">of</span> <span class="pyg-n">element</span><span class="pyg-p">:</span> <span class="pyg-n">Element</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Int</span><span class="pyg-p">?</span> <span class="pyg-p">{</span>
        <span class="pyg-kc">self</span><span class="pyg-p">.</span><span class="pyg-bp">indices</span><span class="pyg-p">.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-n">idx</span> <span class="pyg-k">in</span>
            <span class="pyg-kc">self</span><span class="pyg-p">[</span><span class="pyg-n">idx</span><span class="pyg-p">]</span> <span class="pyg-p">==</span> <span class="pyg-n">element</span>
        <span class="pyg-p">}.</span><span class="pyg-n">forEach</span> <span class="pyg-p">{</span> <span class="pyg-n">idx</span> <span class="pyg-k">in</span>
            <span class="pyg-k">return</span> <span class="pyg-n">idx</span>
        <span class="pyg-p">}</span>
        <span class="pyg-k">return</span> <span class="pyg-kc">nil</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>在 <code>forEach</code> 中的 <code>return</code> 并不能返回到外部函数的作用域之外，它仅仅只是返回到闭包本身之外，这和原来的逻辑就不一样了。在这种情况下，编译器会发现 <code>return</code> 语句的参数没有被使用，从而给出警告，我们可以找到问题所在。但我们不应该将找到所有这类错误的希望寄托在编译器上。</p>
<p>再思考一下下面这个简单的例子：</p>
<div class="highlight"><pre><code><span class="pyg-p">(</span><span class="pyg-mf">1.</span><span class="pyg-p">.&lt;</span><span class="pyg-mi">10</span><span class="pyg-p">).</span><span class="pyg-n">forEach</span> <span class="pyg-p">{</span> <span class="pyg-n">number</span> <span class="pyg-k">in</span>
    <span class="pyg-bp">print</span><span class="pyg-p">(</span><span class="pyg-n">number</span><span class="pyg-p">)</span>
    <span class="pyg-k">if</span> <span class="pyg-n">number</span> <span class="pyg-o">&gt;</span> <span class="pyg-mi">2</span> <span class="pyg-p">{</span> <span class="pyg-k">return</span> <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>你可能一开始还没反应过来，其实这段代码将会把输入的数字全部打印出来。<code>return</code> 语句并不会终止循环，它做的仅仅是从闭包中返回。</p>
<p>在某些情况下，比如上面的 <code>addSubview</code> 的例子里，<code>forEach</code> 可能会更好。它作为一系列链式操作使用时可谓适得其所。想像一下，你在同一个语句中有一系列 <code>map</code> 和 <code>filter</code> 的调用，这时候你想在调试时打印出操作链中间某个步骤的数组值，插入一个 <code>forEach</code> 步骤应该是最快的选择。</p>
<p>不过，因为 <code>return</code> 在其中的行为不太明确，我们建议大多数情况下不要用 <code>forEach</code>。这种时候，使用常规的 <code>for</code> 循环可能会更好。</p>
<h3 id="数组类型">数组类型</h3>
<h4 id="切片">切片</h4>
<p>除了通过单独的下标来访问数组中的元素 (比如 <code>fibs[0]</code>)，我们还可以通过下标来获取某个范围中的元素。比如，想要得到数组中除了首个元素的其他元素，我们可以这么做：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">slice</span> <span class="pyg-p">=</span> <span class="pyg-n">fibs</span><span class="pyg-p">[</span><span class="pyg-mf">1.</span><span class="pyg-p">.&lt;</span><span class="pyg-n">fibs</span><span class="pyg-p">.</span><span class="pyg-n">endIndex</span><span class="pyg-p">]</span>
<span class="pyg-n">slice</span> <span class="pyg-c1">// [1, 1, 2, 3, 5]</span>
<span class="pyg-n">type</span><span class="pyg-p">(</span><span class="pyg-n">of</span><span class="pyg-p">:</span> <span class="pyg-n">slice</span><span class="pyg-p">)</span> <span class="pyg-c1">// ArraySlice&lt;Int&gt;</span>
</code></pre></div>
<p>它将返回数组的一个切片 (slice)，其中包含了原数组中从第二个元素到最后一个元素的数据。得到的结果的类型是 <code>ArraySlice</code>，而不是 <code>Array</code>。切片类型只是数组的一种<strong>表示方式</strong>，它背后的数据仍然是原来的数组，只不过是用切片的方式来进行表示。这意味着原来的数组并不需要被复制。<code>ArraySlice</code> 具有的方法和 <code>Array</code> 上定义的方法是一致的，因此你可以把它们当做数组来进行处理。如果你需要将切片转换为数组的话，你可以通过将切片传递给 <code>Array</code> 的构建方法来完成：</p>
<div class="highlight"><pre><code><span class="pyg-nb">Array</span><span class="pyg-p">(</span><span class="pyg-n">fibs</span><span class="pyg-p">[</span><span class="pyg-mf">1.</span><span class="pyg-p">.&lt;</span><span class="pyg-n">fibs</span><span class="pyg-p">.</span><span class="pyg-n">endIndex</span><span class="pyg-p">])</span> <span class="pyg-c1">// [1, 1, 2, 3, 5]</span>
</code></pre></div>
<div class="figure">
<img src="https://objccn.io/products/advanced-swift/preview/artwork/pdf-as-png/arrayslice.pdf.png" alt="数组切片" />
<p class="caption">数组切片</p>
</div>
<h4 id="桥接">桥接</h4>
<p>Swift 数组可以桥接到 Objective-C 中。实际上它们也能被用在 C 代码里，不过我们<a href="#interoperability">稍后</a>才会涉及到这个问题。因为 <code>NSArray</code> 只能持有对象，所以对 Swift 数组进行桥接转换时曾经有一个限制，那就是数组中的元素需要能被转换为 <code>AnyObject</code>。这限制了只有当数组元素是类实例或者是像是 <code>Int</code>，<code>Bool</code>，<code>String</code> 这样的一小部分能自动桥接到 Objective-C 对应类型的值类型时，Swift 数组才能被桥接。</p>
<p>不过在 Swift 3 中这个限制已经不复存在了。Objective-C 中的 <code>id</code> 类型现在<a href="https://github.com/apple/swift-evolution/blob/master/proposals/0116-id-as-any.md">导入 Swift 中时变成了 <code>Any</code></a>，而不再是 <code>AnyObject</code>，也就是说，任意的 Swift 数组都可以被桥接转换为 <code>NSArray</code> 了。<code>NSArray</code> 本身仍旧只接受对象，所以，编译器和运行时将自动在后台把不适配的那些值用类来进行包装。反方向的解包同样也是自动进行的。</p>
<blockquote>
<p>使用统一的桥接方式来处理所有 Swift 类型到 Objective-C 的桥接工作，不仅仅使数组的处理变得容易，像是字典 (dictionary) 或者集合 (set) 这样的其他集合类型，也能从中受益。除此之外，它还为未来 Swift 与 Objective-C 之间互用性的增强带来了可能。比如，现在 Swift 的值可以桥接到 Objective-C 的对象，那么在未来的 Swift 版本中，一个 Swift 值类型完全有可能可以去遵守一个被标记为 <code>@objc</code> 的协议。</p>
</blockquote>
<h2 id="字典">字典</h2>
<p>Swift 中另一个关键的数据结构是 <code>Dictionary</code>，字典。字典包含键以及它们所对应的值。在一个字典中，每个键都只能出现一次。通过键来获取值所花费的平均时间是常数量级的 (作为对比，在数组中搜寻一个特定元素所花的时间将与数组尺寸成正比)。和数组有所不同，字典是无序的，使用 <code>for</code> 循环来枚举字典中的键值对时，顺序是不确定的。</p>
<p>在下面的例子中，我们虚构一个 app 的设置界面，并使用字典作为模型数据层。这个界面由一系列的设置项构成，每一个设置项都有自己的名字 (也就是我们字典中的键) 和值。值可以是文本，数字或者布尔值之中的一种。我们使用一个带有关联值的 <code>enum</code> 来表示：</p>
<div class="highlight"><pre><code><span class="pyg-kd">enum</span> <span class="pyg-nc">Setting</span> <span class="pyg-p">{</span>
    <span class="pyg-k">case</span> <span class="pyg-n">text</span><span class="pyg-p">(</span><span class="pyg-nb">String</span><span class="pyg-p">)</span>
    <span class="pyg-k">case</span> <span class="pyg-n">int</span><span class="pyg-p">(</span><span class="pyg-nb">Int</span><span class="pyg-p">)</span>
    <span class="pyg-k">case</span> <span class="pyg-n">bool</span><span class="pyg-p">(</span><span class="pyg-nb">Bool</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>

<span class="pyg-kd">let</span> <span class="pyg-nv">defaultSettings</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-nb">String</span><span class="pyg-p">:</span><span class="pyg-n">Setting</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span>
    <span class="pyg-s">&quot;Airplane Mode&quot;</span><span class="pyg-p">:</span> <span class="pyg-p">.</span><span class="pyg-n">bool</span><span class="pyg-p">(</span><span class="pyg-kc">true</span><span class="pyg-p">),</span>
    <span class="pyg-s">&quot;Name&quot;</span><span class="pyg-p">:</span> <span class="pyg-p">.</span><span class="pyg-n">text</span><span class="pyg-p">(</span><span class="pyg-s">&quot;My iPhone&quot;</span><span class="pyg-p">),</span>
<span class="pyg-p">]</span>
</code></pre></div>
<div class="highlight"><pre><code><span class="pyg-n">defaultSettings</span><span class="pyg-p">[</span><span class="pyg-s">&quot;Name&quot;</span><span class="pyg-p">]</span> <span class="pyg-c1">// Optional(Setting.text(&quot;My iPhone&quot;))</span>
</code></pre></div>
<p>我们使用下标的方式可以得到某个设置的值 (比如 <code>defaultSettings[&quot;Name&quot;]</code>)。字典查找将返回的是<strong>可选值</strong>，当特定键不存在时，下标查询返回 <code>nil</code>。这点和数组有所不同，在数组中，使用越界下标进行访问将会导致程序崩溃。</p>
<p>从理论上来说，这个区别的原因是数组索引和字典的键的使用方式有很大不同。我们已经讨论过，对数组来说，你很少需要直接使用数组的索引。即使你用到索引，这个索引也一般是通过某些方式由数组属性计算得来的 (比如从 <code>0..&lt;array.count</code> 这样的范围内获取到)。也就是说，使用一个无效索引一般都是程序员的失误。而另一方面，字典的键往往是从其他渠道得来的，从字典本身获取键反而十分少见。</p>
<p>与数组不同，字典是一种稀疏结构。即使在 <code>name</code> 键下存在某个值，你也还是无法确定 <code>address</code> 键下是否有值。</p>
<h3 id="可变性">可变性</h3>
<p>和数组一样，使用 <code>let</code> 定义的字典是不可变的：你不能向其中添加、删除或者修改条目。如果想要定义一个可变的字典，你需要使用 <code>var</code> 进行声明。想要将某个值从字典中移除，可以用下标将对应的值设为 <code>nil</code>，或者调用 <code>removeValue(forKey:)</code>。后一种方法除了删除这个键以外，还会将被删除的值返回 (如果待删除的键不存在，则返回 <code>nil</code>)。 对于一个不可变的字典，想要进行改变的话，首先需要进行复制：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">localizedSettings</span> <span class="pyg-p">=</span> <span class="pyg-n">defaultSettings</span>
<span class="pyg-n">localizedSettings</span><span class="pyg-p">[</span><span class="pyg-s">&quot;Name&quot;</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-s">&quot;Mein iPhone&quot;</span>
<span class="pyg-n">localizedSettings</span><span class="pyg-p">[</span><span class="pyg-s">&quot;Do Not Disturb&quot;</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-kc">true</span>
</code></pre></div>
<p>再次注意，<code>defaultSettings</code> 的值并没有改变。和键的移除类似，除了下标之外，还有一种方法可以更新字典内容，那就是 <code>updateValue(_:forKey:)</code>，这个方法将在更新之前有值的时候返回这个更新前的值：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">oldName</span> <span class="pyg-p">=</span> <span class="pyg-n">localizedSettings</span>
    <span class="pyg-p">.</span><span class="pyg-n">updateValue</span><span class="pyg-p">(.</span><span class="pyg-n">text</span><span class="pyg-p">(</span><span class="pyg-s">&quot;Il mio iPhone&quot;</span><span class="pyg-p">),</span> <span class="pyg-n">forKey</span><span class="pyg-p">:</span> <span class="pyg-s">&quot;Name&quot;</span><span class="pyg-p">)</span>
<span class="pyg-n">localizedSettings</span><span class="pyg-p">[</span><span class="pyg-s">&quot;Name&quot;</span><span class="pyg-p">]</span> <span class="pyg-c1">// Optional(Setting.text(&quot;Il mio iPhone&quot;))</span>
<span class="pyg-n">oldName</span> <span class="pyg-c1">// Optional(Setting.text(&quot;Mein iPhone&quot;))</span>
</code></pre></div>
<h3 id="有用的字典扩展">有用的字典扩展</h3>
<p>如果我们想要将一个默认的设置字典和某个用户更改过的自定义设置字典合并，应该怎么做呢？自定义的设置应该要覆盖默认设置，同时得到的字典中应当依然含有那些没有被自定义的键值。换句话说，我们需要合并两个字典，用来做合并的字典需要覆盖重复的键。标准库中并没有这样的函数，不过我们可以自己写一个。</p>
<p>我们扩展 <code>Dictionary</code> 类型，为它添加一个 <code>merge</code> 方法，该方法接受待合并的字典作为参数。我们可以将这个参数指明为 <code>Dictionary</code> 类型，不过更好的选择是用更加通用的泛型方法来进行实现。我们对参数的要求是，它必须是一个序列，这样我们就可以对其进行循环枚举。另外，序列的元素必须是键值对，而且它必须和接受方法调用的字典的键值对拥有相同类型。对于任意的 <code>Sequence</code>，如果它的 <code>Iterator.Element</code> 是 <code>(Key, Value)</code> 的话，它就满足我们的要求，因此我们将其作为泛型的约束 (这里的 <code>Key</code> 和 <code>Value</code> 是我们所扩展的 <code>Dictionary</code> 中已经定义的泛型类型参数)：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Dictionary</span> <span class="pyg-p">{</span>
    <span class="pyg-kr">mutating</span> <span class="pyg-kd">func</span> <span class="pyg-nf">merge</span><span class="pyg-p">&lt;</span><span class="pyg-n">S</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">other</span><span class="pyg-p">:</span> <span class="pyg-n">S</span><span class="pyg-p">)</span>
        <span class="pyg-k">where</span> <span class="pyg-n">S</span><span class="pyg-p">:</span> <span class="pyg-n">Sequence</span><span class="pyg-p">,</span> <span class="pyg-n">S</span><span class="pyg-p">.</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span> <span class="pyg-p">==</span> <span class="pyg-p">(</span><span class="pyg-n">key</span><span class="pyg-p">:</span> <span class="pyg-n">Key</span><span class="pyg-p">,</span> <span class="pyg-n">value</span><span class="pyg-p">:</span> <span class="pyg-n">Value</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
        <span class="pyg-k">for</span> <span class="pyg-p">(</span><span class="pyg-n">k</span><span class="pyg-p">,</span> <span class="pyg-n">v</span><span class="pyg-p">)</span> <span class="pyg-k">in</span> <span class="pyg-n">other</span> <span class="pyg-p">{</span>
            <span class="pyg-kc">self</span><span class="pyg-p">[</span><span class="pyg-n">k</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-n">v</span>
        <span class="pyg-p">}</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>正如下例所示，我们可以将一个字典合并进另一个字典了。另外，方法的参数还可以是键值对数组或者其他类似的任意序列，而不一定必须是字典：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">settings</span> <span class="pyg-p">=</span> <span class="pyg-n">defaultSettings</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">overriddenSettings</span><span class="pyg-p">:</span> <span class="pyg-p">[</span><span class="pyg-nb">String</span><span class="pyg-p">:</span><span class="pyg-n">Setting</span><span class="pyg-p">]</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;Name&quot;</span><span class="pyg-p">:</span> <span class="pyg-p">.</span><span class="pyg-n">text</span><span class="pyg-p">(</span><span class="pyg-s">&quot;Jane&#39;s iPhone&quot;</span><span class="pyg-p">)]</span>
<span class="pyg-n">settings</span><span class="pyg-p">.</span><span class="pyg-n">merge</span><span class="pyg-p">(</span><span class="pyg-n">overriddenSettings</span><span class="pyg-p">)</span>
<span class="pyg-n">settings</span>
<span class="pyg-c1">// [&quot;Name&quot;: Setting.text(&quot;Jane\&#39;s iPhone&quot;), &quot;Airplane Mode&quot;: Setting.bool(true)]</span>
</code></pre></div>
<p>另一个有意思的扩展是从一个 <code>(Key, Value)</code> 键值对的序列来创建字典。标准库中为数组提供了一个类似的初始化方法，我们也经常用到它。当你每次将一个范围转变为数组时 (<code>Array(1...10)</code>)，或者是将一个 <code>ArraySlice</code> 转换回数组时 (<code>Array(someSlice)</code>)，你都用到了从序列创建数组的方法。但是，对于 <code>Dictionary</code>，还没有这样的初始化方法。(在 Swift-Evolution 的提案中，有人<a href="https://github.com/apple/swift-evolution/blob/master/proposals/0100-add-sequence-based-init-and-merge-to-dictionary.md">提议添加</a>这样的方法，所以我们有可能在未来能见到这样的初始化方法。)</p>
<p>我们可以先创建一个空字典，然后将序列合并到字典中去。这样一来，我们就可以重用上面的 <code>merge</code> 方法，让它来做实际的工作：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Dictionary</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">init</span><span class="pyg-p">&lt;</span><span class="pyg-n">S</span><span class="pyg-p">:</span> <span class="pyg-n">Sequence</span><span class="pyg-p">&gt;(</span><span class="pyg-kc">_</span> <span class="pyg-n">sequence</span><span class="pyg-p">:</span> <span class="pyg-n">S</span><span class="pyg-p">)</span>
        <span class="pyg-k">where</span> <span class="pyg-n">S</span><span class="pyg-p">.</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span> <span class="pyg-p">==</span> <span class="pyg-p">(</span><span class="pyg-n">key</span><span class="pyg-p">:</span> <span class="pyg-n">Key</span><span class="pyg-p">,</span> <span class="pyg-n">value</span><span class="pyg-p">:</span> <span class="pyg-n">Value</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
        <span class="pyg-kc">self</span> <span class="pyg-p">=</span> <span class="pyg-p">[:]</span>
        <span class="pyg-kc">self</span><span class="pyg-p">.</span><span class="pyg-n">merge</span><span class="pyg-p">(</span><span class="pyg-n">sequence</span><span class="pyg-p">)</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>

<span class="pyg-c1">// 所有 alert 默认都是关闭的</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">defaultAlarms</span> <span class="pyg-p">=</span> <span class="pyg-p">(</span><span class="pyg-mf">1.</span><span class="pyg-p">.&lt;</span><span class="pyg-mi">5</span><span class="pyg-p">).</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-p">(</span><span class="pyg-n">key</span><span class="pyg-p">:</span> <span class="pyg-s">&quot;Alarm </span><span class="pyg-si">\(</span><span class="pyg-nv">$0</span><span class="pyg-si">)</span><span class="pyg-s">&quot;</span><span class="pyg-p">,</span> <span class="pyg-n">value</span><span class="pyg-p">:</span> <span class="pyg-kc">false</span><span class="pyg-p">)</span> <span class="pyg-p">}</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">alarmsDictionary</span> <span class="pyg-p">=</span> <span class="pyg-nb">Dictionary</span><span class="pyg-p">(</span><span class="pyg-n">defaultAlarms</span><span class="pyg-p">)</span>
</code></pre></div>
<p>我们要添加的第三个有用扩展是一个 <code>map</code> 函数，它可以用来操作并转换字典中的值。因为 <code>Dictionary</code> 已经是一个 <code>Sequence</code> 类型，它已经有一个 <code>map</code> 函数来产生数组。不过我们有时候想要的是结果保持字典的结构，只对其中的值进行映射。我们的 <code>mapValues</code> 方法将首先调用标准的 <code>map</code>，来创建一个<strong>(键, 转换后的值)</strong>的数组。接下来，使用上面定义的初始化方法将其转换回字典：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Dictionary</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">mapValues</span><span class="pyg-p">&lt;</span><span class="pyg-n">NewValue</span><span class="pyg-p">&gt;(</span><span class="pyg-n">transform</span><span class="pyg-p">:</span> <span class="pyg-p">(</span><span class="pyg-n">Value</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">NewValue</span><span class="pyg-p">)</span>
        <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">Key</span><span class="pyg-p">:</span><span class="pyg-n">NewValue</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-k">return</span> <span class="pyg-nb">Dictionary</span><span class="pyg-p">&lt;</span><span class="pyg-n">Key</span><span class="pyg-p">,</span> <span class="pyg-n">NewValue</span><span class="pyg-p">&gt;(</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-p">(</span><span class="pyg-n">key</span><span class="pyg-p">,</span> <span class="pyg-n">value</span><span class="pyg-p">)</span> <span class="pyg-k">in</span>
            <span class="pyg-k">return</span> <span class="pyg-p">(</span><span class="pyg-n">key</span><span class="pyg-p">,</span> <span class="pyg-n">transform</span><span class="pyg-p">(</span><span class="pyg-n">value</span><span class="pyg-p">))</span>
        <span class="pyg-p">})</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>

<span class="pyg-kd">let</span> <span class="pyg-nv">settingsAsStrings</span> <span class="pyg-p">=</span> <span class="pyg-n">settings</span><span class="pyg-p">.</span><span class="pyg-n">mapValues</span> <span class="pyg-p">{</span> <span class="pyg-n">setting</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">String</span> <span class="pyg-k">in</span>
    <span class="pyg-k">switch</span> <span class="pyg-n">setting</span> <span class="pyg-p">{</span>
    <span class="pyg-k">case</span> <span class="pyg-p">.</span><span class="pyg-n">text</span><span class="pyg-p">(</span><span class="pyg-kd">let</span> <span class="pyg-nv">text</span><span class="pyg-p">):</span> <span class="pyg-k">return</span> <span class="pyg-n">text</span>
    <span class="pyg-k">case</span> <span class="pyg-p">.</span><span class="pyg-n">int</span><span class="pyg-p">(</span><span class="pyg-kd">let</span> <span class="pyg-nv">number</span><span class="pyg-p">):</span> <span class="pyg-k">return</span> <span class="pyg-nb">String</span><span class="pyg-p">(</span><span class="pyg-n">number</span><span class="pyg-p">)</span>
    <span class="pyg-k">case</span> <span class="pyg-p">.</span><span class="pyg-n">bool</span><span class="pyg-p">(</span><span class="pyg-kd">let</span> <span class="pyg-nv">value</span><span class="pyg-p">):</span> <span class="pyg-k">return</span> <span class="pyg-nb">String</span><span class="pyg-p">(</span><span class="pyg-n">value</span><span class="pyg-p">)</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
<span class="pyg-n">settingsAsStrings</span> <span class="pyg-c1">// [&quot;Name&quot;: &quot;Jane\&#39;s iPhone&quot;, &quot;Airplane Mode&quot;: &quot;true&quot;]</span>
</code></pre></div>
<h3 id="hashable-要求">Hashable 要求</h3>
<p>字典其实是<a href="https://zh.wikipedia.org/wiki/哈希表">哈希表</a>。字典通过键的 <code>hashValue</code> 来为每个键指定一个位置，以及它所对应的存储。这也就是 <code>Dictionary</code> 要求它的 <code>Key</code> 类型需要遵守 <code>Hashable</code> 协议的原因。标准库中所有的基本数据类型都是遵守 <code>Hashable</code> 协议的，它们包括字符串，整数，浮点数以及布尔值。不带有关联值的枚举类型也会自动遵守 <code>Hashable</code>。</p>
<p>如果你想要将自定义的类型用作字典的键，那么你必须手动为你的类型添加 <code>Hashable</code> 并满足它，这需要你实现 <code>hashValue</code> 属性。另外，因为 <code>Hashable</code> 本身是对 <code>Equatable</code> 的扩展，因此你还需要为你的类型重载 <code>==</code> 运算符。你的实现必须保证哈希不变原则：两个同样的实例 (由你实现的 <code>==</code> 定义相同)，<strong>必须</strong>拥有同样地哈希值。不过反过来不必为真：两个相同哈希值的实例不一定需要相等。不同的哈希值的数量是有限的，然而很多可以被哈希的类型 (比如字符串) 的个数是无穷的。</p>
<p>哈希值可能重复这一特性，意味着 <code>Dictionary</code> 必须能够处理哈希碰撞。不必说，优秀的哈希算法总是能给出较少的碰撞，这将保持集合的性能特性。理想状态下，我们希望得到的哈希值在整个整数范围内平均分布。在极端的例子下，如果你的实现对所有实例返回相同的哈希值 (比如 0)，那么这个字典的查找性能将下降到 <span class="math inline"><em>O</em>(<em>n</em>)</span>。</p>
<p>优秀哈希算法的第二个特质是它应该很快。记住，在字典中进行插入，移除，或者查找时，这些哈希值都要被计算。如果你的 <code>hashValue</code> 实现要消耗太多时间，那么它很可能会拖慢你的程序，让你从字典的 <span class="math inline"><em>O</em>(1)</span> 特性中得到的好处损失殆尽。</p>
<p>写一个能同时做到这些要求的哈希算法并不容易。对于一些由本身就是 <code>Hashable</code> 的数据类型组成的类型来说，将成员的哈希值进行“异或” (XOR) 运算往往是一个不错的起点：</p>
<div class="highlight"><pre><code><span class="pyg-kd">struct</span> <span class="pyg-nc">Person</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">var</span> <span class="pyg-nv">name</span><span class="pyg-p">:</span> <span class="pyg-nb">String</span>
    <span class="pyg-kd">var</span> <span class="pyg-nv">zipCode</span><span class="pyg-p">:</span> <span class="pyg-nb">Int</span>
    <span class="pyg-kd">var</span> <span class="pyg-nv">birthday</span><span class="pyg-p">:</span> <span class="pyg-n">Date</span>
<span class="pyg-p">}</span>

<span class="pyg-kd">extension</span> <span class="pyg-nc">Person</span><span class="pyg-p">:</span> <span class="pyg-nb">Equatable</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">static</span> <span class="pyg-kd">func</span> <span class="pyg-p">==(</span><span class="pyg-n">lhs</span><span class="pyg-p">:</span> <span class="pyg-n">Person</span><span class="pyg-p">,</span> <span class="pyg-n">rhs</span><span class="pyg-p">:</span> <span class="pyg-n">Person</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">Bool</span> <span class="pyg-p">{</span>
        <span class="pyg-k">return</span> <span class="pyg-n">lhs</span><span class="pyg-p">.</span><span class="pyg-n">name</span> <span class="pyg-p">==</span> <span class="pyg-n">rhs</span><span class="pyg-p">.</span><span class="pyg-n">name</span>
            <span class="pyg-o">&amp;&amp;</span> <span class="pyg-n">lhs</span><span class="pyg-p">.</span><span class="pyg-n">zipCode</span> <span class="pyg-p">==</span> <span class="pyg-n">rhs</span><span class="pyg-p">.</span><span class="pyg-n">zipCode</span>
            <span class="pyg-o">&amp;&amp;</span> <span class="pyg-n">lhs</span><span class="pyg-p">.</span><span class="pyg-n">birthday</span> <span class="pyg-p">==</span> <span class="pyg-n">rhs</span><span class="pyg-p">.</span><span class="pyg-n">birthday</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>

<span class="pyg-kd">extension</span> <span class="pyg-nc">Person</span><span class="pyg-p">:</span> <span class="pyg-nb">Hashable</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">var</span> <span class="pyg-nv">hashValue</span><span class="pyg-p">:</span> <span class="pyg-nb">Int</span> <span class="pyg-p">{</span>
        <span class="pyg-k">return</span> <span class="pyg-n">name</span><span class="pyg-p">.</span><span class="pyg-n">hashValue</span> <span class="pyg-o">^</span> <span class="pyg-n">zipCode</span><span class="pyg-p">.</span><span class="pyg-n">hashValue</span> <span class="pyg-o">^</span> <span class="pyg-n">birthday</span><span class="pyg-p">.</span><span class="pyg-n">hashValue</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>异或计算方法的一个限制是，这个操作本身是左右对称的 (也就是说 <code>a ^ b == b ^ a</code>)，对于某些数据的哈希计算，这有时候会造成不必要的碰撞。你可以<a href="https://www.mikeash.com/pyblog/friday-qa-2010-06-18-implementing-equality-and-hashing.html">添加一个位旋转</a>并混合使用它们来避免这个问题。</p>
<p>最后，当你使用不具有值语义的类型 (比如可变的对象) 作为字典的键时，需要特别小心。如果你在将一个对象用作字典键后，改变了它的内容，它的哈希值和/或相等特性往往也会发生改变。这时候你将无法再在字典中找到它。这时字典会在错误的位置存储对象，这将导致字典内部存储的错误。对于值类型来说，因为字典中的键不会和复制的值共用存储，因此它也不会被从外部改变，所以不存在这个的问题。</p>
<h2 id="set">Set</h2>
<p>标准库中第三种主要的集合类型是集合 <code>Set</code> (虽然听起来有些别扭)。集合是一组无序的元素，每个元素只会出现一次。你可以将集合想像为一个只存储了键而没有存储值的字典。和 <code>Dictionary</code> 一样，<code>Set</code> 也是通过哈希表实现的，并拥有类似的性能特性和要求。测试集合中是否包含某个元素是一个常数时间的操作，和字典中的键一样，集合中的元素也必须满足 <code>Hashable</code>。</p>
<p>如果你需要高效地测试某个元素是否存在于序列中并且元素的顺序不重要时，使用集合是更好的选择 (同样的操作在数组中的复杂度是 <span class="math inline"><em>O</em>(<em>n</em>)</span>)。另外，当你需要保证序列中不出现重复元素时，也可以使用集合。</p>
<p><code>Set</code> 遵守 <code>ExpressibleByArrayLiteral</code> 协议，也就是说，我们可以用数组字面量的方式初始化一个集合：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">naturals</span><span class="pyg-p">:</span> <span class="pyg-n">Set</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span> <span class="pyg-mi">2</span><span class="pyg-p">,</span> <span class="pyg-mi">3</span><span class="pyg-p">,</span> <span class="pyg-mi">2</span><span class="pyg-p">]</span>
<span class="pyg-n">naturals</span> <span class="pyg-c1">// [2, 3, 1]</span>
<span class="pyg-n">naturals</span><span class="pyg-p">.</span><span class="pyg-bp">contains</span><span class="pyg-p">(</span><span class="pyg-mi">3</span><span class="pyg-p">)</span> <span class="pyg-c1">// true</span>
<span class="pyg-n">naturals</span><span class="pyg-p">.</span><span class="pyg-bp">contains</span><span class="pyg-p">(</span><span class="pyg-mi">0</span><span class="pyg-p">)</span> <span class="pyg-c1">// false</span>
</code></pre></div>
<p>注意数字 <code>2</code> 在集合中只出现了一次，重复的数字并没有被插入到集合中。</p>
<p>和其他集合类型一样，集合也支持我们已经见过的那些基本操作：你可以用 <code>for</code> 循环进行迭代，对它进行 <code>map</code> 或 <code>filter</code> 操作，或者做其他各种事情。</p>
<h3 id="集合代数">集合代数</h3>
<p>正如其名，集合 <code>Set</code> 和数学概念上的集合有着紧密关系；<code>Set</code> 也支持你在高中数学中学到的那些基本集合操作。比如，我们可以在一个集合中求另一个集合的<strong>补集</strong>：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">iPods</span><span class="pyg-p">:</span> <span class="pyg-n">Set</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;iPod touch&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPod nano&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPod mini&quot;</span><span class="pyg-p">,</span> 
    <span class="pyg-s">&quot;iPod shuffle&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPod Classic&quot;</span><span class="pyg-p">]</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">discontinuedIPods</span><span class="pyg-p">:</span> <span class="pyg-n">Set</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;iPod mini&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPod Classic&quot;</span><span class="pyg-p">]</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">currentIPods</span> <span class="pyg-p">=</span> <span class="pyg-n">iPods</span><span class="pyg-p">.</span><span class="pyg-n">subtracting</span><span class="pyg-p">(</span><span class="pyg-n">discontinuedIPods</span><span class="pyg-p">)</span>
<span class="pyg-c1">// [&quot;iPod shuffle&quot;, &quot;iPod nano&quot;, &quot;iPod touch&quot;]</span>
</code></pre></div>
<p>我们也可以求两个集合的<strong>交集</strong>，找出两个集合中都含有的元素：</p>
<div class="highlight"><pre><code><span class="pyg-kd">let</span> <span class="pyg-nv">touchscreen</span><span class="pyg-p">:</span> <span class="pyg-n">Set</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;iPhone&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPad&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPod touch&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;iPod nano&quot;</span><span class="pyg-p">]</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">iPodsWithTouch</span> <span class="pyg-p">=</span> <span class="pyg-n">iPods</span><span class="pyg-p">.</span><span class="pyg-n">intersection</span><span class="pyg-p">(</span><span class="pyg-n">touchscreen</span><span class="pyg-p">)</span>
<span class="pyg-c1">// [&quot;iPod touch&quot;, &quot;iPod nano&quot;]</span>
</code></pre></div>
<p>或者，我们能求两个集合的<strong>并集</strong>，将两个集合合并为一个 (当然，移除那些重复多余的)：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">discontinued</span><span class="pyg-p">:</span> <span class="pyg-n">Set</span> <span class="pyg-p">=</span> <span class="pyg-p">[</span><span class="pyg-s">&quot;iBook&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;Powerbook&quot;</span><span class="pyg-p">,</span> <span class="pyg-s">&quot;Power Mac&quot;</span><span class="pyg-p">]</span>
<span class="pyg-n">discontinued</span><span class="pyg-p">.</span><span class="pyg-n">formUnion</span><span class="pyg-p">(</span><span class="pyg-n">discontinuedIPods</span><span class="pyg-p">)</span>
<span class="pyg-c1">// [&quot;iBook&quot;, &quot;iPod mini&quot;, &quot;Powerbook&quot;, &quot;Power Mac&quot;, &quot;iPod Classic&quot;]</span>
</code></pre></div>
<p>这里我们使用了可变版本的 <code>formUnion</code> 来改变原来的集合 (正因如此，我们需要将原来的集合用 <code>var</code> 声明)。几乎所有的集合操作都有不可变版本以及可变版本的形式，后一种都以 <code>form...</code> 开头。想要了解更多的集合操作，可以看看 <code>SetAlgebra</code> 协议。</p>
<h3 id="索引集合和字符集合">索引集合和字符集合</h3>
<p><code>Set</code> 是标准库中唯一实现了 <code>SetAlgebra</code> 的类型，但是这个协议在 Foundation 中还被另外两个很有意思的类型实现了：那就是 <code>IndexSet</code> 和 <code>CharacterSet</code>。两者都是在 Swift 诞生之前很久就已经存在的东西了。包括这两个类在内的其他一些 Objective-C 类现在被完全以值类型的方式导入到 Swift 中，在此过程中，它们还遵守了一些常见的标准库协议。这对 Swift 开发者来说非常友好，这些类型立刻就变得熟悉了。</p>
<p><code>IndexSet</code> 表示了一个由正整数组成的集合。当然，你可以用 <code>Set&lt;Int&gt;</code> 来做这件事，但是 <code>IndexSet</code> 更加高效，因为它内部使用了一组范围列表进行实现。打个比方，现在你有一个含有 1000 个用户的 table view，你想要一个集合来管理已经被选中的用户的索引。使用 <code>Set&lt;Int&gt;</code> 的话，根据选中的个数不同，最多可能会要存储 1000 个元素。而 <code>IndexSet</code> 不太一样，它会存储连续的范围，也就是说，在选取前 500 行的情况下，<code>IndexSet</code> 里其实只存储了选择的首位和末位两个整数值。</p>
<p>不过，作为 <code>IndexSet</code> 的用户，你不需要关心这个数据结构的内部实现，所有这一切都隐藏在我们所熟知的 <code>SetAlgebra</code> 和 <code>Collection</code> 接口之下。(除非你确实需要直接操作内部的范围，对于这种需求，<code>IndexSet</code> 暴露了它的 <code>rangeView</code> 属性，代表了集合内部的范围)。举例来说，你可以向一个索引集合中添加一些范围，然后对这些索引 map 操作，就像它们是独立的元素一样：</p>
<div class="highlight"><pre><code><span class="pyg-kd">var</span> <span class="pyg-nv">indices</span> <span class="pyg-p">=</span> <span class="pyg-n">IndexSet</span><span class="pyg-p">()</span>
<span class="pyg-bp">indices</span><span class="pyg-p">.</span><span class="pyg-bp">insert</span><span class="pyg-p">(</span><span class="pyg-n">integersIn</span><span class="pyg-p">:</span> <span class="pyg-mf">1.</span><span class="pyg-p">.&lt;</span><span class="pyg-mi">5</span><span class="pyg-p">)</span>
<span class="pyg-bp">indices</span><span class="pyg-p">.</span><span class="pyg-bp">insert</span><span class="pyg-p">(</span><span class="pyg-n">integersIn</span><span class="pyg-p">:</span> <span class="pyg-mf">11.</span><span class="pyg-p">.&lt;</span><span class="pyg-mi">15</span><span class="pyg-p">)</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">evenIndices</span> <span class="pyg-p">=</span> <span class="pyg-bp">indices</span><span class="pyg-p">.</span><span class="pyg-bp">filter</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">%</span> <span class="pyg-mi">2</span> <span class="pyg-p">==</span> <span class="pyg-mi">0</span> <span class="pyg-p">}</span> <span class="pyg-c1">// [2, 4, 12, 14]</span>
</code></pre></div>
<p>同样地，<code>CharacterSet</code> 是一个高效的存储 Unicode 字符的集合。它经常被用来检查一个特定字符串是否只包含某个字符子集 (比如字母数字 <code>alphanumerics</code> 或者数字 <code>decimalDigits</code>) 中的字符。不过和 <code>IndexSet</code> 有所不同，<code>CharacterSet</code> 并不是一个集合类型。我们会在<a href="#strings">字符串</a>一章中对 <code>CharacterSet</code> 进行更多讨论。</p>
<h3 id="在闭包中使用集合">在闭包中使用集合</h3>
<p>就算不暴露给函数的调用者，字典和集合在函数中也会是非常好用的数据结构。我们如果想要为 <code>Sequence</code> 写一个扩展，来获取序列中所有的唯一元素，我们只需要将这些元素放到一个 <code>Set</code> 里，然后返回这个集合的内容就行了。不过，因为 <strong>Set</strong> 并没有定义顺序，所以这么做是<strong>不稳定</strong>的，输入的元素的顺序在结果中可能会不一致。为了解决这个问题，我们可以创建一个扩展来解决这个问题，在扩展方法内部我们还是使用 <code>Set</code> 来验证唯一性：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Sequence</span> <span class="pyg-k">where</span> <span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">:</span> <span class="pyg-nb">Hashable</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">unique</span><span class="pyg-p">()</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">]</span> <span class="pyg-p">{</span>
        <span class="pyg-kd">var</span> <span class="pyg-nv">seen</span><span class="pyg-p">:</span> <span class="pyg-n">Set</span><span class="pyg-p">&lt;</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">&gt;</span> <span class="pyg-p">=</span> <span class="pyg-p">[]</span>
        <span class="pyg-k">return</span> <span class="pyg-bp">filter</span> <span class="pyg-p">{</span>
            <span class="pyg-k">if</span> <span class="pyg-n">seen</span><span class="pyg-p">.</span><span class="pyg-bp">contains</span><span class="pyg-p">(</span><span class="pyg-nv">$0</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
                <span class="pyg-k">return</span> <span class="pyg-kc">false</span>
            <span class="pyg-p">}</span> <span class="pyg-k">else</span> <span class="pyg-p">{</span>
                <span class="pyg-n">seen</span><span class="pyg-p">.</span><span class="pyg-bp">insert</span><span class="pyg-p">(</span><span class="pyg-nv">$0</span><span class="pyg-p">)</span>
                <span class="pyg-k">return</span> <span class="pyg-kc">true</span>
            <span class="pyg-p">}</span>
        <span class="pyg-p">}</span>
    <span class="pyg-p">}</span>
<span class="pyg-p">}</span>

<span class="pyg-p">[</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">2</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">,</span><span class="pyg-mi">12</span><span class="pyg-p">,</span><span class="pyg-mi">1</span><span class="pyg-p">,</span><span class="pyg-mi">3</span><span class="pyg-p">,</span><span class="pyg-mi">4</span><span class="pyg-p">,</span><span class="pyg-mi">5</span><span class="pyg-p">,</span><span class="pyg-mi">6</span><span class="pyg-p">,</span><span class="pyg-mi">4</span><span class="pyg-p">,</span><span class="pyg-mi">6</span><span class="pyg-p">].</span><span class="pyg-n">unique</span><span class="pyg-p">()</span> <span class="pyg-c1">// [1, 2, 3, 12, 4, 5, 6]</span>
</code></pre></div>
<p>上面这个方法让我们可以找到序列中的所有不重复的元素，并且维持它们原来的顺序。在我们传递给 <code>filter</code> 的闭包中，我们使用了一个外部的 <code>seen</code> 变量，我们可以在闭包里访问和修改它的值。我们会在<a href="#functions">函数</a>一章中详细讨论它背后的技术。</p>
<h2 id="range">Range</h2>
<p>范围代表的是两个值的区间，它由上下边界进行定义。你可以通过 <code>..&lt;</code> 来创建一个不包含上边界的半开范围，或者使用 <code>...</code> 创建同时包含上下边界的闭合范围：</p>
<div class="highlight"><pre><code><span class="pyg-c1">// 0 到 9, 不包含 10</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">singleDigitNumbers</span> <span class="pyg-p">=</span> <span class="pyg-mf">0.</span><span class="pyg-p">.&lt;</span><span class="pyg-mi">10</span>

<span class="pyg-c1">// 包含 &quot;z&quot;</span>
<span class="pyg-kd">let</span> <span class="pyg-nv">lowercaseLetters</span> <span class="pyg-p">=</span> <span class="pyg-nb">Character</span><span class="pyg-p">(</span><span class="pyg-s">&quot;a&quot;</span><span class="pyg-p">)...</span><span class="pyg-nb">Character</span><span class="pyg-p">(</span><span class="pyg-s">&quot;z&quot;</span><span class="pyg-p">)</span>
</code></pre></div>
<p>范围看起来很自然地会是一个序列或者集合类型，但是可能出乎你的意料，它并非这两者之一 - 至少不是所有的范围都是序列或者集合类型。</p>
<p>在标准库中，现在有四种范围类型。它们能够被归类到一个 2x2 的矩阵中：</p>
<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">半开范围</th>
<th align="left">闭合范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">元素满足 <code>Comparable</code></td>
<td align="left"><code>Range</code></td>
<td align="left"><code>ClosedRange</code></td>
</tr>
<tr class="even">
<td align="left">元素满足 <code>Strideable</code></td>
<td align="left"><code>CountableRange</code></td>
<td align="left"><code>CountableClosedRange</code></td>
</tr>
<tr class="odd">
<td align="left">(以整数为步长)</td>
<td align="left"></td>
<td align="left"></td>
</tr>
</tbody>
</table>
<p>矩阵中的列对应了我们上面提到的两种生成范围的操作符，它们分别创建半开的 <code>[Countable]Range</code> 或者闭合的 <code>[Countable]ClosedRange</code>。半开和闭合的范围各有所用：</p>
<ul>
<li><p>只有<strong>半开范围</strong>能够表达<strong>空区间</strong>的概念 (当范围的上下边界相等时，比如 <code>5..&lt;5</code>)。</p></li>
<li><p>只有<strong>闭合范围</strong>能够包含它的元素类型所能表达的最大值 (比如 <code>0...Int.max</code>)。半开范围总是最少会有一个值比范围所表达的只要大。</p></li>
</ul>
<p>(在 Swift 2 中，即使一个范围是由 <code>...</code> 操作符创建的，在技术上来说，所有的范围实际上都是半开的。标准库中曾经用了额外的 <code>HalfOpenInterval</code> 和 <code>ClosedInterval</code> 类型来弥补这个问题，不过在 Swift 3 中它们被移除了。)</p>
<p>上表中的行区分了元素类型仅仅只是满足了 <code>Comparable</code> 的“普通”范围 (这是范围元素的最小要求)，以及那些元素满足 <code>Strideable</code> <strong>并且</strong>使用整数作为步长的范围。只有后一种范围是集合类型，它继承了我们在本章中所看到的一系列强大的功能和方法。</p>
<p>Swift 把这些功能更强的范围叫做<strong>可数范围</strong> (Countable Range)，这是因为只有这类范围可以被迭代。对于可数范围，因为类型的 <code>Stride</code> 需要用整数进行约束，所以整数和指针类型是这类范围的有效的边界值，但是浮点类型不是。如果你需要用连续的浮点值迭代某个可数范围，你需要使用 <code>stride(from:to:by)</code> 和 <code>stride(from:through:by)</code> 来创建一个这样的序列。</p>
<p>也就是说，你只能迭代某些范围。比如，我们上面定义的 <code>Character</code> 范围值就不是一个序列，下面的代码将无法工作：</p>
<div class="highlight"><pre><code><span class="pyg-k">for</span> <span class="pyg-n">char</span> <span class="pyg-k">in</span> <span class="pyg-n">lowercaseLetters</span> <span class="pyg-p">{</span>
    <span class="pyg-c1">// ...</span>
<span class="pyg-p">}</span>
<span class="pyg-c1">// 错误： &#39;ClosedRange&lt;Character&gt;&#39; 类型不遵守  &#39;Sequence&#39; 协议</span>
</code></pre></div>
<p>(对字符集进行迭代粗看起来应该没什么难度，但是实际却并非如此，这涉及到 Unicode 的相关知识，我们会在关于<a href="#strings">字符串</a>的章节中再深入这个问题。)</p>
<p>不过，下面的这种方式就没有问题，因为整数范围是一个可数范围，它是一个集合类型：</p>
<div class="highlight"><pre><code><span class="pyg-n">singleDigitNumbers</span><span class="pyg-p">.</span><span class="pyg-bp">map</span> <span class="pyg-p">{</span> <span class="pyg-nv">$0</span> <span class="pyg-o">*</span> <span class="pyg-nv">$0</span> <span class="pyg-p">}</span>
<span class="pyg-c1">// [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]</span>
</code></pre></div>
<p>现在标准库需要将可数范围与其他普通的范围分开，成为 <code>CountableRange</code> 和 <code>CountableClosedRange</code>。理想状态下，它们不应该被区分对待，但是不这么做的话，我们就需要为泛型参数满足约束的 <code>Range</code> 和 <code>ClosedRange</code> 添加扩展，来让它们满足集合类型的要求。我们会在下一章详细讨论这个方面的内容，我们现来看看如果这么做的话，代码会是怎样的：</p>
<div class="highlight"><pre><code><span class="pyg-c1">// Invalid in Swift 3</span>
<span class="pyg-kd">extension</span> <span class="pyg-nc">Range</span><span class="pyg-p">:</span> <span class="pyg-n">RandomAccessCollection</span>
    <span class="pyg-k">where</span> <span class="pyg-n">Bound</span><span class="pyg-p">:</span> <span class="pyg-nb">Strideable</span><span class="pyg-p">,</span> <span class="pyg-n">Bound</span><span class="pyg-p">.</span><span class="pyg-n">Stride</span><span class="pyg-p">:</span> <span class="pyg-n">SignedInteger</span>
<span class="pyg-p">{</span>
    <span class="pyg-c1">// 实现 RandomAccessCollection</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>啊咧，Swift 3 的类型系统并不支持这样的表达方式，你还不能针对泛型参数条件添加扩展，所以这里我们只能使用另外的类型。对于按照条件进行扩展的支持有望在 Swift 4 中被加入，届时 <code>CountableRange</code> 和 <code>CountableClosedRange</code> 也将会被归类到 <code>Range</code> 和 <code>ClosedRange</code> 中去。</p>
<p>半开的 <code>Range</code> 和闭合的 <code>ClosedRange</code> 之间的差异应该会一直存在，这个差异有时候会使得对范围的使用变得十分困难。比如说你有一个方法接受 <code>Range&lt;Character&gt;</code> 作为参数，而同时你想要将我们上面创建的闭合的字符范围传递给它。这时候你会惊奇地发现，这是不可能完成的任务！可能你无法解释，为什么没有一种方法将 <code>ClosedRange</code> 转换为 <code>Range</code> 呢？如果想要将一个闭合范围转换为等效的半开范围，那么你就需要找到原来的闭合范围上界的后一个元素。除非元素本身满足 <code>Strideable</code>，否则那是不可能的。而满足 <code>Strideable</code> 的元素所对应的则是可数范围。</p>
<p>也就是说，这个函数的调用者必须提供合适的类型。如果一个函数接受 <code>Range</code> 作为参数，那么你就不能用 <code>...</code> 来创建它。在实践中，我们不太确定这会带来多大的限制，因为大部分的范围都是基于整数的，不过可以肯定的是，这不太符合我们的直觉。</p>
<h1 id="collection-protocols">集合类型协议</h1>
<p>在前一章中，我们看到了 <code>Array</code>，<code>Dictionary</code> 和 <code>Set</code>，它们并非空中楼阁，而是建立在一系列由 Swift 标准库提供的用来处理元素序列的抽象之上的。这一章我们将讨论 <code>Sequence</code> 和 <code>Collection</code> 协议，它们构成了这套集合类型模型的基石。我们会研究这些协议是如何工作的，它们为什么要以这样的方式工作，以及你如何写出自己的序列和集合类型等话题。</p>
<h2 id="sequence">序列</h2>
<p><code>Sequence</code> 协议是集合类型结构中的基础。一个序列 (sequence) 代表的是一系列具有相同类型的值，你可以对这些值进行迭代。遍历一个序列最简单的方式是使用 <code>for</code> 循环：</p>
<div class="highlight"><pre><code><span class="pyg-k">for</span> <span class="pyg-n">element</span> <span class="pyg-k">in</span> <span class="pyg-n">someSequence</span> <span class="pyg-p">{</span>
    <span class="pyg-n">doSomething</span><span class="pyg-p">(</span><span class="pyg-n">with</span><span class="pyg-p">:</span> <span class="pyg-n">element</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p><code>Sequence</code> 协议提供了许多强大的功能，满足该协议的类型都可以直接使用这些功能。上面这样步进式的迭代元素的能力看起来十分简单，但它却是 <code>Sequence</code> 可以提供这些强大功能的基础。我们已经在上一章提到过不少这类功能了，每当你遇到一个能够针对元素序列进行的通用的操作，你都应该考虑将它实现在 <code>Sequence</code> 层的可能性。在本章和书中接下来的部分，我们将会看到许多这方面的例子。</p>
<p>满足 <code>Sequence</code> 协议的要求十分简单，你需要做的所有事情就是提供一个返回<strong>迭代器</strong> (iterator) 的 <code>makeIterator()</code> 方法：</p>
<div class="highlight"><pre><code><span class="pyg-kd">protocol</span> <span class="pyg-nc">Sequence</span> <span class="pyg-p">{</span>
    <span class="pyg-n">associatedtype</span> <span class="pyg-n">Iterator</span><span class="pyg-p">:</span> <span class="pyg-n">IteratorProtocol</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">makeIterator</span><span class="pyg-p">()</span> <span class="pyg-p">-&gt;</span> <span class="pyg-n">Iterator</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>对于迭代器，我们现在只能从 <code>Sequence</code> 的定义中知道它应该是一个满足 <code>IteratorProtocol</code> 协议的类型。所以我们首先来仔细看看迭代器是什么。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="collection" style="display: none;">集合类型</h2>


<h2 id="索引" style="display: none;">索引</h2>


<h2 id="切片-1" style="display: none;">切片</h2>


<h2 id="专门的集合类型" style="display: none;">专门的集合类型</h2>


<h2 id="总结" style="display: none;">总结</h2>

<h1 id="optionals">可选值</h1>
<h2 id="哨岗值">哨岗值</h2>
<p>在编程世界中有一种非常通用的模式，那就是某个操作是否要返回一个有效值。</p>
<p>当你在读取文件并读到文件末尾时，也许期望的是不返回值，就像下面的 C 代码这样：</p>
<div class="highlight"><pre><code><span class="pyg-kt">int</span> <span class="pyg-n">ch</span><span class="pyg-p">;</span>
<span class="pyg-k">while</span> <span class="pyg-p">((</span><span class="pyg-n">ch</span> <span class="pyg-o">=</span> <span class="pyg-n">getchar</span><span class="pyg-p">())</span> <span class="pyg-o">!=</span> <span class="pyg-n">EOF</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
    <span class="pyg-n">printf</span><span class="pyg-p">(</span><span class="pyg-s">&quot;Read character %c</span><span class="pyg-se">\n</span><span class="pyg-s">&quot;</span><span class="pyg-p">,</span> <span class="pyg-n">ch</span><span class="pyg-p">);</span>
<span class="pyg-p">}</span>
<span class="pyg-n">printf</span><span class="pyg-p">(</span><span class="pyg-s">&quot;Reached end-of-file</span><span class="pyg-se">\n</span><span class="pyg-s">&quot;</span><span class="pyg-p">);</span>
</code></pre></div>
<p><code>EOF</code> 只是对于 <code>-1</code> 的一个 <code>#define</code>。如果文件中还有其他字符，<code>getchar</code> 将会返回它们。如果到达文件末尾，<code>getchar</code> 将返回 <code>-1</code>。</p>
<p>又或者返回空值意味着“未找到”，就像 C++ 中的那样：</p>
<div class="highlight"><pre><code><span class="pyg-k">auto</span> <span class="pyg-n">vec</span> <span class="pyg-o">=</span> <span class="pyg-p">{</span><span class="pyg-mi">1</span><span class="pyg-p">,</span> <span class="pyg-mi">2</span><span class="pyg-p">,</span> <span class="pyg-mi">3</span><span class="pyg-p">};</span>
<span class="pyg-k">auto</span> <span class="pyg-n">iterator</span> <span class="pyg-o">=</span> <span class="pyg-n">std</span><span class="pyg-o">::</span><span class="pyg-n">find</span><span class="pyg-p">(</span><span class="pyg-n">vec</span><span class="pyg-p">.</span><span class="pyg-n">begin</span><span class="pyg-p">(),</span> <span class="pyg-n">vec</span><span class="pyg-p">.</span><span class="pyg-n">end</span><span class="pyg-p">(),</span> <span class="pyg-n">someValue</span><span class="pyg-p">);</span>
<span class="pyg-k">if</span> <span class="pyg-p">(</span><span class="pyg-n">iterator</span> <span class="pyg-o">!=</span> <span class="pyg-n">vec</span><span class="pyg-p">.</span><span class="pyg-n">end</span><span class="pyg-p">())</span> <span class="pyg-p">{</span>
    <span class="pyg-n">std</span><span class="pyg-o">::</span><span class="pyg-n">cout</span> <span class="pyg-o">&lt;&lt;</span> <span class="pyg-s">&quot;vec contains &quot;</span> <span class="pyg-o">&lt;&lt;</span> <span class="pyg-o">*</span><span class="pyg-n">iterator</span> <span class="pyg-o">&lt;&lt;</span> <span class="pyg-n">std</span><span class="pyg-o">::</span><span class="pyg-n">endl</span><span class="pyg-p">;</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>在这里，<code>vec.end()</code> 是容器的“末尾再超一位”的迭代器。这是一个特殊的迭代器，你可以用它来检查容器末尾，但是和 Swift 集合类型中的 <code>endIndex</code> 类似，你不能实际用它来获取这个值。<code>find</code> 使用它来表达容器中没有这样的值。</p>
<p>再或者，是因为函数处理过程中发生了某些错误，而导致没有值能被返回。其中，最臭名昭著的例子大概就是 null 指针了。下面这句看起来人畜无害的 Java 代码就将抛出一个 <code>NullPointerException</code>：</p>
<div class="highlight"><pre><code><span class="pyg-kt">int</span> <span class="pyg-n">i</span> <span class="pyg-o">=</span> <span class="pyg-n">Integer</span><span class="pyg-o">.</span><span class="pyg-na">getInteger</span><span class="pyg-o">(</span><span class="pyg-s">&quot;123&quot;</span><span class="pyg-o">)</span>
</code></pre></div>
<p>因为实际上 <code>Integer.getInteger</code> 做的事情并不是将字符串解析为整数，它实际上会去尝试获取一个叫做 “123” 的系统属性的整数值。因为系统中并不存在这样的属性，所以 <code>getInteger</code> 返回的是 null。当 null 被自动解开成一个 <code>int</code> 时，Java 将抛出异常。</p>
<p>这里还有一个 Objective-C 的例子：</p>
<div class="highlight"><pre><code><span class="pyg-p">[[</span><span class="pyg-bp">NSString</span> <span class="pyg-n">alloc</span><span class="pyg-p">]</span> <span class="pyg-nl">initWithContentsOfURL</span><span class="pyg-p">:</span><span class="pyg-n">url</span> 
    <span class="pyg-nl">encoding</span><span class="pyg-p">:</span><span class="pyg-n">NSUTF8StringEncoding</span> <span class="pyg-nl">error</span><span class="pyg-p">:</span><span class="pyg-o">&amp;</span><span class="pyg-n">e</span><span class="pyg-p">];</span>
</code></pre></div>
<p>在这里，<code>NSString</code> 有可能是 <code>nil</code>，在这种情况下 — 而且只有在这种情况下 — 你应该去检查错误指针。如果得到的 <code>NSString</code> 是非 <code>nil</code> 的话，错误指针并不一定会是有效值。</p>
<p>在上面所有例子中，这些函数都返回了一个“魔法”数来表示函数并没有返回真实的值。这样的值被称为“<a href="http://en.wikipedia.org/wiki/Sentinel_value">哨岗值</a>”。</p>
<p>不过这种策略是有问题的。返回的结果不管从哪个角度看都很像一个真实值。<code>-1</code> 的 <code>int</code> 值依然是一个有效的整数，但是你并不会想将它打印出来。<code>v.end()</code> 是一个迭代器，但是当你使用它的时候，结果却是未定义的。另外，所有人都会把你那陷于 <code>NullPointerException</code> 困境之中的 Java 程序当作一段笑话来看待。</p>
<p>哨岗值很容易产生问题，因为你可能会忘记检查哨岗值，并且不小心使用了它们。使用它们还需要预先的知识。有时候会有像是 C++ 的 <code>end</code> 迭代器这样的约定俗成的用法，有时候又没有这种约定。你通常需要查看文档才能知道需要怎么做。另外，一个函数也没有办法来表明自己<strong>不会</strong>失败。也就是说，当一个函数的调用返回指针时，这个指针有可能绝对不会是 <code>nil</code>。但是除了阅读文档之外，你并没有办法能知道这个事实。更甚者有可能文档本身就是错的。</p>
<p>在 Objective-C 中，对 <code>nil</code> 发送消息是安全的。如果这个消息签名返回一个对象，那么 <code>nil</code> 会被返回；如果消息返回的是一个结构体，那么它的值都将为零。不过，让我们来看看下面这个例子：</p>
<div class="highlight"><pre><code><span class="pyg-bp">NSString</span> <span class="pyg-o">*</span><span class="pyg-n">someString</span> <span class="pyg-o">=</span> <span class="pyg-p">...;</span>
<span class="pyg-k">if</span> <span class="pyg-p">([</span><span class="pyg-n">someString</span> <span class="pyg-nl">rangeOfString</span><span class="pyg-p">:</span><span class="pyg-s">@&quot;swift&quot;</span><span class="pyg-p">].</span><span class="pyg-n">location</span> <span class="pyg-o">!=</span> <span class="pyg-n">NSNotFound</span><span class="pyg-p">)</span> <span class="pyg-p">{</span>
    <span class="pyg-n">NSLog</span><span class="pyg-p">(</span><span class="pyg-s">@&quot;Someone mentioned swift!&quot;</span><span class="pyg-p">);</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>如果 <code>someString</code> 是 <code>nil</code>，那么 <code>rangeOfString:</code> 消息将返回一个值都为零的 <code>NSRange</code>。也就是说，<code>.location</code> 将为零，而 <code>NSNotFound</code> 被定义为 <code>NSIntegerMax</code>。这样一来，当 <code>someString</code> 是 <code>nil</code> 时，if 语句的内容将被执行。</p>
<p><a href="https://zh.wikipedia.org/wiki/東尼·霍爾">Tony Hoare</a> 在 1965 年设计了 null 引用，他对此设计表示痛心疾首，并将这个问题称为“价值十亿美元的错误”：</p>
<blockquote>
<p>那时候，我正在为一门面向对象语言 (ALGOL W) 设计第一个全面的引用类型系统。我的目标是在编译器自动执行的检查的保证下，确保对于引用的所有使用都是安全的。但是我没能抵挡住引入 null 引用的诱惑，因为它太容易实现了。这导致了不计其数的错误，漏洞以及系统崩溃。这个问题可能在过去四十年里造成了有十亿美元的损失。</p>
</blockquote>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="通过枚举解决魔法数的问题" style="display: none;">通过枚举解决魔法数的问题</h2>


<h2 id="可选值概览" style="display: none;">可选值概览</h2>


<h2 id="强制解包的时机" style="display: none;">强制解包的时机</h2>


<h2 id="多灾多难的隐式可选值" style="display: none;">多灾多难的隐式可选值</h2>


<h2 id="总结-1" style="display: none;">总结</h2>

<h1 id="structs-and-classes">结构体和类</h1>
<p>在 Swift 中，要存储结构化的数据，我们有多种不同的选择：结构体、枚举、类以及使用闭包捕获变量。在 Swift 标准库中，绝大多数的公开类型都是结构体，而枚举和类只占很小一部分。这可能是标准库中那些类型的特性使然，但是不管从什么方面这个事实都提醒我们 Swift 中结构体有多么重要。在 Swift 3 中，许多 Foundation 框架中的类现在有专门针对 Swift 构建的对应结构体类型了。在本章中，我们主要来看看结构体和类有哪些区别。我们可能不会花太多精力在枚举类型上，因为它的行为和结构体十分相似。</p>
<p>这里是结构体和类的主要不同点：</p>
<ul>
<li><p>结构体 (和枚举) 是<strong>值类型</strong>，而类是<strong>引用类型</strong>。在设计结构体时，我们可以要求编译器保证不可变性。而对于类来说，我们就得自己来确保这件事情。</p></li>
<li><p>内存的管理方式有所不同。结构体可以被直接持有及访问，但是类的实例只能通过引用来间接地访问。结构体不会被引用，但是会被复制。也就是说，结构体的持有者是唯一的，但是类却能有很多个持有者。</p></li>
<li><p>使用类，我们可以通过继承来共享代码。而结构体 (以及枚举) 是不能被继承的。想要在不同的结构体或者枚举之间共享代码，我们需要使用不同的技术，比如像是组合、泛型以及协议扩展等。</p></li>
</ul>
<p>在本章中，我们将会探索这些不同之处的细节。我们会从实体和值的区别谈起，然后继续讨论可变性所带来的问题。之后，我们会向你展示如何将一个引用类型封装到结构体里，这样我们就能够把它当作一个值类型来使用。最后，我们会详细谈谈两者之间内存管理上的差异，特别是引用类型与闭包一起使用时内存的管理方式的问题，以及如何避免引用循环。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="值类型" style="display: none;">值类型</h2>


<h2 id="可变性-1" style="display: none;">可变性</h2>


<h2 id="valuetypes" style="display: none;">结构体</h2>


<h2 id="写时复制" style="display: none;">写时复制</h2>


<h2 id="闭包和可变性" style="display: none;">闭包和可变性</h2>


<h2 id="memory" style="display: none;">内存</h2>


<h2 id="闭包和内存" style="display: none;">闭包和内存</h2>


<h2 id="闭包和内存-1" style="display: none;">闭包和内存</h2>


<h2 id="总结-2" style="display: none;">总结</h2>

<h1 id="functions">函数</h1>
<p>在开始本章之前，我们先来回顾一下关于函数的事情。如果你已经对头等函数 (first-class function) 的概念很熟悉了的话，你可以直接跳到<a href="#flexibility-through-functions">下一节</a>。但是如果你对此还有些懵懵懂懂的话，可以浏览一下这些内容。</p>
<p>要理解 Swift 中的函数和闭包，你需要切实弄明白三件事情，我们把这三件事按照重要程度进行了大致排序：</p>
<ol style="list-style-type: decimal">
<li><p>函数可以像 <code>Int</code> 或者 <code>String</code> 那样被赋值给变量，也可以作为另一个函数的输入参数，或者另一个函数的返回值来使用。</p></li>
<li><p>函数能够<strong>捕获</strong>存在于其局部作用域之外的变量。</p></li>
<li><p>有两种方法可以创建函数，一种是使用 <code>func</code> 关键字，另一种是 <code>{ }</code>。在 Swift 中，后一种被称为<strong>闭包表达式</strong>。</p></li>
</ol>
<p>有时候新接触闭包的人会认为重要顺序是反过来的，或者是遗漏其中的某点，或者把<strong>闭包</strong>和<strong>闭包表达式</strong>弄混淆了，这确实有时候会很让人迷惑。然而三者鼎足而立，互为补充，如果你少了其中任何一条，那么整个架构将不复存在。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="flexibility-through-functions" style="display: none;">函数的灵活性</h2>


<h2 id="局部函数和变量捕获" style="display: none;">局部函数和变量捕获</h2>


<h2 id="函数作为代理" style="display: none;">函数作为代理</h2>


<h2 id="inout-参数和可变方法" style="display: none;"><code>inout</code> 参数和可变方法</h2>


<h2 id="计算属性和下标" style="display: none;">计算属性和下标</h2>


<h2 id="自动闭包" style="display: none;">自动闭包</h2>


<h2 id="总结-3" style="display: none;">总结</h2>

<h1 id="strings">字符串</h1>
<h2 id="不再固定宽度">不再固定宽度</h2>
<p>事情原本很简单。ASCII 字符串就是由 0 到 127 之间的整数组成的序列。如果你把这种整数放到一个 8 比特的字节里，你甚至还能省出一个比特。由于每个字符宽度都是固定的，所以 ASCII 字符串可以被随机存取。</p>
<p>但这只有当你是用英语书写，并且受众是美国人时才是这样。其他国家和语言需要其他的字符 (就连说英语的英国人都需要一个 £ 符号) ，其中绝大多数需要的字符用七个比特是放不下的。ISO/IEC 8859 使用了额外的第八个比特，并且在 ASCII 范围外又定义了 16 种不同的编码。比如第 1 部分 (ISO/IEC 8859-1，又叫 Latin-1)，涵盖多种西欧语言；以及第 5 部分，涵盖那些使用西里尔 (俄语) 字母的语言。</p>
<p>但是这样依然很受限。如果你想按照 ISO/IEC 8859 来用土耳其语书写关于古希腊的内容，那你就不怎么走运了。因为你只能在第 7 部分 (Latin/Greek) 或者第 9 部分 (Turkish) 中选一种。另外，八个比特对于许多语言的编码来说依然是不够的。比如第 6 部分 (Latin/Arabic) 没有包括书写乌尔都语或者波斯语这样的阿拉伯字母语言所需要的字符。同时，在从 ASCII 的下半区替换了少量字符后，我们才能用八比特去编码基于拉丁字母但同时又有大量变音符组合的越南语。而其他东亚语言则完全不能被放入八个比特中。</p>
<p>当固定宽度的编码空间被用完后，你有两种选择：选择增加宽度或者切换到可变长的编码。最初的时候，Unicode 被定义成两个字节固定宽度的格式，这种格式现在被称为 UCS-2。不过这已经是现实问题出现之前的决定了，而且大家也都承认其实两个字节也还是不够用，四个字节的话在大多数情况下又太低效。</p>
<p>所以今天的 Unicode 是一个可变长格式。它的可变长特性有两种不同的意义：由编码单元 (code unit) 组成编码点 (code point)；由编码点组成字符。</p>
<p>Unicode 数据可以被编码成许多不同宽度的编码单元，最普遍的使用的是 8 比特 (UTF-8) 或者 16 比特 (UTF-16) 。UTF-8 额外的优势在于可以向后兼容 8 比特的 ASCII。这也使其超过 ASCII 成为网上最流行的编码方式。</p>
<p>Unicode 中的“编码点”在 Unicode 编码空间中是介于 <code>0</code> 到 <code>0x10FFFF</code> 之间的一个单一值。对于 UTF-32，一个编码点会占用一个编码单元。对于 UTF-8 一个编码点会占用一至四个编码单元。起始的 256 个 Unicode 编码点组成的字符和 Latin-1 中的一致。</p>
<p>Unicode “标量” (scalar) 是另一种单元。<strong>除了</strong>那些“代理” (surrogate) 编码点 (用来标示成对的 UTF-16 编码的开头或者结尾的编码点) 之外的所有编码点都是 Unicode 标量。标量在 Swift 字符串字面量中以 <code>&quot;\u{xxxx}&quot;</code> 来表示，其中的 xxxx 是十六进制的数字。比如欧元符号 € 在 Swift 中写作 <code>&quot;\u{20AC}&quot;</code>。</p>
<p>但是即使在编码时使用了 32 位编码单元，用户所认为的在屏幕上显示的“单个字符”可能仍需要由多个编码点组合而成。多数操作字符串的代码对 Unicode 可变长的本质都表现出一定程度的背离。而这会导致恼人的 bug。</p>
<p>Swift 的字符串实现竭尽全力去符合 Unicode 规范。当无法保证符合时，至少也要确保你知悉此事。这是有代价的。在 Swift 中 <code>String</code> 不是一个集合，相反，它是一种提供了多种方式来察看字符串的类型：你可以将其看作一组 <code>Character</code> 的集合；也可以看作一组 UTF-8、UTF-16 或者 Unicode 标量的集合。</p>
<p>Swift 的 <code>Character</code> 类型与其它表示方式不同。它可以编码任意数量的编码点，将它们合在一起可以组成单个“字位簇” (grapheme cluster)。我们很快就会看到这样的例子。</p>
<p>对于除了 UTF-16 之外的所有其它表示方式来说，只能通过索引来访问集合，<strong>而并不能</strong>使用随机存取。也就是说，测量两个索引之间的距离或者将一个索引步进后移若干步都不是 <span class="math inline"><em>O</em>(1)</span> 的操作。即使是 UTF-16 的表达，也只在你导入了 Foundation 后才是随机存取 (稍后会说明)。在进行繁重的文本处理时，一些表示方式可能会比其它方式更慢。在本章中，我们会来探寻这背后的原因，以及一些涉及功能和性能的技术。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="字符串和集合" style="display: none;">字符串和集合</h2>


<h2 id="简单的正则表达式匹配器" style="display: none;">简单的正则表达式匹配器</h2>


<h2 id="expressiblebystringliteral" style="display: none;"><code>ExpressibleByStringLiteral</code></h2>


<h2 id="string-的内部结构" style="display: none;"><code>String</code> 的内部结构</h2>


<h2 id="编码单元表示方式" style="display: none;">编码单元表示方式</h2>


<h2 id="customstringconvertible-和-customdebugstringconvertible" style="display: none;"><code>CustomStringConvertible</code> 和 <code>CustomDebugStringConvertible</code></h2>


<h2 id="文本输出流" style="display: none;">文本输出流</h2>


<h2 id="string-performance" style="display: none;">字符串性能</h2>


<h2 id="展望" style="display: none;">展望</h2>

<h1 id="error-handling">错误处理</h1>
<p>Swift 提供了很多种处理错误的方式，它甚至允许我们创建自己的错误处理机制。在<a href="#optionals">可选值</a>中，我们看到过可选值和断言 (assertions) 的方法。可选值意味着一个值可能存在，也可能不存在。我们在实际使用这个值之前，必须先对其确认并解包。断言会验证条件是否为 true，如果条件不满足的话，程序将会崩溃。</p>
<p>如果我们仔细看看标准库中类型的接口的话，我们可以得到一个何时应该使用可选值，而何时不应该使用的大概印象。可选值被广泛用来代表那些可以清楚地表明“不存在”或者“无效输入”的情况。比如说，你在使用一个字符串初始化 <code>Int</code> 时的初始化方法就是可失败的，如果输入不是有效的整数数字字符串，结果就将是 <code>nil</code>。另一个例子是当你在字典里查找一个键时，很多时候这个键并不存在于字典中。因此，字典的查找返回的是一个可选值结果。</p>
<p>对比数组，当通过一个指定的索引获取数组元素时，Swift 会直接返回这个元素，而不是一个包装后的可选值。这是因为一般来说程序员都应该知道某个数组索引是否有效。通过一个超出边界的索引值来访问数组通常被认为是程序员的错误，而这也会让你的应用崩溃。如果你不确定一个索引是否在某个范围内，你应该先对它进行检查。</p>
<p>断言是定位你代码中的 bug 的很好的工具。使用得当的话，它可以在你的程序偏离预订状态的时候尽早对你作出提醒。它们不应该被用来标记像是网络错误那样的<strong>预期中的错误</strong>。</p>
<p>注意数组其实也有返回可选值的访问方式。比如 <code>Collection</code> 的 <code>first</code> 和 <code>last</code> 属性就将在集合为空的时候返回 <code>nil</code>。Swift 标准库的开发者是有意进行这样的设计的，因为当集合可能为空时还需要访问这些值的情况还是比较容易出现的。</p>
<p>除了从方法中返回一个可选值以外，我们还可以通过将函数标记为 <code>throws</code> 来表示可能会出现失败的情况。除了调用者必须处理成功和失败的情况的语法以外，和可选值相比，能抛出异常的方法的主要区别在于，它可以给出一个包含所发生的错误的详细信息的值。</p>
<p>这个区别决定了我们要使用哪种方法来表示错误。回顾下 <code>Collection</code> 的 <code>first</code> 和 <code>last</code>，它们只可能有一种错误的情况，那就是集合为空时。返回一个包含很多信息的错误并不会让调用者获得更多的情报，因为错误的原因已经在可选值中表现了。对比执行网络请求的函数，情况就不一样了。在网络请求中，有很多事情可能会发生错误，比如当前没有网络连接，或者无法解析服务器的返回等等。带有信息的错误在这种情况下就对调用者非常有用了，它们可以根据错误的不同来采取不同的对应方法，或者可以提示用户到底哪里发生了问题。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="result-类型" style="display: none;"><code>Result</code> 类型</h2>


<h2 id="抛出和捕获" style="display: none;">抛出和捕获</h2>


<h2 id="带有类型的错误" style="display: none;">带有类型的错误</h2>


<h2 id="将错误桥接到-objective-c" style="display: none;">将错误桥接到 Objective-C</h2>


<h2 id="错误和函数参数" style="display: none;">错误和函数参数</h2>


<h2 id="使用-defer-进行清理" style="display: none;">使用 <code>defer</code> 进行清理</h2>


<h2 id="错误和可选值" style="display: none;">错误和可选值</h2>


<h2 id="错误链" style="display: none;">错误链</h2>


<h2 id="高阶函数和错误" style="display: none;">高阶函数和错误</h2>


<h2 id="总结-4" style="display: none;">总结</h2>

<h1 id="generics">泛型</h1>
<p>和大多数先进语言一样，Swift 拥有不少能被归类于<strong>泛型编程</strong>下的特性。使用泛型代码，你可以写出可重用的函数和数据结构，只要它们满足你所定义的约束，它们就能够适用于各种类型。比如，像是 <code>Array</code> 和 <code>Set</code> 等多个类型，实际上是它们中的元素类型就是泛型抽象。我们也可以创建泛型方法，它们可以对输入或者输出的类型进行泛型处理。<code>func identity&lt;A&gt;(input: A) -&gt; A</code> 就定义了一个可以作用于任意类型 <code>A</code> 的函数。某种意义上，我们甚至可以认为带有关联类型的协议是“泛型协议”。关联类型允许我们对特定的实现进行抽象。<code>IteratorProtocol</code> 协议就是一个这样的例子：它所生成的 <code>Element</code> 就是一个泛型。</p>
<p>泛型编程的目的是表达算法或者数据结构所要求的<strong>核心接口</strong>。比如，考虑<a href="#builtin-collections">内建集合</a>一章中的 <code>last(where:)</code> 函数。将它写为 <code>Array</code> 的一个扩展原本是最明显的选择，但是 <code>Array</code> 其实包含了很多 <code>last(where:)</code> 并不需要的特性。通过确认核心接口到底是什么，也就是说，找到想要实现的功能的最小需求，我们可以将这个函数定义在宽阔得多的类型范围内。在这个例子中，<code>last(where:)</code> 只有一个需求：它需要能够逆序遍历一系列元素。所以，将这个算法定义为 <code>Sequence</code> 的扩展是更好的选择。</p>
<p>在本章中，我们会研究如何书写泛型代码。我们会先看一看什么是重载 (overloading) ，因为这个概念和泛型紧密相关。然后我们会使用泛型的方式，基于不同的假设，来为一个算法提供多种实现。之后我们将讨论一些你在为集合书写泛型算法时会遇到的常见问题，了解这些问题后你就将能使用泛型数据类型来重构代码，并使它们易于测试，更加灵活。最后，我们会谈一谈编译器是如何处理泛型代码的，以及要如何优化我们的泛型代码以获取更高性能的问题。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="重载" style="display: none;">重载</h2>


<h2 id="对集合采用泛型操作" style="display: none;">对集合采用泛型操作</h2>


<h2 id="使用泛型进行代码设计" style="display: none;">使用泛型进行代码设计</h2>


<h2 id="泛型的工作方式" style="display: none;">泛型的工作方式</h2>


<h2 id="总结-5" style="display: none;">总结</h2>

<h1 id="protocols">协议</h1>
<p>在上一章，我们看到了函数和泛型可以帮助我们写出动态的程序。协议可以与函数和泛型协同工作，让我们代码的动态特性更加强大。</p>
<p>Swift 的协议和 Objective-C 的协议不同。Swift 协议可以被用作代理，也可以让你对接口进行抽象 (比如 <code>IteratorProtocol</code> 和 <code>Sequence</code>)。它们和 Objective-C 协议的最大不同在于我们可以让结构体和枚举类型满足协议。除此之外，Swift 协议还可以有关联类型。我们还可以通过协议扩展的方式为协议添加方法实现。我们会在面向协议编程的部分讨论所有这些内容。</p>
<p>协议允许我们进行动态派发，也就是说，在运行时程序会根据消息接收者的类型去选择正确的方法实现。不过，方法到底什么时候是动态派发，什么时候不是动态派发，有时却不是那么直观，并有可能造成令人意外的结果。我们会在下一节中看到这个问题。</p>
<p>普通的协议可以被当作类型约束使用，也可以当作独立的类型使用。带有关联类型或者 <code>Self</code> 约束的协议特殊一些：我们不能将它当作独立的类型来使用，而只能将它们用作类型约束。这听起来似乎是一个小限制，但是这在实践中让带有关联类型的协议成为了完全不同的东西。我们会在之后详细对此说明，我们还将讨论如何使用 (像是 <code>AnyIterator</code> 这样的) 类型消除的方法来让带有关联类型的协议更加易用。</p>
<p>在面向对象编程中，子类是在多个类之间共享代码的有效方式。一个子类将从它的父类继承所有的方法，然后选择重写其中的某些方法。比如，我们可以有一个 <code>AbstractSequence</code> 类，以及像是 <code>Array</code> 和 <code>Dictionary</code> 这样的子类。这么做的话，我们就可以在 <code>AbstractSequence</code> 中添加方法，所有的子类都将自动继承到这些方法。</p>
<p>不过在 Swift 中，<code>Sequence</code> 中的代码共享是通过协议和协议扩展来实现的。通过这么做，<code>Sequence</code> 协议和它的扩展在结构体和枚举这样的值类型中依然可用，而这些值类型是不支持子类继承的。</p>
<p>不再依赖于子类让类型系统更加灵活。在 Swift 中，一个类只能有一个父类。当我们创建一个类时，我们必须同时选择父类，而且我们只能选择一个父类，比如我们无法创建同时是 <code>AbstractSequence</code> 和 <code>Stream</code> 的子类的类。这有时候会成为问题。在 Cocoa 中就有一些例子，比如 <code>NSMutableAttributedString</code>，框架的设计师必须在 <code>NSAttributedString</code> 和 <code>NSMutableString</code> 之间选择一个父类。</p>
<p>有一些语言有多继承的特性，其中最著名的是 C++。但是这也导致了<a href="https://en.wikipedia.org/wiki/Multiple_inheritance#The_diamond_problem">钻石问题</a> (或者叫菱型缺陷) 的麻烦。举例来说，如果可以多继承，那么我们就可以让 <code>NSMutableAttributedString</code> 同时继承 <code>NSMutableString</code> 和 <code>NSAttributedString</code>。但是要是这两个类中都重写了 <code>NSString</code> 中的某个方法的时候，该怎么办？你可以通过选择其中一个方法来解决这个问题。但是要是这个方式是 <code>isEqual:</code> 这样的通用方法又该怎么处理呢？实际上，为多继承的类提供合适的行为真的是一件非常困难的事情。</p>
<p>因为多继承如此艰深难懂，所以绝大多数语言都不支持它。不过很多语言支持实现多个协议的特性。相比多继承，实现多个协议并没有那些问题。在 Swift 中，编译器会在方法冲突的时候警告我们。</p>
<p>协议扩展是一种可以在不共享基类的前提下共享代码的方法。协议定义了一组最小可行的方法集合，以供类型进行实现。而类型通过扩展的方式在这些最小方法上实现更多更复杂的特性。</p>
<p>比方说，要实现一个对任意序列进行排序的泛型算法，你需要两件事情。首先，你需要知道如何对要排序的元素进行迭代。其次，你需要能够比较这些元素的大小。就这么多。我们没有必要知道元素是如何被存储的，它们可以是在一个链表里，也可以在数组中，或者任何可以被迭代的容器中。我们也没有必要规定这些元素到底是什么，它们可以是字符串，整数，数据，或者是具体的像是“人”这样的数据类型。只要你在类型系统中提供了前面提到的那两个约束，我们就能实现 <code>sort</code> 函数：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">Sequence</span> <span class="pyg-k">where</span> <span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">:</span> <span class="pyg-nb">Comparable</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">func</span> <span class="pyg-nf">sorted</span><span class="pyg-p">()</span> <span class="pyg-p">-&gt;</span> <span class="pyg-p">[</span><span class="pyg-kc">Self</span><span class="pyg-p">.</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">]</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>想要实现原地排序的话，我们需要更多的构建代码。你需要能够通过索引访问元素，而不仅仅是进行线性迭代。<code>Collection</code> 满足这点，而 <code>MutableCollection</code> 在其之上加入了可变特性。最后，你需要能在常数时间内比较索引，并移动它们。<code>RandomAccessCollection</code> 正是用来保证这一点的。这些听起来可能有点复杂，但这正是我们能够实现一个原地排序所需要的前置条件：</p>
<div class="highlight"><pre><code><span class="pyg-kd">extension</span> <span class="pyg-nc">MutableCollection</span> <span class="pyg-k">where</span>
    <span class="pyg-kc">Self</span><span class="pyg-p">:</span> <span class="pyg-n">RandomAccessCollection</span><span class="pyg-p">,</span>
    <span class="pyg-kc">Self</span><span class="pyg-p">.</span><span class="pyg-n">Iterator</span><span class="pyg-p">.</span><span class="pyg-n">Element</span><span class="pyg-p">:</span> <span class="pyg-nb">Comparable</span> <span class="pyg-p">{</span>
        <span class="pyg-kr">mutating</span> <span class="pyg-kd">func</span> <span class="pyg-nf">sort</span><span class="pyg-p">()</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>通过协议来描述的最小功能可以很好地进行整合。你可以一点一点地为某个类型添加由不同协议所带来的不同功能。我们已经在<a href="#listsequence">集合协议</a>这章中一开始使用单个 <code>cons</code> 方法构建 <code>List</code> 类型的例子中看到过这样的应用场景了。我们让 <code>List</code> 实现了 <code>Sequence</code> 协议，而没有改变原来 <code>List</code> 结构体的实现。实际上，即使我们不是这个类型的原作者，也可以使用<strong>追溯建模</strong> (retroactive modeling) 的方式完成这件事情。通过添加 <code>Sequence</code> 的支持，我们直接获得了 <code>Sequence</code> 类型的所有扩展方法。</p>
<p>通过共同的父类来添加共享特性就没那么灵活了；在开发过程进行到一半的时候再决定为很多不同的类添加一个共同基类往往是很困难的。你想这么做的话，可能要面临大量的重构。而且如果你不是这些子类的拥有者的话，你直接就无法这么处理！</p>
<p>子类必须知道哪些方法是它们能够重写而不会破坏父类行为的。比如，当一个方法被重写时，子类可能会需要在合适的时机调用父类的方法，这个时机可能是方法开头，也可能是中间某个地方，又或者是在方法最后。通常这个调用时机是不可预估和指定的。另外，如果重写了错误的方法，子类还可能破坏父类的行为，却不会收到任何来自编译器的警告。</p>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="面向协议编程" style="display: none;">面向协议编程</h2>


<h2 id="协议的两种类型" style="display: none;">协议的两种类型</h2>


<h2 id="带有-self-的协议" style="display: none;">带有 <code>Self</code> 的协议</h2>


<h2 id="protocol-internals" style="display: none;">协议内幕</h2>


<h2 id="总结-6" style="display: none;">总结</h2>

<h1 id="interoperability">互用性</h1>
<p>Swift 最大的一个优点是它在于 C 或者 Objective-C 混合使用时，阻力非常小。Swift 可以自动桥接 Objective-C 的类型，它甚至可以桥接很多 C 的类型。这让我们可以使用现有的代码库，并且在其基础上提供一个漂亮的 API 接口。</p>
<p>在本章中，我们将创建一个对 <a href="http://commonmark.org">CommonMark</a> 库的封装。CommonMark 是 Markdown 的一种正式规范。如果你曾经在 GitHub 或者 Stack Overflow 上写过东西的话，那你应该已经用过 Markdown 了，它是一种很流行的用纯文本进行格式化的语法。在这个实践例子之后，我们会研究一下标准库中所提供的操作内存的工具，以及我们如何使用它们来于 C 代码进行交互。</p>
<h2 id="commonmark">实践：封装 CommonMark</h2>
<p>Swift 调用 C 代码的能力让我们可以很容易地使用大量已经存在的 C 的代码库。用 Swift 来对一个库的接口进行封装，一般来说要比重新发明轮子简单得多，工作量也少得多。同时，封装得当的话，我们的用户将不会看到这个封装和原生实现在类型安全以及易用性上有什么区别。我们只需要一个动态库和它的头文件，就可以开始进行封装工作了。</p>
<p>我们的例子中会用到 C 语言的 CommonMark 库，它是一个 CommonMark 标准的参考实现，这个实现非常高效，而且测试也很齐全。我们采用层层递进的方式进行封装，让我们可以通过 Swift 访问它。首先，我们围绕库所暴露给外界的不透明类型 (opaque type) 来创建一个简易的 Swift 类。然后，我们会将这个类封装到 Swift enum 中，并提供更符合 Swift 风格的 API。</p>
<h3 id="封装-c-代码库">封装 C 代码库</h3>
<p>让我们从封装一个单独的函数开始，这个函数接受 Markdown 格式的文本，并且将它转换为一个 HTML 字符串。C 接口看起来是这样的：</p>
<div class="highlight"><pre><code><span class="pyg-cm">/** 将 &#39;text&#39; (假设是 UTF-8 编码的字符串，且长度为 &#39;len&#39;)</span>
<span class="pyg-cm"> * 从 CommonMark Markdown 转换为 HTML, </span>
<span class="pyg-cm"> * 返回一个以 null 结尾的 UTF-8 编码的字符串。</span>
<span class="pyg-cm"> */</span>
<span class="pyg-kt">char</span> <span class="pyg-o">*</span><span class="pyg-nf">cmark_markdown_to_html</span><span class="pyg-p">(</span><span class="pyg-k">const</span> <span class="pyg-kt">char</span> <span class="pyg-o">*</span><span class="pyg-n">text</span><span class="pyg-p">,</span> <span class="pyg-kt">int</span> <span class="pyg-n">len</span><span class="pyg-p">,</span> <span class="pyg-kt">int</span> <span class="pyg-n">options</span><span class="pyg-p">);</span>
</code></pre></div>
<p>第一个参数的 C 字符串在被导入到 Swift 中时，会变为指向一系列 <code>Int8</code> 值的 <code>UnsafePointer</code> 指针。通过文档，我们知道这些值是 UTF-8 的编码单元。<code>len</code> 参数是字符串的长度：</p>
<div class="highlight"><pre><code><span class="pyg-kd">func</span> <span class="pyg-nf">cmark_markdown_to_html</span>
    <span class="pyg-p">(</span><span class="pyg-kc">_</span> <span class="pyg-n">text</span><span class="pyg-p">:</span> <span class="pyg-nb">UnsafePointer</span><span class="pyg-p">&lt;</span><span class="pyg-nb">Int8</span><span class="pyg-p">&gt;</span><span class="pyg-o">!</span><span class="pyg-p">,</span> <span class="pyg-kc">_</span> <span class="pyg-n">len</span><span class="pyg-p">:</span> <span class="pyg-nb">Int</span><span class="pyg-p">,</span> <span class="pyg-kc">_</span> <span class="pyg-n">options</span><span class="pyg-p">:</span> <span class="pyg-nb">Int32</span><span class="pyg-p">)</span>
    <span class="pyg-p">-&gt;</span> <span class="pyg-nb">UnsafeMutablePointer</span><span class="pyg-p">&lt;</span><span class="pyg-nb">Int8</span><span class="pyg-p">&gt;</span><span class="pyg-o">!</span>
</code></pre></div>
<p>当然了，我们想要封装的函数能接受 Swift 字符串，你可能会想到我们需要将 Swift 字符串转换为一个 <code>Int8</code> 指针。不过，桥接 Swift 字符串和 C 字符串是一个非常常见的操作，所以 Swift 为我们自动做了这件事情。对于 <code>len</code> 参数我们需要特别小心，因为这里函数需要的是 UTF-8 编码的字符串的字节数，并不是字符串中的字符数。我们可以通过 Swift 字符串的 <code>utf8</code> 形式的 <code>count</code> 来获取正确的值，对于选项值 options，我们传入 0 就可以了：</p>
<div class="highlight"><pre><code><span class="pyg-kd">func</span> <span class="pyg-nf">markdownToHtml</span><span class="pyg-p">(</span><span class="pyg-n">input</span><span class="pyg-p">:</span> <span class="pyg-nb">String</span><span class="pyg-p">)</span> <span class="pyg-p">-&gt;</span> <span class="pyg-nb">String</span> <span class="pyg-p">{</span>
    <span class="pyg-kd">let</span> <span class="pyg-nv">outString</span> <span class="pyg-p">=</span> <span class="pyg-n">cmark_markdown_to_html</span><span class="pyg-p">(</span><span class="pyg-n">input</span><span class="pyg-p">,</span> <span class="pyg-n">input</span><span class="pyg-p">.</span><span class="pyg-n">utf8</span><span class="pyg-p">.</span><span class="pyg-bp">count</span><span class="pyg-p">,</span> <span class="pyg-mi">0</span><span class="pyg-p">)</span><span class="pyg-o">!</span>
    <span class="pyg-k">return</span> <span class="pyg-nb">String</span><span class="pyg-p">(</span><span class="pyg-n">cString</span><span class="pyg-p">:</span> <span class="pyg-n">outString</span><span class="pyg-p">)</span>
<span class="pyg-p">}</span>
</code></pre></div>
<p>在上面的实现中，我们对初始化的字符串进行了强制解包。因为我们知道 <code>cmark_markdown_to_html</code> 肯定会返回一个有效的字符串，所以这么做是安全的。通过在方法内部进行强制解包，代码库的用户就可以不必在调用 <code>markdownToHTML</code> 的时候关心可选值的问题了，返回的结果一定不会为 <code>nil</code>。</p>
<blockquote>
<p>注意，在 Swift 自动将 String 原生字符串和 C 字符串之间桥接转换时，假设了你所调用的 C 函数希望的是 UTF-8 编码的字符串。这在绝大多数情况下是正确的，但是也有一些需要不同编码字符串的 C API，这时你就不能用自动桥接了。不过，通常来说转换一下也很简单。比如，如果你需要一个 UTF-16 编码点的数组的话，可以使用 <code>Array(string.utf16)</code>。</p>
</blockquote>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<router-link to="/goodcart"  >购买本书</router-link>，或者<router-link to="/products/advanced-swift/">点击这里</router-link>了解更多关于本书的内容。</div>
  </div>
</div>


<h2 id="低层级类型概览" style="display: none;">低层级类型概览</h2>


<h2 id="函数指针" style="display: none;">函数指针</h2>


    </div>
    <hr>