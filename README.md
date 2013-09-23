# unicode-math

A Clojure library designed to let you painfully write easily readable math.

## Examples

[Binet's Fibonacci Number Formula](http://mathworld.wolfram.com/BinetsFibonacciNumberFormula.html):
```clojure
(defn binet-fib [n]
  (/ (- (ⁿ φ n)
        (ⁿ (- φ) (- n)))
     (√ 5)))
```
[de Morgan's Laws](http://mathworld.wolfram.com/deMorgansLaws.html):
```clojure
(doseq [p [true false] q [true false]]
  (assert (= (¬ (∧ p q))
             (∨ (¬ p) (¬ q)))))
```

[Inclusion-Exclusion Principle](http://mathworld.wolfram.com/Inclusion-ExclusionPrinciple.html):
```clojure
(assert (= (count (∪ A B))
           (+ (count A)
              (count B)
              (- (count (∩ A B))))))
```

## Usage

Add the following to your project.clj:

```clojure
[unicode-math "0.1.0"]
```

## Unicode in your editor

### Emacs

Emacs has simple Unicode support out of the box.  I recommend reading Xah Lee's [Emacs & Unicode Tips](http://ergoemacs.org/emacs/emacs_n_unicode.html) to learn all of the functionality, but the critical commands are:

- `C-x 8 <return>` or `M-x insert-char`, which will prompt you for a character name or hexadecimal code point.
- `C-\` or `M-x toggle-input-method`, which will prompt you for an input method name the first time and then toggle between your current input method and the one that you specify.  I use the "greek-babel" input method, as I'm frequently using Greek letters as variables in formulas.
- `M-x describe-char`, which will display the character code and full Unicode name in the *Help* buffer.

### Vim

Vim users can use the [digraph](http://vimdoc.sourceforge.net/htmldoc/digraph.html) functionality to quickly insert most of the Unicode characters used in unicode-math.  For the characters that don't have digraphs, [CTRL-V](http://vimdoc.sourceforge.net/htmldoc/insert.html#i_CTRL-V) can be used.

## Disclaimer

It's almost certainly a bad idea to use this, but it's fun.

## License

Copyright © 2013 Matthew Adereth

Distributed under the Eclipse Public License, the same as Clojure.
