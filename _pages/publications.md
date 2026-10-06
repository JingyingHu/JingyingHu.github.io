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
    margin: 2.1rem 0 1.25rem;
    padding-top: 1rem;
    text-align: right;
  }

  ol.bibliography {
    list-style: none;
    padding-left: 0;
  }

  ol.bibliography > li {
    margin-bottom: 1.6rem;
  }

  .bibliography .title {
    font-size: 1rem;
    font-weight: 600;
    line-height: 1.35;
  }

  .bibliography .author,
  .bibliography .periodical {
    font-size: 0.92rem;
    line-height: 1.4;
  }

  .publication-meta-note,
  .equal-contribution-note {
    color: #8e6f3e;
    font-size: 0.78rem;
    line-height: 1.35;
  }

  .publication-meta-note {
    display: block;
    margin-top: 0.12rem;
  }

  .equal-contribution-note {
    margin-left: 0.35rem;
    white-space: nowrap;
  }

  .bibliography .abbr figure {
    margin-bottom: 0;
    text-align: center;
  }

  .bibliography img.preview {
    height: auto;
    max-height: 6.5rem;
    max-width: 100%;
    object-fit: contain;
    width: auto;
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
    margin-top: 0.45rem;
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

  .publication-note {
    margin: 0.25rem 0 2rem;
    color: var(--global-text-color-light);
  }
</style>

<p class="publication-note">
  See my
  <a href="https://scholar.google.com/citations?user=APa8s6gAAAAJ&hl=en&authuser=1">Google Scholar profile</a>
  for a complete and up-to-date publication list.
</p>

{% bibliography %}

<script>
  document.addEventListener("DOMContentLoaded", function () {
    var colmEntry = document.querySelector("#hu2026relative");
    if (colmEntry) {
      var colmPeriodical = colmEntry.querySelector(".periodical");
      if (colmPeriodical) {
        var acceptanceNote = document.createElement("span");
        acceptanceNote.className = "publication-meta-note";
        acceptanceNote.textContent = "Acceptance rate: 29% (854 out of 2,939 submissions)";
        colmPeriodical.insertAdjacentElement("afterend", acceptanceNote);
      }
    }

    var aimeEntry = document.querySelector("#osumi2026examining");
    if (aimeEntry) {
      var aimeAuthors = aimeEntry.querySelector(".author");
      if (aimeAuthors) {
        var equalContributionNote = document.createElement("span");
        equalContributionNote.className = "equal-contribution-note";
        equalContributionNote.textContent = "(* Equal contribution)";
        aimeAuthors.appendChild(equalContributionNote);
      }
    }

    document.querySelectorAll('.bibliography .links a[href*="openreview.net/"][href*="JnbJwiJxSQ"]').forEach(function (link) {
      link.textContent = "OpenReview";
    });

    document.querySelectorAll('.bibliography .links a[href*="huggingface.co/datasets/clap-purdue/MultiWhoAudio"]').forEach(function (link) {
      link.textContent = "Dataset";
    });

    document.querySelectorAll('.bibliography .links a[href*="aclanthology.org/2026.aimecon-main.24/"]:not([href$=".pdf"])').forEach(function (link) {
      link.textContent = "ACL Anthology";
    });

    document.querySelectorAll(".bibliography a.abstract").forEach(function (button) {
      button.textContent = "TL;DR";

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
