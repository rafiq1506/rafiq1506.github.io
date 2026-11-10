---
layout: default
title: Publications - Dr. Mohd Rafiq
permalink: /publications/
---

<style>
  .filter-controls {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin-bottom: 2rem;
    align-items: center;
    justify-content: space-between;
  }
  .search-box {
    flex: 1;
    min-width: 250px;
  }
  .search-box input {
    width: 100%;
    padding: 0.7rem 1rem;
    border: 1px solid #ddd;
    border-radius: 6px;
    font-size: 1rem;
    font-family: inherit;
    transition: var(--transition);
  }
  .search-box input:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(239, 35, 60, 0.2);
  }
  .filter-buttons {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
  }
  .filter-btn {
    background-color: white;
    color: var(--primary);
    border: 1px solid var(--secondary);
    padding: 0.5rem 1.2rem;
    border-radius: 20px;
    cursor: pointer;
    font-weight: 600;
    transition: var(--transition);
  }
  .filter-btn:hover, .filter-btn.active {
    background-color: var(--accent);
    color: white;
    border-color: var(--accent);
  }
  .hidden {
    display: none !important;
  }
  .no-results {
    text-align: center;
    color: var(--secondary);
    padding: 2rem;
    font-style: italic;
  }
</style>

<section id="publications-page" class="section animate">
  <h2 class="section-title"><i class="fas fa-book"></i> RESEARCH PUBLICATIONS</h2>

  <!-- Filter & Search Controls -->
  <div class="filter-controls">
    <div class="search-box">
      <input type="text" id="pubSearch" placeholder="Search by title, author, journal, or keyword..." onkeyup="filterPublications()">
    </div>
    <div class="filter-buttons">
      <button class="filter-btn active" onclick="setFilter('all', this)">All</button>
      <button class="filter-btn" onclick="setFilter('wavelets', this)">Wavelets</button>
      <button class="filter-btn" onclick="setFilter('schrodinger', this)">Schrödinger</button>
      <button class="filter-btn" onclick="setFilter('chen-lee-liu', this)">Chen-Lee-Liu</button>
    </div>
  </div>

  <!-- Publications Container -->
  <div id="pubList">

    <div class="publication-item" data-category="wavelets schrodinger">
      <p class="publication-citation">
        <strong>M. Rafiq, A. Abdullah,</strong> Numerical investigation using Fibonacci wavelet collocation method for solving modified unstable nonlinear Schrödinger equation, <i>Int. J. Appl. Comput. Math.</i> <strong>9</strong> (2023) 118.[cite: 4]
        <br>
        <a href="https://doi.org/10.1007/s40819-023-01598-0" target="_blank" class="publication-link">
          <i class="fas fa-external-link-alt"></i> https://doi.org/10.1007/s40819-023-01598-0[cite: 4]
        </a>
      </p>
    </div>

    <div class="publication-item" data-category="wavelets schrodinger">
      <p class="publication-citation">
        <strong>A. Abdullah, M. Rafiq,</strong> A computational approach for finding the numerical solution of modified unstable nonlinear Schrödinger equation via Haar wavelets, <i>Math. Methods Appl. Sci.</i> <strong>45</strong> (2022) 681–696.[cite: 4]
        <br>
        <a href="https://doi.org/10.1002/mma.7805" target="_blank" class="publication-link">
          <i class="fas fa-external-link-alt"></i> https://doi.org/10.1002/mma.7805[cite: 4]
        </a>
      </p>
    </div>

    <div class="publication-item" data-category="wavelets chen-lee-liu">
      <p class="publication-citation">
        <strong>A. Abdullah, M. Rafiq,</strong> A new numerical scheme based on Haar wavelets for the numerical solution of the Chen-Lee-Liu equation, <i>Optik.</i> <strong>226</strong> (2020) 165847.[cite: 4]
        <br>
        <a href="https://doi.org/10.1016/j.ijleo.2020.165847" target="_blank" class="publication-link">
          <i class="fas fa-external-link-alt"></i> https://doi.org/10.1016/j.ijleo.2020.165847[cite: 4]
        </a>
      </p>
    </div>

    <p id="noResultsMessage" class="no-results hidden">No matching publications found.</p>
  </div>
</section>

<script>
  let activeFilter = 'all';

  function setFilter(category, btnElement) {
    activeFilter = category;
    document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
    btnElement.classList.add('active');
    filterPublications();
  }

  function filterPublications() {
    const searchInput = document.getElementById('pubSearch').value.toLowerCase();
    const items = document.querySelectorAll('.publication-item');
    let visibleCount = 0;

    items.forEach(item => {
      const text = item.innerText.toLowerCase();
      const categories = item.getAttribute('data-category') || '';
      
      const matchesSearch = text.includes(searchInput);
      const matchesCategory = (activeFilter === 'all') || categories.includes(activeFilter);

      if (matchesSearch && matchesCategory) {
        item.classList.remove('hidden');
        visibleCount++;
      } else {
        item.classList.add('hidden');
      }
    });

    const noResults = document.getElementById('noResultsMessage');
    if (visibleCount === 0) {
      noResults.classList.remove('hidden');
    } else {
      noResults.classList.add('hidden');
    }
  }
</script>
