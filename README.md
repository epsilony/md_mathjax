# md_mathjax #

md_mathjax is a simple extension of the Python implementation of John Gruber's [Markdown](https://pypi.python.org/pypi/Markdown)

## Supported MathJax LaTeX environments ##
+ displayed: `$$ $$`
+ displayed: `\[ \]`
+ begin-end environment blocks: `\begin{} \end{}`
+ inline: `\( \)`

thus a typical sample markdown below can be parsed:
```markdown
<meta charset="utf8">
<script type="text/javascript"
  src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

# A sample markdown text file with mathjax elements #

## inline formulas ##
    this is an inline math: \( a<\frac{a}{b} \)

this is an inline math: \( a<\frac{a}{b} \)

## displayed mathematics ##
    $$
    x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
    $$

$$
x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
$$

    \[
    e=mc^2
    \]

\[
e=mc^2
\]

## environments ##
    \begin{align*}
    a=&1\\
    \int_{a}^{b}\frac{c}{d}\,dx=&2
    \end{align*}

\begin{align*}
a=&1\\
\int_{a}^{b}\frac{c}{d}\,dx=&2
\end{align*}
```

## try to use it ##

```bash
git clone git@github.com:epsilony/md_mathjax.git
cd md_mathjax
python -m markdown -x mathjax demo/sample.md > demo/sample.html
```

then open the `demo/sample.html` with your browser

## use when programming ##
put the `mdx_mathjax.py` into `PYTHONPATH`
```python
from mdx_mathjax import MathJaxExtension
from markdown import Markdown

text=r'$$ \frac{a}{b} $$'

md=Markdown(extensions=[MathJaxExtension()])
html=md.convert(text)
print(html)
```
