# Challenge: Comprehensive Deal Management API with Investment and Pricing Plan

_Keep in mind this is an over-simplified part of the product that we've built at Odin_ 😄

_Please, reach out in case you have any question!_

# Problem Statement:

Your task is to develop a robust API for handling investment deals, involving calculation based on a pricing plan.

### Price Plan:

A price plan is associated with each deal and includes the following attributes:

- **ID**: A required unique identifier for the price plan.
- **Percentage**: A required percentage to be deducted from each investment.
- **Floor**: A required minimum amount deducted from each investment, used when the percentage is too low.
- **Cap**: A required maximum amount deducted from each investment, used when the percentage is too high.

### Deal:

A deal possesses the following attributes:

- **ID**: A required unique identifier for the deal.
- **Name**: A required field, between 5 to 25 characters.
- **Description**: An optional field, between 5 to 150 characters if provided.
- **Price Plan ID**: A required field representing the associated price plan.
- **Allocation**: A required field specifying the amount of money the deal aims to raise, denominated in US dollars or UK pounds.
- **Status**: A required field indicating the deal's status, with accepted values: draft, live, closed. Note: No investments can be made if the deal is in draft or closed status.

### Investment:

An investment is characterised by:

- **ID**: A required unique identifier for the investment.
- **Amount**: A required field specifying the invested amount, Note: Must be in the same currency as the deal.
- **Investor Email**: A required unique reference used to identify the investor for each deal.

To fulfil the functionality requirements for deal management API, the following behaviour are expected to be implemented behind an HTTP server (feel free to use REST/GraphQL/whatever):

1. Retrieve a list of deals filtered by status.
2. Retrieve details of a specific deal by its ID.
3. Create a new **draft** deal.
4. Add/change data of a **draft** deal.
5. Move a draft deal to **live** status. Once live, the information cannot be modified, and investors can begin making investments.
6. Invest in a deal.
7. Move a draft deal to **closed** status. This endpoint calculates and exposes the net investment amount for each investor, considering the price plan (% fee, floor, cap), and associated fees. It also stores the remaining allocation amount after each investment, net of the price plan, in the deal's details.

# Expectations:

- **Validation and Edge Cases**: Keep in mind the consumer of those APIs, implement strong validation to ensure that inputs conform to the problem context, and handle edge cases and errors gracefully. (Hint: attention to details is a must for Odin!)
- **Correctness and Simplicity**: Prioritise correctness in your implementation, ensuring that each component functions as intended. Additionally, emphasise simplicity in your design, avoiding unnecessary complexity that could introduce bugs or make the system challenging to understand. (Hint: we always test our code!)
- **Code Style**: Follow idiomatic code practices for Go. Ensure that your code is clean, readable, and well-organised. Consistent packaging and naming conventions alongside a well-though  structure contribute to maintainability. (Hint: Go std-lib is your friend!)
- **Documentation**: Write a clear documentation to guide developers through your code. Explain the purpose of each design choice and any assumptions made during the implementation.  Please, write down any considerations you made regarding the scalability of your solution. Address potential bottlenecks and suggest strategies for handling increased load or data volume. (Hint: we communicate a lot asynchronously, this is a good chance to show us how good you are at it!)

# **Getting Started:**

You can fork this repo and use the fork as a basis for your project.

Get back to us with a timeline for when you expect to complete the challenge. We appreciate your transparency and proactive communication throughout the process.
