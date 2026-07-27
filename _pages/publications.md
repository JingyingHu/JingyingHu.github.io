---
layout: page
permalink: /publications/
title: Publications
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

  .bibliography .abbr abbr.badge {
    background-color: color-mix(in srgb, var(--global-theme-color) 72%, white);
    border-radius: 4px;
    box-shadow: 0 0.18rem 0.45rem rgba(0, 0, 0, 0.1);
    color: #fff;
    display: block;
    font-size: 0.78rem;
    font-weight: 600;
    letter-spacing: 0;
    line-height: 1.2;
    margin: 0 auto 0.55rem;
    max-width: 7.5rem;
    padding: 0.24rem 0.42rem;
    text-align: center;
    white-space: normal;
  }

  .bibliography .links {
    margin-top: 0.65rem;
  }

  .bibliography .links a.btn {
    background: transparent;
    border: 1px solid var(--global-text-color);
    border-radius: 3px;
    color: var(--global-text-color);
    font-size: 0.68rem;
    font-weight: 500;
    line-height: 1.2;
    margin: 0 0.38rem 0.35rem 0;
    min-width: 2.8rem;
    padding: 0.28rem 0.48rem;
    text-align: center;
    text-transform: uppercase;
  }

  .bibliography .links a.btn:hover,
  .bibliography .links a.btn:focus {
    background: var(--global-theme-color);
    border-color: var(--global-theme-color);
    color: #fff;
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
