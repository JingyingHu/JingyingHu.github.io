---
layout: page
permalink: /publications/
title: publications
nav: true
nav_order: 2
---

<style>
  .bibliography .author em,
  .bibliography .authors em {
    font-style: normal;
    font-weight: inherit;
    text-decoration: underline;
    text-underline-offset: 0.16em;
  }

  h2.bibliography {
    border-top: 1px solid var(--global-divider-color);
    color: #d8d8d8;
    font-size: 2.8rem;
    font-weight: 300;
    line-height: 1;
    margin: 2.6rem 0 1.6rem;
    padding-top: 1.25rem;
    text-align: right;
  }

  ol.bibliography {
    list-style: none;
    padding-left: 0;
  }

  ol.bibliography > li {
    margin-bottom: 2.4rem;
  }

  .bibliography .title {
    font-weight: 600;
  }

  .bibliography .abstract:not(.btn),
  .bibliography .bibtex:not(.btn) {
    border: 1px dashed var(--global-text-color);
    font-size: 0.9rem;
    line-height: 1.55;
    margin-top: 0.7rem;
    padding: 1rem 1.15rem;
  }

  .bibliography .links a.bibtex,
  .bibliography .links a[href*="sciencedirect.com"],
  .bibliography .links a[href*="aclanthology.org/2025.cmcl-1.22/"]:not([href$=".pdf"]),
  .bibliography .links a[href*="frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2023.1133003/full"] {
    display: none;
  }
</style>

{% include bib_search.liquid %}

{% bibliography %}

<script>
  document.addEventListener("DOMContentLoaded", function () {
    document.querySelectorAll(".bibliography a.abstract").forEach(function (button) {
      button.addEventListener("click", function (event) {
        event.preventDefault();
        var target = button.parentElement.nextElementSibling;

        while (target && !target.classList.contains(button.classList[0])) {
          target = target.nextElementSibling;
        }

        if (target) {
          target.classList.toggle("hidden");
        }
      });
    });
  });
</script>
