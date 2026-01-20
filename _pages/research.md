---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

<style>
.research-details {
  border: 1px solid #d9d9d9;
  border-radius: 6px;
  padding: 0.5rem 0.85rem;
  margin: 0.1rem 0 0.5rem 0.6rem;
  background-color: transparent;
  font-size: 0.8rem;
}
.research-details summary {
  font-weight: 400;
  font-size: 0.8rem;
  cursor: pointer;
}
</style>


## Research overview
My research is at the intersection of applied probability and optimization. Specifically, I study delay in a variety of Stochastic Processing Networks (or queueing systems). I love developing novel analysis methodologies that allow better understanding of the delay or queue lengths distribution in queueing systems. In particular, I enjoy using Moment Generating Functions and most of my work is on heavy-traffic analysis.


## Publications

### Work in Progress

1. Markov Modulated JSQ in Heavy Traffic via the Poisson Equation
   <details class="research-details" markdown="1">
     <summary>Coauthored with <a href="https://isaacg1.github.io/">Izzy Grosof</a>. Click for more information.</summary>

     **Abstract:** 
     In parallel-server systems with a single stream of arrivals, Join-the-Shortest-Queue (JSQ) is one of the most popular routing algorithms due to its simplicity and strong performance properties: it is well known that routing with JSQ is throughput and heavy-traffic optimal, regardless of whether the servers are homogeneous or not. Further, JSQ is optimal and does not need any information about the servers' rates. In this work, we study a JSQ system with Markov-modulated arrival and service rates. Specifically, we provide sufficient conditions on the Markov-modulated arrival and service rates to ensure state space collapse, and compute the heavy-traffic distribution of queue lengths. We establish the distribution of queue lengths using a novel hybrid methodology that combines the Transform Method for queue-lengths analysis, and Poisson Equation of the Markov-modulating chain.

     **Slides:**
     I've given this talk multiple times during 2025, in different versions depending on the available time and the audience. The most complete talk was in SNAPP seminar on Dec 1st, 2025. [Here's the slides]({{ site.baseurl }}/files/Slides SNAPP 2025.pdf){:target="_blank"}.

     **Current status:**
     We are writing the paper at the moment. I will post a pdf once it's ready.
   </details>

### Under Review

1. Outperforming Multiserver SRPT at All Loads
   <details class="research-details" markdown="1">
     <summary>Coauthored with <a href="https://isaacg1.github.io/">Izzy Grosof</a>. Click for more information.</summary>

     **Abstract:**
     A well-designed scheduling policy can unlock significant performance improvements with no additional resources. Multiserver SRPT (SRPT-k) is known to achieve asymptotically optimal mean response time in the heavy traffic limit, as load approaches capacity. No better policy is known for the M/G/$k$ queue in any regime. We introduce a new policy, SRPT-Except-k+1 & Modified SRPT (SEK-SMOD), which is the first policy to provably achieve lower mean response time than SRPT-k. SEK-SMOD outperforms SRPT-k across all loads and all job size distributions.  The key idea behind SEK-SMOD is to prioritize large jobs over small jobs in specific scenarios to improve server utilization, and thereby improve the response time of subsequent jobs in expectation. Our proof is a novel application of hybrid worst-case and stochastic techniques to relative analysis, where we analyze the deviations of our proposed SEK-SMOD policy away from the SRPT-k baseline policy. Furthermore, we design Practical-SEK (a simplified variant of SEK-SMOD) and empirically verify the improvement over SRPT-k via simulation.

     **Current status:**
     Accepted for ACM Sigmetrics 2026; Journal version under review. The latest version is available [here]({{ site.baseurl }}/files/sek-improves.pdf){:target="_blank"}.
   </details>

2. Exponential Tail Bounds on Queues: A Confluence of Non-Asymptotic Heavy-Traffic and Large Deviations
   <details class="research-details" markdown="1">
     <summary>Coauthored with <a href="https://sites.google.com/view/prakirtjhunjhunwala">Prakirt Jhunjhunwala</a> and <a href="https://sites.google.com/site/sivatheja/">Siva Theja Maguluri</a>. Click for more information.</summary>

     **Abstract:**
     Details coming soon.

     **Slides:**
     Slides are not yet available.

     **Current status:**
     Accepted for IFIP Performance 2023; Journal version under review. The conference version is available [here](https://dl.acm.org/doi/abs/10.1145/3649477.3649488){% include base_path %}, and the latest journal version available [here](https://arxiv.org/pdf/2306.10187){% include base_path %}.
   </details>

### Published work

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}" target="_blank" rel="noopener noreferrer">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

<!-- New style rendering if publication categories are defined -->
{% if site.publication_category %}
  {% for category in site.publication_category  %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}
      {% unless title_shown %}
        <h2>{{ category[1].title }}</h2><hr />
        {% assign title_shown = true %}
      {% endunless %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  {% for post in site.publications reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}
