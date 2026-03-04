<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Solana Wallet Customer Insights</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --sol: #9945FF;
    --sol2: #14F195;
    --bg: #0a0a0f;
    --card: #111118;
    --border: #1e1e2e;
    --text: #e8e8f0;
    --muted: #6b6b80;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    padding: 40px 16px 80px;
    background-image: radial-gradient(ellipse 60% 40% at 70% 10%, rgba(153,69,255,0.12) 0%, transparent 70%),
                      radial-gradient(ellipse 40% 30% at 20% 80%, rgba(20,241,149,0.07) 0%, transparent 60%);
  }
  .wrap { max-width: 620px; margin: 0 auto; }
  h1 {
    font-size: clamp(1.6rem, 5vw, 2.4rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    background: linear-gradient(135deg, #fff 30%, var(--sol2));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    margin-bottom: 10px;
  }
  .subtitle {
    color: var(--muted);
    font-size: 0.9rem;
    line-height: 1.6;
    margin-bottom: 36px;
    font-family: 'Space Mono', monospace;
  }
  .section {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    margin-bottom: 20px;
  }
  label.q {
    display: block;
    font-weight: 600;
    font-size: 0.95rem;
    margin-bottom: 14px;
    color: #fff;
  }
  label.q span { color: var(--sol); }
  .opts { display: flex; flex-direction: column; gap: 8px; }
  .opt {
    display: flex; align-items: center; gap: 10px;
    background: #16161f;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 10px 14px;
    cursor: pointer;
    transition: border-color .2s, background .2s;
    font-size: 0.88rem;
  }
  .opt:hover { border-color: var(--sol); background: #1a1a28; }
  .opt input { accent-color: var(--sol); width: 16px; height: 16px; flex-shrink: 0; }
  .opt.sel { border-color: var(--sol2); background: rgba(20,241,149,0.06); }
  .letter {
    width: 22px; height: 22px;
    border-radius: 6px;
    background: var(--border);
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    font-size: 0.7rem;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
  }
  select, input[type=number] {
    width: 100%;
    background: #16161f;
    border: 1px solid var(--border);
    border-radius: 10px;
    color: var(--text);
    font-family: 'Syne', sans-serif;
    font-size: 0.9rem;
    padding: 11px 14px;
    outline: none;
    transition: border-color .2s;
    appearance: none;
  }
  select:focus, input[type=number]:focus { border-color: var(--sol); }
  .grid2 { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
  .submit-btn {
    display: flex; align-items: center; gap: 10px;
    background: linear-gradient(135deg, var(--sol), var(--sol2));
    border: none; border-radius: 12px;
    color: #000; font-family: 'Syne', sans-serif;
    font-size: 1rem; font-weight: 700;
    padding: 14px 32px;
    cursor: pointer;
    margin-top: 8px;
    transition: opacity .2s, transform .15s;
  }
  .submit-btn:hover { opacity: 0.9; transform: translateY(-1px); }
  .tally { text-align: right; color: var(--muted); font-size: 0.75rem; font-family: 'Space Mono', monospace; margin-top: 24px; }
  .tally span { color: var(--sol2); }
</style>
</head>
<body>
<div class="wrap">
  <h1>Solana Wallet Customer Insights</h1>
  <p class="subtitle">We care deeply about building the best self-custody Solana wallet in the world. Help us co-create this vision by answering a few questions about what you really need.</p>

  <!-- Q1 -->
  <div class="section">
    <label class="q">Which self-custody Solana wallets do you regularly use? <span>*</span></label>
    <div class="grid2" id="wallets">
      <label class="opt"><input type="checkbox"><span class="letter">A</span>Solflare</label>
      <label class="opt"><input type="checkbox"><span class="letter">B</span>Phantom wallet</label>
      <label class="opt"><input type="checkbox"><span class="letter">C</span>Trust Wallet</label>
      <label class="opt"><input type="checkbox"><span class="letter">D</span>Ledger Nano X</label>
      <label class="opt"><input type="checkbox"><span class="letter">E</span>Metamask wallet</label>
      <label class="opt"><input type="checkbox"><span class="letter">F</span>I prefer not to say</label>
      <label class="opt"><input type="checkbox"><span class="letter">G</span>Trezor model T</label>
      <label class="opt"><input type="checkbox"><span class="letter">H</span>Exodus wallet</label>
    </div>
  </div>

  <!-- Q2 -->
  <div class="section">
    <label class="q">Which one best describes your main Solana activity? <span>*</span></label>
    <div class="opts" id="activity">
      <label class="opt"><input type="radio" name="act"><span class="letter">A</span>I buy meme coins, flip NFTs, and chase fast gains</label>
      <label class="opt"><input type="radio" name="act"><span class="letter">B</span>I use crypto as a way to move money or get paid</label>
      <label class="opt"><input type="radio" name="act"><span class="letter">C</span>I use crypto to earn yield, trade tokens, and do things in DeFi</label>
      <label class="opt"><input type="radio" name="act"><span class="letter">D</span>I actively farm airdrops, use lots of wallets, and try out new dApps</label>
      <label class="opt"><input type="radio" name="act"><span class="letter">E</span>I buy and hold crypto assets, investing for the long term</label>
      <label class="opt"><input type="radio" name="act"><span class="letter">F</span>I'm new to crypto and just trying to figure things out</label>
    </div>
  </div>

  <!-- Q3 -->
  <div class="section">
    <label class="q">How much risk did you take with your crypto investment? <span>*</span></label>
    <div class="opts" id="risk">
      <label class="opt"><input type="radio" name="risk"><span class="letter">A</span>High risk</label>
      <label class="opt"><input type="radio" name="risk"><span class="letter">B</span>Low risk</label>
    </div>
  </div>

  <!-- Q4 Goal -->
  <div class="section">
    <label class="q">What is your #1 goal with crypto right now on Solana? <span>*</span></label>
    <div class="opts">
      <label class="opt"><input type="checkbox">Find early opportunities (airdrops, alpha, new projects)</label>
      <label class="opt"><input type="checkbox">Send and receive money or payments easily (cross-border, small business)</label>
      <label class="opt"><input type="checkbox">Make fast trades or flip high-risk assets for profit (memecoins, NFTs)</label>
      <label class="opt"><input type="checkbox">Hold crypto securely for savings or diversification (BTC, ETH, stablecoins)</label>
      <label class="opt"><input type="checkbox">Explore DeFi at a beginner level</label>
      <label class="opt"><input type="checkbox">Maximize returns through advanced DeFi (staking, farming, cross-chain trading)</label>
      <label class="opt"><input type="checkbox">Grow my holdings through long-term investing (e.g., DCA)</label>
    </div>
  </div>

  <!-- Q5 Frustrations -->
  <div class="section">
    <label class="q">What are your 3 biggest frustrations with your Solana wallet app? (Pick up to 3) <span>*</span></label>
    <select>
      <option value="">Select up to 3...</option>
      <option>Slow transactions / high fees</option>
      <option>Poor UI/UX</option>
      <option>Security concerns</option>
      <option>Lack of DeFi integrations</option>
      <option>Bad mobile experience</option>
      <option>No multi-wallet support</option>
    </select>
  </div>

  <!-- Q6 Needs -->
  <div class="section">
    <label class="q">What are your top 3 needs from your Solana wallet? <span>*</span></label>
    <div class="opts">
      <label class="opt"><input type="checkbox"><span class="letter">A</span>Scam protection, risk alerts, and wallet safety features</label>
      <label class="opt"><input type="checkbox"><span class="letter">B</span>Reliable low-fee stablecoin transfers and fiat off-ramps</label>
      <label class="opt"><input type="checkbox"><span class="letter">C</span>Simple onboarding, wallet recovery, and educational tools</label>
      <label class="opt"><input type="checkbox"><span class="letter">D</span>Clear transaction tagging (e.g., personal vs business)</label>
      <label class="opt"><input type="checkbox"><span class="letter">E</span>Easy and secure multi-wallet management</label>
      <label class="opt"><input type="checkbox"><span class="letter">F</span>A fast and intuitive experience for buying, swapping, and bridging</label>
    </div>
  </div>

  <!-- Q7 Frequency -->
  <div class="section">
    <label class="q">How often do you use a self-custody wallet like Solana Wallet? <span>*</span></label>
    <div class="opts" id="freq">
      <label class="opt"><input type="radio" name="freq"><span class="letter">A</span>I've never used one</label>
      <label class="opt"><input type="radio" name="freq"><span class="letter">B</span>Weekly</label>
      <label class="opt"><input type="radio" name="freq"><span class="letter">C</span>Daily</label>
      <label class="opt"><input type="radio" name="freq"><span class="letter">D</span>Rarely (Few times a year)</label>
      <label class="opt"><input type="radio" name="freq"><span class="letter">E</span>Monthly</label>
    </div>
  </div>

  <!-- Q8 Years -->
  <div class="section">
    <label class="q">Number of years in crypto <span>*</span></label>
    <select>
      <option>1</option><option selected>2</option><option>3</option>
      <option>4</option><option>5+</option>
    </select>
  </div>

  <button class="submit-btn">Submit →</button>
  <p class="tally">Made with <span>Tally ★</span></p>
</div>

<script>
  // Highlight selected options
  document.querySelectorAll('.opt input').forEach(inp => {
    inp.addEventListener('change', () => {
      if (inp.type === 'radio') {
        document.querySelectorAll(`input[name="${inp.name}"]`).forEach(r => r.closest('.opt').classList.remove('sel'));
      }
      inp.closest('.opt').classList.toggle('sel', inp.checked);
    });
  });
</script>
</body>
</html>
