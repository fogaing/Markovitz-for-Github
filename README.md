# Portfolio Optimization using Historical Volatility

This project demonstrates a portfolio optimization strategy using historical volatility to minimize portfolio risk while adhering to predefined constraints. The method utilizes historical market data to compute the covariance matrix and optimize the portfolio weights accordingly.

## Overview
The optimization process involves solving the following quadratic programming problem:

$$
\begin{aligned}
    &\underset{\mathbf{w}}{\text{minimize}} & & \mathbf{w}^T \Sigma \mathbf{w} \\
    &\text{subject to} & & \sum_{j=1}^{n} w_j = 1 \\
    & & & w_j \geq 0, \quad j = 1, \ldots, N \\
    & & & w_j \leq 0.10, \quad j = 1, \ldots, N \\
    & & & w_j \geq 0.02, \quad j = 1, \ldots, N
\end{aligned}
$$

### Key Concepts
1. **Historical Volatility:** The optimization leverages historical price data to compute the covariance matrix (\( \Sigma \)) of asset returns, which represents the interdependencies and variances of the assets in the portfolio.
2. **Portfolio Weights (\( \mathbf{w} \)):** The weights represent the proportion of the total portfolio allocated to each asset.
3. **Risk Minimization:** The objective is to minimize the portfolio's overall risk (variance) while adhering to allocation constraints.

### Constraints
- The sum of all portfolio weights must equal 1.
- Each asset's weight must be at least 2% of the portfolio.
- Each asset's weight cannot exceed 10% of the portfolio.
- All weights must be non-negative.

## Implementation

### Steps
1. **Data Collection:**
   - Historical price data for the selected portfolio assets is downloaded using `yfinance`.
   - Foreign exchange rates are retrieved to ensure all asset prices are converted to a common currency (EUR).

2. **Covariance Matrix Calculation:**
   - The covariance matrix of historical returns is computed to capture the relationships between asset volatilities.

3. **Optimization:**
   - A quadratic programming solver is used to find the optimal weights that minimize portfolio variance while satisfying the constraints.

4. **Portfolio Value Calculation:**
   - The final portfolio value is computed based on the last available prices and optimized weights.

### Dependencies
- Python 3.x
- `numpy`
- `pandas`
- `yfinance`
- `scipy`

### Usage
1. Clone the repository:
   ```bash
   git clone <https://github.com/fogaing/Markovitz-for-Github>
   ```
2. Run the script:
   ```bash
   python minimum_Volatility.py
   ```

## Results
The output includes:
- Optimized portfolio weights.
- Total portfolio value in EUR.
- Risk minimization achieved through historical volatility.

## File Structure
- `minimum_Volatility.py`: Main script for portfolio optimization.
- `README.md`: Project documentation.

## Future Improvements
- Extend the model to incorporate expected returns for mean-variance optimization.
- Allow dynamic constraints based on user input.
- Explore the impact of different look-back periods for historical volatility calculations.

## License
This project is licensed under the MIT License.

## Contact
For questions or suggestions, feel free to contact me.
