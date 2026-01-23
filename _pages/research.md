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
     <summary>Coauthored with <a href="https://isaacg1.github.io/" target="_blank" rel="noopener">Izzy Grosof</a>. Click for more information.</summary>

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
     <summary>Coauthored with <a href="https://isaacg1.github.io/" target="_blank" rel="noopener">Izzy Grosof</a>. Click for more information.</summary>

     **Abstract:**
     A well-designed scheduling policy can unlock significant performance improvements with no additional resources. Multiserver SRPT (SRPT-k) is known to achieve asymptotically optimal mean response time in the heavy traffic limit, as load approaches capacity. No better policy is known for the M/G/$k$ queue in any regime. We introduce a new policy, SRPT-Except-k+1 & Modified SRPT (SEK-SMOD), which is the first policy to provably achieve lower mean response time than SRPT-k. SEK-SMOD outperforms SRPT-k across all loads and all job size distributions.  The key idea behind SEK-SMOD is to prioritize large jobs over small jobs in specific scenarios to improve server utilization, and thereby improve the response time of subsequent jobs in expectation. Our proof is a novel application of hybrid worst-case and stochastic techniques to relative analysis, where we analyze the deviations of our proposed SEK-SMOD policy away from the SRPT-k baseline policy. Furthermore, we design Practical-SEK (a simplified variant of SEK-SMOD) and empirically verify the improvement over SRPT-k via simulation.

     **Current status:**
     Accepted for ACM Sigmetrics 2026; Journal version under review. The latest version is available [here]({{ site.baseurl }}/files/sek-improves.pdf){:target="_blank"}.
   </details>

2. Exponential Tail Bounds on Queues: A Confluence of Non-Asymptotic Heavy-Traffic and Large Deviations
   <details class="research-details" markdown="1">
     <summary>Coauthored with <a href="https://sites.google.com/view/prakirtjhunjhunwala" target="_blank" rel="noopener">Prakirt Jhunjhunwala</a> and <a href="https://sites.google.com/site/sivatheja/" target="_blank" rel="noopener">Siva Theja Maguluri</a>. Click for more information.</summary>

     **Abstract:**
     In general, obtaining the exact steady-state distribution of queue lengths is not feasible. Therefore, our focus is on establish bounds for the tail probabilities of queue lengths. Specifically, we examine queueing systems under Heavy-Traffic (HT) conditions and provide exponentially decaying bounds for the probability $P(\epsilon q>x)$, where $\epsilon$ is the HT parameter denoting how far the load is from the maximum allowed load. Our bounds are not limited to asymptotic cases and are applicable even for finite values of $\epsilon$, and they get sharper as $\epsilon\to 0$. Consequently, we derive non-asymptotic convergence rates for the tail probabilities. Unlike other approaches such as moment bounds based on drift arguments and bounds on Wasserstein distance using Stein’s method, our method yields sharper tail bounds. Furthermore, our results offer bounds on the exponential rate of decay of the tail, given by $−\tfrac{1}{x} \log P(\epsilon q > x)$ for any finite value of $x$. These can be interpreted as non-asymptotic versions of Large Deviation (LD) results. To obtain our results, we use an exponential Lyapunov function to bound the moment generating function of queue lengths and apply Markov’s inequality. 
     
     We demonstrate our approach by presenting tail bounds for: (i) a continuous time Join-the-shortest queue (JSQ) load balancing system, (ii) a discrete time single-server queue and (iii) an $M/M/n$ queue. We not only bridge the gap between classical-HT and LD regimes but also explore the large system HT regimes for JSQ and $M/M/n$ systems. In these regimes, both the system size and the system load increase simultaneously. Our results also close a gap in the existing literature on the limiting distribution of JSQ in the super-NDS (a.k.a. super slowdown) regime. This contribution is of an independent interest. Here, a key ingredient is a more refined characterization of state space collapse for JSQ system, achieved by using an exponential Lyapunov function designed to approximate the ℓ∞ norm.

     **Current status:**
     - Accepted for IFIP Performance 2023. This version is available <a href="https://dl.acm.org/doi/abs/10.1145/3649477.3649488" target="_blank" rel="noopener"> here </a>
     - Journal version under review. The latest journal version available <a href="https://arxiv.org/pdf/2306.10187" target="_blank" rel="noopener"> here </a>
   </details>

### Published work

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}" target="_blank" rel="noopener noreferrer">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

{% assign ordered_publications = site.publications | sort: "date" | reverse %}
<ol class="publication-list" reversed>
  {% for post in ordered_publications %}
    {% assign publication_year = post.date | default: "1900-01-01" | date: "%Y" %}
    {% assign final_link = post.paperurl | default: post.link %}
    {% if final_link %}
      {% assign link_target = final_link %}
    {% else %}
      {% assign link_target = base_path | append: post.url %}
    {% endif %}
    {% assign is_external = link_target contains '://' %}
    <li>
      <a href="{{ link_target }}"{% if is_external %} target="_blank" rel="noopener noreferrer"{% endif %}>{{ post.title }}</a>
      {% if post.venue %}
        — <i>{{ post.venue }}</i>
      {% endif %}
      {% if publication_year %}
        , {{ publication_year }}
      {% endif %}
    </li>
  {% endfor %}
</ol>
