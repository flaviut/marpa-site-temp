---
layout: page
title: "Marpa: A modern parser"
---
{::options parse_block_html="true" /}

Marpa: A modern parser
{: .tagline}

{% highlight perl %}
use strict;
use warnings;
use Marpa::R2;

my $dsl = <<'EOG';
lexeme default = latm => 1

Calculator ::= Expr action => ::first
Expr ::= Number action => ::first
      # `||` denotes precedence
      || Expr '×' Expr action => do_mul
      || Expr '+' Expr action => do_add

Number ~ [\d]+

whitespace ~ [\s]+
:discard ~ whitespace
EOG

my $grammar = Marpa::R2::Scanless::G->new( { source => \$dsl} );
my $value_ref = $grammar->parse( \'7 + 42 × 1', 'Calc' );

print "$$value_ref\n";
#=> 49

# $_ looks like [context, Expr1, ('+'|'×'), Expr2]
sub Calc::do_add { return $_[1] + $_[3]; }
sub Calc::do_mul { return $_[1] * $_[3]; }
{% endhighlight %} {: .big-example}


<div class="features">
  <div class="third">
### Fast
Marpa parses all <abbr title="grammars parsable by regexes, LALR, or recursive descent">practical grammars</abbr> in linear time.
  </div>
  <div class="third">
### Expressive
Marpa will parse any grammar you can express with [BNF][bnf_def], even ambiguous ones.
  </div>
  <div class="third">
### Flexible
Marpa can be paused at any point to run custom parsing logic with full location awareness.
  </div>
</div>


[bnf_def]: http://en.wikipedia.org/wiki/Backus%E2%80%93Naur_Form
