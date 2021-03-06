{
   "image" : null,
   "title" : "Perl Unicode Cookbook: Always Decompose and Recompose",
   "categories" : "unicode",
   "date" : "2012-04-03T06:00:01-08:00",
   "thumbnail" : "/images/_pub_2012_04_perlunicook-standard-preamble/unicode.jpg",
   "tags" : [],
   "draft" : null,
   "authors" : [
      "tom-christiansen"
   ],
   "description" : "To handle Unicode effectively, always decompose on the way in, then\nrecompose on the way out.",
   "slug" : "/pub/2012/04/perl-unicode-cookbook-always-decompose-and-recompose.html"
}



**℞ 1: Generic Unicode-savvy ﬁlter**
------------------------------------

Unicode allows multiple representations of the same characters. Comparing such strings for equivalence (sorting, searching, exact matching) requires care—including a coherent and consistent strategy of normalizing these representations to well-understood forms. Enter [Unicode::Normalize]({{<mcpan "Unicode::Normalize" >}}).

To handle Unicode effectively, always decompose on the way in, then recompose on the way out.

     use Unicode::Normalize;

     while (<>) {
         $_ = NFD($_);   # decompose + reorder canonically
         ...
     } continue {
         print NFC($_);  # recompose (where possible) + reorder canonically
     }

See the [Unicode Normalization FAQ](http://www.unicode.org/faq/normalization.html) for more details.

Series Index: [The Standard Preamble](/pub/2012/04/perlunicook-standard-preamble.html)

Next: [℞ 2: Fine-Tuning Unicode Warnings](/pub/2012/04/perl-unicook-fine-tuning-warnings.html)
