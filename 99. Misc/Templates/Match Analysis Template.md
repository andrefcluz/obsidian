<%*
const date = tp.date.now("YYYY-MM-DD");
const id = await tp.system.prompt("Enter bet sequence number (e.g., 01):");
const home = await tp.system.prompt("Enter Home Team:");
const away = await tp.system.prompt("Enter Away Team:");
const comp = await tp.system.prompt("Enter Competition:");
const title = `${date}_${id} - ${home} x ${away}`;
tp.file.rename(title);
%>---
date: <% `${date}` %>
bet_id: <% `${tp.date.now("YYYYMMDD")}_${id}` %>
league: <% `"${comp}"` %>
home_team: <% `"${home}"` %>
away_team: <% `"${away}"` %>
market: 
odds: 
stake_units:     # In units (1 unit = 1% of bankroll)
bankroll_before: 
profit_units:
bankroll_after:   # Fill after result
result: pending # win / lose / pending
---
# 📝 Bet Log — Over X.5 Goals

## Match Details 

- **League:** <% `${comp}` %>
- **Home Team:** <% `${home}` %>
- **Away Team:**  <% `${away}` %>
- **Date/Time:** 
- **Market:** 
- **Result:** 

---

## 📊 1. Statistical Trends

- **Last 10 Matches (Combined Teams):**
    - Avg. Goals per Match:
    - % of Matches Over X.5 Goals:
- **Home Team (Last 5 Home Games):**
    - Avg. Goals Scored:
    - Avg. Goals Conceded:
- **Away Team (Last 5 Away Games):**
    - Avg. Goals Scored:
    - Avg. Goals Conceded:
- **Head-to-Head (Last 3 Matches):**
    - Avg. Goals per Match: 
    - Over X.5 Goals in: X/3 Matches: 

---

## ⚙️ 2. Style of Play

- **Are both teams attack-minded? (Y/N):**
- **Are both teams defensively weak/leaky? (Y/N):**
- **Expected Lineups Confirmed? (Y/N):**
- **Key Injuries/Suspensions that affect defense/offense?:**

---

## 🧠 3. Motivation & Context

- **Match Importance (Must-win, Relaxed, Mid-table):**
- **Weather Conditions (Rain, Wind, Good Pitch?):**
- **Other Factors (Derby match, player fatigue, recent scandals, etc.):**

---

## 💰 4. Odds & Market Value

- **Current Odds for Over X.5 Goals:**
- **Implied Probability (convert odds to %):**
- **Do you believe this line offers value? (Y/N):**
- **Bookie Odds vs Your Expected % Difference:**

---

## ✅ 5. Betting Decision

- **Bet? (Yes / No):**
- **Stake Size (Units / % of Bankroll):**
- **Reason for Bet/Pass (Short Justification):**

---

## 🧘 6. Emotional Check

- **Am I placing this bet emotionally or out of tilt? (Y/N):**
- **If this bet loses, do I have a stop-loss limit for today? (Y/N):**

---

## ➡️ End-of-Day Recap (Optional)

- **Planned Bets vs Actual Bets:**
- **Did I stick to the pre-planned bets? (Y/N):**
- **Notes on Discipline & Emotional Control:**

---
