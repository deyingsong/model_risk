# Chapter 1 An Overview of Financial Planning and Modeling

## Summary (TLDR)

Financial planning is the specification of future decisions and actions to reach a stated goal, while a financial model is a deliberately simplified system of verbal or mathematical relationships linking the firm's environment, decisions, constraints, and objectives. For daily model risk management, the chapter's central lesson is that a model must begin with a clearly defined decision problem, objective, intended user, planning horizon, and minimum useful output rather than with available data or computational capability. The modeler should enumerate decision alternatives broadly, express how each decision reaches the objective, and identify company, industry, economic, legal, technological, and resource constraints. Structural input, including equations, variables, constraints, and objective functions, should be separated from data input, including current conditions, estimated parameters, and forecasts, so assumptions can be challenged and changed without altering model logic. Model detail should be limited to what improves the decision because excessive cross-sectional or time-series detail can obscure relationships, overwhelm users, and increase cost. Simulation explains what may happen under specified decisions but leaves ranking to the user, whereas optimization selects the best feasible decision but requires an explicit objective and constraints. Forecast uncertainty, parameter estimation, data-model congruence, decision-useful output, and managerial understanding should therefore be central validation concerns.

## Table of Contents

- [What Is Planning?](#what-is-planning)
- [What Is Financial Planning?](#what-is-financial-planning)
- [The Input to Financial Planning](#the-input-to-financial-planning)
  - [The Goals of Financial Decisions](#the-goals-of-financial-decisions)
  - [The Decision Alternatives](#the-decision-alternatives)
  - [The Links between Decisions and Goals](#the-links-between-decisions-and-goals)
  - [Resources and Constraints](#resources-and-constraints)
  - [The Planning Horizon and the Amount of Detail](#the-planning-horizon-and-the-amount-of-detail)
- [Ingredients of a Financial Model](#ingredients-of-a-financial-model)
  - [What Is a Model?](#what-is-a-model)
  - [What Does a Model Do?](#what-does-a-model-do)
- [How to Develop the Model](#how-to-develop-the-model)
  - [The Decision Problem](#the-decision-problem)
  - [The Output](#the-output)
  - [The Structural Input](#the-structural-input)
  - [The Data Input](#the-data-input)
- [Types of Models](#types-of-models)
  - [Simulation](#simulation)
  - [Optimization](#optimization)
- [What Do We Get Out of the Modeling Process?](#what-do-we-get-out-of-the-modeling-process)
  - [Explicit Benefits](#explicit-benefits)
  - [Implicit Benefits](#implicit-benefits)

## What Is Planning?

- **Broad definition of planning:** Planning is the specification of future decisions and actions to reach a stated goal, or simply deciding what you are going to do to get where you want to go.
- **Plan should specify the objectives and the actions:** Whether complex and detailed or broad and simple, a plan should specify the objectives and the actions that lead to those objectives while allowing for uncertainty.
- **Criteria for judging progress:** Once the primary objective is set, the planner must specify signposts or standards, such as return on assets, profit margin, and asset turnover, for measuring progress toward it.
- **Link between decision and objective:** Defining how a decision affects progress toward the objective is often the primary source of planning complexity because relationships between management's actions and the objective are usually complex and poorly understood.

## What Is Financial Planning?

- **Financial planning is concerned with:** Financial planning sets objectives for future investment and financing decisions, judges the effects of alternatives on progress toward those objectives, and selects the investment or financing alternatives to undertake.
- **Enormous range of problems:** Financial planning ranges from detailed working-capital decisions over a day or week to broad strategic investment and expansion plans over a decade.

## The Input to Financial Planning

- **Necessary ingredients:** A complete financial plan requires the goal, decision alternatives, the link between decisions and the goal, resources and constraints, and the planning horizon and desired amount of detail.
- **The goal:** The goal specifies the destination that future financial decisions and actions are intended to reach.
- **The decision alternatives:** Decision alternatives enumerate the possible routes or actions available for reaching the goal.
- **The link between the decisions and the goal:** The decision-goal link shows whether and how each prospective action contributes to the desired objective.
- **The resources for implementing the decisions and constraints inhibiting goal attainment:** Resources make prospective decisions possible, while their limits and other constraints restrict what can be accomplished.
- **The planning horizon and the desired amount of planning detail:** The planner must choose both how far into the future the plan applies and how specifically its decisions, timing, and results are represented.

### The Goals of Financial Decisions

- **Maximize the value of the firm's equity shares:** The generally accepted objective for investment and financing decisions is to choose alternatives that make the market price of the firm's equity shares as high as possible.
- **Arguments supporting this position:** Share-value maximization reflects management's fiduciary duty to stockholders, makes all stockholders wealthier, and promotes the efficient use and social allocation of resources, while additional goals can be treated as constraints.

### The Decision Alternatives

- **Overlooked:** Managers frequently overlook decision alternatives by asking what will happen if they make a particular decision instead of asking which possible decision will maximize stockholder wealth.
- **Comprehensive list:** The planner should brainstorm a list as comprehensive as possible, ranging from doing nothing to actions that initially appear infeasible or counterproductive, before eliminating possibilities.

### The Links between Decisions and Goals

- **Valuation model:** A valuation model supplies the necessary link from prospective investment and financing decisions to the hypothetical value of the firm and its stock.
- **Operational terms:** A problem's objective may be stated in operational terms consistent with share-price maximization, such as maximizing net present value for capital budgeting or minimizing the weighted average cost of capital for financing mix decisions.

### Resources and Constraints

- **Factors that will be available to assist in attaining the goal:** Resources are positive factors available to help attain the goal, while constraints limit the firm's actions or goal attainment, although limited resources also act as constraints.
- **Classification:** Present and future resources and constraints are classified as company-specific, industry-specific, related to the economy as a whole, or influenced by the legal and political environment.
- **Company-specific:** Company-specific resources and constraints describe the firm's present condition and the base from which it will develop and build in the future.
- **Company-specific - balance sheet:** The balance sheet describes assets that provide resources but limit activity when scarce and liabilities that constrain future actions through promised payments.
- **Company-specific - production technology:** Production technology determines attainable output, required inputs, costs, profit margins, operating leverage, break-even point, and business risk.
- **Company-specific - sources of supply:** Established suppliers are resources, while interrupted or limited supplies create risk, constrain production, affect the input mix, and influence profitability.
- **Company-specific - labor and management:** Labor and management are major resources whose availability, reliability, productivity, strength, ambition, and creativity determine whether plans can be carried out and adapted to surprises.
- **Company-specific - products:** The firm's product mix, product uniqueness, patents, and future product prospects must be evaluated in relation to its industry and market.
- **Industry-specific:** Industry-specific conditions usually constrain goal attainment, although industry growth opportunities may serve as a resource.
- **Industry-specific - demand:** Forecast future demand is usually the most important planning input because the sales forecast drives most other forecasts and industry sales limit the total market available to firms.
- **Industry-specific - industry structure:** The number and competitiveness of firms, industry concentration, patents, licenses, returns to scale, marketing, and distribution constrain company sales, pricing, and market share.
- **Related to the economy as a whole:** A firm's fortunes and risk depend to varying degrees on local, national, and international economic conditions, making forecasts of general or specialized economic variables important planning inputs.
- **Influenced by the legal and political environment:** Government rules, political realities, social demands, upheavals, expropriations, devaluations, and exchange-rate fluctuations constrain actions and may alter their results.

### The Planning Horizon and the Amount of Detail

- **Length:** The planning horizon is the length of time over which the plan applies, and its choice affects the plan's results, usefulness, development cost, effort, and detail.
- **Planning horizon sufficiently long to show the full effects of the decision over a full cycle:** As a general rule, the horizon should be long enough to show the full effects of a decision over a full relevant cycle.
- **Division of the planning horizon into sub-periods:** The nature and timing of the decision should determine whether the horizon is divided into daily, weekly, monthly, quarterly, annual, or other sub-periods.
- **Amount of detail:** Information and detail should be balanced against their cost and effort because computers can easily produce more detail than is meaningful or evaluable.
- **How much detail is useful:** Detail should be minimized to the level sufficient to help the analyst understand and decide on the problem because excessive detail can overwhelm the user and obscure links among decisions, results, and objectives.
- **Cross-sectional detail and time-series detail:** Cross-sectional detail is the amount of data, variables, and decisions for a given period, while time-series detail is the amount considered at different points in time.
- **Length of the planning horizon should be limited to the horizon of reasonable forecasts:** A plan dependent on forecasts should not extend beyond the period over which reasonable forecasts can be made, although broad long-term trend forecasts may support longer horizons with less frequent sub-periods.

## Ingredients of a Financial Model

### What Is a Model?

- **Definition:** A financial model is a set of verbal or mathematical statements expressing the system of relations and links between the firm's environment, its decisions and actions, and its objectives.
- **Parameters:** Parameters are constants in equations that operate on variables and usually estimate economic behavior or technological relationships, as in the general demand function $Units\ Sold = a + b \times Price\ per\ Unit$, where $Units\ Sold$ is quantity demanded, $Price\ per\ Unit$ is the decision variable, $a$ is the intercept, and $b$ is the estimated response of demand to price.
- **Two tasks:** The model builder must determine the general form of the relationships and estimate the parameter values, preferably by identifying the best structural form and using historical data.
- **Financial models made up of variables, equations, and parameters:** A simple financial model links the decision to the objective through variables, equations, and parameters, as in $Total\ Revenue_t = Units\ Sold_t \times Price\ per\ Unit_t$ and $Units\ Sold_t = 500 - 30 \times Price\ per\ Unit_t$, where $t$ is the time period, $Price\ per\ Unit_t$ is management's decision variable, $Units\ Sold_t$ is demand, $Total\ Revenue_t$ is the objective output, $500$ is demand at a zero price, and $30$ is the reduction in units demanded for each one-dollar price increase.

### What Does a Model Do?

- **Testing platform:** As a small copy of the firm, a financial model lets managers assess prospective decisions before implementation and avoid experimenting on the firm itself.
- **Traces through the complex financial relationship:** A financial model traces complex relationships among financial variables to reveal the direction and magnitude of a decision's effects and provide information that improves decision making.

## How to Develop the Model

### The Decision Problem

- **What is the problem:** The model must be at least as broad as the thoroughly assessed decision problem so it can analyze every important facet and reasonable decision alternative.
- **What questions must be answered:** The model builder should enumerate the questions whose answers suggest the solution because those questions define the model's structure, focal variables, and required output.
- **What is the time horizon of the problem:** The length of the planning horizon and its sub-periods should be consistent with the timing and duration of the decisions and their consequences.
- **How important is the problem:** The problem's importance to the firm's goals and survival should determine the time, effort, and expense committed to model development, with an unimportant problem handled by a scaled-down model when possible.

### The Output

- **What kind of information is needed:** The model should generate the specific information needed to answer the decision questions, rather than mountains of output that do not help the planner make a better decision.
- **How will the information be evaluated:** The planner should decide in advance how alternatives will be ranked and design output that relates each decision's effects to the firm's objectives.
- **What kind of detail is necessary:** The model should produce no less than the smallest amount of detail needed to make the decision and no more than the point at which additional detail no longer changes the decision.
- **Who will use the information:** Output type and format should suit its audience, with detailed data for analysts and consolidated, quickly grasped summaries for executives.

### The Structural Input

- **What is the goal:** Most models should have an objective function or summary output representing the goal, such as $Total\ Revenue_t = Units\ Sold_t \times Price\ per\ Unit_t$, where $Total\ Revenue_t$ is the result to maximize and the other quantities determine it.
- **What are the decision alternatives:** Decision variables representing the possible choices should be clearly specified and easy to manipulate, such as $Price\ per\ Unit_t$ in the sales model.
- **What are the linkages between the decisions and the goal:** The whole model should feed decision variables through linked equations into the objective function, as $Price\ per\ Unit_t$ affects $Units\ Sold_t = a - b \times Price\ per\ Unit_t$ and then $Total\ Revenue_t = Units\ Sold_t \times Price\ per\ Unit_t$, where $a$ is base demand and $b$ is the positive magnitude of demand's price response.
- **What are the constraints:** Constraints are equations or inequalities arising from definitions, industry and economic conditions, technology, resources, or law that limit choices over decision variables.
- **Definitional constraints:** Definitional equations maintain model consistency, aggregate accounts, and link periods, as in $Total\ Assets_t = Current\ Assets_t + Fixed\ Assets_t$ and $Earned\ Surplus_t = Earned\ Surplus_{t-1} + Retained\ Earnings_t$, where the first identity aggregates assets and the second rolls earned surplus from the prior period into period $t$.
- **Constraints from the industry and economy:** Industry and economic conditions can constrain decisions through a demand function and explicit restrictions such as $Price\ per\ Unit_t \geq 0$, which prevents the model from selecting a negative price.
- **Technological constraints:** A production function such as $Units\ Produced_t = 5 \times Labor_t^{0.33} \times Capital_t^{0.67}$ limits output for a given endowment, where $Units\ Produced_t$ is maximum period-$t$ output, $Labor_t$ and $Capital_t$ are inputs, $5$ is a productivity parameter, and $0.33$ and $0.67$ are output elasticities.
- **Resource constraints:** Available resources impose inequalities such as $Capital_t \leq 40$ and $Labor_t \leq 60$, which allow the firm to use less than the available 40 units of capital and 60 units of labor but prohibit using more.
- **What is the planning horizon:** The horizon length and number of sub-periods are structural inputs that determine the number of equations and variables, the volume of output, and the model's complexity.

### The Data Input

- **The current state of the system:** The current state is the firm's and environment's starting condition, including present resources and constraints, from which its projected trajectory evolves.
- **Internal data - the firm:** Financial statements and data on productive capacity, supply, labor, management, and products describe the firm's initial condition, and the model's required detail must match the detail available in the data.
- **External data:** External data describe current operating-environment conditions such as interest rates, stock prices, and prices of goods and labor.
- **Relations between variables:** Unknown relationships can be modeled and estimated from historical data, as in $Accounts\ Receivable_t = a + b_1 Sales_{t-1} + b_2 Sales_{t-2} + b_3 Sales_{t-3}$, where $Accounts\ Receivable_t$ is the current balance, $Sales_{t-i}$ is sales lagged $i$ periods, $a$ is the intercept, and each $b_i$ measures the effect of a sales lag estimated by least squares.
- **Forecasts of future conditions:** Forecasts are essential inputs for dealing with future uncertainty, so modelers should remain skeptical of forecast accuracy and assess how forecast errors affect the plan and goal attainment.

## Types of Models

### Simulation

- **Links the prospective decision to the hypothetical results:** A simulation model combines specified decisions with the current state and forecasts of future conditions to generate the hypothetical consequences and projected future state.
- **Does not tell which decision is best:** Simulation answers what will happen under a user-specified decision but leaves evaluation and selection of the best strategy to the user.
- **Advantages over optimization models:** Simulation models are usually easier to develop, solve, understand, and accept, and managers may better support decisions they make themselves from simulated consequences.
- **Problem 1 - too much output overwhelming user:** Simulation can generate so much detailed output across periods and alternatives that users become unable to evaluate results or determine the best decision.
- **Problem 2 - fail to specify the criteria necessary for determining the best decision:** Simulation users may generate detailed financial statements without criteria for resolving trade-offs and ranking alternatives.
- **Objective function helps a bit:** Adding an objective function helps rank simulated alternatives, but the number of decision combinations can remain too large to inspect efficiently, as $15^{10} = 5.77 \times 10^{11}$ combinations result from ten decision variables with fifteen possible values each.

### Optimization

- **Expression representing goal and constraints:** An optimization model adds to a simulation model an expression representing the decision goal and equations or inequalities constraining the choices.
- **Objective function:** The objective function is an equation portraying how decision variables influence the quantity the user wants to maximize or minimize.
- **Decision variables:** Decision variables represent choices available to the decision maker, such as inventory investment, borrowing, and new shares issued.
- **Constraints:** Constraints are equations or inequalities expressing limitations or sub-goals that prevent the model from making the objective arbitrarily large or small.
- **Two advantages over simulation:** Optimization forces the user to clarify and state objectives and relieves the user of searching through a mountain of simulated results to identify the best feasible decision.

## What Do We Get Out of the Modeling Process?

### Explicit Benefits

- **Test ideas and decisions:** Modeling lets management experiment with decisions before implementation, anticipate their results, and understand how they relate to overall objectives.
- **Plan helps:** A well-documented plan enables post-implementation review and analysis to identify where triumphs and mistakes occurred.
- **Ease of exploring decision alternatives:** Easy exploration of alternatives gives managers more time to consider broader issues such as defining, setting, and evaluating policies.

### Implicit Benefits

- **Force planner to systematize thoughts:** The planning process forces the planner to systematize objectives, decisions, assumptions, alternatives, and interactions within the firm and between variables.
- **Force the planner to think carefully:** Building a model compels careful thought about complex financial relationships, measures of progress, consistency among business units, and the basic objectives of the firm.
- **Mind the costs:** Modeling and planning consume software, staff time, effort, and money, and their net payoff is difficult to measure because the counterfactual decisions without the process are unknown.
