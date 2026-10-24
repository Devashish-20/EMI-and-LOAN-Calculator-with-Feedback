# LoanSmart Optimizer 💰
### Smart Loan & EMI Calculator with Health Feedback & Repayment Optimization

A full-stack Node.js + React web application designed to help borrowers understand the true cost of their loans. It calculates monthly EMI, reveals the exact extra interest paid over time, delivers an intelligent **"Good or Bad Loan?"** health evaluation score, and simulates high-impact repayment strategies to save money and cut years off the loan.

---

## 🌟 Key Features

1. **Precision EMI & Extra Cost Calculator**:
   - Computes standard monthly EMI using monthly compounding formulas.
   - Highlights the **"Extra Money Paid"**: Total Interest and the Extra Cost Ratio ($\frac{\text{Total Interest}}{\text{Principal}} \times 100\%$).
   - Multi-currency support: ₹ INR (with Lakh/Crore compact notation), $ USD, € EUR, £ GBP.
   - 1-click presets: Home Loan, Car Loan, Personal Loan, Education Loan.

2. **Intelligent Loan Health & Feedback Engine ("Is it Good or Bad?")**:
   - **Financial Health Score (0 - 100)**:
     - **Interest Rate Tier**: Prime (<8.5%), Standard (8.5–11%), High (11–15%), Very High/Predatory (>15%).
     - **Extra Interest Drag**: Flags when interest starts consuming 50% or over 100% of the original loan.
     - **Tenure Drag**: Warns when lengthy tenures (20–30 years) secretly compound into massive bank profits.
   - **Verdicts**: *Great Loan (Healthy)*, *Good / Reasonable*, *Fair / Moderate Drag*, *Costly Loan*, or *Poor / High-Risk*.
   - **Transparency**: Detailed bullet points explaining the strengths, risks, and red flags of the loan.

3. **Smarter Repayment Strategies ("Better Options")**:
   - **Shorten Tenure**: Demonstrates how reducing tenure by 2–3 years drastically reduces compounding interest.
   - **Pay +10% Extra Monthly EMI**: Calculates how adding just 10% each month cuts debt duration.
   - **1 Extra EMI Every Year**: Models putting an annual bonus toward a 13th EMI every year.
   - **Refinance / Lower Rate**: Simulates negotiating or transferring balance to a 1.5% lower interest rate.
   - Direct *"Simulate this option"* buttons that update the calculator instantly.

4. **Interactive Visualizations & Amortization Schedule**:
   - **Donut Chart**: Principal vs Extra Interest breakdown.
   - **Yearly Trajectory Chart**: Principal paid vs Interest paid year-by-year.
   - **Amortization Table**: Full year-by-year schedule with expandable monthly drilldowns and payoff progress bars.
   - **CSV Export & Print**: One-click download of the complete repayment table.

---

## 🚀 Quick Start

### 1. Prerequisites
- Node.js (v18+ recommended)
- npm

### 2. Run in Development Mode
Starts both the Express API (port 5000) and the Vite React frontend (port 5173 with proxy) simultaneously:
```bash
npm run dev
```
Open [http://localhost:5173](http://localhost:5173) in your browser.

### 3. Build & Run for Production
Builds the React frontend and serves everything from the Express backend:
```bash
npm run build
npm start
```
Open [http://localhost:5000](http://localhost:5000) in your browser.

---

## 📡 Backend API Endpoints

- `GET /api/health`: Health status of the backend API.
- `POST /api/calculate`: Primary calculation endpoint.
  - **Request Body**:
    ```json
    {
      "principal": 5000000,
      "annualRate": 8.5,
      "tenureYears": 20,
      "tenureMonths": 0
    }
    ```
  - **Response**:
    - `summary`: Monthly EMI, total payment, total interest, extra percentage.
    - `health`: Health score (0-100), verdict, badges, pros, cons, and warnings.
    - `betterOptions`: 4 optimized repayment strategies with savings and tenure reduction.
    - `amortization`: Yearly and monthly schedule breakdown.

---

## 🛠️ Tech Stack
- **Backend**: Node.js, Express, CORS
- **Frontend**: React 19, Vite, Tailwind CSS v4, Lucide Icons, Chart.js, react-chartjs-2
