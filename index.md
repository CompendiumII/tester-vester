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
    <button onclick="selectOption('yes')" style="
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

    <button onclick="selectOption('no')" style="
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
  function selectOption(choice) {
    const image = document.getElementById('mainImage');
    const text = document.getElementById('question-text');
    const buttons = document.getElementById('buttonGroup');

    if (choice === 'yes') {
      image.src = "{{ '/assets/images/happy-cat.jfif' | relative_url }}";
      text.textContent = "YAY!!! 💖 I can’t wait to spend Saturday with you!";
    } else {
      image.src = "{{ '/assets/images/sad-cat.jfif' | relative_url }}";
      text.textContent = "Oh no 😿 I’ll still bring snacks though...";
    }

    // Hide buttons after selection
    buttons.style.display = 'none';
  }
</script>
