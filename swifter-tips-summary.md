<hr>
    <div class="article-content">
<h1>Swift 新元素</h1>

<h1 id="toc_0">柯里化 (Currying)</h1>

<p>Swift 里可以将方法进行<a href="http://en.wikipedia.org/wiki/Currying">柯里化 (Currying)</a>，这是也就是把接受多个参数的方法进行一些变形，使其更加灵活的方法。函数式的编程思想贯穿于 Swift 中，而函数的柯里化正是这门语言函数式特点的重要表现。</p>

<p>举个例子，下面的函数简单地将输入的数字加 1：</p>

<pre><code class="language-swift">func addOne(num: Int) -&gt; Int {
    return num + 1
}
</code></pre>

<p>这个函数所表达的内容非常有限，如果我们之后还需要一个将输入数字加 2，或者加 3 的函数，可能不得不类似地去定义返回为 <code>num + 2</code> 或者 <code>num + 3</code> 的版本。有没有更通用的方法呢？我们其实可以定义一个通用的函数，它将接受需要与输入数字相加的数，并返回一个函数。返回的函数将接受输入数字本身，然后进行操作：</p>

<pre><code class="language-swift">func addTo(_ adder: Int) -&gt; (Int) -&gt; Int {
    return {
        num in
        return num + adder
    }
}
</code></pre>

<p>有了 <code>addTo</code>，我们现在就能轻易写出像是 <code>addOne</code> 或者 <code>addTwo</code> 这样的函数了：</p>

<pre><code class="language-swift">let addTwo = addTo(2)    // addTwo: Int -&gt; Int
let result = addTwo(6)   // result = 8
</code></pre>

<p>再举一个例子，我们可以创建一个比较大小的函数：</p>

<pre><code class="language-swift">func greaterThan(_ comparer: Int) -&gt; (Int) -&gt; Bool {
    return { $0 &gt; comparer }
}

let greaterThan10 = greaterThan(10);

greaterThan10(13)    // =&gt; true
greaterThan10(9)     // =&gt; false
</code></pre>

<p>柯里化是一种量产相似方法的好办法，可以通过柯里化一个方法模板来避免写出很多重复代码，也方便了今后维护。</p>

<p>举一个实际应用时候的例子，在 <a href="selector.md">Selector</a> 一节中，我们提到了在 Swift 中 <code>Selector</code> 只能使用字符串在生成。这面临一个很严重的问题，就是难以重构，并且无法在编译期间进行检查，其实这是十分危险的行为。但是 target-action 又是 Cocoa 中如此重要的一种设计模式，无论如何我们都想安全地使用的话，应该怎么办呢？一种可能的解决方式就是利用方法的柯里化。Ole Begemann 在<a href="http://oleb.net/blog/2014/07/swift-instance-methods-curried-functions/?utm_campaign=iOS_Dev_Weekly_Issue_157&amp;utm_medium=email&amp;utm_source=iOS%2BDev%2BWeekly">这篇帖子</a>里提到了一种很好封装，这为我们如何借助柯里化，安全地改造和利用 target-action 提供了不少思路。</p>

<pre><code class="language-swift">protocol TargetAction {
    func performAction()
}

struct TargetActionWrapper&lt;T: AnyObject&gt;:
                            TargetAction {
    weak var target: T?
    let action: (T) -&gt; () -&gt; ()

    func performAction() -&gt; () {
        if let t = target {
            action(t)()
        }
    }
}

enum ControlEvent {
    case TouchUpInside
    case ValueChanged
    // ...
}


class Control {
    var actions = [ControlEvent: TargetAction]()

    func setTarget&lt;T: AnyObject&gt;(target: T,
                   action: @escaping (T) -&gt; () -&gt; (),
                controlEvent: ControlEvent) {

        actions[controlEvent] = TargetActionWrapper(
            target: target, action: action)
    }

    func removeTargetForControlEvent(controlEvent: ControlEvent) {
        actions[controlEvent] = nil
    }

    func performActionForControlEvent(controlEvent: ControlEvent) {
        actions[controlEvent]?.performAction()
    }
}
</code></pre>

<h1 id="toc_0">模式匹配</h1>

<p>在之前的<a href="regex.md">正则表达式</a>中，我们实现了 <code>=~</code> 操作符来完成简单的正则匹配。虽然在 Swift 中没有内置的正则表达式支持，但是一个和正则匹配有些相似的特性其实是内置于 Swift 中的，那就是<a href="http://en.wikipedia.org/wiki/Pattern_matching">模式匹配</a>。</p>

<p>当然，从概念上来说正则匹配只是模式匹配的一个子集，但是在 Swift 里现在的模式匹配还很初级，也很简单，只能支持最简单的相等匹配和范围匹配。在 Swift 中，使用 <code>~=</code> 来表示模式匹配的操作符。如果我们看看 API 的话，可以看到这个操作符有下面几种版本：</p>

<pre><code class="language-swift">func ~=&lt;T : Equatable&gt;(a: T, b: T) -&gt; Bool

func ~=&lt;T&gt;(lhs: _OptionalNilComparisonType, rhs: T?) -&gt; Bool

func ~=&lt;I : IntervalType&gt;(pattern: I, value: I.Bound) -&gt; Bool

</code></pre>

<p>从上至下在操作符左右两边分别接收可以判等的类型，可以与 <code>nil</code> 比较的类型，以及一个范围输入和某个特定值，返回值很明了，都是是否匹配成功的 <code>Bool</code> 值。你是否有想起些什么呢..没错，就是 Swift 中非常强大的 switch，我们来看看 switch 的几种常见用法吧：</p>

<ol>
<li><p>可以判等的类型的判断</p>

<pre><code class="language-swift">let password = &quot;akfuv(3&quot;
switch password {
    case &quot;akfuv(3&quot;: print(&quot;密码通过&quot;)
    default:        print(&quot;验证失败&quot;)
}
</code></pre></li>
<li><p>对 Optional 的判断</p>

<pre><code class="language-swift">let num: Int? = nil
switch num {
    case nil: print(&quot;没值&quot;)
    default:  print(&quot;\(num!)&quot;)
}
</code></pre></li>
<li><p>对范围的判断</p>

<pre><code class="language-swift">let x = 0.5
switch x {
    case -1.0...1.0: print(&quot;区间内&quot;)
    default: print(&quot;区间外&quot;)
}
</code></pre></li>
</ol>

<p>这并不是巧合。没错，Swift 的 <code>switch</code> 就是使用了 <code>~=</code> 操作符进行模式匹配，<code>case</code> 指定的模式作为左参数输入，而等待匹配的被 <code>switch</code> 的元素作为操作符的右侧参数。只不过这个调用是由 Swift 隐式地完成的。于是我们可以发挥想象的地方就很多了，比如在 <code>switch</code> 中做 <code>case</code> 判断的时候，我们完全可以使用我们自定义的模式匹配方法来进行判断，有时候这会让代码变得非常简洁，具有条理。我们只需要按照需求重载 <code>~=</code> 操作符就行了，接下来我们通过一个使用正则表达式做匹配的例子加以说明。</p>

<p>首先我们要做的是重载 <code>~=</code> 操作符，让它接受一个 <code>NSRegularExpression</code> 作为模式，去匹配输入的 <code>String</code>：</p>

<pre><code class="language-swift">func ~=(pattern: NSRegularExpression, input: String) -&gt; Bool {
    return pattern.numberOfMatches(in: input,
        options: [],
        range: NSRange(location: 0, length: input.characters.count)) &gt; 0
}
</code></pre>

<p>然后为了简便起见，我们再添加一个将字符串转换为 <code>NSRegularExpression</code> 的操作符 (当然也可以使用 <a href="literal.md"><code>StringLiteralConvertible</code></a>，但是它不是这个 tip 的主题，在此就先不使用它了)：</p>

<pre><code class="language-swift">prefix operator ~/

prefix func ~/(pattern: String) -&gt; NSRegularExpression {
    return NSRegularExpression(pattern: pattern, options: nil, error: nil)
}
</code></pre>

<p>现在，我们在 <code>case</code> 语句里使用正则表达式的话，就可以去匹配被 <code>switch</code> 的字符串了：</p>

<pre><code class="language-swift">let contact = (&quot;http://onevcat.com&quot;, &quot;onev@onevcat.com&quot;)

let mailRegex: NSRegularExpression
let siteRegex: NSRegularExpression

mailRegex = 
    try ~/&quot;^([a-z0-9_\\.-]+)@([\\da-z\\.-]+)\\.([a-z\\.]{2,6})$&quot;
siteRegex = 
    try ~/&quot;^(https?:\\/\\/)?([\\da-z\\.-]+)\\.([a-z\\.]{2,6})([\\/\\w \\.-]*)*\\/?$&quot;

switch contact {
    case (siteRegex, mailRegex): print(&quot;同时拥有有效的网站和邮箱&quot;)
    case (_, mailRegex): print(&quot;只拥有有效的邮箱&quot;)
    case (siteRegex, _): print(&uot;只拥有有效的网站&quot;)
    default: print(&quot;嘛都没有&quot;)
}

// 输出
// 同时拥有网站和邮箱
</code></pre>

<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<a href="https://sites.fastspring.com/onevcat/instant/swifter-tips" target="_blank">购买本书</a>，或者<a href="/products/swifter-tips/">点击这里</a>了解更多关于本书的内容。</div>
  </div>
</div>

<h1>从 Objective-C/C 到 Swift</h1>

<h1 id="toc_0">Selector</h1>

<p><code>@selector</code> 是 Objective-C 时代的一个关键字，它可以将一个方法转换并赋值给一个 <code>SEL</code> 类型，它的表现很类似一个动态的函数指针。在 Objective-C 时 selector 非常常用，从设定 target-action，到自举询问是否响应某个方法，再到指定接受通知时需要调用的方法等等，都是由 selector 来负责的。在 Objective-C 里生成一个 selector 的方法一般是这个样子的：</p>

<pre><code class="language-objc">-(void) callMe {
    //...
}

-(void) callMeWithParam:(id)obj {
    //...
}

SEL someMethod = @selector(callMe);
SEL anotherMethod = @selector(callMeWithParam:);

// 或者也可以使用 NSSelectorFromString
// SEL someMethod = NSSelectorFromString(@&quot;callMe&quot;);
// SEL anotherMethod = NSSelectorFromString(@&quot;callMeWithParam:&quot;);
</code></pre>

<p>一般为了方便，很多人会选择使用 <code>@selector</code>，但是如果要追求灵活的话，可能会更愿意使用 <code>NSSelectorFromString</code> 的版本 -- 因为我们可以在运行时动态生成字符串，从而通过方法的名字来调用到对应的方法。</p>

<p>在 Swift 中没有 <code>@selector</code> 了，取而代之，从 Swift 2.2 开始我们使用 <code>#selector</code> 来从暴露给 Objective-C 的代码中获取一个 selector。类似地，在 Swift 里对应原来 <code>SEL</code> 的类型是一个叫做 <code>Selector</code> 的结构体。像上面的两个例子在 Swift 中等效的写法是：</p>

<pre><code class="language-swift">func callMe() {
    //...
}

func callMeWithParam(obj: AnyObject!) {
    //...
}

let someMethod = #selector(callMe)
let anotherMethod = #selector(callMeWithParam(obj:))
</code></pre>

<p>和 Objective-C 时一样，记得在 <code>callMeWithParam</code> 后面加上冒号和参数名 (:)，这才是完整的方法名字。多个参数的方法名也和原来类似，是这个样子：</p>

<pre><code class="language-swift">func turn(by angle: Int, speed: Float) {
    //...
}

let method = #selector(turn(by:speed:))
</code></pre>

<p>最后需要注意的是，selector 其实是 Objective-C runtime 的概念，如果你的 selector 对应的方法只在 Swift 中可见的话 (也就是说它是一个 Swift 中的 private 方法)，在调用这个 selector 时你会遇到一个 unrecognized selector 错误：</p>

<blockquote>
<h3 id="toc_1">这是错误代码</h3>

<pre><code class="language-swift">private func callMe() {
     //...
}

NSTimer.scheduledTimerWithTimeInterval(1, target: self,
            selector:#selector(callMe), userInfo: nil, repeats: true)
</code></pre>
</blockquote>

<p>正确的做法是在 <code>private</code> 前面加上 <code>@objc</code> 关键字，这样运行时就能找到对应的方法了。</p>

<pre><code class="language-swift">@objc private func callMe() {
    //...
}

NSTimer.scheduledTimerWithTimeInterval(1, target: self,
             selector:#selector(callMe), userInfo: nil, repeats: true)
</code></pre>

<p>最后，值得一提的是，如果方法名字在方法所在域内是唯一的话，我们可以简单地只是用方法的名字来作为 <code>#selector</code> 的内容。相比于前面带有冒号的完整的形式来说，这么写起来会方便一些：</p>

<pre><code class="language-swift">let someMethod = #selector(callMe)
let anotherMethod = #selector(callMeWithParam)
let method = #selector(turn)
</code></pre>

<p>但是，如果在同一个作用域中存在同样名字的两个方法，即使它们的函数签名不相同，Swift 编译器也不允许编译通过：</p>

<pre><code>func commonFunc() {
    
}

func commonFunc(input: Int) -&gt; Int {
    return input
}

let method = #selector(commonFunc)
// 编译错误，`commonFunc` 有歧义
</code></pre>

<p>对于这种问题，我们可以通过将方法进行强制转换来使用：</p>

<pre><code class="language-swift">let method1 = #selector(commonFunc as ()-&gt;())
let method2 = #selector(commonFunc as (Int)-&gt;Int)
</code></pre>


<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<a href="https://sites.fastspring.com/onevcat/instant/swifter-tips" target="_blank">购买本书</a>，或者<a href="/products/swifter-tips/">点击这里</a>了解更多关于本书的内容。</div>
  </div>
</div>

<h1>Swift 与开发环境及一些实践</h1>

<h1 id="toc_0">print 和 debugPrint</h1>

<p>在定义和实现一个类型的时候，Swift 中的一种非常常见，也是非常先进的做法是先定义最简单的类型结构，然后再通过扩展 (extension) 的方式来实现为数众多的协议和各种各样的功能。这种按照特性进行分离的设计理念对于功能的可扩展性的提升很有帮助。虽然在 Objective-C 中我们也可以通过类似的 protocol + category 的形式完成类似的事情，但 Swift 相比于原来的方式更加简单快捷。</p>

<p><code>CustomStringConvertible</code> 和 <code>CustomDebugStringConvertible</code> 这两个协议就是很好的例子。对于一个普通的对象，我们在调用 <code>print</code> 对其进行打印时只能打印出它的类型：</p>

<pre><code class="language-swift">class MyClass {
    var num: Int
    init() {
        num = 1
    }
}

let obj = MyClass()
print(obj)
// MyClass
</code></pre>

<p>对于 struct 来说，情况好一些。打印一个 struct 实例的话，会列举出它所有成员的名字和值：比如我们有一个日历应用存储了一些会议预约，model 类型包括会议的地点，位置和参与者的名字：</p>

<pre><code class="language-swift">struct Meeting {
    var date: NSDate
    var place: String
    var attendeeName: String
}

let meeting = Meeting(date: NSDate(timeIntervalSinceNow: 86400),
                     place: &quot;会议室B1&quot;,
              attendeeName: &quot;小明&quot;)
print(meeting)
// 输出:
// Meeting(date: 2015-08-10 03:15:55 +0000, 
//          place: &quot;会议室B1&quot;, attendeeName: &quot;小明&quot;)
</code></pre>

<p>直接这样进行输出对了解对象的信息很有帮助，但也会存在问题。首先如果实例很复杂，我们将很难在其中找到想要的结果；其次，对于 <code>class</code> 的对象来说，只能得到类型名字，可以说是毫无帮助。我们可以对输出进行一些修饰，让它看起来好一些，比如使用格式化输出的方式：</p>

<pre><code class="language-swift">print(&quot;于 \(meeting.date) 在 \(meeting.place) 与 \(meeting.attendeeName) 进行会议&quot;)
// 输出:
// 于 2014-08-25 11:05:28 +0000 在 会议室B1 与 小明 进行会议
</code></pre>

<p>但是如果每次输出的时候，我们都去写这么一大串东西的话，显然是不可接受的。正确的做法应该是使用 <code>CustomStringConvertible</code> 协议，这个协议定义了将该类型实例输出时所用的字符串。相对于直接在原来的类型定义中进行更改，我们更应该倾向于使用一个 <code>extension</code>，这样不会使原来的核心部分的代码变乱变脏，是一种很好的代码组织的形式：</p>

<pre><code class="language-swift">extension Meeting: CustomStringConvertible {
    var description: String {
        return &quot;于 \(self.date) 在 \(self.place) 与 \(self.attendeeName) 进行会议&quot;
    }
}
</code></pre>

<p>这样，再当我们使用 <code>print</code> 时，就不再需要去做格式化，而是简单地将实例进行打印就可以了：</p>

<pre><code class="language-swift">print(meeting)
// 输出:
// 于 2015-08-10 03:33:34 +0000 在 会议室B1 与 小明 进行会议
</code></pre>

<p><code>CustomDebugStringConvertible</code> 与 <code>CustomStringConvertible</code> 的作用很类似，但是仅发生在调试中使用 debugger 来进行打印的时候的输出。对于实现了 <code>CustomDebugStringConvertible</code> 协议的类型，我们可以在给 <code>meeting</code> 赋值后设置断点并在控制台使用类似 <code>po meeting</code> 的命令进行打印，控制台输出将为 <code>CustomDebugStringConvertible</code> 中定义的 <code>debugDescription</code> 返回的字符串。</p>


<div class="panel panel-warning">
  <div class="panel-heading">
    <h3 class="panel-title">抱歉，本章内容不包含于预览中</h3>
  </div>
  <div class="panel-body">
    <div>请考虑<a href="https://sites.fastspring.com/onevcat/instant/swifter-tips" target="_blank">购买本书</a>，或者<a href="/products/swifter-tips/">点击这里</a>了解更多关于本书的内容。</div>
  </div>
</div>
    </div>
    <hr>