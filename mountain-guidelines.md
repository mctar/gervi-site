---
layout: page
title: The Mountain Guidelines for AI
permalink: /mountain-guidelines/
description: Nine guidelines for the terrain of AI, after the Norwegian fjellvettreglene — shaped from practice, not policy.
wide: true
---

<style>
  .mr-eyebrow {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.55rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--crimson);
    margin-bottom: 1.25rem;
  }
  .mr-lede {
    font-family: 'IBM Plex Serif', Georgia, serif;
    font-size: 1.05rem;
    line-height: 1.65;
    color: var(--muted);
    margin: 0 0 2.5rem;
    max-width: 620px;
  }
  .mr-lede em { color: var(--cream); font-style: italic; opacity: 0.9; }

  .mr-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.25rem;
    margin: 0 0 2.5rem;
  }

  .mr-card {
    position: relative;
    border: 1px solid var(--line-hard);
    background: var(--bg-soft);
    padding: 1.75rem 1.75rem 1.5rem 1.75rem;
  }

  .mr-num {
    position: absolute;
    top: 1.4rem;
    left: 1.4rem;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: var(--crimson);
    color: var(--cream);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.04em;
  }

  .mr-card h3 {
    margin: 0 0 0.5rem 2.75rem;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.6rem;
    line-height: 1.05;
    letter-spacing: 0.02em;
    text-transform: uppercase;
    color: var(--cream);
  }

  .mr-lead {
    margin: 0 0 1rem 2.75rem;
    font-family: 'IBM Plex Serif', Georgia, serif;
    font-size: 1rem;
    line-height: 1.6;
    color: var(--cream);
    opacity: 0.85;
  }

  .mr-quote {
    margin: 0 0 1.25rem 2.75rem;
    padding: 0.1rem 0 0.1rem 1rem;
    border-left: 2px solid var(--crimson);
    font-family: 'IBM Plex Serif', Georgia, serif;
    font-size: 0.95rem;
    font-style: italic;
    line-height: 1.6;
    color: var(--muted);
  }

  .mr-compare {
    margin-left: 2.75rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.75rem;
  }

  .mr-box {
    padding: 0.75rem 0.9rem;
    font-family: 'IBM Plex Serif', Georgia, serif;
    font-size: 0.9rem;
    line-height: 1.55;
  }
  .mr-box--dont {
    border-left: 2px solid var(--crimson);
    background: rgba(220, 38, 38, 0.05);
    color: var(--muted);
  }
  .mr-box--do {
    border-left: 2px solid var(--gold);
    background: rgba(201, 168, 76, 0.06);
    color: var(--cream);
  }

  .mr-label {
    display: block;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.5rem;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    margin-bottom: 0.35rem;
  }
  .mr-box--dont .mr-label { color: var(--crimson); }
  .mr-box--do .mr-label { color: var(--gold); }

  .mr-closing {
    margin: 3rem 0 0;
    padding: 1.75rem;
    border: 1px solid var(--line-hard);
    background: var(--bg-soft);
  }
  .mr-closing p {
    font-family: 'IBM Plex Serif', Georgia, serif;
    font-size: 1rem;
    line-height: 1.65;
    color: var(--muted);
    margin: 0 0 0.9rem;
  }
  .mr-closing p:last-child { margin: 0; }
  .mr-closing strong { color: var(--cream); }
  .mr-closing em { color: var(--cream); opacity: 0.9; }

  @media (max-width: 640px) {
    .mr-card { padding: 1.5rem 1.25rem 1.25rem; }
    .mr-num { top: 1.25rem; left: 1.1rem; }
    .mr-card h3,
    .mr-lead,
    .mr-quote,
    .mr-compare { margin-left: 2.4rem; }
    .mr-compare { grid-template-columns: 1fr; }
  }
</style>

<p class="mr-eyebrow">Codified practice · nine guidelines</p>

<p class="mr-lede">After the Norwegian <em>fjellvettreglene</em>, the nine rules Norwegians grow up with — written by people who had been in trouble in the mountains. These are ours for the terrain of AI, shaped the same way: from practice, not policy.</p>

<div class="mr-grid">

  <article class="mr-card">
    <span class="mr-num">1</span>
    <h3>Bring what you have</h3>
    <p class="mr-lead">The more information you give the AI, the better the answer you get. Share everything that's relevant to the task.</p>
    <blockquote class="mr-quote">Think of AI as a person you're asking for help. If you needed someone to help you with this, what would you tell them? You'd explain why, what you want, and what a good result looks like. Do the same here.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Plan a podcast for me.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        Help me plan a podcast for a 17-year-old who wants to start a gaming show, has a 2000 kr budget, and wants the first episode ready in three weeks. The audience is other teenagers.
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">2</span>
    <h3>Give it a role</h3>
    <p class="mr-lead">Ask the AI to act as an expert or specialist in the area you need help with.</p>
    <blockquote class="mr-quote">Like Neo in The Matrix downloading Kung Fu. AI can become whichever expert you need. Just say: "You're a teacher," or "You're a marketing expert."</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Help me with marketing.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        You're an experienced digital marketer. Help me build a marketing strategy for a new app aimed at students.
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">3</span>
    <h3>Ask again</h3>
    <p class="mr-lead">Ask follow-up questions the way you would with a friend. If you're stuck, say so. The AI can go deeper and explain better.</p>
    <blockquote class="mr-quote">You know how this works when you're talking to someone. You don't just take the first answer and walk away. You follow up: "But what if…", "Can you elaborate?", "What do you mean by…?" If you're stuck or the answers are thin, you can ask the AI: "How could I phrase this better?" or "Based on what I've told you, write me a sharper prompt for this."</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Give up after the first weak answer.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        "What if I have a smaller budget?" or "Based on what I've told you about my podcast idea, write me a prompt that will get me more concrete advice."
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">4</span>
    <h3>Talk to several</h3>
    <p class="mr-lead">Use different AIs for what each one is best at. Each has its own strengths and blind spots.</p>
    <blockquote class="mr-quote">Think of it like asking several people for advice on the same problem. They give you different perspectives. Test the same question on different AIs and compare.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Use only one AI for everything.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        Work with several AIs. Learn their strengths and weaknesses, and how it feels to collaborate with each one on different kinds of tasks.
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">5</span>
    <h3>Use all your senses</h3>
    <p class="mr-lead">Upload images. Use your voice. Share links. The AI can work with more than just text.</p>
    <blockquote class="mr-quote">You know how much easier it is to show a picture to explain something? Work with AI the same way. It can handle images, audio, and speech. Most AIs can now see you, listen to you, and talk back.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Rely only on written descriptions.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        Upload a picture that explains. Show it a video. Explain with your voice. Share a file with it.
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">6</span>
    <h3>Start with a conversation</h3>
    <p class="mr-lead">Record yourself thinking out loud about the problem. The AI can pick up where you left off.</p>
    <blockquote class="mr-quote">Like thinking out loud to clear your own head. Talk about what you want to do and record it. The AI can use the recording as a starting point. This is especially useful when you don't know where to begin.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Sit there stuck, staring at an empty prompt.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        Record yourself: "So, I want to start a podcast, but I'm not sure… I like gaming, but is that interesting?" Give the audio to the AI and say, "Help me develop these ideas."
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">7</span>
    <h3>You're the boss. Always check</h3>
    <p class="mr-lead">Think critically about the answers. Ask for sources. You know when someone says, "I read somewhere that…" Do the same with AI.</p>
    <blockquote class="mr-quote">Treat the AI as an advisor. It suggests, you decide. Does the advice actually make sense? Ask, "Where does this come from?" Ask the AI to flag what it's uncertain about. Evaluate critically before you use anything. What you send out is always your responsibility.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Take everything the AI says at face value.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        "That sounds strange. Can you explain how you got there? Do you have sources? Flag anywhere you're uncertain."
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">8</span>
    <h3>Turn back in time. Watch for rabbit holes</h3>
    <p class="mr-lead">Don't get stuck in endless conversations. Set a goal for the session, and know when to stop.</p>
    <blockquote class="mr-quote">Like when you get lost in a long conversation and have to say, "ok wait, let's start over." If you're drowning in information or going in circles with the AI, take a break. There's no shame in restarting with simpler questions.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Get stuck in endless discussions about the details.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        "We've covered the main points I needed. Let me test this first, then I'll come back if I need more help."
      </div>
    </div>
  </article>

  <article class="mr-card">
    <span class="mr-num">9</span>
    <h3>Have fun</h3>
    <p class="mr-lead">AI opens up possibilities you didn't have before. Try wild ideas, and stay creative.</p>
    <blockquote class="mr-quote">AI can help you do things you didn't think were possible. Try creative tasks, experiment with strange ideas, use AI for art, humor, or projects outside your usual work. The best stuff often shows up when you play and push the edges.</blockquote>
    <div class="mr-compare">
      <div class="mr-box mr-box--dont">
        <span class="mr-label">Don't</span>
        Only use AI for what you already know it can do.
      </div>
      <div class="mr-box mr-box--do">
        <span class="mr-label">Do instead</span>
        Test what happens when you give it a sound and ask for a color. Or: "Take a picture of my room and turn it into a place I've never seen before."
      </div>
    </div>
  </article>

</div>

<div class="mr-closing">
  <p><strong>Why these guidelines, and why now.</strong> The <em>fjellvettreglene</em> work because they were written by people with scars. They don't tell you what to think. They tell you what to do when the weather turns. They assume you're competent and treat you like an adult.</p>
  <p>AI has its own weather. The same posture works: short guidelines, easy to remember under pressure, shaped by practice rather than policy.</p>
</div>
