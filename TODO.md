* TODO [2015-01-03 Sat] iod: Merge modes

  Either with a new directive (e.g. C<!mode_merge>) or using an option to
  C<!merge>, e.g. C<!merge -mode + SECTNAME>.
* TODO [2015-01-03 Sat] iod: Directive to add prefix to section name

  Example:

       [foo]
       key=val
       ;!section_prefix=pre.
       [bar]
       key=val
       [baz]
       key=val
  Then the resulting data would be (in pseudo-JSON):

       {
         "foo"    : {"key":"val"},
         "pre.bar": {"key":"val"},
         "pre.baz": {"key":"val"},
       }
* TODO [2015-01-03 Sat] iod: Encoding for section names

  So section name can contain, e.g., C<]> or untrimmed whitespaces.
* TODO [2015-01-03 Sat] iod: Encoding for key names

  Sample syntax:

      !base64 Zm9vIGJhcg== = baz ; equals to: foo bar=baz
  To ease parsing the C<=> sign, only C<!base64> is allowed and it must be
  separated with a space to avoid ambiguity.
* TODO [2015-01-03 Sat] ciod: Option to only allow include if owner is the same.
* IDEA [2014-10-17 Fri] iod: minta https://gist.github.com/espadrine/5028426 dan orang2x di https://news.ycombinator.com/item?id=5272634 utk mereview IOD

  - perlu buat round-trip parser dulu Config::IOD
* TODO [2014-12-17 Wed] dump-iod: i hate that i have to write: 'dump-iod --naked-res some.iod' instead of just 'dump-iod some.iod'

  - fix this! :)
* IDEA [2014-08-27 Wed] perl module: Config::IOD::Functions

  - read_iod, get_iod_key, get_iod_section, list_iod_sections, ...
  - one-off, no-caching, mirip Unix::Passwd::File
  - nanti App::IODUtils bisa dipindah untuk pake ini
