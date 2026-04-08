# Design Principles for Presentations

## The One-Slide Rule
Every slide should communicate **one thing**. If you find yourself writing a slide that needs to say two things, split it into two slides. Slides are cheap. Clarity is expensive.

## The Squint Test
Squint at your slide until it blurs. Can you still see:
- What's the most important element?
- Where your eye goes first?
- A clear separation between foreground and background?

If no, you have a hierarchy problem.

## Presentation-Specific Contrast
Normal web contrast guidelines (4.5:1) are insufficient for projected slides in bright rooms. Aim for **7:1 or higher**. When in doubt, go darker or lighter.

## The Legibility Threshold
Text below **1.6vw** is illegible at the back of a room. Never go smaller. Use layout tricks (fewer words, abbreviations, visual encoding) instead of shrinking text.

## Background Atmosphere
Flat solid backgrounds are missed opportunities. Instead, consider:

**Texture overlays** (subtle noise):
```css
.slide::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  opacity: 0.15;
  pointer-events: none;
}
```

**Gradient mesh backgrounds**:
```css
background: 
  radial-gradient(ellipse at 20% 20%, hsla(220,80%,60%,0.15) 0%, transparent 60%),
  radial-gradient(ellipse at 80% 80%, hsla(280,70%,50%,0.10) 0%, transparent 60%),
  var(--bg);
```

**Geometric accent elements**:
```css
/* Large decorative circle, clipped at edge */
.slide::after {
  content: '';
  position: absolute;
  right: -10vw;
  top: -10vw;
  width: 40vw;
  height: 40vw;
  border-radius: 50%;
  border: 1px solid rgba(255,255,255,0.06);
  pointer-events: none;
}
```

## Negative Space is Structure
Don't fill slides. Leave 40–60% of each slide empty. Negative space:
- Makes text feel more important
- Creates visual breathing room
- Guides the eye to what matters

## The Accent Color Discipline
Your accent color should appear on approximately 20% of visual elements. More than that, and it loses impact. Use it for:
- Key numbers/statistics
- The most important word in a heading
- Bullet markers / decorative elements
- Hover states on interactive elements

Never use it for: body text, backgrounds, decorative fills that don't carry meaning.

## Motion Hierarchy
Not everything needs to animate. Reserve animation for:
1. **Slide entrance** — one coordinated reveal as the slide appears
2. **Key data moments** — a counter ticking up, a bar filling in
3. **Interaction feedback** — hover states, button clicks

Avoid: spinning elements, bouncing elements, continuous loops (unless they're extremely subtle and peripheral).

## The Presentation Triangle
Every slide sits at some point in this triangle:

```
         INFORMATION
              △
             / \
            /   \
           /     \
    EMOTION ─────── PERSUASION
```

- **Information slides**: Data, timelines, process steps — prioritize clarity and scannability
- **Emotion slides**: Quotes, stories, statements — prioritize impact and atmosphere  
- **Persuasion slides**: Benefits, CTAs, proposals — prioritize clarity + emotion together

Knowing where a slide lives helps you decide whether to add atmospheric backgrounds (emotion), clean grid layouts (information), or bold typography (persuasion).

## Slide Pacing
Vary your slide types. A deck with 12 content+text slides in a row is exhausting. A good rhythm:
```
Title → Statement → Content → Divider → Data → Content → Quote → Content → Closing
```

Rule of thumb: Insert a "breathing" slide (statement, divider, or visual-only) every 3–4 content slides.