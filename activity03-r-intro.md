Activity 3
================
Team Name

Today you will be creating and manipulating vectors, lists, and data
frames to uncover a top secret message.

As you work through this document with your Team members, remember to:

-   Ask questions
-   Google is your friend! If an error is confusing, copy it into Google
    and see what other people are saying. If you don’t know how to do
    something, search for it.
-   Just because there is no error message doesn’t mean everything went
    smoothly. Use the console to check each step and make sure you have
    accomplished what you wanted to accomplish.

Do not edit this first R code chunk. This will allow you to knit your
document and view errors within the knitted report.

### Setup

Each of the following R chunks will cause an error and/or do the desired
task incorrectly. Find the mistake, and correct it to complete the
intended action.

Create three vectors that contain: 1) the lower case letters, 2) the
upper case letters, and 3) some punctuation marks.

``` r
lower_case <- c("a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z")

upper_case <- c("A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z")

punctuation <- c(".", ",", "!", "?", "'", '"', "(", ")", " ", "-", ";", ":")
```

Comment on what you noticed about the errors and how you used this
information to correct the issues.

**Response**: In the Upper case i found missing comma and in punctuation
i changed """ into ‘"’ to mix the strings.

Make one long vector containing all the symbols.

``` r
my_symbols <- c(lower_case, upper_case, punctuation)
my_symbols
```

    ##  [1] "a"  "b"  "c"  "d"  "e"  "f"  "g"  "h"  "i"  "j"  "k"  "l"  "m"  "n"  "o" 
    ## [16] "p"  "q"  "r"  "s"  "t"  "u"  "v"  "w"  "x"  "y"  "z"  "A"  "B"  "C"  "D" 
    ## [31] "E"  "F"  "G"  "H"  "I"  "J"  "K"  "L"  "M"  "N"  "O"  "P"  "Q"  "R"  "S" 
    ## [46] "T"  "U"  "V"  "W"  "X"  "Y"  "Z"  "."  ","  "!"  "?"  "'"  "\"" "("  ")" 
    ## [61] " "  "-"  ";"  ":"

Comment on what you noticed about the errors and how you used this
information to correct the issues.

**Response**: It’s because the vectors aren’t the same length

Turn the `my_symbols` vector into a data frame, with the variable name
“Symbol”.

``` r
my_symbols <- data.frame(my_symbols)
names(my_symbols) = "Symbol"
my_symbols
```

    ##    Symbol
    ## 1       a
    ## 2       b
    ## 3       c
    ## 4       d
    ## 5       e
    ## 6       f
    ## 7       g
    ## 8       h
    ## 9       i
    ## 10      j
    ## 11      k
    ## 12      l
    ## 13      m
    ## 14      n
    ## 15      o
    ## 16      p
    ## 17      q
    ## 18      r
    ## 19      s
    ## 20      t
    ## 21      u
    ## 22      v
    ## 23      w
    ## 24      x
    ## 25      y
    ## 26      z
    ## 27      A
    ## 28      B
    ## 29      C
    ## 30      D
    ## 31      E
    ## 32      F
    ## 33      G
    ## 34      H
    ## 35      I
    ## 36      J
    ## 37      K
    ## 38      L
    ## 39      M
    ## 40      N
    ## 41      O
    ## 42      P
    ## 43      Q
    ## 44      R
    ## 45      S
    ## 46      T
    ## 47      U
    ## 48      V
    ## 49      W
    ## 50      X
    ## 51      Y
    ## 52      Z
    ## 53      .
    ## 54      ,
    ## 55      !
    ## 56      ?
    ## 57      '
    ## 58      "
    ## 59      (
    ## 60      )
    ## 61       
    ## 62      -
    ## 63      ;
    ## 64      :

Comment on what you noticed about the errors and how you used this
information to correct the issues.

**Response**: Symbols was just an un-used variable that we had to give
values to.

Find the total number of symbols we have in our data frame.

``` r
len <- lengths(my_symbols)
len
```

    ## Symbol 
    ##     64

Comment on what you noticed about the errors and how you used this
information to correct the issues.

**Response**: Used Lengths instead of length

5.  Create a new variable in your dataframe that assigns a number to
    each symbol.

``` r
my_symbols_num <- 1:len
```

Comment on what you noticed about the errors and how you used this
information to correct the issues.

**Response**: Can’t use a % in a variable name

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you feel that you have a good
understanding of these Base R commands, feel free to start working on
your project. The remainder of this activity will help to expand these
Base R commands and I will post a solution on Blackboard by the end of
class.

### Decoding the secret message.

This chunk will load up the encoded secret message data and assign it as
a vector. There are no errors here.

``` r
# Read in full csv file
top_secret <- readr::read_csv("data/secret_code.csv", col_names = FALSE)
```

    ## 
    ## ── Column specification ────────────────────────────────────────────────────────
    ## cols(
    ##   X1 = col_double()
    ## )

``` r
# Pick off only the column X1
top_secret <- top_secret$X1
top_secret
```

    ##    [1] 0.3822556 0.3468030 0.3945748 0.3749030 0.3530014 0.3490264 0.3636401
    ##    [8] 0.3984390 0.3880637 0.3757322 0.4005234 0.3895931 0.3828942 0.3713138
    ##   [15] 0.3828942 0.3765374 0.3795434 0.4048531 0.3795434 0.4059756 0.3919687
    ##   [22] 0.3890926 0.3890926 0.3924204 0.3933023 0.3984390 0.4095814 0.3953918
    ##   [29] 0.3910427 0.3973351 0.4114496 0.3949863 0.3977080 0.3969572 0.3973351
    ##   [36] 0.4136208 0.4024621 0.4088472 0.5067359 0.3998458 0.5067652 0.4021482
    ##   [43] 0.4199443 0.4144439 0.5068235 0.4078370 0.4212441 0.4479079 0.4114496
    ##   [50] 0.4059756 0.4482702 0.4127726 0.5069399 0.4571325 0.4236743 0.4832826
    ##   [57] 0.4217162 0.5070124 0.4105312 0.5070413 0.4328749 0.4256392 0.4835197
    ##   [64] 0.4835535 0.4336980 0.4182291 0.5071424 0.4390315 0.4148465 0.4370373
    ##   [71] 0.4199443 0.5072144 0.4676440 0.4625078 0.5072574 0.4189279 0.4273471
    ##   [78] 0.4182291 0.4408138 0.4202750 0.4230864 0.5073577 0.4288355 0.4310404
    ##   [85] 0.4520767 0.5074149 0.4279770 0.4319188 0.4505167 0.4383540 0.4273471
    ##   [92] 0.4508467 0.4329791 0.4267026 0.4432177 0.4260427 0.5075714 0.4256392
    ##   [99] 0.4248140 0.4419666 0.4284708 0.5076423 0.4259089 0.4272194 0.4522332
    ##  [106] 0.4466648 0.4542881 0.4543845 0.5077412 0.4277267 0.5077694 0.4455626
    ##  [113] 0.4312626 0.4314830 0.4307037 0.4424886 0.4321341 0.5078678 0.4299018
    ##  [120] 0.4466012 0.4320267 0.5079239 0.4557925 0.4488638 0.4489810 0.4473554
    ##  [127] 0.5079939 0.4562464 0.4381820 0.4347914 0.5080497 0.4342997 0.4402590
    ##  [134] 0.4346937 0.5081055 0.4858790 0.4395291 0.4363086 0.5081611 0.4573064
    ##  [141] 0.4345957 0.4476637 0.4372165 0.5082305 0.4701827 0.4861872 0.5082720
    ##  [148] 0.4412807 0.4516550 0.4486279 0.4386100 0.5083411 0.4864008 0.4421915
    ##  [155] 0.4392814 0.4570888 0.4396111 0.5084238 0.4379220 0.4574361 0.4402590
    ##  [162] 0.5084788 0.4592315 0.4407352 0.4639433 0.4410482 0.4520244 0.4868533
    ##  [169] 0.4415112 0.4416638 0.4524405 0.5094438 0.4688424 0.4422661 0.4405774
    ##  [176] 0.4587831 0.5095101 0.4545764 0.4505167 0.4424886 0.5087385 0.4418912
    ##  [183] 0.4550504 0.4694647 0.4609559 0.5088065 0.4424146 0.4541427 0.4437875
    ##  [190] 0.5088607 0.4875330 0.4473554 0.4449609 0.4486279 0.4603023 0.5089419
    ##  [197] 0.4489810 0.4450284 0.4457603 0.4442767 0.5090093 0.4567814 0.4469808
    ##  [204] 0.5090497 0.4472311 0.4652433 0.4559294 0.5091035 0.4834522 0.4627938
    ##  [211] 0.5091438 0.4460868 0.4475408 0.4509013 0.4566486 0.4493296 0.5092241
    ##  [218] 0.4513345 0.4570014 0.5092642 0.4470436 0.5092909 0.4501266 0.4474173
    ##  [225] 0.4575222 0.4504613 0.5093575 0.4483899 0.4480292 0.4556548 0.4557467
    ##  [232] 0.4497878 0.4493873 0.5094505 0.4960519 0.4523371 0.4503502 0.5095035
    ##  [239] 0.4785663 0.4536034 0.4649157 0.4500141 0.4538989 0.4614456 0.4570014
    ##  [246] 0.4513345 0.4653084 0.5037515 0.5096487 0.4537515 0.4546719 0.3858839
    ##  [253] 0.3933023 0.5061597 0.4282250 0.4243921 0.5061597 0.3388118 0.4383540
    ##  [260] 0.2777778 0.3388118 0.4109942 0.4993880 0.5061597 0.4813090 0.4282250
    ##  [267] 0.4813090 0.3998458 0.4243921 0.5023917 0.5061597 0.2777778 0.5061597
    ##  [274] 0.4202750 0.2777778 0.3388118 0.3933023 0.3998458 0.4243921 0.3671910
    ##  [281] 0.5061597 0.3858839 0.4469179 0.4243921 0.5061597 0.4904801 0.3998458
    ##  [288] 0.4202750 0.3671910 0.5061597 0.4904801 0.3998458 0.4202750 0.3671910
    ##  [295] 0.5061597 0.5061597 0.4736867 0.4469179 0.4383540 0.4383540 0.3998458
    ##  [302] 0.3388118 0.2777778 0.4243921 0.3671910 0.5061597 0.4608798 0.4243921
    ##  [309] 0.4243921 0.3998458 0.3671910 0.5061597 0.4383540 0.3998458 0.4318105
    ##  [316] 0.4318105 0.3671910 0.3547941 0.5061597 0.4813090 0.3933023 0.3671910
    ##  [323] 0.5061597 0.3388118 0.3671910 0.3998458 0.4158281 0.3998458 0.4243921
    ##  [330] 0.3858839 0.5061597 0.4282250 0.3773200 0.3773200 0.5061597 0.2777778
    ##  [337] 0.5061597 0.3388118 0.3933023 0.4469179 0.4383540 0.3388118 0.3933023
    ##  [344] 0.5061597 0.2777778 0.4243921 0.3547941 0.5061597 0.4109942 0.3998458
    ##  [351] 0.4158281 0.4158281 0.3671910 0.3547941 0.5061597 0.3671910 0.4495024
    ##  [358] 0.3671910 0.4383540 0.4566042 0.4282250 0.4243921 0.3671910 0.5061597
    ##  [365] 0.3998458 0.4243921 0.4413577 0.3998458 0.3547941 0.3671910 0.5061597
    ##  [372] 0.4962125 0.4282250 0.4469179 0.5061597 0.4813090 0.4469179 0.4383540
    ##  [379] 0.4243921 0.5061597 0.4282250 0.4243921 0.5061597 0.4813090 0.3933023
    ##  [386] 0.3671910 0.5061597 0.4813090 0.3671910 0.4158281 0.4158281 0.4566042
    ##  [393] 0.5061597 0.2777778 0.4243921 0.3547941 0.5061597 0.3671910 0.4495024
    ##  [400] 0.3671910 0.4383540 0.4566042 0.5061597 0.4282250 0.4813090 0.3933023
    ##  [407] 0.3671910 0.4383540 0.5061597 0.4413577 0.4813090 0.4282250 0.4383540
    ##  [414] 0.4566042 0.5061597 0.3998458 0.4413577 0.5061597 0.4813090 0.3671910
    ##  [421] 0.4158281 0.4158281 0.3998458 0.4243921 0.5023917 0.5061597 0.4566042
    ##  [428] 0.4282250 0.4469179 0.5061597 0.4413577 0.4282250 0.4202750 0.3671910
    ##  [435] 0.3162860 0.4282250 0.3547941 0.4566042 0.5061597 0.3547941 0.3998458
    ##  [442] 0.3671910 0.3547941 0.5061597 0.4892590 0.3998458 0.4413577 0.4813090
    ##  [449] 0.3671910 0.4383540 0.5061597 0.4109942 0.3998458 0.4158281 0.4158281
    ##  [456] 0.3671910 0.3547941 0.5061597 0.3933023 0.3671910 0.4383540 0.5061597
    ##  [463] 0.3162860 0.2777778 0.3162860 0.3671910 0.3919687 0.3900848 0.3082948
    ##  [470] 0.2777778 0.3623478 0.3595677 0.3224844 0.3919687 0.3595677 0.3355400
    ##  [477] 0.3224844 0.3919687 0.3082948 0.3530014 0.3623478 0.3468030 0.3162860
    ##  [484] 0.3510849 0.3900848 0.3795434 0.3919687 0.2777778 0.3275489 0.3275489
    ##  [491] 0.3530014 0.3580659 0.3162860 0.3919687 0.3795434 0.3530014 0.3919687
    ##  [498] 0.3275489 0.3224844 0.3224844 0.3162860 0.3919687 0.3388118 0.3795434
    ##  [505] 0.3919687 0.3693288 0.3510849 0.3162860 0.3919687 0.3648748 0.3224844
    ##  [512] 0.3900848 0.3580659 0.3224844 0.3919687 0.3595677 0.3224844 0.3510849
    ##  [519] 0.3162860 0.4080930 0.4093388 0.4075786 0.4189279 0.4098219 0.4070545
    ##  [526] 0.4095814 0.3547941 0.3468030 0.3224844 0.3919687 0.3795434 0.3530014
    ##  [533] 0.3919687 0.3795434 0.3355400 0.3224844 0.3919687 0.3490264 0.3530014
    ##  [540] 0.3530014 0.3510849 0.3919687 0.3835184 0.3224844 0.3547941 0.3795434
    ##  [547] 0.3224844 0.3490264 0.2970319 0.3224844 0.3580659 0.3919687 0.3490264
    ##  [554] 0.3671910 0.3919687 0.3082948 0.3530014 0.3623478 0.3595677 0.3388118
    ##  [561] 0.3510849 0.3919687 0.3795434 0.3580659 0.3388118 0.3224844 0.3162860
    ##  [568] 0.3919687 0.3580659 0.3224844 0.3224844 0.3275489 0.3224844 0.3580659
    ##  [575] 0.3919687 0.3275489 0.3530014 0.3580659 0.3919687 0.3795434 0.3355400
    ##  [582] 0.3224844 0.3919687 0.3636401 0.3224844 0.3580659 0.3671910 0.3919687
    ##  [589] 0.3275489 0.3388118 0.3580659 0.3595677 0.3795434 0.3919687 0.3795434
    ##  [596] 0.3388118 0.3490264 0.3224844 0.3919687 0.3802467 0.3530014 0.3648748
    ##  [603] 0.3919687 0.3355400 0.3224844 0.3900848 0.3595677 0.3919687 0.3162860
    ##  [610] 0.3530014 0.3388118 0.3510849 0.3318308 0.3919687 0.3355400 0.3530014
    ##  [617] 0.3580659 0.3595677 0.3224844 0.3928649 0.3919687 0.3388118 0.3795434
    ##  [624] 0.3900848 0.3595677 0.3919687 0.3773200 0.3623478 0.3510849 0.3224844
    ##  [631] 0.3919687 0.3841289 0.3388118 0.3490264 0.3224844 0.3919687 0.3841289
    ##  [638] 0.3388118 0.3490264 0.3224844 0.3919687 0.3919687 0.3765374 0.3795434
    ##  [645] 0.3900848 0.3595677 0.3919687 0.3595677 0.3388118 0.3468030 0.3468030
    ##  [652] 0.3671910 0.3885829 0.3919687 0.3510849 0.3530014 0.3895931 0.3919687
    ##  [659] 0.3858839 0.3355400 0.3224844 0.3510849 0.3919687 0.2777778 0.3919687
    ##  [666] 0.3580659 0.3530014 0.3082948 0.3443860 0.3224844 0.3795434 0.3919687
    ##  [673] 0.3595677 0.3355400 0.3388118 0.3547941 0.3919687 0.3224844 0.3660571
    ##  [680] 0.3547941 0.3468030 0.3530014 0.3162860 0.3224844 0.3595677 0.3919687
    ##  [687] 0.3693288 0.3510849 0.3162860 0.3919687 0.3224844 0.3636401 0.3224844
    ##  [694] 0.3580659 0.3671910 0.2970319 0.3530014 0.3162860 0.3671910 0.3919687
    ##  [701] 0.3595677 0.3795434 0.3388118 0.3468030 0.3468030 0.3919687 0.3648748
    ##  [708] 0.2777778 0.3510849 0.3795434 0.3595677 0.3919687 0.3795434 0.3530014
    ##  [715] 0.3919687 0.3275489 0.3468030 0.3671910 0.3919687 0.3835184 0.3530014
    ##  [722] 0.3490264 0.3224844 0.3919687 0.3595677 0.2777778 0.3671910 0.3919687
    ##  [729] 0.2777778 0.3919687 0.3490264 0.2777778 0.3510849 0.3919687 0.2777778
    ##  [736] 0.3388118 0.3510849 0.3900848 0.3795434 0.3919687 0.3355400 0.2777778
    ##  [743] 0.3547941 0.3547941 0.3671910 0.3919687 0.3847263 0.3510849 0.3468030
    ##  [750] 0.3224844 0.3595677 0.3595677 0.3919687 0.2585237 0.3727146 0.3297723
    ##  [757] 0.2585237 0.3318308 0.3727146 0.3602893 0.3388118 0.3430938 0.3275489
    ##  [764] 0.3479369 0.3727146 0.2970319 0.3195577 0.3032303 0.3403137 0.3727146
    ##  [771] 0.3616785 0.3162860 0.3693288 0.3727146 0.3456208 0.3162860 0.3479369
    ##  [778] 0.3703390 0.3727146 0.3648748 0.3195577 0.3297723 0.3032303 0.3727146
    ##  [785] 0.3648748 0.3195577 0.3297723 0.3032303 0.3727146 0.3727146 0.3510849
    ##  [792] 0.2585237 0.2777778 0.3479369 0.3727146 0.3297723 0.2585237 0.3251319
    ##  [799] 0.3032303 0.3727146 0.2585237 0.3727146 0.3403137 0.3355400 0.3032303
    ##  [806] 0.3032303 0.2890407 0.3162860 0.3693288 0.3727146 0.3403137 0.3602893
    ##  [813] 0.2585237 0.3388118 0.3727146 0.3456208 0.2585237 0.3388118 0.3403137
    ##  [820] 0.3727146 0.3082948 0.3275489 0.3479369 0.3727146 0.3609926 0.3032303
    ##  [827] 0.3195577 0.3125767 0.3162860 0.2777778 0.3337473 0.3388118 0.3403137
    ##  [834] 0.3727146 0.3224844 0.3430938 0.3403137 0.3602893 0.3727146 0.3403137
    ##  [841] 0.3162860 0.3195577 0.3318308 0.3032303 0.3727146 0.3195577 0.3602893
    ##  [848] 0.3727146 0.3337473 0.3318308 0.3727146 0.3510849 0.3430938 0.3602893
    ##  [855] 0.3727146 0.3195577 0.3082948 0.3727146 0.2585237 0.3727146 0.3318308
    ##  [862] 0.3195577 0.3125767 0.3162860 0.3602893 0.3727146 0.3082948 0.2585237
    ##  [869] 0.3275489 0.3275489 0.3403137 0.3727146 0.2585237 0.3318308 0.2970319
    ##  [876] 0.3727146 0.2585237 0.3727146 0.2777778 0.3337473 0.3297723 0.2777778
    ##  [883] 0.3727146 0.3082948 0.2585237 0.3275489 0.3275489 0.3403137 0.3727146
    ##  [890] 0.3666298 0.3195577 0.3275489 0.3275489 0.3727146 0.2585237 0.3318308
    ##  [897] 0.3479369 0.2777778 0.3337473 0.2970319 0.3479369 0.3727146 0.3403137
    ##  [904] 0.3032303 0.3032303 0.3727146 0.3602893 0.3162860 0.3032303 0.3727146
    ##  [911] 0.2970319 0.2585237 0.3456208 0.3318308 0.3727146 0.3648748 0.3195577
    ##  [918] 0.3297723 0.3032303 0.3727146 0.3648748 0.3195577 0.3297723 0.3032303
    ##  [925] 0.3727146 0.3727146 0.3572834 0.3403137 0.3727146 0.3195577 0.3602893
    ##  [932] 0.3727146 0.3403137 0.3195577 0.3275489 0.3275489 0.3479369 0.3693288
    ##  [939] 0.3727146 0.3318308 0.3337473 0.3703390 0.3727146 0.3666298 0.3162860
    ##  [946] 0.3032303 0.3318308 0.3727146 0.2585237 0.3727146 0.3388118 0.3337473
    ##  [953] 0.2890407 0.3251319 0.3032303 0.3602893 0.3727146 0.2777778 0.3275489
    ##  [960] 0.3337473 0.3456208 0.3403137 0.3727146 0.3430938 0.3355400 0.3727146
    ##  [967] 0.3500747 0.3318308 0.2970319 0.3727146 0.3032303 0.3443860 0.3032303
    ##  [974] 0.3388118 0.3479369 0.2777778 0.3337473 0.2970319 0.3479369 0.3727146
    ##  [981] 0.3403137 0.3602893 0.3195577 0.3275489 0.3275489 0.3727146 0.3456208
    ##  [988] 0.2585237 0.3318308 0.3602893 0.3403137 0.3727146 0.3602893 0.3337473
    ##  [995] 0.3727146 0.3082948 0.3275489 0.3479369 0.3727146 0.3642643 0.3337473
    ## [1002] 0.3297723 0.3032303 0.3727146 0.3403137 0.2585237 0.3479369 0.3727146
    ## [1009] 0.3297723 0.2585237 0.3318308 0.3727146 0.2585237 0.3195577 0.3318308
    ## [1016] 0.3708307 0.3602893 0.3727146 0.3162860 0.2585237 0.3355400 0.3355400
    ## [1023] 0.3479369 0.3693288 0.3727146 0.3602893 0.3388118 0.3430938 0.3275489
    ## [1030] 0.3479369 0.3727146 0.3654722 0.3318308 0.3602893 0.3195577 0.3275489
    ## [1037] 0.3727146 0.2585237 0.3727146 0.3297723 0.2585237 0.3318308 0.3727146
    ## [1044] 0.3602893 0.3388118 0.3430938 0.3275489 0.3479369 0.3727146 0.2970319
    ## [1051] 0.3195577 0.3032303 0.3403137 0.3727146 0.3616785 0.3162860 0.3693288
    ## [1058] 0.3727146 0.3456208 0.3162860 0.3479369 0.3703390 0.3727146 0.3616785
    ## [1065] 0.3162860 0.3693288 0.3727146 0.3456208 0.3162860 0.3479369 0.3703390
    ## [1072] 0.3727146 0.3642643 0.3195577 0.3125767 0.3318308 0.3727146 0.3337473
    ## [1079] 0.3708307 0.3727146 0.3602893 0.3162860 0.3032303 0.3727146 0.3648748
    ## [1086] 0.3195577 0.3297723 0.3032303 0.3403137 0.3727146 0.3648748 0.3195577
    ## [1093] 0.3297723 0.3032303 0.3727146 0.3648748 0.3195577 0.3297723 0.3032303
    ## [1100] 0.3727146 0.3727146 0.3642643 0.3195577 0.3125767 0.3318308 0.3727146
    ## [1107] 0.3337473 0.3708307 0.3727146 0.3602893 0.3162860 0.3032303 0.3727146
    ## [1114] 0.3602893 0.3195577 0.3297723 0.3032303 0.3403137 0.3727146 0.3297723
    ## [1121] 0.3032303 0.3403137 0.3403137 0.3727146 0.3456208 0.3195577 0.3602893
    ## [1128] 0.3162860 0.3727146 0.3479369 0.3337473 0.3430938 0.3388118 0.3727146
    ## [1135] 0.3297723 0.3195577 0.3318308 0.2970319 0.3727146 0.3564781 0.3430938
    ## [1142] 0.3388118 0.3388118 0.3479369 0.3727146 0.2777778 0.3032303 0.3082948
    ## [1149] 0.3337473 0.3388118 0.3032303 0.3727146 0.3195577 0.3602893 0.3708307
    ## [1156] 0.3403137 0.3727146 0.3602893 0.3337473 0.3337473 0.3727146 0.3275489
    ## [1163] 0.2585237 0.3602893 0.3032303 0.3727146 0.3595677 0.3032303 0.3602893
    ## [1170] 0.3708307 0.3403137 0.3727146 0.3082948 0.2585237 0.3275489 0.3275489
    ## [1177] 0.3727146 0.3195577 0.3318308 0.3727146 0.3275489 0.3337473 0.3443860
    ## [1184] 0.3032303 0.3693288 0.3727146 0.3125767 0.3032303 0.3602893 0.3727146
    ## [1191] 0.3297723 0.2585237 0.3388118 0.3388118 0.3195577 0.3032303 0.2970319
    ## [1198] 0.3693288 0.3727146 0.3162860 0.2585237 0.3443860 0.3032303 0.3727146
    ## [1205] 0.2585237 0.3727146 0.2777778 0.2585237 0.2777778 0.3479369 0.3727146
    ## [1212] 0.3666298 0.3032303 0.3708307 0.3275489 0.3275489 0.3727146 0.2890407
    ## [1219] 0.2585237 0.3275489 0.3275489 0.3727146 0.3162860 0.3195577 0.3297723
    ## [1226] 0.3727146 0.3609926 0.2585237 0.3602893 0.3032303 0.3693288 0.3727146
    ## [1233] 0.3195577 0.3082948 0.3727146 0.3195577 0.3602893 0.3708307 0.3403137
    ## [1240] 0.3727146 0.2585237 0.3727146 0.2777778 0.3337473 0.3479369 0.3727146
    ## [1247] 0.3648748 0.3195577 0.3297723 0.3032303 0.3727146 0.3648748 0.3195577
    ## [1254] 0.3297723 0.3032303

By altering this top secret set of numbers, you will be able to create a
message. Write your own code to complete the steps below.

1.  Add 14 to every number.
2.  Multiply every number by 18, then subtract 257.
3.  Exponentiate every number. (You may need to Google how to this in
    R!)
4.  Square every number.

``` r
top_secret2 <- (exp((top_secret+14)*18-257))^2
top_secret2
```

    ##    [1]   43.0   12.0   67.0   33.0   15.0   13.0   22.0   77.0   53.0   34.0
    ##   [11]   83.0   56.0   44.0   29.0   44.0   35.0   39.0   97.0   39.0  101.0
    ##   [21]   61.0   55.0   55.0   62.0   64.0   77.0  115.0   69.0   59.0   74.0
    ##   [31]  123.0   68.0   75.0   73.0   74.0  133.0   89.0  112.0 3799.0   81.0
    ##   [41] 3803.0   88.0  167.0  137.0 3811.0  108.0  175.0  457.0  123.0  101.0
    ##   [51]  463.0  129.0 3827.0  637.0  191.0 1633.0  178.0 3837.0  119.0 3841.0
    ##   [61]  266.0  205.0 1647.0 1649.0  274.0  157.0 3855.0  332.0  139.0  309.0
    ##   [71]  167.0 3865.0  930.0  773.0 3871.0  161.0  218.0  157.0  354.0  169.0
    ##   [81]  187.0 3885.0  230.0  249.0  531.0 3893.0  223.0  257.0  502.0  324.0
    ##   [91]  218.0  508.0  267.0  213.0  386.0  208.0 3915.0  205.0  199.0  369.0
    ##  [101]  227.0 3925.0  207.0  217.0  534.0  437.0  575.0  577.0 3939.0  221.0
    ##  [111] 3943.0  420.0  251.0  253.0  246.0  376.0  259.0 3957.0  239.0  436.0
    ##  [121]  258.0 3965.0  607.0  473.0  475.0  448.0 3975.0  617.0  322.0  285.0
    ##  [131] 3983.0  280.0  347.0  284.0 3991.0 1793.0  338.0  301.0 3999.0  641.0
    ##  [141]  283.0  453.0  311.0 4009.0 1019.0 1813.0 4015.0  360.0  523.0  469.0
    ##  [151]  327.0 4025.0 1827.0  372.0  335.0  636.0  339.0 4037.0  319.0  644.0
    ##  [161]  347.0 4045.0  687.0  353.0  814.0  357.0  530.0 1857.0  363.0  365.0
    ##  [171]  538.0 4188.0  971.0  373.0  351.0  676.0 4198.0  581.0  502.0  376.0
    ##  [181] 4083.0  368.0  591.0  993.0  731.0 4093.0  375.0  572.0  394.0 4101.0
    ##  [191] 1903.0  448.0  411.0  469.0  714.0 4113.0  475.0  412.0  423.0  401.0
    ##  [201] 4123.0  629.0  442.0 4129.0  446.0  853.0  610.0 4137.0 1643.0  781.0
    ##  [211] 4143.0  428.0  451.0  509.0  626.0  481.0 4155.0  517.0  634.0 4161.0
    ##  [221]  443.0 4165.0  495.0  449.0  646.0  501.0 4175.0  465.0  459.0  604.0
    ##  [231]  606.0  489.0  482.0 4189.0 2586.0  536.0  499.0 4197.0 1378.0  561.0
    ##  [241]  843.0  493.0  567.0  744.0  634.0  517.0  855.0 3412.0 4219.0  564.0
    ##  [251]  583.0   49.0   64.0 3721.0  225.0  196.0 3721.0    9.0  324.0    1.0
    ##  [261]    9.0  121.0 2916.0 3721.0 1521.0  225.0 1521.0   81.0  196.0 3249.0
    ##  [271] 3721.0    1.0 3721.0  169.0    1.0    9.0   64.0   81.0  196.0   25.0
    ##  [281] 3721.0   49.0  441.0  196.0 3721.0 2116.0   81.0  169.0   25.0 3721.0
    ##  [291] 2116.0   81.0  169.0   25.0 3721.0 3721.0 1156.0  441.0  324.0  324.0
    ##  [301]   81.0    9.0    1.0  196.0   25.0 3721.0  729.0  196.0  196.0   81.0
    ##  [311]   25.0 3721.0  324.0   81.0  256.0  256.0   25.0   16.0 3721.0 1521.0
    ##  [321]   64.0   25.0 3721.0    9.0   25.0   81.0  144.0   81.0  196.0   49.0
    ##  [331] 3721.0  225.0   36.0   36.0 3721.0    1.0 3721.0    9.0   64.0  441.0
    ##  [341]  324.0    9.0   64.0 3721.0    1.0  196.0   16.0 3721.0  121.0   81.0
    ##  [351]  144.0  144.0   25.0   16.0 3721.0   25.0  484.0   25.0  324.0  625.0
    ##  [361]  225.0  196.0   25.0 3721.0   81.0  196.0  361.0   81.0   16.0   25.0
    ##  [371] 3721.0 2601.0  225.0  441.0 3721.0 1521.0  441.0  324.0  196.0 3721.0
    ##  [381]  225.0  196.0 3721.0 1521.0   64.0   25.0 3721.0 1521.0   25.0  144.0
    ##  [391]  144.0  625.0 3721.0    1.0  196.0   16.0 3721.0   25.0  484.0   25.0
    ##  [401]  324.0  625.0 3721.0  225.0 1521.0   64.0   25.0  324.0 3721.0  361.0
    ##  [411] 1521.0  225.0  324.0  625.0 3721.0   81.0  361.0 3721.0 1521.0   25.0
    ##  [421]  144.0  144.0   81.0  196.0 3249.0 3721.0  625.0  225.0  441.0 3721.0
    ##  [431]  361.0  225.0  169.0   25.0    4.0  225.0   16.0  625.0 3721.0   16.0
    ##  [441]   81.0   25.0   16.0 3721.0 2025.0   81.0  361.0 1521.0   25.0  324.0
    ##  [451] 3721.0  121.0   81.0  144.0  144.0   25.0   16.0 3721.0   64.0   25.0
    ##  [461]  324.0 3721.0    4.0    1.0    4.0   25.0   61.0   57.0    3.0    1.0
    ##  [471]   21.0   19.0    5.0   61.0   19.0    8.0    5.0   61.0    3.0   15.0
    ##  [481]   21.0   12.0    4.0   14.0   57.0   39.0   61.0    1.0    6.0    6.0
    ##  [491]   15.0   18.0    4.0   61.0   39.0   15.0   61.0    6.0    5.0    5.0
    ##  [501]    4.0   61.0    9.0   39.0   61.0   27.0   14.0    4.0   61.0   23.0
    ##  [511]    5.0   57.0   18.0    5.0   61.0   19.0    5.0   14.0    4.0  109.0
    ##  [521]  114.0  107.0  161.0  116.0  105.0  115.0   16.0   12.0    5.0   61.0
    ##  [531]   39.0   15.0   61.0   39.0    8.0    5.0   61.0   13.0   15.0   15.0
    ##  [541]   14.0   61.0   45.0    5.0   16.0   39.0    5.0   13.0    2.0    5.0
    ##  [551]   18.0   61.0   13.0   25.0   61.0    3.0   15.0   21.0   19.0    9.0
    ##  [561]   14.0   61.0   39.0   18.0    9.0    5.0    4.0   61.0   18.0    5.0
    ##  [571]    5.0    6.0    5.0   18.0   61.0    6.0   15.0   18.0   61.0   39.0
    ##  [581]    8.0    5.0   61.0   22.0    5.0   18.0   25.0   61.0    6.0    9.0
    ##  [591]   18.0   19.0   39.0   61.0   39.0    9.0   13.0    5.0   61.0   40.0
    ##  [601]   15.0   23.0   61.0    8.0    5.0   57.0   19.0   61.0    4.0   15.0
    ##  [611]    9.0   14.0    7.0   61.0    8.0   15.0   18.0   19.0    5.0   63.0
    ##  [621]   61.0    9.0   39.0   57.0   19.0   61.0   36.0   21.0   14.0    5.0
    ##  [631]   61.0   46.0    9.0   13.0    5.0   61.0   46.0    9.0   13.0    5.0
    ##  [641]   61.0   61.0   35.0   39.0   57.0   19.0   61.0   19.0    9.0   12.0
    ##  [651]   12.0   25.0   54.0   61.0   14.0   15.0   56.0   61.0   49.0    8.0
    ##  [661]    5.0   14.0   61.0    1.0   61.0   18.0   15.0    3.0   11.0    5.0
    ##  [671]   39.0   61.0   19.0    8.0    9.0   16.0   61.0    5.0   24.0   16.0
    ##  [681]   12.0   15.0    4.0    5.0   19.0   61.0   27.0   14.0    4.0   61.0
    ##  [691]    5.0   22.0    5.0   18.0   25.0    2.0   15.0    4.0   25.0   61.0
    ##  [701]   19.0   39.0    9.0   12.0   12.0   61.0   23.0    1.0   14.0   39.0
    ##  [711]   19.0   61.0   39.0   15.0   61.0    6.0   12.0   25.0   61.0   45.0
    ##  [721]   15.0   13.0    5.0   61.0   19.0    1.0   25.0   61.0    1.0   61.0
    ##  [731]   13.0    1.0   14.0   61.0    1.0    9.0   14.0   57.0   39.0   61.0
    ##  [741]    8.0    1.0   16.0   16.0   25.0   61.0   47.0   14.0   12.0    5.0
    ##  [751]   19.0   19.0   61.0    0.5   30.5    6.5    0.5    7.0   30.5   19.5
    ##  [761]    9.0   10.5    6.0   12.5   30.5    2.0    4.5    2.5    9.5   30.5
    ##  [771]   20.5    4.0   27.0   30.5   11.5    4.0   12.5   28.0   30.5   23.0
    ##  [781]    4.5    6.5    2.5   30.5   23.0    4.5    6.5    2.5   30.5   30.5
    ##  [791]   14.0    0.5    1.0   12.5   30.5    6.5    0.5    5.5    2.5   30.5
    ##  [801]    0.5   30.5    9.5    8.0    2.5    2.5    1.5    4.0   27.0   30.5
    ##  [811]    9.5   19.5    0.5    9.0   30.5   11.5    0.5    9.0    9.5   30.5
    ##  [821]    3.0    6.0   12.5   30.5   20.0    2.5    4.5    3.5    4.0    1.0
    ##  [831]    7.5    9.0    9.5   30.5    5.0   10.5    9.5   19.5   30.5    9.5
    ##  [841]    4.0    4.5    7.0    2.5   30.5    4.5   19.5   30.5    7.5    7.0
    ##  [851]   30.5   14.0   10.5   19.5   30.5    4.5    3.0   30.5    0.5   30.5
    ##  [861]    7.0    4.5    3.5    4.0   19.5   30.5    3.0    0.5    6.0    6.0
    ##  [871]    9.5   30.5    0.5    7.0    2.0   30.5    0.5   30.5    1.0    7.5
    ##  [881]    6.5    1.0   30.5    3.0    0.5    6.0    6.0    9.5   30.5   24.5
    ##  [891]    4.5    6.0    6.0   30.5    0.5    7.0   12.5    1.0    7.5    2.0
    ##  [901]   12.5   30.5    9.5    2.5    2.5   30.5   19.5    4.0    2.5   30.5
    ##  [911]    2.0    0.5   11.5    7.0   30.5   23.0    4.5    6.5    2.5   30.5
    ##  [921]   23.0    4.5    6.5    2.5   30.5   30.5   17.5    9.5   30.5    4.5
    ##  [931]   19.5   30.5    9.5    4.5    6.0    6.0   12.5   27.0   30.5    7.0
    ##  [941]    7.5   28.0   30.5   24.5    4.0    2.5    7.0   30.5    0.5   30.5
    ##  [951]    9.0    7.5    1.5    5.5    2.5   19.5   30.5    1.0    6.0    7.5
    ##  [961]   11.5    9.5   30.5   10.5    8.0   30.5   13.5    7.0    2.0   30.5
    ##  [971]    2.5   11.0    2.5    9.0   12.5    1.0    7.5    2.0   12.5   30.5
    ##  [981]    9.5   19.5    4.5    6.0    6.0   30.5   11.5    0.5    7.0   19.5
    ##  [991]    9.5   30.5   19.5    7.5   30.5    3.0    6.0   12.5   30.5   22.5
    ## [1001]    7.5    6.5    2.5   30.5    9.5    0.5   12.5   30.5    6.5    0.5
    ## [1011]    7.0   30.5    0.5    4.5    7.0   28.5   19.5   30.5    4.0    0.5
    ## [1021]    8.0    8.0   12.5   27.0   30.5   19.5    9.0   10.5    6.0   12.5
    ## [1031]   30.5   23.5    7.0   19.5    4.5    6.0   30.5    0.5   30.5    6.5
    ## [1041]    0.5    7.0   30.5   19.5    9.0   10.5    6.0   12.5   30.5    2.0
    ## [1051]    4.5    2.5    9.5   30.5   20.5    4.0   27.0   30.5   11.5    4.0
    ## [1061]   12.5   28.0   30.5   20.5    4.0   27.0   30.5   11.5    4.0   12.5
    ## [1071]   28.0   30.5   22.5    4.5    3.5    7.0   30.5    7.5   28.5   30.5
    ## [1081]   19.5    4.0    2.5   30.5   23.0    4.5    6.5    2.5    9.5   30.5
    ## [1091]   23.0    4.5    6.5    2.5   30.5   23.0    4.5    6.5    2.5   30.5
    ## [1101]   30.5   22.5    4.5    3.5    7.0   30.5    7.5   28.5   30.5   19.5
    ## [1111]    4.0    2.5   30.5   19.5    4.5    6.5    2.5    9.5   30.5    6.5
    ## [1121]    2.5    9.5    9.5   30.5   11.5    4.5   19.5    4.0   30.5   12.5
    ## [1131]    7.5   10.5    9.0   30.5    6.5    4.5    7.0    2.0   30.5   17.0
    ## [1141]   10.5    9.0    9.0   12.5   30.5    1.0    2.5    3.0    7.5    9.0
    ## [1151]    2.5   30.5    4.5   19.5   28.5    9.5   30.5   19.5    7.5    7.5
    ## [1161]   30.5    6.0    0.5   19.5    2.5   30.5   19.0    2.5   19.5   28.5
    ## [1171]    9.5   30.5    3.0    0.5    6.0    6.0   30.5    4.5    7.0   30.5
    ## [1181]    6.0    7.5   11.0    2.5   27.0   30.5    3.5    2.5   19.5   30.5
    ## [1191]    6.5    0.5    9.0    9.0    4.5    2.5    2.0   27.0   30.5    4.0
    ## [1201]    0.5   11.0    2.5   30.5    0.5   30.5    1.0    0.5    1.0   12.5
    ## [1211]   30.5   24.5    2.5   28.5    6.0    6.0   30.5    1.5    0.5    6.0
    ## [1221]    6.0   30.5    4.0    4.5    6.5   30.5   20.0    0.5   19.5    2.5
    ## [1231]   27.0   30.5    4.5    3.0   30.5    4.5   19.5   28.5    9.5   30.5
    ## [1241]    0.5   30.5    1.0    7.5   12.5   30.5   23.0    4.5    6.5    2.5
    ## [1251]   30.5   23.0    4.5    6.5    2.5

**HQ UPDATE:** Headquarters has informed you that at this stage of
decoding, there should be 496 numbers in the secret message that are
below 17.

5.  Turn your vector of numbers into a matrix with 5 columns.
6.  Separately from your top secret numbers, create a vector of all the
    even numbers between 1 and 502. Name it “`evens`”. That is, `evens`
    should be an R object that contain the values 2, 4, 6, 8, …, 502.
7.  Subtract the “evens” vector from the first column of your secret
    message matrix.
8.  Subtract 100 from all numbers 18-24th rows of the 3rd column.
9.  Multiply all numbers in the 4th and 5th column by 2.
10. Turn your matrix back into a vector.

``` r
top_secret3 <- matrix(top_secret2, ncol = 5)
evens <- seq(2,502,2)
top_secret3[,1] <- top_secret3[,1]-evens
top_secret3[18:24] <- top_secret3[18:24]-100
top_secret3[,4:5] <- top_secret3[,4:5]*2
vec <- c(top_secret3)
```

**HQ UPDATE:** Headquarters has informed you that at this stage of
decoding, all numbers in indices 500 and beyond are below 100.

11. Take the square root of all numbers in indices 38 to 465.
12. Round all numbers to the nearest whole number.
13. Replace all instances of the number 39 with 20.

``` r
vec[38:465] <- sqrt(vec[38:465])
vec <- round(vec)
vec <- replace(vec, vec==39, 20)
my_symbols <- vec
```

**HQ UPDATE:** Headquarters has informed you that your final message
should have 421 even numbers.

![](README-img/noun_pause.png) **Planned Pause Point**: If things made
sense, feel free to continue on while you wait. Otherwise, contact your
instructor to have them verify your work.

## The secret message!

Use your final vector of numbers as indices for `my_symbols` to discover
the final message, by running the following code:

``` r
stringr::str_c(my_symbols$Symbol[top_secret], collapse = "")
```

    ## Error in my_symbols$Symbol: $ operator is invalid for atomic vectors

Google the first line of this message, if you do not recognize it, to
see what it is.

**delete this line and comment on what on the activity as a whole**

Comment on what you noticed about the activity as a whole.

**Response**:

Knit, then stage everything listed in your **Git** pane, commit (with a
meaningful commit message), and push to your GitHub repo. Go to GitHub
and verify that your `activity03-r-intro.Rmd` file appears as you
intended it to.

You can now go back to the `README` file.

## Attribution

This activity is based on a lab from [Dr. Kelly
Bodwin](https://www.kelly-bodwin.com/)’s Stat 331 course