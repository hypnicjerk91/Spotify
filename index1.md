<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
  <meta http-equiv="Content-Style-Type" content="text/css" />
  <meta name="generator" content="pandoc" />
  <title>index1.utf8</title>
  <style type="text/css">
      code{white-space: pre-wrap;}
      span.smallcaps{font-variant: small-caps;}
      span.underline{text-decoration: underline;}
      div.column{display: inline-block; vertical-align: top; width: 50%;}
  </style>
  <style type="text/css">
a.sourceLine { display: inline-block; line-height: 1.25; }
a.sourceLine { pointer-events: none; color: inherit; text-decoration: inherit; }
a.sourceLine:empty { height: 1.2em; }
.sourceCode { overflow: visible; }
code.sourceCode { white-space: pre; position: relative; }
div.sourceCode { margin: 1em 0; }
pre.sourceCode { margin: 0; }
@media screen {
div.sourceCode { overflow: auto; }
}
@media print {
code.sourceCode { white-space: pre-wrap; }
a.sourceLine { text-indent: -1em; padding-left: 1em; }
}
pre.numberSource a.sourceLine
  { position: relative; left: -4em; }
pre.numberSource a.sourceLine::before
  { content: attr(title);
    position: relative; left: -1em; text-align: right; vertical-align: baseline;
    border: none; pointer-events: all; display: inline-block;
    -webkit-touch-callout: none; -webkit-user-select: none;
    -khtml-user-select: none; -moz-user-select: none;
    -ms-user-select: none; user-select: none;
    padding: 0 4px; width: 4em;
    color: #aaaaaa;
  }
pre.numberSource { margin-left: 3em; border-left: 1px solid #aaaaaa;  padding-left: 4px; }
div.sourceCode
  {  }
@media screen {
a.sourceLine::before { text-decoration: underline; }
}
code span.al { color: #ff0000; font-weight: bold; } /* Alert */
code span.an { color: #60a0b0; font-weight: bold; font-style: italic; } /* Annotation */
code span.at { color: #7d9029; } /* Attribute */
code span.bn { color: #40a070; } /* BaseN */
code span.bu { } /* BuiltIn */
code span.cf { color: #007020; font-weight: bold; } /* ControlFlow */
code span.ch { color: #4070a0; } /* Char */
code span.cn { color: #880000; } /* Constant */
code span.co { color: #60a0b0; font-style: italic; } /* Comment */
code span.cv { color: #60a0b0; font-weight: bold; font-style: italic; } /* CommentVar */
code span.do { color: #ba2121; font-style: italic; } /* Documentation */
code span.dt { color: #902000; } /* DataType */
code span.dv { color: #40a070; } /* DecVal */
code span.er { color: #ff0000; font-weight: bold; } /* Error */
code span.ex { } /* Extension */
code span.fl { color: #40a070; } /* Float */
code span.fu { color: #06287e; } /* Function */
code span.im { } /* Import */
code span.in { color: #60a0b0; font-weight: bold; font-style: italic; } /* Information */
code span.kw { color: #007020; font-weight: bold; } /* Keyword */
code span.op { color: #666666; } /* Operator */
code span.ot { color: #007020; } /* Other */
code span.pp { color: #bc7a00; } /* Preprocessor */
code span.sc { color: #4070a0; } /* SpecialChar */
code span.ss { color: #bb6688; } /* SpecialString */
code span.st { color: #4070a0; } /* String */
code span.va { color: #19177c; } /* Variable */
code span.vs { color: #4070a0; } /* VerbatimString */
code span.wa { color: #60a0b0; font-weight: bold; font-style: italic; } /* Warning */
  </style>
</head>
<body>
<h2 id="top-50-tracks-in-2019">Top 50 Tracks in 2019</h2>
<p>An analysis of the top 50 tracks on Spotify with R. <strong>What a way to say goodbye to 2019!</strong> You can find the dataset on Kaggle, <a href="https://www.kaggle.com/leonardopena/top50spotify2019" class="uri">https://www.kaggle.com/leonardopena/top50spotify2019</a>.</p>
<h3 id="lets-take-a-look-at-the-dataset">Let’s take a look at the dataset:</h3>
<div class="sourceCode" id="cb1"><pre class="sourceCode r"><code class="sourceCode r"><a class="sourceLine" id="cb1-1" title="1"><span class="kw">summary</span>(top50)</a></code></pre></div>
<pre><code>##        X                                   Track.Name        Artist.Name
##  Min.   : 1.00   0.958333333333333              : 1   Ed Sheeran   : 4  
##  1st Qu.:13.25   7 rings                        : 1   Ariana Grande: 2  
##  Median :25.50   Antisocial (with Travis Scott) : 1   Billie Eilish: 2  
##  Mean   :25.50   bad guy                        : 1   J Balvin     : 2  
##  3rd Qu.:37.75   bad guy (with Justin Bieber)   : 1   Lil Nas X    : 2  
##  Max.   :50.00   Beautiful People (feat. Khalid): 1   Marshmello   : 2  
##                  (Other)                        :44   (Other)      :36  
##               Genre    Beats.Per.Minute     Energy       Danceability  
##  dance pop       : 8   Min.   : 85.0    Min.   :32.00   Min.   :29.00  
##  pop             : 7   1st Qu.: 96.0    1st Qu.:55.25   1st Qu.:67.00  
##  latin           : 5   Median :104.5    Median :66.50   Median :73.50  
##  canadian hip hop: 3   Mean   :120.1    Mean   :64.06   Mean   :71.38  
##  edm             : 3   3rd Qu.:137.5    3rd Qu.:74.75   3rd Qu.:79.75  
##  brostep         : 2   Max.   :190.0    Max.   :88.00   Max.   :90.00  
##  (Other)         :22                                                   
##  Loudness..dB..      Liveness        Valence.        Length.     
##  Min.   :-11.00   Min.   : 5.00   Min.   :10.00   Min.   :115.0  
##  1st Qu.: -6.75   1st Qu.: 8.00   1st Qu.:38.25   1st Qu.:176.8  
##  Median : -6.00   Median :11.00   Median :55.50   Median :198.0  
##  Mean   : -5.66   Mean   :14.66   Mean   :54.60   Mean   :201.0  
##  3rd Qu.: -4.00   3rd Qu.:15.75   3rd Qu.:69.50   3rd Qu.:217.5  
##  Max.   : -2.00   Max.   :58.00   Max.   :95.00   Max.   :309.0  
##                                                                  
##  Acousticness..   Speechiness.     Popularity   
##  Min.   : 1.00   Min.   : 3.00   Min.   :70.00  
##  1st Qu.: 8.25   1st Qu.: 5.00   1st Qu.:86.00  
##  Median :15.00   Median : 7.00   Median :88.00  
##  Mean   :22.16   Mean   :12.48   Mean   :87.50  
##  3rd Qu.:33.75   3rd Qu.:15.00   3rd Qu.:90.75  
##  Max.   :75.00   Max.   :46.00   Max.   :95.00  
## </code></pre>
<div style="margin-bottom:50px;">

</div>
<div class="sourceCode" id="cb3"><pre class="sourceCode r"><code class="sourceCode r"><a class="sourceLine" id="cb3-1" title="1"><span class="co"># Plotting by popularity</span></a>
<a class="sourceLine" id="cb3-2" title="2">top50<span class="op">$</span>Track.Name&lt;-<span class="kw">factor</span>(top50<span class="op">$</span>Track.Name,<span class="dt">levels=</span>top50<span class="op">$</span>Track.Name[<span class="kw">order</span>(top50<span class="op">$</span>Popularity)])</a>
<a class="sourceLine" id="cb3-3" title="3"></a>
<a class="sourceLine" id="cb3-4" title="4"><span class="kw">ggplot</span>(top50,<span class="kw">aes</span>(<span class="dt">y=</span>top50<span class="op">$</span>Track.Name,<span class="dt">x=</span>top50<span class="op">$</span>Popularity)) <span class="op">+</span><span class="st"> </span></a>
<a class="sourceLine" id="cb3-5" title="5"><span class="st">  </span><span class="kw">xlab</span>(<span class="st">&quot;Popularity&quot;</span>) <span class="op">+</span><span class="st"> </span></a>
<a class="sourceLine" id="cb3-6" title="6"><span class="st">  </span><span class="kw">ylab</span>(<span class="st">&quot;Track name&quot;</span>) <span class="op">+</span><span class="st"> </span></a>
<a class="sourceLine" id="cb3-7" title="7"><span class="st">  </span><span class="kw">geom_bar</span>(<span class="dt">stat=</span><span class="st">&quot;identity&quot;</span>) <span class="op">+</span></a>
<a class="sourceLine" id="cb3-8" title="8"><span class="st">  </span><span class="kw">theme</span>(<span class="dt">axis.text.x=</span><span class="kw">element_text</span>(<span class="dt">angle=</span><span class="dv">90</span>,<span class="dt">hjust=</span><span class="dv">1</span>))</a></code></pre></div>
<img src="index1_files/figure-html/popularity_plot-1.png" /><!-- -->
<div style="margin-bottom:50px;">

</div>
<h3 id="what-about-the-music-genre">What About the Music Genre?</h3>
<div style="margin-bottom:50px;">

</div>
<div class="sourceCode" id="cb4"><pre class="sourceCode r"><code class="sourceCode r"><a class="sourceLine" id="cb4-1" title="1"><span class="co"># Plotting Genre Count</span></a>
<a class="sourceLine" id="cb4-2" title="2"></a>
<a class="sourceLine" id="cb4-3" title="3">genre_count<span class="op">$</span>Genre&lt;-<span class="kw">factor</span>(genre_count<span class="op">$</span>Genre,<span class="dt">levels=</span>genre_count<span class="op">$</span>Genre[<span class="kw">order</span>(genre_count<span class="op">$</span>count)])</a>
<a class="sourceLine" id="cb4-4" title="4"></a>
<a class="sourceLine" id="cb4-5" title="5"><span class="kw">ggplot</span>(genre_count,<span class="kw">aes</span>(<span class="dt">x=</span>genre_count<span class="op">$</span>Genre,<span class="dt">y=</span>genre_count<span class="op">$</span>count)) <span class="op">+</span><span class="st"> </span></a>
<a class="sourceLine" id="cb4-6" title="6"><span class="st">  </span><span class="kw">xlab</span>(<span class="st">&quot;Genre&quot;</span>) <span class="op">+</span><span class="st"> </span></a>
<a class="sourceLine" id="cb4-7" title="7"><span class="st">  </span><span class="kw">ylab</span>(<span class="st">&quot;Count&quot;</span>) <span class="op">+</span><span class="st"> </span></a>
<a class="sourceLine" id="cb4-8" title="8"><span class="st">  </span><span class="kw">geom_bar</span>(<span class="dt">stat=</span><span class="st">&quot;identity&quot;</span>) <span class="op">+</span></a>
<a class="sourceLine" id="cb4-9" title="9"><span class="st">  </span><span class="kw">theme</span>(<span class="dt">axis.text.x=</span><span class="kw">element_text</span>(<span class="dt">angle=</span><span class="dv">90</span>,<span class="dt">hjust=</span><span class="dv">1</span>))</a></code></pre></div>
<img src="index1_files/figure-html/genre_plot-1.png" /><!-- -->
<div style="margin-bottom:50px;">

</div>
<h3 id="artists-by-number-of-songs-in-the-top-50-list">Artists by Number of Songs in the Top 50 List</h3>
<div class="sourceCode" id="cb5"><pre class="sourceCode r"><code class="sourceCode r"><a class="sourceLine" id="cb5-1" title="1">knitr<span class="op">::</span><span class="kw">kable</span>(artist_count, <span class="dt">col.names =</span> <span class="kw">c</span>(<span class="st">&quot;Artist&quot;</span>,<span class="st">&quot;Count&quot;</span>)) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">kable_styling</span>() <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">scroll_box</span>(<span class="dt">width=</span><span class="st">&quot;50%&quot;</span>,<span class="dt">height=</span><span class="st">&quot;200px&quot;</span>)</a></code></pre></div>
<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:200px; overflow-x: scroll; width:50%; ">
<table class="table" style="margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">
Artist
</th>
<th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;">
Count
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Ed Sheeran
</td>
<td style="text-align:right;">
4
</td>
</tr>
<tr>
<td style="text-align:left;">
Ariana Grande
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Billie Eilish
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
J Balvin
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Lil Nas X
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Marshmello
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Post Malone
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Sech
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Shawn Mendes
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
The Chainsmokers
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
Ali Gatie
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Anuel AA
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Bad Bunny
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Chris Brown
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Daddy Yankee
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
DJ Snake
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Drake
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Jhay Cortez
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Jonas Brothers
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Katy Perry
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Khalid
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Kygo
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Lady Gaga
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Lauv
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Lewis Capaldi
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Lil Tecca
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Lizzo
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Lunay
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Maluma
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Martin Garrix
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
MEDUZA
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Nicky Jam
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
ROSALΝA
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Sam Smith
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Taylor Swift
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Tones and I
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Y2K
</td>
<td style="text-align:right;">
1
</td>
</tr>
<tr>
<td style="text-align:left;">
Young Thug
</td>
<td style="text-align:right;">
1
</td>
</tr>
</tbody>
</table>
</div>
<div style="margin-bottom:50px;">

</div>
<h3 id="artists-by-popularity-of-songs">Artists by Popularity of Songs</h3>
<div class="sourceCode" id="cb6"><pre class="sourceCode r"><code class="sourceCode r"><a class="sourceLine" id="cb6-1" title="1">artist_pop &lt;-top50 <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">select</span>(Artist.Name,Popularity)</a>
<a class="sourceLine" id="cb6-2" title="2">artist_pop &lt;-artist_pop <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">group_by</span>(Artist.Name) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">summarise</span>(<span class="dt">average_pop=</span><span class="kw">mean</span>(Popularity)) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">arrange</span>(<span class="kw">desc</span>(average_pop))</a>
<a class="sourceLine" id="cb6-3" title="3"></a>
<a class="sourceLine" id="cb6-4" title="4">knitr<span class="op">::</span><span class="kw">kable</span>(artist_pop, <span class="dt">col.names =</span> <span class="kw">c</span>(<span class="st">&quot;Artist&quot;</span>,<span class="st">&quot;Average Popularity&quot;</span>)) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">kable_styling</span>() <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">scroll_box</span>(<span class="dt">width=</span><span class="st">&quot;50%&quot;</span>,<span class="dt">height=</span><span class="st">&quot;200px&quot;</span>)</a></code></pre></div>
<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:200px; overflow-x: scroll; width:50%; ">
<table class="table" style="margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">
Artist
</th>
<th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;">
Average Popularity
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Bad Bunny
</td>
<td style="text-align:right;">
93.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Post Malone
</td>
<td style="text-align:right;">
92.50
</td>
</tr>
<tr>
<td style="text-align:left;">
Anuel AA
</td>
<td style="text-align:right;">
92.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Billie Eilish
</td>
<td style="text-align:right;">
92.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Drake
</td>
<td style="text-align:right;">
92.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lil Tecca
</td>
<td style="text-align:right;">
92.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Daddy Yankee
</td>
<td style="text-align:right;">
91.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lizzo
</td>
<td style="text-align:right;">
91.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lunay
</td>
<td style="text-align:right;">
91.00
</td>
</tr>
<tr>
<td style="text-align:left;">
MEDUZA
</td>
<td style="text-align:right;">
91.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Sam Smith
</td>
<td style="text-align:right;">
90.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Taylor Swift
</td>
<td style="text-align:right;">
90.00
</td>
</tr>
<tr>
<td style="text-align:left;">
J Balvin
</td>
<td style="text-align:right;">
89.50
</td>
</tr>
<tr>
<td style="text-align:left;">
Ali Gatie
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Katy Perry
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lil Nas X
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Maluma
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Martin Garrix
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Sech
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Young Thug
</td>
<td style="text-align:right;">
89.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Kygo
</td>
<td style="text-align:right;">
88.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lewis Capaldi
</td>
<td style="text-align:right;">
88.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Marshmello
</td>
<td style="text-align:right;">
88.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Nicky Jam
</td>
<td style="text-align:right;">
88.00
</td>
</tr>
<tr>
<td style="text-align:left;">
ROSALΝA
</td>
<td style="text-align:right;">
88.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Y2K
</td>
<td style="text-align:right;">
88.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Ariana Grande
</td>
<td style="text-align:right;">
87.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lady Gaga
</td>
<td style="text-align:right;">
87.00
</td>
</tr>
<tr>
<td style="text-align:left;">
DJ Snake
</td>
<td style="text-align:right;">
86.00
</td>
</tr>
<tr>
<td style="text-align:left;">
The Chainsmokers
</td>
<td style="text-align:right;">
86.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Ed Sheeran
</td>
<td style="text-align:right;">
84.75
</td>
</tr>
<tr>
<td style="text-align:left;">
Khalid
</td>
<td style="text-align:right;">
84.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Jhay Cortez
</td>
<td style="text-align:right;">
83.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Tones and I
</td>
<td style="text-align:right;">
83.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Chris Brown
</td>
<td style="text-align:right;">
82.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Jonas Brothers
</td>
<td style="text-align:right;">
80.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Lauv
</td>
<td style="text-align:right;">
78.00
</td>
</tr>
<tr>
<td style="text-align:left;">
Shawn Mendes
</td>
<td style="text-align:right;">
74.50
</td>
</tr>
</tbody>
</table>
</div>
<div style="margin-bottom:50px;">

</div>
<h3 id="artists-energy">Artists’ Energy</h3>
<div class="sourceCode" id="cb7"><pre class="sourceCode r"><code class="sourceCode r"><a class="sourceLine" id="cb7-1" title="1">artist_energy&lt;-top50 <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">select</span>(Artist.Name,Energy)</a>
<a class="sourceLine" id="cb7-2" title="2">artist_energy&lt;-artist_energy <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">group_by</span>(Artist.Name) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">summarise</span>(<span class="dt">average_energy=</span><span class="kw">mean</span>(Energy)) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">arrange</span>(<span class="kw">desc</span>(average_energy))</a>
<a class="sourceLine" id="cb7-3" title="3"></a>
<a class="sourceLine" id="cb7-4" title="4">knitr<span class="op">::</span><span class="kw">kable</span>(artist_energy, <span class="dt">col.names =</span> <span class="kw">c</span>(<span class="st">&quot;Artist&quot;</span>,<span class="st">&quot;Average Energy&quot;</span>)) <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">kable_styling</span>() <span class="op">%&gt;%</span><span class="st"> </span><span class="kw">scroll_box</span>(<span class="dt">width=</span><span class="st">&quot;50%&quot;</span>,<span class="dt">height=</span><span class="st">&quot;200px&quot;</span>)</a></code></pre></div>
<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:200px; overflow-x: scroll; width:50%; ">
<table class="table" style="margin-left: auto; margin-right: auto;">
<thead>
<tr>
<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">
Artist
</th>
<th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;">
Average Energy
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Katy Perry
</td>
<td style="text-align:right;">
88.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Daddy Yankee
</td>
<td style="text-align:right;">
86.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Anuel AA
</td>
<td style="text-align:right;">
81.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Jhay Cortez
</td>
<td style="text-align:right;">
79.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lunay
</td>
<td style="text-align:right;">
78.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Nicky Jam
</td>
<td style="text-align:right;">
75.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Sech
</td>
<td style="text-align:right;">
74.5
</td>
</tr>
<tr>
<td style="text-align:left;">
MEDUZA
</td>
<td style="text-align:right;">
74.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Ed Sheeran
</td>
<td style="text-align:right;">
73.5
</td>
</tr>
<tr>
<td style="text-align:left;">
Jonas Brothers
</td>
<td style="text-align:right;">
73.0
</td>
</tr>
<tr>
<td style="text-align:left;">
J Balvin
</td>
<td style="text-align:right;">
72.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Martin Garrix
</td>
<td style="text-align:right;">
72.0
</td>
</tr>
<tr>
<td style="text-align:left;">
DJ Snake
</td>
<td style="text-align:right;">
71.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Maluma
</td>
<td style="text-align:right;">
71.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Marshmello
</td>
<td style="text-align:right;">
70.5
</td>
</tr>
<tr>
<td style="text-align:left;">
ROSALΝA
</td>
<td style="text-align:right;">
69.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Shawn Mendes
</td>
<td style="text-align:right;">
68.5
</td>
</tr>
<tr>
<td style="text-align:left;">
Kygo
</td>
<td style="text-align:right;">
68.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Sam Smith
</td>
<td style="text-align:right;">
68.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Taylor Swift
</td>
<td style="text-align:right;">
68.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lil Tecca
</td>
<td style="text-align:right;">
64.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Bad Bunny
</td>
<td style="text-align:right;">
62.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lizzo
</td>
<td style="text-align:right;">
62.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lil Nas X
</td>
<td style="text-align:right;">
60.5
</td>
</tr>
<tr>
<td style="text-align:left;">
The Chainsmokers
</td>
<td style="text-align:right;">
60.5
</td>
</tr>
<tr>
<td style="text-align:left;">
Tones and I
</td>
<td style="text-align:right;">
59.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Young Thug
</td>
<td style="text-align:right;">
59.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Post Malone
</td>
<td style="text-align:right;">
56.5
</td>
</tr>
<tr>
<td style="text-align:left;">
Ariana Grande
</td>
<td style="text-align:right;">
56.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lauv
</td>
<td style="text-align:right;">
56.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Drake
</td>
<td style="text-align:right;">
50.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Ali Gatie
</td>
<td style="text-align:right;">
46.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Chris Brown
</td>
<td style="text-align:right;">
45.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Billie Eilish
</td>
<td style="text-align:right;">
44.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lewis Capaldi
</td>
<td style="text-align:right;">
41.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Khalid
</td>
<td style="text-align:right;">
40.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Lady Gaga
</td>
<td style="text-align:right;">
39.0
</td>
</tr>
<tr>
<td style="text-align:left;">
Y2K
</td>
<td style="text-align:right;">
39.0
</td>
</tr>
</tbody>
</table>
</div>
<div style="margin-bottom:50px;">

</div>
<h3 id="which-are-the-factors-contributing-to-popularity">Which Are the Factors Contributing to Popularity?</h3>
<h4 id="to-be-continued">(to be continued)</h4>
<div style="margin-bottom:50px;">

</div>
</body>
</html>
