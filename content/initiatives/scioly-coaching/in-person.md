---
title: "SOCP - In-Person Coaching"
date: 2026-01-25T00:00:00+08:00
draft: false
language: en
description: SOCP - In-Person Coaching
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
    <h3>In-Person Coaching</h3>
    <div class="text-content" style="font-size: 1.1rem;">
      <p>You are required to pass this clearance to do coaching in person. Please read through this guide before beginning clearance so you don’t confuse yourself.</p>
      <p style="margin-top: 1rem;">If you can and willing to coach in person please get start on this as soon as possible. If you need help, please email Michael (<a href="mailto:mtin@riversideunified.org" target="_blank" class="link-text">mtin@riversideunified.org</a>).</p>
    </div>
  </div>

  <!-- FAQ Accordion -->
  <div class="bento-card card-full">
    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 1rem;">
      <h3 style="margin-bottom: 0;">In-Person Volunteer Clearance Process</h3>
      <div style="display: flex; gap: 0.75rem;">
        <button id="expand-all-btn" class="badge" style="cursor: pointer; appearance: none; outline: none; font-family: inherit;">Expand All</button>
        <button id="collapse-all-btn" class="badge" style="cursor: pointer; appearance: none; outline: none; font-family: inherit;">Collapse All</button>
      </div>
    </div>
    
<div class="accordion-container">
    <div class="accordion-item">
    <button class="accordion-header">
        1. Official website
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Visit <a href="https://www.riversideunified.org/parents/volunteer_opportunities" target="_blank" class="link-text">https://www.riversideunified.org/parents/volunteer_opportunities</a> and click on "Adult Volunteer Participation Form".</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        2. Filling out the form
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Indicate "Riverside STEM Academy" under "School site at which you wish to volunteer" and "Student Volunteer for Science Olympiad" for the reason you are requesting to volunteer.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        3. Required volunteer training
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Complete the Required Volunteer Training. This will take 5-10 minutes.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        4a. TB Risk Assessment
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Call the phone number provided on the form (as of 7/22/25 it should be (951)274-4213).</p>
        <p style="margin-top: 0.5rem;">State you are calling for TB risk assessment. And you are volunteering to coach science Olympiad at Riverside Stem Academy (RSA).</p>
        <p style="margin-top: 0.5rem;">You will likely not need to do TB test unless you traveled out of country over summer.</p>
        <p style="margin-top: 0.5rem;">If need TB test, consider telling them about any recent TB test (ex. the one you take to get into UCR).</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        4b. If you do require a TB test AFTER talking the TB Risk Assessment
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>USHIP- Student Health Center</p>
        <p style="margin-top: 0.5rem;">Or any other clinic that accepts your insurance</p>
        <p style="margin-top: 0.5rem;">CVS near UCR @ 491 East Alessandro Boulevard, Riverside, CA 92508</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        5. Fingerprint procedure
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Gmail <a href="mailto:nvu042@ucr.edu" target="_blank" class="link-text">nvu042@ucr.edu</a> to request a voucher and schedule to meet up in person and get your voucher. You can redeem the voucher at 5198 Arlington Ave Riverside, CA 92504 to clear your fingerprinting requirement.</p>
        <p style="margin-top: 0.5rem;">You should bring the live scan form sent to you by rusd volunteeer gmail (it is sent to you once you start the volunteer application processs) to this appointment.</p>
        <p style="margin-top: 0.5rem;"><em>*I will be at UCR starting at week zero 9/15/25*</em></p>
        <p style="margin-top: 0.5rem;"><em>*You can request locations convenient for you that is at UCR.*</em></p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        6. After receiving clearance email
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Please check with Michael (<a href="mailto:mtin@riversideunified.org" target="_blank" class="link-text">mtin@riversideunified.org</a>) that you have officially been cleared.</p>
    </div>
    </div>
    <div class="accordion-item">
    <button class="accordion-header">
        7. Optional feedback
        <svg class="accordion-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
    </button>
    <div class="accordion-content">
        <p>Give us feedback on your experience by emailing <a href="mailto:nvu042@ucr.edu" target="_blank" class="link-text">nvu042@ucr.edu</a></p>
        <p style="margin-top: 0.5rem;">Did you find the guide helpful? What make it helpful?</p>
        <p style="margin-top: 0.5rem;">Did you find any problems with the clearance process?</p>
        <p style="margin-top: 0.5rem;">Is anything on the guide not clear?</p>
        <p style="margin-top: 0.5rem;">Any other comments?</p>
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