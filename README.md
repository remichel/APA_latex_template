# APA LaTeX Template 

A simple APA template based on the apa6/7 classes provided by the [apa6 package](https://ctan.org/pkg/apa7?lang=de) and [apa7 package](https://ctan.org/pkg/apa7?lang=de).



### Bug fixing

In case that file `apa6.cbx` (located somewhere in `..\MiKTeX 2.9\tex\latex\biblatex-apa6\`) causes a bug, use the following workaround: 

Copy and rename the original file to something like `apa6old.cbx`. Then comment out the following lines in the new `apa6.cbx`:

```
% (APA 6.21) No parens round year for cites when the cite is in
%            parentheses. Use new command \nptextcite for such cites.

\DeclareDelimAlias[nptextcite]{finalnamedelim}[parencite]{finalnamedelim}

\DeclareCiteCommand{\nptextcite}
  {\usebibmacro{cite:init}%
   \usebibmacro{prenote}}
  {\usebibmacro{citeindex}%
   \usebibmacro{cite}%
   \usebibmacro{cite:post}}
  {}
  {\usebibmacro{postnote}}

\DeclareMultiCiteCommand{\nptextcites}{\nptextcite}{\setunit{\multicitedelim}}

\DeclareCiteCommand*{\nptextcite}
  {\usebibmacro{cite:init}%
   \usebibmacro{prenote}}
  {\usebibmacro{citeindex}%
   \usebibmacro{citeyear}%
   \usebibmacro{cite:post}}
  {}
  {\usebibmacro{postnote}}
  
 ```
