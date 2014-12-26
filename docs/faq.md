---
layout: default
title:  "FAQ"

---

# FAQ

### What is Marpa?
 Marpa refers to the [parsing algorithm developed by Jeffrey
 Kegler][kegler_paper] based upon [Jay Earley][earley_paper], [Joop
 Leo][leo_paper], [Aycock, and Horspool][ayhor_paper]. For more information on
 the algorithms involved, see the [Marpa::R2::Advanced::Bibliography][r2_docs_bib]
 documentation.

[kegler_paper]: https://docs.google.com/file/d/0B9_mR_M2zOc4Ni1zSW5IYzk3TGc/edit?usp=sharing
[earley_paper]: http://ccl.pku.edu.cn/alcourse/nlp/LectureNotes/An_Efficient_Context_Free_Parsing_Algorithm%20%28Earley%20Algorithm%29.pdf
[leo_paper]: http://dx.doi.org/10.1016/0304-3975%2891%2990180-A
[ayhor_paper]: http://webhome.cs.uvic.ca/~nigelh/Publications/PracticalEarleyParsing.pdf
[r2_docs_bib]: http://search.cpan.org/~jkegl/Marpa-R2-2.100000/pod/Advanced/Bibliography.pod

### Theory is fine and all, but I want code!
 [libmarpa][libmarpa_desc] implements the marpa parsing algorithm, and there
 are two high-level interfaces available: [Kollos (early WIP)][kollos_desc] and
 [Marpa::R2][r2_desc]. See [this page][structure] for more information.

[libmarpa_desc]: {{ site.baseurl }}docs/structure.html#libmarpa
[kollos_desc]: {{ site.baseurl }}docs/structure.html#kollos
[r2_desc]: {{ site.baseurl }}docs/structure.html#marpar2scanless
[structure]: {{ site.baseurl }}docs/structure.html

### How do I get started?
 - Install perl (you probably have it preinstalled on linux)
 - install the Marpa::R2 module
 - You probably want to use the Scanless interface
   - The docs for Marpa::R2::Scanless are [here][scanless_docs]
   - The docs for the BNF language used are [here][bnf_dsl_docs]

[scanless_docs]: http://search.cpan.org/~jkegl/Marpa-R2-2.100000/pod/Scanless.pod
[bnf_dsl_docs]: http://search.cpan.org/~jkegl/Marpa-R2-2.100000/pod/Scanless/DSL.pod
