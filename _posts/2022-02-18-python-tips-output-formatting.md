---
keywords: fastai
description: Some handy Python output tips
title: Python - A collection of output formatting tips
toc: true 
badges: true
comments: true
categories: [python]
show_tags: true
image: images/copied_from_nb/images/2022-02-18-python-tips-output-formatting.jpeg
nb_path: _notebooks/2022-02-18-python-tips-output-formatting.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-02-18-python-tips-output-formatting.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="/myblog/images/copied_from_nb/images/2022-02-18-python-tips-output-formatting.jpeg" alt=""></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="About">About<a class="anchor-link" href="#About"> </a></h2><p>This notebook is a collection of useful tips to format Python string literals and output.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Environment">Environment<a class="anchor-link" href="#Environment"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<details class="description">
      <summary class="btn btn-sm" data-open="Hide Code" data-close="Show Code"></summary>
        <p><div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">platform</span> <span class="kn">import</span> <span class="n">python_version</span>

<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;python==&quot;</span> <span class="o">+</span> <span class="n">python_version</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>
</p>
    </details>
<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>python==3.8.5
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="f-string:-Expressions-inside-a-string">f-string: Expressions inside a string<a class="anchor-link" href="#f-string:-Expressions-inside-a-string"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">r</span> <span class="o">=</span> <span class="s1">&#39;red&#39;</span>
<span class="n">g</span> <span class="o">=</span> <span class="s1">&#39;green&#39;</span>
<span class="n">b</span> <span class="o">=</span> <span class="mi">1001</span>

<span class="c1"># f-string has a simple syntax. Put &#39;f&#39; at the start of string, and put expressions in {}</span>
<span class="sa">f</span><span class="s2">&quot;Stop = </span><span class="si">{</span><span class="n">r</span><span class="si">}</span><span class="s2">, Go = </span><span class="si">{</span><span class="n">g</span><span class="si">}</span><span class="s2">&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;Stop = red, Go = green&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># &#39;F&#39; can also be used to start an f-string</span>
<span class="sa">F</span><span class="s2">&quot;binary = </span><span class="si">{</span><span class="n">b</span><span class="si">}</span><span class="s2">. If you need value in brackets </span><span class="se">{{</span><span class="si">{</span><span class="n">b</span><span class="si">}</span><span class="se">}}</span><span class="s2">&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;binary = 1001. If you need value in brackets {1001}&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># f-string can also be started with &quot;&quot;&quot; quotes</span>
<span class="sa">f</span><span class="s2">&quot;&quot;&quot;</span><span class="si">{</span><span class="n">r</span><span class="si">}</span><span class="s2"> or </span><span class="si">{</span><span class="n">g</span><span class="si">}</span><span class="s2">&quot;&quot;&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;red or green&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># f-string on multiple lines. </span>
<span class="c1"># 1. Use &quot;&quot;&quot; with backslash \</span>
<span class="sa">f</span><span class="s2">&quot;&quot;&quot;</span><span class="si">{</span><span class="n">r</span><span class="si">}</span><span class="se">\</span>
<span class="s2"> or </span><span class="se">\</span>
<span class="si">{</span><span class="n">g</span><span class="si">}</span><span class="s2">&quot;&quot;&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;red or green&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># f-string on multiple lines. </span>
<span class="c1"># 2. Use only backslash \</span>
<span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">r</span><span class="si">}</span><span class="s2">&quot;</span> \
<span class="s2">&quot; or &quot;</span> \
<span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">g</span><span class="si">}</span><span class="s2">&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;red or green&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># f-string on multiple lines. </span>
<span class="c1"># 3. Use  brackets ()</span>
<span class="p">(</span><span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">r</span><span class="si">}</span><span class="s2">&quot;</span>
<span class="s2">&quot; or &quot;</span>
<span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">g</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;red or green&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># you can also compute an expression in an f-string</span>
<span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span> <span class="mi">40</span> <span class="o">+</span> <span class="mi">2</span><span class="si">}</span><span class="s2">&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;42&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># functions can also be called from inside an f-string</span>
<span class="sa">f</span><span class="s2">&quot;This is in CAPS: </span><span class="si">{</span> <span class="nb">str</span><span class="o">.</span><span class="n">upper</span><span class="p">(</span><span class="n">r</span><span class="p">)</span> <span class="si">}</span><span class="s2">&quot;</span>

<span class="c1"># same as above</span>
<span class="sa">f</span><span class="s2">&quot;This is in CAPS: </span><span class="si">{</span> <span class="n">r</span><span class="o">.</span><span class="n">upper</span><span class="p">()</span> <span class="si">}</span><span class="s2">&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;This is in CAPS: RED&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="f-string:-Padding-the-output">f-string: Padding the output<a class="anchor-link" href="#f-string:-Padding-the-output"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Inside f-string, passing an integer after &#39;:&#39; will cause that field to be a minimum number of characters wide. </span>
<span class="c1"># This is useful for making columns line up.</span>

<span class="n">groups</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">&#39;small&#39;</span><span class="p">:</span> <span class="mi">100</span><span class="p">,</span>
    <span class="s1">&#39;medium&#39;</span><span class="p">:</span> <span class="mi">100100</span><span class="p">,</span>
    <span class="s1">&#39;large&#39;</span><span class="p">:</span> <span class="mi">100100100</span>
<span class="p">}</span>

<span class="k">for</span> <span class="n">group</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">groups</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">value</span><span class="si">:</span><span class="s2">10</span><span class="si">}</span><span class="s2"> ==&gt; </span><span class="si">{</span><span class="n">group</span><span class="si">:</span><span class="s2">20</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="s1">&#39;****&#39;</span><span class="o">*</span><span class="mi">10</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span> <span class="c1"># another nice trick</span>

<span class="k">for</span> <span class="n">group</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">groups</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">group</span><span class="si">:</span><span class="s2">10</span><span class="si">}</span><span class="s2"> ==&gt; </span><span class="si">{</span><span class="n">value</span><span class="si">:</span><span class="s2">20</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>       100 ==&gt; small               
    100100 ==&gt; medium              
 100100100 ==&gt; large               
****************************************
small      ==&gt;                  100
medium     ==&gt;               100100
large      ==&gt;            100100100
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="f-string:-Binary-and-hexadecimal-format">f-string: Binary and hexadecimal format<a class="anchor-link" href="#f-string:-Binary-and-hexadecimal-format"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># you can convert integers to binary and hexadecimal format</span>
<span class="nb">print</span><span class="p">(</span> <span class="sa">f</span><span class="s2">&quot;5 in binary </span><span class="si">{</span><span class="mi">5</span><span class="si">:</span><span class="s2">b</span><span class="si">}</span><span class="s2">&quot;</span> <span class="p">)</span>

<span class="nb">print</span><span class="p">(</span> <span class="sa">f</span><span class="s2">&quot;5 in hexadecimal </span><span class="si">{</span><span class="mi">5</span><span class="si">:</span><span class="s2">#b</span><span class="si">}</span><span class="s2">&quot;</span> <span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>5 in binary 101
5 in hexadecimal 0b101
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="f-string:-Controlling-the-decimal-places">f-string: Controlling the decimal places<a class="anchor-link" href="#f-string:-Controlling-the-decimal-places"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">math</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;The value of pi is approximately (no formatting) </span><span class="si">{</span><span class="n">math</span><span class="o">.</span><span class="n">pi</span><span class="si">}</span><span class="s1">&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;The value of pi is approximately </span><span class="si">{</span><span class="n">math</span><span class="o">.</span><span class="n">pi</span> <span class="si">:</span><span class="s1">.3f</span><span class="si">}</span><span class="s1">&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>The value of pi is approximately (no formatting) 3.141592653589793
The value of pi is approximately 3.142
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="f-string:-Putting-commas-in-numerical-output">f-string: Putting commas in numerical output<a class="anchor-link" href="#f-string:-Putting-commas-in-numerical-output"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">num</span> <span class="o">=</span> <span class="mf">3214298342.234</span>
<span class="sa">f</span><span class="s2">&quot;</span><span class="si">{</span><span class="n">num</span><span class="si">:</span><span class="s2">,</span><span class="si">}</span><span class="s2">&quot;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;3,214,298,342.234&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

</div>
 

