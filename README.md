# fanime-www
Tooling around with a Symfony2-based redone version of fanime.com and its supporting features.

# Scope
The fanime-* repositories are each designed for a specific purpose. While the entire set isn't foreseen as constructing
a major application, as more major features are designed they will be added as microservices under the fanime-* namespace.

This project is specifically focused on defining the user-facing website and will experiment with providing a means for 
non-developers to add static pages through a CMS interface using the [Symfony CMF project](http://cmf.symfony.com/).

Specific features:
* Registration flows (excluding payment processing)
* Registration management (for post-registration)
* Email server integration for notifications
* Static pages for FAQs, Fanime information, and other such pages
* An admin-only CMS portal for modifying event pages
* Integration with Twitter, other social feeds
* Link to a Wordpress or other such application for news posts

## Overall Design Philosophy
This project isn't built to reinvent the wheel on any of these major types of functionality. Wherever appropriate, external
services will be used for common functions like news, email, and payment handling. This project is all about keeping it
simple for users to sign up and for developers and administrators to maintain without headaches. 

### Some specific development guidelines
* **Keep it simple**
* Keep it cohesive
* Your services should be unit-testable, and your user flows tested with [Behat scenarios](http://behat.org/en/latest/quick_start.html)
* Separate concerns: your controller code should not have business logic, your twigs should just represent data, and anything
more interesting belongs in a service
* Your forms should be defined as Symfony forms with front-end AND back-end validation because users do dumb (and sometimes
naughty) things
* Don't use whatever new fancy library you find just because it's cool; most of what this project is responsible for doesn't
need that, so just pick what you need and what you know will continue to be supported
* Focus on response optimization, but not before making sure it works and is tested
* If it's in master, all tests should be passing
    * If tests are not passing, roll forward

### Product design priority
1. Ease of registration
2. Mobile-first design
3. Quick page-load times
4. Secure user interactions

# Contributing
* Read the above guidelines
* Get your local environment up and running with all the project dependencies by cloning the [Fanime Dev VM(https://github.com/oopu/fanime-vm)
    * Still a WIP! ;_;
* Use local draft branches however you like, but create pull requests for specific issues on the project in the below format
* The master branch is locked, so submit your pull requests and assign it to **oopu** for review and merges.
 Run your tests first!
* Anyone can submit an issue to the project, but keep your issues focused on deliverables and mindful of the design priorities above

## Getting Started
TBD!

## Git commit message example
``````
  Adds a registration FAQ page
  
  Issue: GH-9
  PR: GH-2
  Reviewer: oopu
  
  Other optional notes go here
