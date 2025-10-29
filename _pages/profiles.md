---
layout: page
permalink: /happy-paws/
title: Happy Paws
description: Meet my three westies! 🐾
nav: true
nav_order: 5
---

<div class="intro-text">
  <p>Meet Doggie, Duffy, and Dolly!</p>
</div>

<div class="dog-gallery">
  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/doggie.jpg' | relative_url }}" alt="Doggie">
    </div>
    <div class="dog-info">
      <h3>Doggie</h3>
      <p class="dog-breed">West Highland White Terrier, Boy, Birthday: 2021/08/19</p>
      <p class="dog-description">
        Love to watch Bluey! 🐶
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/duffy.jpg' | relative_url }}" alt="Duffy">
    </div>
    <div class="dog-info">
      <h3>Duffy</h3>
      <p class="dog-breed">West Highland White Terrier, Girl, Birthday: 2022/04/16</p>
      <p class="dog-description">
        Love to chase squirrels! 🐿️
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/dolly.jpg' | relative_url }}" alt="Dolly">
    </div>
    <div class="dog-info">
      <h3>Dolly</h3>
      <p class="dog-breed">West Highland White Terrier, Girl, Birthday: 2023/06/16</p>
      <p class="dog-description">
        Love all kinds of food!!!🍔🌭🌮🍕🍟🍗🥓🍛🍩
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/ridding.jpg' | relative_url }}" alt="Rollin' In My Benz">
    </div>
    <div class="dog-info">
      <h3>Rollin' In My Benz</h3>
      <p class="dog-description">
        Mom got us new ride! 🚗
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/xmax_2024.jpg' | relative_url }}" alt="Christmas 2024">
    </div>
    <div class="dog-info">
      <h3>Christmas 2024</h3>
      <p class="dog-description">
        ALL THREE OF US! Happy Christmas! 🎄
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/ucsd.jpg' | relative_url }}" alt="My Old Man Graduated Here">
    </div>
    <div class="dog-info">
      <h3>My Old Man Graduated Here</h3>
      <p class="dog-description">
        We are Tritons! 🔱
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/shanghai.jpg' | relative_url }}" alt="Heading to the USA">
    </div>
    <div class="dog-info">
      <h3>Heading to the USA</h3>
      <p class="dog-description">
        At Shanghai Pudong Airport before departure! ✈️
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/lax.jpg' | relative_url }}" alt="Exhausted at LAX">
    </div>
    <div class="dog-info">
      <h3>Exhausted at LAX</h3>
      <p class="dog-description">
        12 hours flight! We good dogs made it! 🐶
      </p>
    </div>
  </div>

  <div class="dog-card">
    <div class="dog-image">
      <img src="{{ 'assets/img/dogs/leaf.jpg' | relative_url }}" alt="Leaf Peeping in Indy">
    </div>
    <div class="dog-info">
      <h3>Leaf Peeping in Indy</h3>
      <p class="dog-description">
        Enjoy the Fall in Indy! Pretty! 🍂
      </p>
    </div>
  </div>
  
</div>

<style>
.intro-text {
  text-align: center;
  max-width: 700px;
  margin: 0 auto 3rem auto;
  font-size: 1.1rem;
  color: #666;
}

.dog-gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.dog-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.dog-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}

.dog-image {
  width: 100%;
  height: 450px;  /* Increased from 300px to 450px */
  overflow: hidden;
  background: #f5f5f5;
}

.dog-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;  /* Centers the image */
}

.dog-info {
  padding: 1.25rem;  /* Reduced from 1.5rem */
}

.dog-info h3 {
  margin: 0 0 0.3rem 0;  /* Reduced spacing */
  font-size: 1.5rem;
  color: var(--global-theme-color);
}

.dog-breed {
  color: #999;
  font-size: 0.95rem;
  margin: 0 0 0.75rem 0;  /* Reduced spacing */
}

.dog-description {
  color: #666;
  line-height: 1.6;
  margin: 0;
  font-size: 0.95rem;
}

/* Responsive */
@media (max-width: 1024px) {
  .dog-gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .dog-gallery {
    grid-template-columns: 1fr;
  }
  
  .dog-image {
    height: 400px;
  }
}
</style>