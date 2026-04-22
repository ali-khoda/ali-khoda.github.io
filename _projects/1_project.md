---
layout: page
title: Secure LLM
description: Chat with AI safely without exposing sensitive data.
permalink: /projects/securellm/
img: assets/img/securellm/redaction-shield.svg
importance: 1
category: work
related_publications: false
images:
  compare: true
---

This system protects privacy in LLM workflows by redacting sensitive entities before any prompt is sent to the model. Detected PIIs are masked with placeholders (for example, `[person_1]`, `[email_1]`, and `[account_1]`), the sanitized prompt is then processed by the LLM, and the original values are restored in the final response.

Because the model only sees placeholders, users get nearly the same experience while private information never leaves the protected layer. The redaction pipeline covers 40+ entity types, including names, addresses, bank details, SSNs, emails, money amounts, URLs, API keys, and more.

<style>
  .securellm-compare-frame {
    margin-top: 1rem;
    margin-bottom: 0.75rem;
    padding: 0.75rem;
    border: 1px solid rgba(0, 0, 0, 0.12);
    border-radius: 12px;
    background: #f6f8fb;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
  }

  .securellm-compare-frame img-comparison-slider {
    --divider-width: 2px;
    --divider-color: #4f5b66;
    --default-handle-color: #1f2937;
    --default-handle-opacity: 1;
    display: block;
    border: 1px solid rgba(0, 0, 0, 0.14);
    border-radius: 10px;
    overflow: hidden;
    background: #ffffff;
  }

  .securellm-compare-frame img-comparison-slider img {
    display: block;
    background: #ffffff;
  }

  .securellm-compare-labels {
    position: relative;
    width: 100%;
    height: 1.5rem;
    margin-top: 0.35rem;
    font-size: 0.9rem;
    color: #4b5563;
  }

  .securellm-compare-labels span {
    position: absolute;
    transform: translateX(-50%);
    white-space: nowrap;
  }

  .securellm-compare-labels .left-label {
    left: 25%;
  }

  .securellm-compare-labels .right-label {
    left: 75%;
  }

  .securellm-compare-note {
    margin-top: 0.4rem;
    text-align: center;
    font-size: 0.9rem;
    color: #4b5563;
  }

  img-comparison-slider,
  img-comparison-slider * {
    -webkit-user-select: none;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
  }

  img-comparison-slider:focus,
  img-comparison-slider:focus-visible,
  img-comparison-slider *:focus,
  img-comparison-slider *:focus-visible {
    outline: none !important;
    box-shadow: none !important;
  }
</style>

<div class="securellm-compare-frame">
  <img-comparison-slider class="w-100">
    {% include figure.liquid loading="eager" path="assets/img/securellm/after.jpeg" title="after image" class="img-fluid" slot="first" %}
    {% include figure.liquid loading="eager" path="assets/img/securellm/before.jpeg" title="before image" class="img-fluid" slot="second" %}
  </img-comparison-slider>
</div>
<script>
  document.querySelectorAll("img-comparison-slider img").forEach((img) => img.setAttribute("draggable", "false"));
</script>

<div class="securellm-compare-labels">
  <span class="left-label">What AI Sees</span>
  <span class="right-label">What Users See</span>
</div>
<div class="securellm-compare-note">
  Move the slider to compare the user perspective with what the AI sees.
</div>
