# Competitive Analysis & Journey Map (Module 2)

## Responses
- **Role, who are you solving for? (the specific user segment or profile):** A shift-working consumer whose income varies week to week, trying to manage one or more open claims entirely through the digital portal rather than by phone.
- **Goal, what is this user ultimately trying to achieve?:** To commit to an instalment plan she's actually confident she can keep — without needing to call anyone to get there
- **Friction, the main barrier (moment of misery) stopping them from succeeding:** At the exact moment she's asked to commit, the system shows her a single number with no reasoning behind it — "It just gave me a number. I don't know why that number and not a different one, so I didn't trust it" — and no explanation of what happens if her variable income means she falls short — "Nobody told me what happens if I miss one payment versus two. I just assumed the worst." This persona drives the highest agent-escalation rate of any archetype in the research (high cost per claim), and is also the only persona tied to a confirmed post-agreement default — a case our own research explicitly flags as "resolved at creation, but didn't hold" (payment default risk).
- **External tools, the outside platforms or tools the user is forced to use:** Call Consumer Support
- **The process, the 3 to 5 manual steps the user takes to get the job done:** Step 1 — She opens the portal but doesn't commit on the spot; she parks the decision
Step 2 — She tries to sanity-check the number herself, informally, with whatever she has on hand (recent bank balance, a rough mental tally of upcoming shifts) — because the system gave her no way to do this inside the journey.
Step 3 — She calls Daniel specifically to ask the two things the portal never told her: "why this number" and "what happens if I miss a payment."
Step 4 — If she doesn't call and still doesn't get clarity, she commits anyway, essentially gambling rather than deciding.
- **Core frustration, the exact moment the process feels most “broken”:** Being asked to commit to a specific number, with zero explanation of where it came from and zero visibility into what happens if she can't keep up with it.
It's not the income question, not the document request, not even the initial outreach — she gets through all of that willingly. The process breaks at one precise instant: the screen that shows her the proposed instalment amount and asks her to agree to it.
- **The evidence, a specific quote or behavior from the research that proves this:** "It just gave me a number. I don't know why that number and not a different one, so I didn't trust it."
"Nobody told me what happens if I miss one payment versus two. I just assumed the worst."
- **Your journey map, a shareable link, or the map file you committed (e.g. journey-map.html):** <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Future State Journey — Transparent, Adaptive Self-Service</title>
<style>
  :root {
    --ink: #1a2233;
    --muted: #5b6478;
    --paper: #ffffff;
    --bg: #f4f6fb;
    --accent: #2f6fed;
    --accent-light: #e8f0ff;
    --stage1: #c0392b;
    --stage2: #d68910;
    --stage3: #2e86c1;
    --stage4: #1e8449;
    --radius: 16px;
    --shadow: 0 10px 30px rgba(26, 34, 51, 0.08);
  }

  * { box-sizing: border-box; }

  body {
    margin: 0;
    font-family: 'Segoe UI', 'Helvetica Neue', Arial, sans-serif;
    background: linear-gradient(180deg, #eef2fb 0%, #f7f9fd 40%, #ffffff 100%);
    color: var(--ink);
    padding: 48px 24px 80px;
  }

  .wrap {
    max-width: 1180px;
    margin: 0 auto;
  }

  header.page-header {
    text-align: center;
    margin-bottom: 36px;
  }

  .eyebrow {
    display: inline-block;
    font-size: 12px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    font-weight: 700;
    background: var(--accent-light);
    padding: 6px 14px;
    border-radius: 999px;
    margin-bottom: 14px;
  }

  h1 {
    font-size: 32px;
    margin: 0 0 10px;
    font-weight: 800;
    letter-spacing: -0.01em;
  }

  .persona-line {
    color: var(--muted);
    font-size: 15px;
    max-width: 760px;
    margin: 0 auto;
    line-height: 1.5;
  }

  .strategy-card {
    background: var(--paper);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 22px 28px;
    margin: 28px 0 44px;
    border-left: 6px solid var(--accent);
  }

  .strategy-card .label {
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--accent);
    font-weight: 700;
    margin-bottom: 6px;
  }

  .strategy-card p {
    margin: 0;
    font-size: 16px;
    line-height: 1.55;
  }

  /* Visual timeline */
  .timeline {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    position: relative;
    margin-bottom: 56px;
  }

  .timeline::before {
    content: "";
    position: absolute;
    top: 46px;
    left: 6%;
    right: 6%;
    height: 3px;
    background: linear-gradient(90deg, var(--stage1), var(--stage2), var(--stage3), var(--stage4));
    z-index: 0;
    border-radius: 3px;
  }

  .tl-stop {
    position: relative;
    z-index: 1;
    text-align: center;
    padding: 0 10px;
  }

  .tl-mood {
    width: 68px;
    height: 68px;
    margin: 0 auto 10px;
    border-radius: 50%;
    background: var(--paper);
    box-shadow: var(--shadow);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 30px;
    border: 3px solid var(--line-color);
  }

  .tl-stop:nth-child(1) .tl-mood { border-color: var(--stage1); }
  .tl-stop:nth-child(2) .tl-mood { border-color: var(--stage2); }
  .tl-stop:nth-child(3) .tl-mood { border-color: var(--stage3); }
  .tl-stop:nth-child(4) .tl-mood { border-color: var(--stage4); }

  .tl-moment {
    font-size: 13px;
    color: var(--muted);
    font-weight: 600;
  }

  .tl-arrow {
    display: none;
  }

  /* Stage cards */
  .stages {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    margin-bottom: 56px;
  }

  .stage-card {
    background: var(--paper);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 24px 20px 22px;
    display: flex;
    flex-direction: column;
    gap: 14px;
    border-top: 5px solid var(--c);
  }

  .stage-card.s1 { --c: var(--stage1); }
  .stage-card.s2 { --c: var(--stage2); }
  .stage-card.s3 { --c: var(--stage3); }
  .stage-card.s4 { --c: var(--stage4); }

  .stage-badge {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background: var(--c);
    color: #fff;
    font-weight: 800;
    font-size: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .stage-name {
    font-size: 17px;
    font-weight: 800;
    margin: 0;
    line-height: 1.3;
  }

  .field {
    font-size: 13px;
    line-height: 1.5;
  }

  .field .k {
    display: block;
    font-size: 10.5px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--muted);
    font-weight: 700;
    margin-bottom: 3px;
  }

  .field .v {
    color: var(--ink);
  }

  .ab-box {
    margin-top: auto;
    background: var(--accent-light);
    border-radius: 10px;
    padding: 12px 14px;
    font-size: 13px;
    font-weight: 600;
    color: #16305f;
    line-height: 1.45;
  }

  .ab-box .k {
    display: block;
    font-size: 10.5px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--accent);
    font-weight: 700;
    margin-bottom: 4px;
  }

  .arrow-sym {
    color: var(--accent);
    font-weight: 800;
  }

  /* Competitive advantages */
  .advantages {
    margin-top: 20px;
  }

  .advantages h2 {
    text-align: center;
    font-size: 22px;
    font-weight: 800;
    margin-bottom: 6px;
  }

  .advantages .sub {
    text-align: center;
    color: var(--muted);
    font-size: 14px;
    margin-bottom: 28px;
  }

  .adv-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
  }

  .adv-card {
    background: linear-gradient(160deg, #ffffff 0%, #f3f7ff 100%);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 24px 22px;
    position: relative;
  }

  .adv-num {
    font-size: 42px;
    font-weight: 900;
    color: var(--accent-light);
    position: absolute;
    top: 10px;
    right: 18px;
    line-height: 1;
  }

  .adv-card h3 {
    font-size: 15px;
    margin: 0 0 8px;
    font-weight: 800;
    position: relative;
    z-index: 1;
  }

  .adv-card p {
    font-size: 13.5px;
    color: var(--muted);
    line-height: 1.5;
    margin: 0;
    position: relative;
    z-index: 1;
  }

  footer {
    text-align: center;
    margin-top: 50px;
    font-size: 12px;
    color: var(--muted);
  }

  @media (max-width: 980px) {
    .timeline, .stages, .adv-grid {
      grid-template-columns: 1fr;
    }
    .timeline::before { display: none; }
    .tl-stop { margin-bottom: 18px; }
  }
</style>
</head>
<body>
  <div class="wrap">

    <header class="page-header">
      <span class="eyebrow">Future State Journey</span>
      <h1>From Blind Commitment to Confident Self-Service</h1>
      <p class="persona-line">
        A shift-working consumer whose income varies week to week, managing one or more open claims
        entirely through the digital portal — without needing to call anyone to agree to a plan she
        actually trusts she can keep.
      </p>
    </header>

    <div class="strategy-card">
      <div class="label">Strategy</div>
      <p>
        <strong>Transparent, Adaptive Self-Service</strong> — explain the number, show the consequence,
        and let her adjust the plan herself when her income changes, so trust (not pressure) drives commitment.
      </p>
    </div>

    <!-- Visual timeline -->
    <div class="timeline">
      <div class="tl-stop">
        <div class="tl-mood">😐</div>
        <div class="tl-moment">Guarded</div>
      </div>
      <div class="tl-stop">
        <div class="tl-mood">🤔</div>
        <div class="tl-moment">Informed</div>
      </div>
      <div class="tl-stop">
        <div class="tl-mood">😌</div>
        <div class="tl-moment">Confident</div>
      </div>
      <div class="tl-stop">
        <div class="tl-mood">💪</div>
        <div class="tl-moment">Empowered</div>
      </div>
    </div>

    <!-- Stage cards -->
    <div class="stages">

      <div class="stage-card s1">
        <div class="stage-badge">1</div>
        <h2 class="stage-name">See Herself Reflected<br><span style="font-weight:500;font-size:12px;color:var(--muted)">Income-Aware Setup</span></h2>
        <div class="field">
          <span class="k">User Action</span>
          <span class="v">Confirms a flexible income range or shift pattern instead of one fixed figure.</span>
        </div>
        <div class="field">
          <span class="k">Internal State</span>
          <span class="v">Guarded but curious — wants a plan that fits how she actually earns.</span>
        </div>
        <div class="field">
          <span class="k">Pain Point Addressed</span>
          <span class="v">No way to model "what if my income drops" before committing.</span>
        </div>
        <div class="ab-box">
          <span class="k">Action → Benefit</span>
          Confirms variable income range <span class="arrow-sym">→</span> gets a plan built for her reality, not a guess.
        </div>
      </div>

      <div class="stage-card s2">
        <div class="stage-badge">2</div>
        <h2 class="stage-name">See the Why<br><span style="font-weight:500;font-size:12px;color:var(--muted)">Transparent Recommendation</span></h2>
        <div class="field">
          <span class="k">User Action</span>
          <span class="v">Reviews a plain-language breakdown of how the suggested amount was calculated.</span>
        </div>
        <div class="field">
          <span class="k">Internal State</span>
          <span class="v">Shifts from skepticism to trust — she can finally see the math.</span>
        </div>
        <div class="field">
          <span class="k">Pain Point Addressed</span>
          <span class="v">"It just gave me a number... I didn't trust it."</span>
        </div>
        <div class="ab-box">
          <span class="k">Action → Benefit</span>
          Views reasoning behind the number <span class="arrow-sym">→</span> trusts the plan because she understands it.
        </div>
      </div>

      <div class="stage-card s3">
        <div class="stage-badge">3</div>
        <h2 class="stage-name">See the Safety Net<br><span style="font-weight:500;font-size:12px;color:var(--muted)">Consequence-Aware Commitment</span></h2>
        <div class="field">
          <span class="k">User Action</span>
          <span class="v">Views a short "what happens if you miss a payment" explainer before confirming.</span>
        </div>
        <div class="field">
          <span class="k">Internal State</span>
          <span class="v">Relief and control — she knows the real downside, so she isn't guessing.</span>
        </div>
        <div class="field">
          <span class="k">Pain Point Addressed</span>
          <span class="v">"Nobody told me what happens... I just assumed the worst."</span>
        </div>
        <div class="ab-box">
          <span class="k">Action → Benefit</span>
          Previews consequences before committing <span class="arrow-sym">→</span> agrees without fear of the unknown.
        </div>
      </div>

      <div class="stage-card s4">
        <div class="stage-badge">4</div>
        <h2 class="stage-name">Stay on Track Herself<br><span style="font-weight:500;font-size:12px;color:var(--muted)">Adaptive Self-Service</span></h2>
        <div class="field">
          <span class="k">User Action</span>
          <span class="v">Returns mid-plan to adjust the amount or pause a payment when income dips.</span>
        </div>
        <div class="field">
          <span class="k">Internal State</span>
          <span class="v">Empowered — it's still her plan, even when things change.</span>
        </div>
        <div class="field">
          <span class="k">Pain Point Addressed</span>
          <span class="v">The root cause of both escalation and default — no way to self-correct.</span>
        </div>
        <div class="ab-box">
          <span class="k">Action → Benefit</span>
          Adjusts plan herself when income dips <span class="arrow-sym">→</span> keeps the agreement instead of defaulting silently.
        </div>
      </div>

    </div>

    <!-- Competitive advantages -->
    <div class="advantages">
      <h2>3 Competitive Advantages Over the Manual Workaround</h2>
      <p class="sub">Why this future state outperforms stalling, self-estimating, and calling an agent</p>
      <div class="adv-grid">
        <div class="adv-card">
          <div class="adv-num">1</div>
          <h3>Documented, Not Guessed</h3>
          <p>Replaces unaudited mental math with a system-held affordability record Riverty can actually see.</p>
        </div>
        <div class="adv-card">
          <div class="adv-num">2</div>
          <h3>No Call Required</h3>
          <p>Eliminates the call to an agent by answering the two unanswered questions inside the portal itself.</p>
        </div>
        <div class="adv-card">
          <div class="adv-num">3</div>
          <h3>Durable, Not One-Time</h3>
          <p>Turns a one-off "resolved" moment into a self-correcting relationship that survives income shocks.</p>
        </div>
      </div>
    </div>

    <footer>
      Riverty Case Study — BU Collection: A Fair Way Forward · Future State Journey Map
    </footer>

  </div>
</body>
</html>
