---
layout: page
title: "О Ruby"
lang: ru
---

Удивляетесь, почему Ruby так популярен? Его поклонники называют его красивым,
искусным языком. И в то же время они говорят, что он удобный и практичный.
Что же перевешивает?

### Идеалы создателя Ruby

Ruby – это тщательно сбалансированный язык. Его создатель [Юкихиро
Мацумото][1] (так же известный как "matz"), объединил части его любимых
языков (Perl, Smalltalk, Eiffel, Ada и Lisp) чтобы сформировать новый
язык, в котором парадигма функционального программирования сбаланасирована
принципами императивного программирования.

Он часто повторял, что он "пытается сделать Ruby естественным, но не
простым" языком, который отражает жизнь.

Основываясь на этом, он добавляет:

> Ruby прост на вид, но очень сложен внутри, подобно
> человеческому телу<sup>[1](#fn1)</sup>.

### Рост популярности Ruby’s

Со времени выпуска публичной версии в 1995 году, Ruby привлек внимание
программистов со всего мира. В 2006 году Ruby завоевал массовое признание.
В крупнейших городах по всему миру активно действуют группы
пользователей Ruby, а конференции, посвященные Ruby, заполнены до
предела.

![Graph courtesy of
Gmane.](http://gmane.org/plot-rate.php?group=gmane.comp.lang.ruby.general&amp;width=320&amp;height=160&amp;title=Ruby-Talk+Activity
"Graph courtesy of Gmane."){: style="padding-left:8px;"}
{: style="float:right"}

Ruby-Talk, основная [рассылка](/en/community/mailing-lists/) для
обсуждения языка Ruby, содержала всреднем 200 сообщений ежедневно в 2006
году. В последние годы это количество уменьшилось, так как сообщество
стало использовать несколько тематических рассылок вместо одной общей.

Индекс [TIOBE][6], который измеряет рост популярности языков
программирования, помещяет Ruby на 9 место среди общепризнанных языков
программирования. Во многом, рост популярности языка приписывается
популярности программного обеспечения, написанного на Ruby, в
особенности – Ruby on Rails, среде разработки веб-приложений.<sup>[2](#fn2)</sup>.

Ruby также [абсолютно открыт]({{ site.license.url }}). Открыт для бесплатного использования,
изменений, копирования и распространения.

### Всё в Ruby – объекты.

Вначале Matz рассматривал другие языки в поисках идеального синтаксиса.
Вспоминая свои изыскания, он говорил: "Мне нужен был скриптовый язык,
который был бы более мощным, чем Perl, и более объектно-ориентированным,
чем Python."<sup>[3](#fn3)</sup>.”

В Ruby всё – объект. Для каждой частицы информации или кода могут быть
определены собственные свойства и действия.
 Object-oriented programming
calls properties by the name *instance variables* and actions are known
as *methods*. Ruby’s pure object-oriented approach is most commonly
demonstrated by a bit of code which applies an action to a number.

{% highlight ruby %}
5.times { print "We *love* Ruby -- it's outrageous!" }
{% endhighlight %}

In many languages, numbers and other primitive types are not objects.
Ruby follows the influence of the Smalltalk language by giving methods
and instance variables to all of its types. This eases one’s use of
Ruby, since rules applying to objects apply to all of Ruby.

### Ruby’s Flexibility

Ruby is seen as a flexible language, since it allows its users to freely
alter its parts. Essential parts of Ruby can be removed or redefined, at
will. Existing parts can be added upon. Ruby tries not to restrict the
coder.

For example, addition is performed with the plus (`+`) operator. But, if
you’d rather use the readable word `plus`, you could add such a method
to Ruby’s builtin `Numeric` class.

{% highlight ruby %}
class Numeric
  def plus(x)
    self.+(x)
  end
end

y = 5.plus 6
# y is now equal to 11
{% endhighlight %}

Ruby’s operators are syntactic sugar for methods. You can redefine them
as well.

### Blocks, a Truly Expressive Feature

Ruby’s block are also seen as a source of great flexibility. A
programmer can attach a closure to any method, describing how that
method should act. The closure is called a *block* and has become one of
the most popular features for newcomers to Ruby from other imperative
languages like PHP or Visual Basic.

Blocks are inspired by functional languages. Matz said, “in Ruby
closures, I wanted to respect the Lisp culture<sup>[4](#fn4)</sup>.”

{% highlight ruby %}
search_engines =
  %w[Google Yahoo MSN].map do |engine|
    "http://www." + engine.downcase + ".com"
  end
{% endhighlight %}

In the above code, the block is described inside the `do ... end`
construct. The `map` method applies the block to the provided list of
words. Many other methods in Ruby leave a hole open for a coder to write
their own block to fill in the details of what that method should do.

### Ruby and the Mixin

Unlike many object-oriented languages, Ruby features single inheritance
only, **on purpose**. But Ruby knows the concept of modules (called
Categories in Objective-C). Modules are collections of methods.

Classes can mixin a module and receive all its methods for free. For
example, any class which implements the `each` method can mixin the
`Enumerable` module, which adds a pile of methods that use `each` for
looping.

{% highlight ruby %}
class MyArray
  include Enumerable
end
{% endhighlight %}

Generally, Rubyists see this as a much clearer way than multiple
inheritance, which is complex and can be too restrictive.

### Ruby’s Visual Appearance

While Ruby often uses very limited punctuation and usually prefers
English keywords, some punctuation is used to decorate Ruby. Ruby needs
no variable declarations. It uses simple naming conventions to denote
the scope of variables.

* `var` could be a local variable.
* `@var` is an instance variable.
* `$var` is a global variable.

These sigils enhance readability by allowing the programmer to easily
identify the roles of each variable. It also becomes unnecessary to use
a tiresome `self.` prepended to every instance member.

### Beyond the Basics

Ruby has a wealth of other features, among which are the following:

* Ruby has exception handling features, like Java or Python, to make it
  easy to handle errors.
^

* Ruby features a true mark-and-sweep garbage collector for all Ruby
  objects. No need to maintain reference counts in extension libraries.
  As Matz says, “This is better for your health.”
^

* Writing C extensions in Ruby is easier than in Perl or Python, with a
  very elegant API for calling Ruby from C. This includes calls for
  embedding Ruby in software, for use as a scripting language. A SWIG
  interface is also available.
^

* Ruby can load extension libraries dynamically if an OS allows.
^

* Ruby features OS independent threading. Thus, for all platforms on
  which Ruby runs, you also have multithreading, regardless of if the OS
  supports it or not, even on MS-DOS!
^

* Ruby is highly portable: it is developed mostly on GNU/Linux, but
  works on many types of UNIX, Mac OS X, Windows 95/98/Me/NT/2000/XP,
  DOS, BeOS, OS/2, etc.

#### References

<sup>1</sup> Matz, speaking on the Ruby-Talk mailing list, [May 12th,
2000][2].
{: #fn1}

<sup>2</sup> See the [Ruby on Rails][3] home page for more.
{: #fn2}

<sup>3</sup> Matz, in [An Interview with the Creator of Ruby][4], Nov.
29th, 2001.
{: #fn3}

<sup>4</sup> Matz, in [Blocks and Closures in Ruby][5], December 22nd,
2003.
{: #fn4}



[1]: http://www.rubyist.net/~matz/
[2]: http://blade.nagaokaut.ac.jp/cgi-bin/scat.rb/ruby/ruby-talk/2773
[3]: http://rubyonrails.org/
[4]: http://www.linuxdevcenter.com/pub/a/linux/2001/11/29/ruby.html
[5]: http://www.artima.com/intv/closures2.html
[6]: http://www.tiobe.com/index.php/content/paperinfo/tpci/index.html
