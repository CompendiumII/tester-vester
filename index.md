---
layout: default
title: Home
---

# Hello Aeriel :]

<p id="question-text">
  WILL YOU BE MY VALENTINES THIS SATURDAY?
</p>

<div style="text-align: center; margin-top: 2rem;">

  <img id="mainImage"
       src="{{ '/assets/images/cat.jfif' | relative_url }}"
       alt="Cat image"
       style="max-width: 300px; width: 100%; margin-bottom: 1.5rem;">

  <div id="buttonGroup">
    <button id="yesBtn" onclick="handleYes()" style="
      padding: 0.6rem 1.4rem;
      margin: 0.3rem 0.8rem;
      background: #0366d6;
      color: white;
      border: none;
      border-radius: 6px;
      font-weight: 600;
      cursor: pointer;
    ">
      YES!!!
    </button>

    <button onclick="handleNo()" style="
      padding: 0.6rem 1.4rem;
      margin: 0.3rem 0.8rem;
      background: #6f42c1;
      color: white;
      border: none;
      border-radius: 6px;
      font-weight: 600;
      cursor: pointer;
    ">
      No...
    </button>
  </div>

</div>

<script>
  let state = 'initial'; // initial | sure | accepted

  function handleYes() {
    const image = document.getElementById('mainImage');
    const text = document.getElementById('question-text');
    const buttons = document.getElementById('buttonGroup');

    // YES only works on the first screen
    if (state !== 'initial') return;

    image.src = "{{ '/assets/images/dancing_cat.gif' | relative_url }}";
    text.textContent = "HOOORAY!!! I LOVE YOU AND I'M EXCITED TO SEE YOU SATURDAY!!!";
    buttons.style.display = 'none';
    state = 'accepted';
  }

  function handleNo() {
    const image = document.getElementById('mainImage');
    const text = document.getElementById('question-text');
    const yesBtn = document.getElementById('yesBtn');

    if (state === 'initial') {
      // First NO → Are you sure?
      image.src = "{{ '/assets/images/sad_cat.jfif' | relative_url }}";
      text.textContent = "Are you sure? 🥺";
      yesBtn.style.opacity = '0.5';
      yesBtn.style.cursor = 'not-allowed';
      state = 'sure';
    } else if (state === 'sure') {
      // Second NO → reset to start
      image.src = "{{ '/assets/images/cat.jfif' | relative_url }}";
      text.textContent = "WILL YOU BE MY VALENTINES THIS SATURDAY?";
      yesBtn.style.opacity = '1';
      yesBtn.style.cursor = 'pointer';
      state = 'initial';
    }
  }
</script>
