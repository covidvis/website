---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: single
---

About
-----
The rapid spread of COVID-19 has led many countries and regions to enact various interventions, such as social
distancing, school closures, and border control in order to mitigate the growth of infection rates. Understanding the effects
of these policies is particularly important since every intervention strategy comes with its side effects.
We wanted to understand the impact of strategies and their combinations on the disease spread.
After collecting data at the country and state levels for various types of interventions, we overlaid
them on the disease growth curves, shown below.
{% comment %}
For example, in addition to the economic impact to businesses, there are
<a href="https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)30460-8/fulltext">
negative mental health implications
</a> to self-isolation and quarantine.
{% endcomment %}

<div class="tabs">

    <div class="tab">
        <input type="radio" id="tab-1" name="tab-group-1" checked>
        <label for="tab-1">World: Cases</label>

        <div class="tab-content">
            <h2 class="centered">Country Trends</h2>
            <div id="country_vis"></div>
        </div>
    </div>
    
    <div class="tab">
        <input type="radio" id="tab-2" name="tab-group-1">
        <label for="tab-2">World: Deaths</label>

        <div class="tab-content">
            <h2 class="centered">Country Trends</h2>
            <div id="country_death_vis"></div>
        </div>
    </div>

    <div class="tab">
        <input type="radio" id="tab-3" name="tab-group-1">
        <label for="tab-3">USA: Cases</label>

        <div class="tab-content">
            <h2 class="centered">State Trends</h2>
            <div id="state_vis"></div>
        </div>
    </div>

    <div class="tab">
        <input type="radio" id="tab-4" name="tab-group-1">
        <label for="tab-4">USA: Deaths</label>

        <div class="tab-content">
            <h2 class="centered">State Trends</h2>
            <div id="state_death_vis"></div>
        </div>
    </div>

</div>
(<b>Disclaimer</b>: There is danger in
extrapolating too much from limited historical data, especially since many of the case numbers are subjected to
other confounds, such as the amount and availability of tests. We will be keeping the dashboard up-to-date with
latest data to see how these trends unfold.)

<h2 id="lockdown_section">Effect of lockdown</h2>
<p>
    First, we plot the log of the number confirmed cases across the top ten countries with highest number of cases. We
    overlaid SARS-CoV-2 trends with various countermeasures taken by governing entities. We invite the reader to reveal
    such measures in the chart by clicking the legend, the dropdown below the chart, or the chart itself.
</p>


<p>
    A lockdown can be a full lockdown in that there is a nation-wide declaration of a lockdown.{% comment %}(level of enforcement? or simply stay-at-home-order? Need more info here){% endcomment %}
    On the other hand, a partial lockdown means that some but not all
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


Team
----
Covidvis is a collaborative effort across epidemiology, public health, and visualization researchers at UC Berkeley ([EECS](https://eecs.berkeley.edu/), [School of Information](https://www.ischool.berkeley.edu/), and [School of Public Health](https://publichealth.berkeley.edu/)), University of Illinois ([Computer Science](https://www.cs.illinois.edu/)), and Georgia Tech ([Computational Science and Engineering](https://cse.gatech.edu/)). 
From the visualization side, the team includes [Doris Jung-Lin Lee](http://dorisjunglinlee.com/) (UC Berkeley School of Information); [Stephen Macke](https://smacke.net/) (University of Illinois Computer Science and UC Berkeley EECS); [Ti-Chung Cheng](https://tichung.com/), [Tana Wattanawaroon](https://www.linkedin.com/in/tanawattanawaroon/), and Pingjing Yang (University of Illinois Computer Science); and [Aditya Parameswaran](https://people.eecs.berkeley.edu/~adityagp/) (UC Berkeley School of Information and EECS).
From the public health and epidemiology side, the team includes [Ziad Obermeyer](https://publichealth.berkeley.edu/people/ziad-obermeyer/) (UC Berkeley School of Public Health) and [B Aditya Prakash](http://www.cc.gatech.edu/~badityap) (Georgia Tech Computational Science and Engineering).

Acknowledgements
----------------
We draw on data regarding COVID-19 cases and deaths from [JHU Coronavirus Resource Center](https://coronavirus.jhu.edu/data) as well as the [New York Times US dataset](https://github.com/nytimes/covid-19-data).  We draw on data regarding national and regional interventions from [Wikpedia](https://en.wikipedia.org/wiki/National_responses_to_the_2019%E2%80%9320_coronavirus_pandemic) as well as the [New York Times](https://github.com/nytimes/covid-19-data). 
There are many visualizations of COVID-19 growth curves online that we draw on for inspiration. We are fans of visualizations from [John Burn-Murdoch, Financial Times](https://www.ft.com/john-burn-murdoch), such as [this one](https://www.ft.com/coronavirus-latest), as well as the [New York Times](https://www.nytimes.com/news-event/coronavirus), such as [this](https://www.nytimes.com/interactive/2020/04/06/us/coronavirus-deaths-united-states.html), [this](https://www.nytimes.com/interactive/2020/world/coronavirus-maps.html), [this](https://www.nytimes.com/interactive/2020/04/03/upshot/coronavirus-metro-area-tracker.html), and [this](https://www.nytimes.com/interactive/2020/us/coronavirus-stay-at-home-order.html). We drew on data preprocessing scripts from [Wade Fagen](https://waf.cs.illinois.edu/)'s excellent ["Flip the script on COVID-19" dashboard](http://91-divoc.com/). 
Our visualization dashboard employs many popular open-source packages, including
[Altair](https://altair-viz.github.io/) and [Vega-Lite](https://vega.github.io/vega-lite/) for visualization,
[Pandas](https://pandas.pydata.org/) for data processing, and [Jupyter](https://jupyter.org/) for sharing code and visualizations. 
We furthermore build on the preprocessing script by
[Wade Fagen](https://github.com/wadefagen/91-DIVOC/blob/master/pages/covid-visualization/processData.py)
for this work.

FAQs
----
- *Why build yet another COVID-19 visualization?*

While there are many COVID-19 visualization dashboards, including those that employ helpful log-linear extrapolation to understand the trends in various regions, we haven't found any dashboards that try to visualize the overlaid visual impact of various intervention measures, apart from anecdotal reports of the [curve being flattened](https://www.nytimes.com/article/flatten-curve-coronavirus.html) thanks to interventions. If there are any visualization dashboards that we should be aware of and can link to, please share them with us at covidvis@berkeley.edu.

- *What's next for the project?*

The dashboards above simply scratch the surface of what can be and what needs to be done for this project. Apart from keeping our dashboards up-to-date on a regular basis, we're in the process of collecting, studying, and visualizing the impact of fine-grained interventions (specifically, the impact of various combinations of interventions, such as school closures, banning of gatherings, non-essential business closures, and so on). Beyond Wikipedia, we are aware of other data gathering efforts on this front, such as those from [Keystone](https://www.keystonestrategy.com/coronavirus-covid19-intervention-dataset-model/) and [Stanford](https://socialdistancing.stanford.edu/). We hope to leverage these datasets as well as others we manually collect to perform these analyses. 

- *How can we reproduce the charts above?*

Our Jupyter notebooks and processing scripts are online on [GitHub](https://github.com/covidvis/covid19-vis). We also plan to make our intervention data available soon.

- *How can I contribute?* 

Please write to us at [covidvis@berkeley.edu](mailto:covidvis@berkeley.edu)

{% comment %}
Sources
-------
1. Data derived from John Hopkins CSSE [[link]](https://github.com/CSSEGISandData/COVID-19)
{% endcomment %}
