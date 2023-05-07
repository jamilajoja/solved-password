Download Link: https://assignmentchef.com/product/solved-password
<br>
<a href="https://www.youtube.com/playlist?list=PLhOuww6rJJNMRNnUQyUkGjpztCBUCiwZt" rel="nofollow">https://www.youtube.com/playlist?list=PLhOuww6rJJNMRNnUQyUkGjpztCBUCiwZt</a>

Cf. <a href="https://xkcd.com/936/" rel="nofollow">https://xkcd.com/936/</a>

Create a program that will randomly combine words from given text(s) to create novel, memorable, unbreakable passwords:

<pre><code>$ ./password.pyEchinochloaJapeCollinglyRadiotricianEthanedithiolRefleePrebudgetPolyphonismBerriChamaecyparisOutdraftArcifera</code></pre>

By default, the program should read the standard word dictionary <code>/usr/share/dict/words</code> for the word list but should also accept optional positional arguments. The program should create a list of unique words with all non-word characters removed, randomly select some <code>-w</code> or <code>--num_words</code> for each password, and join the titlecased selections into new passwords:

<pre><code>$ ./password.py -w 3 scarlet/*ShouldOfferPeculiarLongDeathWillLikeVenerableBear</code></pre>

The words selected should have a <code>-m</code> or <code>--min_word_len</code> that defaults to 3 in order to remove short, unmemorable words:

<pre><code>$ ./password.py -m 5 sonnets/*IndigestPublishPaintingParticularAccidentImprintDancePosterityExcuseGrossStateLaughd</code></pre>

The program should accept a <code>-n</code> and <code>--num</code> flag to control the number of passwords that are created:

<pre><code>$ ./password.py -n 2 const/*NumberFollowExtraordinaryCompelThinkLegislationAppellateEligible</code></pre>

Be sure to accept a <code>-s</code> or <code>--seed</code> option to use as the random seed to ensure reproducibility:

<pre><code>$ ./password.py -s 1ChromePorometerUnwastableUnconditionatedThujaAwesomelyEyeglanceCatabolinOptiveThicketMoratoriaNoncompetent</code></pre>

If the <code>--l33t</code> flag is present, the passwords should be obfuscated by:

<ol>

 <li>Using the “ransom” algorightm from chapter 13</li>

 <li>Using a character substitution as in chapter 5</li>

 <li>Add a randomly selected punctuation at the end</li>

</ol>

Here is the substitution table:

<pre><code>a =&gt; @A =&gt; 4o =&gt; 0O =&gt; 0t =&gt; +e =&gt; 3E =&gt; 3I =&gt; 1S =&gt; 5</code></pre>

Here is what the output would look like without:

<pre><code>$ ./password.py sonnets/* -s 1EagerCarcanetLilyDialWantTempestTwireRondureHealCrawlVerdictBase</code></pre>

And the same passwords with the encoding:

<pre><code>$ ./password.py sonnets/* -s 1 --l33t<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="44777003773627703607702a7710282d083d202d04086a">[email protected]</a><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a99cd999db8298ff9aebe9dafd">[email protected]</a>@RDhURT5uFf3Rdrh3T0r1cC0n+3ndsU1T3Dw1l+`</code></pre>

The program should print a usage for the <code>-h</code> and <code>--help</code> flags:

<pre><code>$ ./password.py -husage: password.py [-h] [-n int] [-w int] [-m int] [-s int] [-l]                   [FILE [FILE ...]]Password makerpositional arguments:  FILE                  Input file(s) (default: [&lt;_io.TextIOWrapper                        name='/usr/share/dict/words' mode='r'                        encoding='UTF-8'&gt;])optional arguments:  -h, --help            show this help message and exit  -n int, --num int     Number of passwords to generate (default: 3)  -w int, --num_words int                        Number of words to use for password (default: 4)  -m int, --min_word_len int                        Minimum word length (default: 4)  -s int, --seed int    Random seed (default: None)  -l, --l33t            Obfuscate letters (default: False)</code></pre>

Run the test suite to ensure your program is correct:

<pre><code>$ make testpytest -xv test.py============================= test session starts ==============================...collected 7 itemstest.py::test_exists PASSED                                              [ 14%]test.py::test_usage PASSED                                               [ 28%]test.py::test_bad_file PASSED                                            [ 42%]test.py::test_bad_num PASSED                                             [ 57%]test.py::test_bad_num_words PASSED                                       [ 71%]test.py::test_bad_min_word_len PASSED                                    [ 85%]test.py::test_bad_seed PASSED                                            [100%]============================== 7 passed in 0.46s ===============================</code></pre>