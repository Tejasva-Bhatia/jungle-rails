# Jungle

A mini e-commerce application built with Rails 6.1 for purposes of learning Rails.

## Project Description

This project aims to:

- Become familiar with Ruby and the Rails framework.
- Learn how to navigate an existing codebase.
- Use existing code style and approach to implement new features in unfamiliar territory.
- Apply previous learning tactics to research and become familiar with a new paradigm, language, and framework.
- Simulate real-world scenarios where feature and bug-fix requests are listed instead of step-by-step instructions.

## Product Screenshots
![Jungle Landing Page](https://github.com/Tejasva-Bhatia/jungle-rails/blob/master/public/images/Jungle-Landing-Page.png?raw=true)

----------------------------------------------------------------------------------------------------------------------------

![Jungle Products](https://github.com/Tejasva-Bhatia/jungle-rails/blob/master/public/images/Jungle-Products.png?raw=true)


## Completed Features and Fixes in this Project

### Feature: Sold Out Badge
- **Major:** Display a sold out badge on the product list page when a product has 0 quantity.
- **Minor:** Implement as a question/boolean method in view helper and/or Product model.

### Feature: Admin Categories
- **Major:** Admin users can list and create new categories.
- **Major:** Admins can add new products using the new category.
- **Major:** Use restful routes (resources) with no extra, unused routes exposed.
- **Bonus:** All admin controllers should inherit from `Admin::BaseController` or similarly named abstract controller, containing the authentication filter.

### Feature: User Authentication
- **Major:** Visitors can access the registration page from any page to create an account.
- **Major:** Visitors can sign up with email, password, first name, and last name.
- **Major:** Visitors can sign in using email and password.
- **Major:** Users can log out from any page.
- **Major:** Users cannot sign up with an existing email address (uniqueness validation).
- **Major:** Passwords are not stored as plain text; `has_secure_password` is used in the User model with bcrypt gem.

### Enhancement: Order Details Page
- **Major:** The order page displays items, their image, name, description, quantities, and line item totals.
- **Major:** Display the final amount for the order.
- **Minor:** Display the email used to place the order.
- **Minor:** Visitors can place an order without logging in (preserving original functionality).

### Bug: Missing Admin Security
- **Major:** Users must enter HTTP auth login/password to access admin functionality.
- **Bonus:** Implement in an abstract top-level class for admin controllers (e.g., `Admin::BaseController`).

### Bug: Checking Out with Empty Cart
- **Major:** When the cart is empty and the user goes to the `carts#show` page, display a friendly message about the empty cart and link to the home page instead of showing cart contents and a Stripe checkout button.

## Setup

1. Run `bundle install` to install dependencies
2. Create `config/database.yml` by copying `config/database.example.yml`
3. Create `config/secrets.yml` by copying `config/secrets.example.yml`
4. Run `bin/rails db:reset` to create, load and seed db
5. Create .env file based on .env.example
6. Sign up for a Stripe account
7. Put Stripe (test) keys into appropriate .env vars
8. Run `bin/rails s -b 0.0.0.0` to start the server

## Database

If Rails is complaining about authentication to the database, uncomment the user and password fields from `config/database.yml` in the development and test sections, and replace if necessary the user and password `development` to an existing database user.

## Stripe Testing

Use Credit Card # 4111 1111 1111 1111 for testing success scenarios.

More information in their docs: <https://stripe.com/docs/testing#cards>

## Dependencies

- Rails 6.1 [Rails Guide](http://guides.rubyonrails.org/v6.1/)
- Bootstrap 5
- PostgreSQL 9.x
- Stripe
