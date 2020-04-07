---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: single
---
<div class="tabs">

    <div class="tab">
        <input type="radio" id="tab-1" name="tab-group-1" checked>
        <label for="tab-1">World</label>

        <div class="tab-content">
            <h2 class="centered">Country Trends</h2>
            <div id="country_vis"></div>
        </div>
    </div>

    <div class="tab">
        <input type="radio" id="tab-2" name="tab-group-1">
        <label for="tab-2">USA</label>

        <div class="tab-content">
            <h2 class="centered">State Trends</h2>
            <div id="state_vis"></div>
        </div>
    </div>

</div>

<h2>About</h2>
<p>
    The rapid spread of COVID-19 has led many countries and regions to enact various interventions, such as social
    distancing, school closures, and border control in order to mitigate the growth of infection rates. Understanding the effects
    of these policies is particularly important since every intervention strategy comes with its side effects.
    For example, in addition to the economic impact to businesses, there are
    <a href="https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)30460-8/fulltext">
    negative mental health implications
    </a> to self-isolation and quarantine.
</p>
<p>
    To this end, in this project, we wanted to understand the impact of strategies and their combinations on the disease
    spread, by looking at how the growth curve evolves. We have been manually collecting data at the country, state, and
    county level for various types of interventions to understand their effects. (<b>Disclaimer</b>: There is danger in
    extrapolating too much from limited historical data, especially since many of the case numbers are subjected to
    other confounds, such as the amount and availability of tests. We will be keeping the dashboard up-to-date with
    latest data to see how these trends unfold.)
</p>

<h2 id="country_vis_section">Explore Country-Level Trends</h2>
<p>
    First, we plot the log of the number confirmed cases across the top ten countries with highest number of cases. We
    overlaid SARS-CoV-2 trends with various countermeasures taken by governing entities. We invite the reader to reveal
    such measures in the chart by clicking the legend, the dropdown below the chart, or the chart itself.
</p>
 
{% comment %} 
<div id="country_vis" class="overflow-center"></div>
-------------------------------------------------------
{% endcomment %} 

<p>
    A lockdown can be a full lockdown in that there is a nation-wide declaration of a lockdown (level of enforcement? or
    simply stay-at-home-order? Need more info here). On the other hand, a partial lockdown means that some but not all
    regions within the country that have declared a lockdown, such as in case of the United States. We also plot a
    projection line for the original trajectory of the trend before the lockdown date. The projection extrapolates the
    growth curve based on the slope computed up until the lockdown date. This projection is based on the simple
    assumption that the growth rate stays fixed throughout the entire period of time, which is not always a valid
    assumption for a number of reasons. For example, as the number of infected individuals increases, the
    <a href="https://www.washingtonpost.com/graphics/2020/world/corona-simulator/">
    growth will likely slow
    </a>
    due to the growing number of recovered people with immunity. Nevertheless, this serves as one comparison point that
    we can use to understand the effects of these interventions in slowing the infection rates.
</p>

<h2 id="state_vis_section">Explore State-Level Trends</h2>
Now we take a look at the state-level trends in the US. 
{% comment %} 
<div id="state_vis" class="overflow-center"></div>
-------------------------------------------------------
{% endcomment %} 

The trends for US states are less clear. For some states, such as New York and
Illinois, there are visible decreases in growth of the number of confirmed
cases. But for other states, such as California and Pennsylvania, the trend is
less clear. We note that this does not mean that stay-at-home policies are less
effective in these region. 

{% comment %} 
There are many potential reasons why: 
- Variation in the availability of level of testing across states.
	- Stay-at-home order are less strict than full lockdown (in some of the country data, esp European and Asian countries). It might take more time for the data to show decreases.
 <div style="display: inline-block;">
	<div id="state_big_changes" style="width: 40%;"></div>
	<div id="state_minimal_changes" style="width: 40%;"></div>
</div>
{% endcomment %} 

<h3>Acknowledgments</h3>
<p>
We build on the preprocessing script by
<a href="https://github.com/wadefagen/91-DIVOC/blob/master/pages/covid-visualization/processData.py">Wade Fagen</a>
for this work.
</p>

<h3 id="references">Sources</h3>
<ol id="references-list" class="references">
    <li id="jhu_data" class="title">
    Data derived from John Hopkins CSSE <a href="https://github.com/CSSEGISandData/COVID-19">[link]</a>
    </li>
</ol>
