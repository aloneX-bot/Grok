
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>getebook.ai: Write an ebook once, let it earn forever</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #fcfaf8;
  --text: #3c302a;
  --text-heading: #3d3129;
  --accent: #ff6b4a;
  --accent-hover: #e85a3a;
  --muted: #8a7a72;
  --border: #e8e2dc;
  --card: #ffffff;
  --green: #2d8a5e;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: "DM Sans", Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background: var(--bg);
  color: var(--text);
  line-height: 1.6;
  font-size: 16px;
}
a { text-decoration: none; color: inherit; }
.container { max-width: 1120px; margin: 0 auto; padding: 0 24px; }

/* Nav */
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 18px 0;
  position: sticky;
  top: 0;
  background: rgba(252,250,248,0.92);
  backdrop-filter: blur(10px);
  z-index: 100;
  border-bottom: 1px solid transparent;
}
.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-weight: 700;
  font-size: 1.15rem;
  color: var(--text-heading);
}
.logo-mark {
  width: 32px; height: 32px;
  background: var(--accent);
  border-radius: 8px;
  display: flex; align-items: center; justify-content: center;
  color: white; font-weight: 800; font-size: 1.1rem;
}
.nav-links { display: flex; gap: 28px; align-items: center; font-size: 0.95rem; font-weight: 500; }
.nav-links a:hover { color: var(--accent); }
.nav-cta { display: flex; gap: 12px; align-items: center; }
.btn {
  display: inline-flex; align-items: center; justify-content: center;
  padding: 10px 20px;
  border-radius: 10px;
  font-weight: 600;
  font-size: 0.95rem;
  cursor: pointer;
  border: none;
  transition: all 0.15s;
}
.btn-primary {
  background: var(--accent);
  color: white;
}
.btn-primary:hover { background: var(--accent-hover); }
.btn-ghost {
  background: transparent;
  color: var(--text);
  border: 1px solid var(--border);
}
.btn-ghost:hover { background: #f5f2ef; }
.btn-lg { padding: 14px 28px; font-size: 1.05rem; border-radius: 12px; }

/* Hero */
.hero {
  text-align: center;
  padding: 80px 0 60px;
}
.badge {
  display: inline-block;
  background: #fff;
  border: 1px solid var(--border);
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--muted);
  margin-bottom: 24px;
}
.hero h1 {
  font-size: clamp(2.4rem, 5vw, 3.75rem);
  font-weight: 700;
  line-height: 1.1;
  color: var(--text-heading);
  letter-spacing: -0.03em;
  margin-bottom: 20px;
}
.hero p.sub {
  font-size: 1.2rem;
  max-width: 640px;
  margin: 0 auto 28px;
  color: var(--text);
}
.examples {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  margin-bottom: 32px;
}
.example-pill {
  background: #fff;
  border: 1px solid var(--border);
  padding: 8px 16px;
  border-radius: 999px;
  font-size: 0.9rem;
}
.hero-note {
  font-size: 0.9rem;
  color: var(--muted);
  margin-bottom: 24px;
}
.hero-actions { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; margin-bottom: 40px; }
.platforms {
  font-size: 0.8rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 12px;
}
.platform-logos {
  display: flex; gap: 28px; justify-content: center; flex-wrap: wrap;
  font-weight: 600; color: #555; font-size: 0.95rem;
}

/* Book Flip */
.book-section {
  padding: 40px 0 80px;
  text-align: center;
}
.section-label {
  font-size: 0.75rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--accent);
  font-weight: 600;
  margin-bottom: 8px;
}
.book-section h2 { font-size: 2rem; margin-bottom: 12px; color: var(--text-heading); }
.book-section p { max-width: 560px; margin: 0 auto 32px; color: var(--muted); }
.book-carousel {
  display: flex; gap: 40px; justify-content: center; flex-wrap: wrap;
}
.book-card {
  background: var(--card);
  border-radius: 16px;
  padding: 24px;
  box-shadow: 0 8px 30px rgba(0,0,0,0.06);
  width: 280px;
}
.book-cover {
  height: 220px;
  background: linear-gradient(135deg, #f8f4f0, #e8e0d8);
  border-radius: 8px;
  display: flex; align-items: center; justify-content: center;
  margin-bottom: 16px;
  font-weight: 600;
  color: var(--text-heading);
  position: relative;
  overflow: hidden;
}
.book-cover::after {
  content: "📖";
  font-size: 3rem;
  opacity: 0.6;
}
.book-title { font-weight: 600; margin-bottom: 4px; }
.book-meta { font-size: 0.85rem; color: var(--muted); }
.page-indicator { font-size: 0.8rem; color: var(--muted); margin-top: 12px; }

/* Features */
.features { padding: 80px 0; }
.features h2 { text-align: center; font-size: 2.2rem; margin-bottom: 12px; color: var(--text-heading); }
.features > .container > p { text-align: center; max-width: 520px; margin: 0 auto 48px; color: var(--muted); }
.feature-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 32px;
}
.feature h3 { font-size: 1.15rem; margin-bottom: 8px; color: var(--text-heading); }
.feature p { color: var(--muted); font-size: 0.95rem; }

/* How it works */
.how { padding: 80px 0; background: #fff; }
.how h2 { text-align: center; font-size: 2.2rem; margin-bottom: 48px; color: var(--text-heading); }
.steps { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 32px; }
.step { text-align: center; padding: 24px; }
.step-num {
  width: 48px; height: 48px;
  background: var(--accent);
  color: white;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-weight: 700;
  margin: 0 auto 16px;
}
.step h3 { margin-bottom: 10px; color: var(--text-heading); }
.step p { color: var(--muted); font-size: 0.95rem; }

/* Testimonials */
.testimonials { padding: 80px 0; }
.testimonials h2 { text-align: center; font-size: 2.2rem; margin-bottom: 8px; color: var(--text-heading); }
.testimonials .sub { text-align: center; color: var(--muted); margin-bottom: 40px; }
.testi-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}
.testi-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 20px;
}
.testi-header { display: flex; align-items: center; gap: 12px; margin-bottom: 12px; }
.avatar {
  width: 40px; height: 40px;
  border-radius: 50%;
  background: #f0ebe6;
  display: flex; align-items: center; justify-content: center;
  font-weight: 600; font-size: 0.85rem;
  color: var(--text-heading);
}
.testi-name { font-weight: 600; }
.testi-role { font-size: 0.8rem; color: var(--muted); }
.testi-quote { font-style: italic; margin-bottom: 12px; font-size: 0.95rem; }
.testi-result { font-weight: 600; color: var(--green); font-size: 0.9rem; }

/* Pricing */
.pricing { padding: 80px 0; background: #fff; text-align: center; }
.pricing h2 { font-size: 2.2rem; margin-bottom: 12px; color: var(--text-heading); }
.pricing .sub { color: var(--muted); margin-bottom: 40px; }
.price-card {
  max-width: 420px;
  margin: 0 auto 40px;
  background: var(--card);
  border: 2px solid var(--accent);
  border-radius: 16px;
  padding: 32px;
  position: relative;
}
.most-popular {
  position: absolute;
  top: -12px; left: 50%; transform: translateX(-50%);
  background: var(--accent);
  color: white;
  font-size: 0.75rem;
  font-weight: 700;
  padding: 4px 12px;
  border-radius: 999px;
  letter-spacing: 0.05em;
}
.price-card h3 { font-size: 1.4rem; margin-bottom: 4px; }
.price { font-size: 2.8rem; font-weight: 700; color: var(--text-heading); }
.price span { font-size: 1.1rem; font-weight: 500; color: var(--muted); }
.credits { color: var(--muted); margin: 8px 0 16px; }
.price-features { text-align: left; margin: 20px 0; list-style: none; }
.price-features li { padding: 6px 0; display: flex; gap: 8px; font-size: 0.95rem; }
.price-features li::before { content: "✓"; color: var(--green); font-weight: 700; }
.tiers {
  display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; margin: 24px 0;
}
.tier {
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 10px 16px;
  font-size: 0.9rem;
  background: #fff;
}
.tier.popular { border-color: var(--accent); background: #fff8f6; }

/* FAQ */
.faq { padding: 80px 0; }
.faq h2 { text-align: center; font-size: 2.2rem; margin-bottom: 40px; color: var(--text-heading); }
.faq-item {
  border-bottom: 1px solid var(--border);
  padding: 16px 0;
}
.faq-q {
  font-weight: 600;
  cursor: pointer;
  display: flex; justify-content: space-between; align-items: center;
}
.faq-a { color: var(--muted); margin-top: 8px; display: none; font-size: 0.95rem; }
.faq-item.open .faq-a { display: block; }

/* Final CTA */
.final-cta {
  text-align: center;
  padding: 80px 0;
  background: linear-gradient(180deg, var(--bg) 0%, #fff 100%);
}
.final-cta h2 { font-size: 2.4rem; margin-bottom: 16px; color: var(--text-heading); }
.final-cta p { max-width: 480px; margin: 0 auto 28px; color: var(--muted); }
.final-notes { display: flex; gap: 24px; justify-content: center; flex-wrap: wrap; margin-top: 20px; font-size: 0.9rem; color: var(--muted); }

/* Footer */
footer {
  padding: 48px 0 32px;
  border-top: 1px solid var(--border);
  font-size: 0.9rem;
  color: var(--muted);
}
.footer-grid {
  display: grid;
  grid-template-columns: 1.5fr repeat(3, 1fr);
  gap: 32px;
  margin-bottom: 40px;
}
.footer-brand { font-weight: 700; color: var(--text-heading); margin-bottom: 8px; }
footer h4 { font-size: 0.85rem; font-weight: 600; color: var(--text); margin-bottom: 12px; text-transform: uppercase; letter-spacing: 0.05em; }
footer ul { list-style: none; }
footer li { margin-bottom: 8px; }
footer a:hover { color: var(--accent); }
.copyright { text-align: center; padding-top: 24px; border-top: 1px solid var(--border); font-size: 0.85rem; }

@media (max-width: 768px) {
  .nav-links { display: none; }
  .footer-grid { grid-template-columns: 1fr 1fr; }
  .hero { padding: 48px 0 40px; }
}
</style>
</head>
<body>

<nav>
  <div class="container" style="display:flex; width:100%; align-items:center; justify-content:space-between;">
    <a href="#" class="logo">
      <div class="logo-mark">G</div>
      getebook.ai
    </a>
    <div class="nav-links">
      <a href="#how">How it works</a>
      <a href="#features">Features</a>
      <a href="#pricing">Pricing</a>
      <a href="#faq">FAQ</a>
    </div>
    <div class="nav-cta">
      <a href="#" class="btn btn-ghost">Log in</a>
      <a href="#cta" class="btn btn-primary">Start building, free</a>
    </div>
  </div>
</nav>

<section class="hero">
  <div class="container">
    <div class="badge">Loved by 12,000+ creators publishing with AI</div>
    <h1>Write it once.<br>Let it earn forever.</h1>
    <p class="sub">Just tell Booker what you know. Watch it write every chapter and design your cover, building your finished ebook live in front of you.</p>
    <div class="examples">
      <span class="example-pill">A meal-prep guide for busy parents</span>
      <span class="example-pill">Side-hustle 101 for complete beginners</span>
      <span class="example-pill">A productivity system that actually sticks</span>
    </div>
    <p class="hero-note">No credit card to start · cancel anytime · plans from $29/mo</p>
    <div class="hero-actions">
      <a href="#cta" class="btn btn-primary btn-lg">Start building, free</a>
      <a href="#books" class="btn btn-ghost btn-lg">See how it works ↓</a>
    </div>
    <div class="platforms">Publish and sell on</div>
    <div class="platform-logos">
      <span>Amazon KDP</span>
      <span>Etsy</span>
      <span>Apple Books</span>
      <span>Gumroad</span>
    </div>
  </div>
</section>

<section class="book-section" id="books">
  <div class="container">
    <div class="section-label">Flip through a real book</div>
    <h2>See exactly what you'll create</h2>
    <p>These are real books made with getebook.ai. One is a polished ebook, the other a print-ready coloring book. Tap the arrows to flip through the cover and first pages.</p>
    <div class="book-carousel">
      <div class="book-card">
        <div class="book-cover">Meal Prep</div>
        <div class="book-title">Meal Prep Made Easy for Parents</div>
        <div class="book-meta">eBook · cover + 10 pages</div>
        <div class="page-indicator">1 of 12</div>
      </div>
      <div class="book-card">
        <div class="book-cover">Pip's Garden</div>
        <div class="book-title">Pip's Garden Tea Party</div>
        <div class="book-meta">Coloring book · cover + 10 pages</div>
        <div class="page-indicator">1 of 12</div>
      </div>
    </div>
  </div>
</section>

<section class="features" id="features">
  <div class="container">
    <div class="section-label">What you get</div>
    <h2>Everything you need to publish and profit</h2>
    <p>No writing degree, no design skills, no ghostwriter invoice. Just your idea and a few minutes.</p>
    <div class="feature-grid">
      <div class="feature">
        <h3>From idea to finished book</h3>
        <p>Type one sentence about what you know. getebook turns it into a titled, chaptered, fully written ebook.</p>
      </div>
      <div class="feature">
        <h3>Covers that earn the click</h3>
        <p>Get a professional cover designed for you, the kind that stands out on a crowded store page.</p>
      </div>
      <div class="feature">
        <h3>Ebooks and coloring books</h3>
        <p>Lead magnets, guides, reports, workbooks, courses, and novels, plus a studio for print-ready coloring books. Pick what fits your goal.</p>
      </div>
      <div class="feature">
        <h3>Store-ready in one click</h3>
        <p>Export a clean, typeset PDF or EPUB that is ready for KDP, Etsy, or Apple Books the same day.</p>
      </div>
    </div>
    <div style="text-align:center; margin-top:40px;">
      <a href="#cta" class="btn btn-primary btn-lg">Create your ebook for free</a>
    </div>
  </div>
</section>

<section class="how" id="how">
  <div class="container">
    <div class="section-label">Idea to sellable ebook, live</div>
    <h2>Three steps from your idea to a published ebook</h2>
    <div class="steps">
      <div class="step">
        <div class="step-num">1</div>
        <h3>Tell Booker your idea</h3>
        <p>Describe what you know in a sentence. Booker turns it into a titled, chaptered ebook brief. That is the whole setup.</p>
      </div>
      <div class="step">
        <div class="step-num">2</div>
        <h3>Watch it build live</h3>
        <p>Booker writes every chapter and designs your cover in front of you. Preview the whole ebook, cover to cover, and edit anything before you commit.</p>
      </div>
      <div class="step">
        <div class="step-num">3</div>
        <h3>Go Pro, download and sell</h3>
        <p>Go Pro from $29/mo to unlock the download. Export a store-ready PDF, EPUB, or DOCX and list it on Amazon KDP, Etsy, or your own site.</p>
      </div>
    </div>
  </div>
</section>

<section class="testimonials">
  <div class="container">
    <div class="section-label">Not just words, real income</div>
    <h2>Real creators. Real income.</h2>
    <p class="sub">Results from people who shipped with getebook.ai</p>
    <div class="testi-grid">
      <div class="testi-card">
        <div class="testi-header">
          <div class="avatar">BH</div>
          <div>
            <div class="testi-name">Ben H.</div>
            <div class="testi-role">Side-hustle creator</div>
          </div>
        </div>
        <div class="testi-quote">"I turned a topic I already knew well into a short guide over a weekend. It was live on KDP by Monday and made its first sales that week."</div>
        <div class="testi-result">$612 in week one</div>
      </div>
      <div class="testi-card">
        <div class="testi-header">
          <div class="avatar">DR</div>
          <div>
            <div class="testi-name">David R.</div>
            <div class="testi-role">Newsletter writer</div>
          </div>
        </div>
        <div class="testi-quote">"I always meant to write an ebook and never did. With getebook I shipped five in a month and they sell while I sleep."</div>
        <div class="testi-result">5 guides published</div>
      </div>
      <div class="testi-card">
        <div class="testi-header">
          <div class="avatar">SK</div>
          <div>
            <div class="testi-name">Sofia K.</div>
            <div class="testi-role">Marketing consultant</div>
          </div>
        </div>
        <div class="testi-quote">"I made a free lead magnet in an afternoon. It looks like something I paid a designer for, and it doubled my signups."</div>
        <div class="testi-result">Grew my email list</div>
      </div>
      <div class="testi-card">
        <div class="testi-header">
          <div class="avatar">MD</div>
          <div>
            <div class="testi-name">Marco D.</div>
            <div class="testi-role">Etsy shop owner</div>
          </div>
        </div>
        <div class="testi-quote">"I added a few digital ebooks to my Etsy shop with zero inventory and zero design work. Traffic and orders climbed without any extra work from me."</div>
        <div class="testi-result">80% more shop visits</div>
      </div>
      <div class="testi-card">
        <div class="testi-header">
          <div class="avatar">PJ</div>
          <div>
            <div class="testi-name">Priya J.</div>
            <div class="testi-role">Course creator</div>
          </div>
        </div>
        <div class="testi-quote">"The cover and formatting are what sold me. It looks professional out of the box, so I had nothing left to fix before publishing."</div>
        <div class="testi-result">Idea to launch in a day</div>
      </div>
      <div class="testi-card">
        <div class="testi-header">
          <div class="avatar">JM</div>
          <div>
            <div class="testi-name">James M.</div>
            <div class="testi-role">Solopreneur</div>
          </div>
        </div>
        <div class="testi-quote">"This is the first thing I have made that keeps earning after I stop working on it. The math finally works in my favor."</div>
        <div class="testi-result">First passive income</div>
      </div>
    </div>
  </div>
</section>

<section class="pricing" id="pricing">
  <div class="container">
    <div class="section-label">Start free, pay only if you publish</div>
    <h2>Plans from $29/mo, pay only when you're ready to sell</h2>
    <p class="sub">Most Popular</p>
    <div class="price-card">
      <div class="most-popular">MOST POPULAR</div>
      <h3>Pro</h3>
      <div class="price">$29 <span>/mo</span></div>
      <div class="credits">300 credits every month</div>
      <p style="font-size:0.9rem; color:var(--muted); margin-bottom:16px;">Cancel anytime · billed monthly · no lock-in</p>
      <ul class="price-features">
        <li>Download every ebook you build, instantly</li>
        <li>Credits refresh every month</li>
        <li>Export store-ready PDF, EPUB, and DOCX</li>
        <li>Full commercial license — sell on KDP, Etsy, or your own site</li>
        <li>Regenerate any chapter, title, or cover</li>
        <li>Cancel anytime, no lock-in</li>
      </ul>
      <a href="#cta" class="btn btn-primary btn-lg" style="width:100%;">Get Pro — $29/mo</a>
    </div>
    <h3 style="margin-bottom:16px;">Pro plans</h3>
    <p style="color:var(--muted); margin-bottom:16px;">Pick the monthly credits that fit you — tap a plan, then subscribe. Change anytime.</p>
    <div class="tiers">
      <div class="tier popular">$29 /mo<br>300 credits</div>
      <div class="tier">$39 /mo<br>500 credits</div>
      <div class="tier">$49 /mo<br>750 credits</div>
      <div class="tier">$59 /mo<br>1000 credits</div>
      <div class="tier">$79 /mo<br>1500 credits</div>
      <div class="tier">$99 /mo<br>2000 credits</div>
    </div>
    <p style="font-size:0.9rem; color:var(--muted);">Every plan includes the full Pro feature set. Cancel anytime.</p>
  </div>
</section>

<section class="faq" id="faq">
  <div class="container" style="max-width:720px;">
    <h2>Questions? We've got answers.</h2>
    <div class="faq-item">
      <div class="faq-q">How is this different from writing it myself or using ChatGPT? <span>+</span></div>
      <div class="faq-a">ChatGPT gives you raw text in a chat window, and you still have to structure it, format it, design a cover, and turn it into a file a store will accept. getebook does the whole job. It builds the outline, writes every chapter in your voice, designs the cover, and exports a typeset PDF or EPUB that is ready to upload. You stay the editor, the tool does the heavy lifting.</div>
    </div>
    <div class="faq-item">
      <div class="faq-q">Who is getebook for? <span>+</span></div>
      <div class="faq-a">Coaches, consultants, course creators, solopreneurs, and self-publishers who want to turn their knowledge into sellable ebooks quickly.</div>
    </div>
    <div class="faq-item">
      <div class="faq-q">Can I make coloring books too? <span>+</span></div>
      <div class="faq-a">Yes. There's a dedicated studio for print-ready coloring books alongside regular ebooks.</div>
    </div>
    <div class="faq-item">
      <div class="faq-q">Is the AI writing actually good enough to sell? <span>+</span></div>
      <div class="faq-a">Creators are shipping and selling the books. You can preview and edit everything before publishing.</div>
    </div>
    <div class="faq-item">
      <div class="faq-q">Do I own what I create, and can I sell it? <span>+</span></div>
      <div class="faq-a">Yes. Full commercial license — sell on KDP, Etsy, or your own site.</div>
    </div>
    <div class="faq-item">
      <div class="faq-q">What can I realistically expect to earn? <span>+</span></div>
      <div class="faq-a">Results vary. Some creators report first sales in week one and ongoing catalog income. Sell just 2 ebooks at $14.99 and your Pro plan is covered.</div>
    </div>
  </div>
</section>

<section class="final-cta" id="cta">
  <div class="container">
    <h2>Your knowledge is worth more than you think.</h2>
    <p>Tell Booker your idea, watch it build your ebook, then go Pro from $29/mo to download and sell it.</p>
    <a href="#" class="btn btn-primary btn-lg">Start building, free</a>
    <div class="final-notes">
      <span>Plans from $29/mo</span>
      <span>Cancel anytime</span>
      <span>You own everything</span>
    </div>
  </div>
</section>

<footer>
  <div class="container">
    <div class="footer-grid">
      <div>
        <div class="footer-brand">getebook.ai</div>
        <p>Publish once. Earn on repeat.</p>
      </div>
      <div>
        <h4>Product</h4>
        <ul>
          <li><a href="#how">How it works</a></li>
          <li><a href="#features">Features</a></li>
          <li><a href="#pricing">Pricing</a></li>
          <li><a href="#">Examples</a></li>
        </ul>
      </div>
      <div>
        <h4>Resources</h4>
        <ul>
          <li><a href="#">Blog</a></li>
          <li><a href="#">Free tools</a></li>
          <li><a href="#">Ebook types</a></li>
          <li><a href="#">Glossary</a></li>
        </ul>
      </div>
      <div>
        <h4>Company</h4>
        <ul>
          <li><a href="#">Contact</a></li>
          <li><a href="#">Privacy</a></li>
          <li><a href="#">Terms</a></li>
          <li><a href="#">Cookies</a></li>
        </ul>
      </div>
    </div>
    <div class="copyright">
      © 2026 getebook.ai. All rights reserved. · support@getebook.ai
    </div>
  </div>
</footer>

<script>
document.querySelectorAll('.faq-q').forEach(q => {
  q.addEventListener('click', () => {
    const item = q.parentElement;
    item.classList.toggle('open');
    q.querySelector('span').textContent = item.classList.contains('open') ? '−' : '+';
  });
});
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    const target = document.querySelector(a.getAttribute('href'));
    if (target) {
      e.preventDefault();
      target.scrollIntoView({ behavior: 'smooth' });
    }
  });
});
</script>
</body>
</html>
