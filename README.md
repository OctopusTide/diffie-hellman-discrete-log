# A little advice suffices: Diffie–Hellman is as hard as discrete logarithm

This repository holds a paper proving that discrete logarithm and Diffie–Hellman are polynomially equivalent in every group of prime order $p$, given an advice string of $O(\log p)$ bits that depends only on $p$. Maurer's reduction (1994) needed short intervals to contain enough integers with only small prime factors, an assumption that stood for thirty years. The paper proves it from a zero-free half-plane for the Riemann zeta function.

The statements and proofs were generated mainly by AI systems and reviewed over several rounds by independent AI agents. See the section "Use of AI" of the paper.

Paper: [`paper/diffie_hellman_discrete_log.pdf`](paper/diffie_hellman_discrete_log.pdf) (15 pages). Companion paper: [hyperelliptic-curve-method](https://github.com/OctopusTide/hyperelliptic-curve-method).

## Main results

- **Diffie–Hellman is as hard as discrete logarithm.** There are a constant $c$ and a probabilistic algorithm such that, for every prime $p$, there is an advice string $\sigma_p$ of at most $30\lceil\log_2 p\rceil+12$ bits with which the algorithm computes discrete logarithms in every cyclic group of order $p$, for every generator, from a Diffie–Hellman oracle in expected time $O((\log p)^c)$.
- **Smooth numbers in short intervals.** If $\zeta(s)\neq0$ for $\operatorname{Re}s>1-\delta$, then for every $\theta>17/30$ and every fixed $K$ above an explicit threshold $K^*(\theta,\delta)$, the number of $(\log x)^K$-smooth integers in $[x,x+h]$ is asymptotic to the count predicted by their local density whenever $x^\theta\le h=o(x)$. With the half-plane $\operatorname{Re}s>7/8$, now known, the genus-2 window $[x,x+x^{3/4}]$ needs $K=25$.
- **Consequences, now without assumptions.**
  - An adversary that solves Diffie–Hellman on a fraction $\varepsilon$ of inputs yields discrete logarithms in time $\mathrm{poly}(\log p,1/\varepsilon)$.
  - Wolf's characterisation: discrete logarithm and Diffie–Hellman are generically equivalent in cyclic groups of order $n$ exactly when the largest prime $q$ with $q^2\mid n$ is polylogarithmic in $n$.
  - Maurer and Raub's impossibility of field-homomorphic one-way permutations extends to large characteristic, for characteristic fixed by the security parameter.
  - With $\varepsilon\log p$ yes/no queries in place of advice the reduction stays polynomial (Koblitz, Menezes and Shparlinski); with one precomputation of $p^\varepsilon$ steps per prime it costs $(\log p)^{O(1/\varepsilon)}$ per instance; with no help at all it runs in time $L_p(\tfrac12,\sqrt2)$.

The reduction is the classical one of den Boer and Maurer, run on genus-2 Jacobians. What is new is the proof that auxiliary groups of polylogarithmically smooth order exist: polylogarithmic smoothness keeps the saddle point of the counting integral about $1/K$ from the line $\operatorname{Re}s=1$, and a zero-free strip of any fixed width absorbs that shift once $K$ is large.

## Repository

```
paper/
  diffie_hellman_discrete_log.pdf   the paper
  tex/                              TeX source: main.tex, Sections 2-6, Appendix (app_smooth.tex), refs.bib
```

## Building

```bash
cd paper/tex
pdflatex main && bibtex main && pdflatex main && pdflatex main
```

Setting `\anontrue` in `main.tex` gives the anonymous version.

## Citation

```bibtex
@misc{zhou2026advice,
  author       = {Yuwen Zhou},
  title        = {A little advice suffices: {D}iffie--{H}ellman is as hard as discrete logarithm},
  year         = {2026},
  howpublished = {\url{https://github.com/OctopusTide/diffie-hellman-discrete-log}}
}
```

## License

[CC BY 4.0](LICENSE).
