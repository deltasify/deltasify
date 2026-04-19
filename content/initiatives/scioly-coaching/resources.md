---
title: "SOCP - Resources"
date: 2026-01-25T00:00:00+08:00
draft: false
language: en
description: SOCP - Resources
# featured_image: ../assets/images/featured/
featured_image:
---

<style>
  /* Base Bento and Accordion styles */
  .bento-grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-auto-rows: minmax(min-content, auto);
    gap: 1.5rem;
    font-family: inherit;
    color: var(--color-zinc-800);
    margin-top: 2rem;
    margin-bottom: 2rem;
  }

  .dark .bento-grid {
    color: var(--color-zinc-200);
  }

  .bento-card {
    background-color: var(--color-white);
    border: 1px solid var(--color-zinc-200);
    border-radius: 1.5rem;
    padding: 1.75rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    display: flex;
    flex-direction: column;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease-out, transform 0.6s ease-out, box-shadow 0.2s ease, border-color 0.2s ease;
  }

  .bento-card.is-visible {
    opacity: 1;
    transform: translateY(0);
  }

  .dark .bento-card {
    background-color: var(--color-zinc-900);
    border-color: var(--color-zinc-800);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.2);
  }

  .bento-card h3 {
    margin-top: 0;
    margin-bottom: 1rem;
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--color-indigo-600);
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .dark .bento-card h3 {
    color: var(--color-indigo-400);
  }

  /* Grid alignment */
  .card-full { grid-column: span 12; }
  .card-half { grid-column: span 12; }
  .card-stat { grid-column: span 6; padding: 1.5rem; justify-content: center; }
  
  @media (min-width: 768px) {
    .card-half { grid-column: span 6; }
    .card-stat { grid-column: span 3; }
  }

  .stat-value {
    font-size: 1.75rem;
    font-weight: 800;
    line-height: 1.1;
    color: var(--color-zinc-900);
    margin-bottom: 0.5rem;
  }

  @media (min-width: 1024px) {
    .stat-value { font-size: 2.25rem; }
  }

  .dark .stat-value {
    color: var(--color-white);
  }

  .stat-label {
    font-size: 0.875rem;
    font-weight: 600;
    color: var(--color-zinc-500);
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
  
  .dark .stat-label {
    color: var(--color-zinc-400);
  }

  .text-content {
    line-height: 1.6;
    color: var(--color-zinc-700);
  }

  .dark .text-content {
    color: var(--color-zinc-300);
  }

  /* Accordion Styles */
  .accordion-container {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .accordion-item {
    border: 1px solid var(--color-zinc-200);
    border-radius: 0.75rem;
    overflow: hidden;
    background-color: var(--color-zinc-50);
    transition: all 0.2s ease;
  }

  .dark .accordion-item {
    border-color: var(--color-zinc-700);
    background-color: var(--color-zinc-800);
  }

  .accordion-header {
    width: 100%;
    padding: 1rem 1.25rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: none;
    border: none;
    cursor: pointer;
    font-weight: 600;
    font-size: 1rem;
    color: var(--color-zinc-900);
    text-align: left;
    transition: color 0.2s ease;
  }

  .dark .accordion-header {
    color: var(--color-white);
  }

  .accordion-header:hover {
    color: var(--color-indigo-600);
  }
  
  .dark .accordion-header:hover {
    color: var(--color-indigo-400);
  }

  .accordion-icon {
    transition: transform 0.3s ease;
    width: 1.25rem;
    height: 1.25rem;
    flex-shrink: 0;
  }

  .accordion-item.active .accordion-icon {
    transform: rotate(180deg);
  }

  .accordion-content {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease-out, padding 0.3s ease;
    padding: 0 1.25rem;
    color: var(--color-zinc-600);
    font-size: 0.95rem;
    line-height: 1.6;
  }

  .dark .accordion-content {
    color: var(--color-zinc-300);
  }

  .accordion-item.active .accordion-content {
    padding-bottom: 1.25rem;
  }

  /* Links */
  .bento-card a.link-text {
    color: var(--color-indigo-600);
    text-decoration: underline;
    font-weight: 500;
  }

  .dark .bento-card a.link-text {
    color: var(--color-indigo-400);
  }

  .bento-card a.link-text:hover {
    color: var(--color-indigo-500);
  }

  /* Shared Inner Card Styling (Links & Winners) */
  .inner-card-container {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    height: 100%;
    justify-content: center;
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .inner-card-container.horizontal {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 0.75rem;
    align-items: stretch;
  }

  @media (min-width: 640px) {
    .inner-card-container.horizontal {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media (min-width: 1024px) {
    .inner-card-container.horizontal {
      grid-template-columns: repeat(4, 1fr);
    }
  }

  .inner-card {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 0.75rem 1rem;
    background-color: var(--color-zinc-50);
    color: var(--color-zinc-700);
    text-decoration: none;
    border-radius: 0.75rem;
    font-weight: 600;
    border: 1px solid var(--color-zinc-200);
    transition: all 0.2s ease;
    height: 100%;
    box-sizing: border-box;
  }

  a.inner-card:hover {
    background-color: var(--color-indigo-50);
    color: var(--color-indigo-700);
    border-color: var(--color-indigo-200);
    transform: translateX(4px);
  }

  .inner-card-container.horizontal a.inner-card:hover {
    transform: translateY(-4px);
  }

  .dark .inner-card {
    background-color: var(--color-zinc-800);
    color: var(--color-zinc-300);
    border-color: var(--color-zinc-700);
  }

  .dark a.inner-card:hover {
    background-color: var(--color-indigo-950);
    color: var(--color-indigo-300);
    border-color: var(--color-indigo-800);
  }

  /* Specifics for Links */
  .inner-card .arrow {
    transition: transform 0.2s ease;
    opacity: 0.5;
  }
  
  a.inner-card:hover .arrow {
    transform: translateX(4px);
    opacity: 1;
  }

  .inner-card-container.horizontal a.inner-card:hover .arrow {
    transform: translateX(4px);
  }
  
  .badge {
    display: inline-flex;
    align-items: center;
    padding: 0.5rem 1rem;
    border-radius: 9999px;
    font-size: 0.875rem;
    font-weight: 600;
    background-color: var(--color-indigo-50);
    color: var(--color-indigo-700);
    border: 1px solid var(--color-indigo-200);
    transition: all 0.2s ease;
    text-decoration: none;
  }
  
  .badge:hover {
    background-color: var(--color-indigo-100);
    border-color: var(--color-indigo-300);
    transform: translateY(-2px);
  }

  .dark .badge {
    background-color: var(--color-indigo-950);
    color: var(--color-indigo-300);
    border-color: var(--color-indigo-800);
  }

  .dark .badge:hover {
    background-color: var(--color-zinc-800);
    border-color: var(--color-indigo-700);
  }
</style>

<div class="bento-grid">

  <!-- Main Intro -->
  <div class="bento-card card-full">
    <h3>Resources for Coaches</h3>
    <div class="text-content" style="font-size: 1.1rem;">
      <p>Practice! Bond! Prepare! It is recommend that coaches give short lectures that build students' foundational skills / knowledge, then allow them to do practice tests.</p>
    </div>
  </div>

  <!-- FAQ Accordion -->
  <div class="bento-card card-full">
    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 1rem;">
      <h3 style="margin-bottom: 0;">Frequently Asked Questions</h3>
      <div style="display: flex; gap: 0.75rem;">
        <button id="expand-all-btn" class="badge" style="cursor: pointer; appearance: none; outline: none; font-family: inherit;">Expand All</button>
        <button id="collapse-all-btn" class="badge" style="cursor: pointer; appearance: none; outline: none; font-family: inherit;">Collapse All</button>
      </div>
    </div>
    
<div class="accordion-container">
    <div class="accordion-item">
    <button class="accordion-header">
        Is there an official coach training?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>We don't have an official training to be a coach. But there are resources on the "coaching resource" tab of our website.</p>
        <p style="margin-top: 0.5rem;">Additionally, some events ARE continued (likely with some modifications). So you may be able to utilize material from previous year's coach material.</p>
        <p style="margin-top: 0.5rem;">Lastly, if you really struggle to make lessons, feel free to <a href="mailto:nvu042@ucr.edu" target="_blank" class="link-text">nvu042@ucr.edu</a> me or we can schedule a virtual / in person at ucr meeting to talk about it.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        What is the Event Folder?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Each event will have a folder and team document; this will be shared with you on Google Drive after you are confirmed for an event.</p>
        <p style="margin-top: 0.5rem;">The folder is a place for you and team members to store resources, create notes documents and anything else that suits your team’s needs. The team document has the standing Google Meet link (for virtual meetings), a place to put questions and resources needed, and a practice log.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        What if I have not gain access to event folder by the time I start coaching?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Let Michael <a href="mailto:mtin@riversideunified.org" target="_blank" class="link-text">mtin@riversideunified.org</a> and Nam <a href="mailto:nvu042@ucr.edu" target="_blank" class="link-text">nvu042@ucr.edu</a> know immediately</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        Why do practice tests?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>The open-ended nature of the science Olympiad means that trying to give in depth lecture that cover all possible content is very difficult.</p>
        <p style="margin-top: 0.5rem;">Doing practice tests will give students practice with the vast variety of possible testing questions and help highlight where they struggle, which allow you to correct any misunderstanding they have.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        Where can I find practice test and lecture resources?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p><a href="https://www.soinc.org/events/2026-division-b-events" target="_blank" class="link-text">https://www.soinc.org/events/2026-division-b-events</a> : Each event has "Practice problem and test section". And "Resources & Links" (lecture material)</p>
        <p style="margin-top: 0.5rem;"><a href="https://scioly.org/wiki" target="_blank" class="link-text">https://scioly.org/wiki</a> : Clicking on events give you "wikipedia" of event (may not be detailed). Clck on "Test Exchange" or "Test Archive" under scioly.org resources for practice tests</p>
        <p style="margin-top: 0.5rem;">You may consider using ChatGPT or other AI tools to explain material and helping to come with practice questions.</p>
        <p style="margin-top: 0.5rem;">You will given an event folder containing previous coaches' material <em>*Not all events has previous material*</em></p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        How do I get comfortable with coaching? How do I get kids to become comfortable with me coaching them?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>You should get to know each other through ice breaker games and conversational starter (Example attached).</p>
        <p style="margin-top: 0.5rem;">Some kids are more outgoing than others, and students on your team may not even feel the most comfortable with each other at first. If things are a bit awkward at first, give it some time!</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        What are some first meeting ideas?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Introductions: Share a little about yourself and ask the kids to share some things about themselves</p>
        <p style="margin-top: 0.5rem;">Rules: Read over the rules and discuss any previous experience (or lack of experience) you and the students have in the area. Make clear some basic behavior expectations.</p>
        <p style="margin-top: 0.5rem;">Lecture: Get started right away by diving into some basic concepts</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        Should coaches plan out time to make a study guide near competition time?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>It is recommend for coaches to guide students (instead of directly doing it for them) toward making a study guide to help students review the material. Additionally, some events allow for cheat sheets (double check the event parameter in the rule book).</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        How do I plan out a coaching schedule?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p><strong>Update later</strong></p>
        <p style="margin-top: 0.5rem;"><a href="https://docs.google.com/document/d/1u0e51L5E215jtPuNNbn_vgKAHUnftfyRt_EHnyj_TNY/edit?tab=t.0" target="_blank" class="link-text">https://docs.google.com/document/d/1u0e51L5E215jtPuNNbn_vgKAHUnftfyRt_EHnyj_TNY/edit?tab=t.0</a></p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        What are some general ideas for lessons?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>-Quiz to review last week’s concepts: print out practice tests, kids quiz each other on notes they have taken, asking questions as conduct lab, etc..</p>
        <p style="margin-top: 0.5rem;">-Have students do and then share research</p>
        <p style="margin-top: 0.5rem;">-Lecture on a topic</p>
        <p style="margin-top: 0.5rem;">-Go over homework for the week.</p>
        <p style="margin-top: 0.5rem;">-Doing worksheet as team, pair of two or individually.</p>
        <p style="margin-top: 0.5rem;">-Create study materials: information summaries, flashcards, mind maps.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        What are some extra coaching ideas?
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p><a href="https://docs.google.com/document/d/1H3Mh1Dg7yvEvJKl-k2qzCdUnQhxvuWPu8pBrwl_IoHs/edit?tab=t.0" target="_blank" class="link-text">https://docs.google.com/document/d/1H3Mh1Dg7yvEvJKl-k2qzCdUnQhxvuWPu8pBrwl_IoHs/edit?tab=t.0</a></p>
        <p style="margin-top: 0.5rem;">Extra coaching ideas if you are interested. I will continue to add more ideas when I find them.</p>
    </div>
    </div>
</div>
</div>

</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    // Bento card animations
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible');
          setTimeout(() => {
            entry.target.style.transitionDelay = '0s';
            entry.target.style.transition = 'all 0.2s ease';
          }, 600);
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });

    document.querySelectorAll('.bento-card').forEach((card, index) => {
      card.style.transitionDelay = `${(index % 4) * 0.1}s`;
      observer.observe(card);
    });

    // Accordion logic
    const accordions = document.querySelectorAll('.accordion-header');

    function toggleAccordion(item, content, forceState) {
      if (forceState === 'expand') {
        item.classList.add('active');
        content.style.maxHeight = content.scrollHeight + 40 + "px";
      } else if (forceState === 'collapse') {
        item.classList.remove('active');
        content.style.maxHeight = null;
      } else {
        item.classList.toggle('active');
        if (item.classList.contains('active')) {
          content.style.maxHeight = content.scrollHeight + 40 + "px";
        } else {
          content.style.maxHeight = null;
        }
      }
    }

    accordions.forEach(acc => {
      acc.addEventListener('click', function() {
        const item = this.parentElement;
        const content = this.nextElementSibling;
        toggleAccordion(item, content);
      });
    });

    const expandAllBtn = document.getElementById('expand-all-btn');
    const collapseAllBtn = document.getElementById('collapse-all-btn');

    if (expandAllBtn && collapseAllBtn) {
      expandAllBtn.addEventListener('click', () => {
        accordions.forEach(acc => {
          const item = acc.parentElement;
          const content = acc.nextElementSibling;
          toggleAccordion(item, content, 'expand');
        });
      });

      collapseAllBtn.addEventListener('click', () => {
        accordions.forEach(acc => {
          const item = acc.parentElement;
          const content = acc.nextElementSibling;
          toggleAccordion(item, content, 'collapse');
        });
      });
    }
  });
</script>