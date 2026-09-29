Lecture.06

=>Selectors types:
1. Universal Selector -> *{}
2. Element Selector -> element_name {}
3. Class Selector -> .{}
4. Attribute Selector -> [attribute_name] {}


=> Regular Expressions:
1. '$' - end of line ( e.g: href '$' = ".pdf" )
2. '^' - start of line ( e.g: href '^' = "http" )
3.  *  finding specific word anywhere  ( e.g: href '*' = "qau" ) (finding 'qau' within qau website)
4.  ~(tilda) - matching an exact word '( e.g: href '~' = "books" )'



   =>Pseudo-Class selectors:
   . it describes the  "state" of an element
   . e.g. a:link , a:visited , a: hover, :first/last-child , :nthchild
   . syntax: ':' + class

   =>Pseudo-element selectors:
   . it describes the position of an element
   . e.g. :first-letter , :first-line

   =>Contextual Selectors (Combinators):
   . '>' - direct child
   . '+' - adjacent sibling
   . '~' - general sibling

   =>Specificity:
   Precedence/Sequence of applying styles
