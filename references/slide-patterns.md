# Slide Layout Patterns

Copy-paste these patterns and adapt to your content and aesthetic.

---

## Title Slide — Full Bleed

```html
<section class="slide active" data-slide="1">
  <div class="slide-title-full">
    <div class="eyebrow animate-in">Company / Event / Context</div>
    <h1 class="display-title animate-in">Main Presentation<br>Title Here</h1>
    <p class="subtitle animate-in">Subtitle or tagline — one line</p>
    <div class="meta animate-in">
      <span>Speaker Name</span>
      <span class="sep">·</span>
      <span>Month Year</span>
    </div>
  </div>
</section>
```

```css
.slide-title-full {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0 10vw;
}
.eyebrow {
  font-family: var(--font-body);
  font-size: 1.2vw;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 2vh;
}
.display-title {
  font-family: var(--font-display);
  font-size: 7vw;
  line-height: 1.05;
  margin: 0 0 3vh;
}
.subtitle {
  font-size: 1.8vw;
  color: var(--muted);
  margin: 0 0 4vh;
}
.meta {
  font-size: 1.2vw;
  color: var(--muted);
  display: flex;
  gap: 1.5ch;
}
.sep { opacity: 0.4; }
```

---

## Statement Slide — Single Big Idea

```html
<section class="slide" data-slide="2">
  <div class="slide-statement">
    <blockquote class="statement animate-in">
      The single most important insight you want them to remember.
    </blockquote>
  </div>
</section>
```

```css
.slide-statement {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 12vw;
  text-align: center;
}
.statement {
  font-family: var(--font-display);
  font-size: 4.5vw;
  line-height: 1.3;
  margin: 0;
  font-style: italic;
}
```

---

## Content + Visual (Split Layout)

```html
<section class="slide" data-slide="3">
  <div class="slide-split">
    <div class="split-left">
      <h2 class="slide-heading animate-in">Section Heading</h2>
      <p class="body-text animate-in">Supporting explanation — keep under 40 words. Make it punchy and direct.</p>
      <ul class="bullet-list">
        <li class="animate-in">Key point one</li>
        <li class="animate-in">Key point two</li>
        <li class="animate-in">Key point three</li>
      </ul>
    </div>
    <div class="split-right animate-in">
      <!-- SVG, illustration, or visual element -->
      <svg viewBox="0 0 200 200" class="slide-visual">
        <!-- your SVG here -->
      </svg>
    </div>
  </div>
</section>
```

```css
.slide-split {
  height: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 6vw;
  align-items: center;
  padding: 6vh 8vw;
}
.slide-heading {
  font-family: var(--font-display);
  font-size: 3.5vw;
  line-height: 1.15;
  margin: 0 0 2vh;
}
.body-text {
  font-size: 1.8vw;
  line-height: 1.65;
  color: var(--muted);
  margin: 0 0 3vh;
}
.bullet-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1.5vh;
}
.bullet-list li {
  font-size: 1.6vw;
  padding-left: 1.8ch;
  position: relative;
}
.bullet-list li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--accent);
}
.slide-visual {
  width: 100%;
  height: auto;
  max-height: 60vh;
  object-fit: contain;
}
```

---

## Statistics / Data Highlight

```html
<section class="slide" data-slide="4">
  <div class="slide-stats">
    <h2 class="slide-heading animate-in">Key Numbers</h2>
    <div class="stats-grid">
      <div class="stat-card animate-in">
        <span class="stat-value">$4.2B</span>
        <span class="stat-label">Market Size</span>
      </div>
      <div class="stat-card animate-in">
        <span class="stat-value">340%</span>
        <span class="stat-label">Growth YoY</span>
      </div>
      <div class="stat-card animate-in">
        <span class="stat-value">12M</span>
        <span class="stat-label">Users Reached</span>
      </div>
    </div>
  </div>
</section>
```

```css
.slide-stats {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6vh 8vw;
}
.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 4vw;
  margin-top: 4vh;
}
.stat-card {
  display: flex;
  flex-direction: column;
  gap: 1vh;
}
.stat-value {
  font-family: var(--font-display);
  font-size: 7vw;
  line-height: 1;
  color: var(--accent);
}
.stat-label {
  font-size: 1.4vw;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
```

---

## Quote Slide

```html
<section class="slide" data-slide="5">
  <div class="slide-quote">
    <div class="quote-mark animate-in">"</div>
    <blockquote class="quote-text animate-in">
      The quote text goes here. Keep it to 2–3 lines for maximum impact on screen.
    </blockquote>
    <cite class="quote-attribution animate-in">— Person Name, Title / Context</cite>
  </div>
</section>
```

```css
.slide-quote {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6vh 15vw;
}
.quote-mark {
  font-family: var(--font-display);
  font-size: 20vw;
  line-height: 0.6;
  color: var(--accent);
  opacity: 0.3;
  margin-bottom: -2vh;
}
.quote-text {
  font-family: var(--font-display);
  font-size: 2.8vw;
  line-height: 1.5;
  font-style: italic;
  margin: 0 0 3vh;
}
.quote-attribution {
  font-size: 1.4vw;
  color: var(--muted);
  font-style: normal;
}
```

---

## Section Divider

```html
<section class="slide" data-slide="6">
  <div class="slide-divider">
    <span class="section-number animate-in">02</span>
    <h2 class="section-title animate-in">Section Name</h2>
    <div class="section-rule animate-in"></div>
  </div>
</section>
```

```css
.slide-divider {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0 8vw;
  background: var(--accent);  /* Invert colors for section breaks */
  color: var(--bg);
}
.section-number {
  font-family: var(--font-body);
  font-size: 1.2vw;
  letter-spacing: 0.3em;
  opacity: 0.5;
  margin-bottom: 2vh;
}
.section-title {
  font-family: var(--font-display);
  font-size: 8vw;
  line-height: 1;
  margin: 0 0 3vh;
}
.section-rule {
  width: 6vw;
  height: 4px;
  background: currentColor;
  opacity: 0.4;
}
```

---

## Steps / Process Slide

```html
<section class="slide" data-slide="7">
  <div class="slide-steps">
    <h2 class="slide-heading animate-in">How It Works</h2>
    <ol class="steps-list">
      <li class="step animate-in">
        <span class="step-num">01</span>
        <div class="step-content">
          <strong>Step Title</strong>
          <p>Brief explanation of this step.</p>
        </div>
      </li>
      <li class="step animate-in">
        <span class="step-num">02</span>
        <div class="step-content">
          <strong>Step Title</strong>
          <p>Brief explanation of this step.</p>
        </div>
      </li>
      <li class="step animate-in">
        <span class="step-num">03</span>
        <div class="step-content">
          <strong>Step Title</strong>
          <p>Brief explanation of this step.</p>
        </div>
      </li>
    </ol>
  </div>
</section>
```

```css
.slide-steps {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6vh 8vw;
}
.steps-list {
  list-style: none;
  padding: 0;
  margin: 3vh 0 0;
  display: flex;
  flex-direction: column;
  gap: 3vh;
}
.step {
  display: flex;
  align-items: flex-start;
  gap: 3vw;
}
.step-num {
  font-family: var(--font-display);
  font-size: 3vw;
  color: var(--accent);
  line-height: 1;
  flex-shrink: 0;
  min-width: 4vw;
}
.step-content strong {
  font-size: 1.8vw;
  display: block;
  margin-bottom: 0.5vh;
}
.step-content p {
  font-size: 1.4vw;
  color: var(--muted);
  margin: 0;
}
```

---

## Closing / CTA Slide

```html
<section class="slide" data-slide="12">
  <div class="slide-closing">
    <h2 class="closing-title animate-in">Thank You</h2>
    <p class="closing-line animate-in">One memorable closing line.</p>
    <div class="cta-block animate-in">
      <span class="cta-label">Get in touch</span>
      <a class="cta-link" href="mailto:name@domain.com">name@domain.com</a>
    </div>
  </div>
</section>
```

```css
.slide-closing {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 6vh 12vw;
}
.closing-title {
  font-family: var(--font-display);
  font-size: 8vw;
  margin: 0 0 2vh;
}
.closing-line {
  font-size: 2vw;
  color: var(--muted);
  margin: 0 0 5vh;
  max-width: 50ch;
}
.cta-block {
  display: flex;
  flex-direction: column;
  gap: 1vh;
}
.cta-label {
  font-size: 1.2vw;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: var(--muted);
}
.cta-link {
  font-size: 2vw;
  color: var(--accent);
  text-decoration: none;
  border-bottom: 1px solid currentColor;
  padding-bottom: 0.3vh;
}
```