# utl_format_variable_values_based_on_values
Format variable values based on values. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.
    Format variable values based on values

    github
    https://goo.gl/DCpS84
    https://github.com/rogerjdeangelis/utl_format_variable_values_based_on_values

      Failed in WPS
         ERROR: Found ""comma15.2"" when expecting Format specifier.

    see
    https://goo.gl/oNQ3XU
    https://communities.sas.com/t5/Base-SAS-Programming/Format-variable-values-based-on-values/m-p/430447


    INPUT
    =====

     proc format;
      value twins
        low-<10000000   =  ['comma15.2']
        10000000-high   =  ['dollar15.2']
     ;run;quit;

     WORK.HAVE total obs=7

      NAME         AMOUNT

      A           4568442.00
      Acat1     628727452.17
      Acat2     819125592.25
      Acat3    9491576104.14
      Acat4     221336147.01
      Aset1       2026005.00
      Aset2       1247890.00


    PROCESS (All the code)
    =======================

      proc print data=have width=min;
      format amount twins.;
      run;quit;

    OUTPUT
    ======

        NAME         AMOUNT

        A           4,568,442.00
        Acat1    $628,727,452.17
        Acat2    $819,125,592.25
        Acat3     $9491576104.14
        Acat4    $221,336,147.01
        Aset1       2,026,005.00
        Aset2       1,247,890.00

    *                _               _       _
     _ __ ___   __ _| | _____     __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \   / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/  | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|   \__,_|\__,_|\__\__,_|

    ;
     proc format;
       value twins
         low-<10000000   =  ["comma15.2"]
         10000000-high   =  ["dollar15.2"]
    ;run;quit;

    data have;
    input Name$ Amount;
    cards4;
     A 4568442
     Acat1 628727452.17
     Acat2 819125592.25
     Acat3 9491576104.14
     Acat4 221336147.01
     Aset1 2026005
     Aset2 1247890
    ;;;;
    run;quit;
    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;

     proc print data=wrk.have width=min;
       format amount twins.;
     run;quit;

