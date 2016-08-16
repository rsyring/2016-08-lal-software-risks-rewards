.. default-role:: code

===========================================
Automated Testing & Agile Workflows
===========================================

Asset or Liability?

| By: Randy Syring
| Twitter: @RandySyring
| Email: randy.syring@level12.io
| https://github.com/rsyring/

.. epigraph::
    Impassioned. Software. Craftsmanship.

.. image:: _static/level12-logo.png

Introduction
==============

.. image:: _static/level12-logo.png
    :align: right

I'm the Chief Executive Developer at `Level 12 <https://www.level12.io/>`_.

Level 12 is software development firm specializing in web and
data(base) projects tailor made for our customers.

Agile methodologies make our customers happy...really, really, happy.

Why should you care?

This Presentation
=================

* My Journey
* Agile review
* Agile & automated testing
* Testing: Where to Begin
* Testing: 10 tips (if we have time)

Will This Help You?
====================

- It has helped me
- It has helped lots of others
- These are "Best Practices"
- It's very likely it can help you


It's Worth It!
====================

Technology fatigue is real, but this is worth it!

(P.S. I'm a slow adopter)


My Journey
============================

- Started developing web apps FT in 2004
- Exposed to automated testing in PHP late 2006
- Moved to Python & intentional testing model in late 2008
- Adopted a Test Centric model during 2009/2010 (some resistance)
- More robust dev model including CI in last 18 months
- Was practicing Agile "naturally" before I had a label for it


I Practice What I Preach
============================
.. csv-table::
   :header: "", "Proj A", "Proj B"
   :widths: 35, 35, 35

   "Age", "6+ years", 1.5 years
   "Python Tests", "8,294", "1,444"
   "JS Tests", 309, 0
   "DB Tables", 200+, 35+
   "Python LoC", "145K", "26.5K"
   "Python Test LoC", "61K (42%)", "14.7K (55%)"
   "Code Coverage", 95%, 96%
   "Test Time", 39:04, 6:58

Release interval: whenever (multiple times per day if needed)


Agile: Let's Review
==========================

- **Individuals and interactions** over processes and tools
- **Working software** over comprehensive documentation
- **Customer collaboration** over contract negotiation
- **Responding to change** over following a plan

(Source: http://agilemanifesto.org/)


Agile: Select Principles
==========================

- Our highest priority is to satisfy the customer through early and continuous delivery of
  valuable software.
- Welcome changing requirements, even late in development.
- Deliver working software frequently...with a preference [for a] shorter timescale.
- Working software is the primary measure of progress.
- Continuous attention to technical excellence and good design enhances agility.
- The entire process needs to be sustainable over time.

(Source: http://agilemanifesto.org/principles.html)


Agile Essentials
================

A software development process that is:

* Dynamic: change is welcomed with minimal friction
* High velocity: short iterations & frequent delivery (days/weeks)
* Excellent: predictably high quality


How are we doing?
==========================

* Any objections or concerns so far?
* Do we have a good feel for what Agile means for a software team?
* Is this ideal?


The Challenge
===============

What's the challenge of a software process that is committed to
each of these?

* Dynamic: change is welcomed with minimal friction
* High velocity: short iterations & frequent delivery (days/weeks)
* Excellent: predictably high quality


The Solution: Automation
========================

Without heavy use of automated processes, especially testing,
a true Agile workflow is unsustainable.


Preamble: Test Types
=============================

* unit tests: isolate to function or method
* integration tests: multiple components
* functional tests: from the perspective of a browser/client
* browser tests: functional but using Selenium
* sytem tests: infrastructure dependent testing
* qa testing: let a human break it

Your definitions may differ.


Reason
=============================

* Quick iterations and frequent change causes bugs.
* If you want high-quality software, you have to test for and fix bugs.
* As code volume and complexity grows over time, it becomes impossible to
  manually verify all functionality.
* Without automation, quality or velocity (usually both) will suffer.


Regression Testing Unsustainable
================================

.. image:: _static/increasing-regression-tests.png
   :class: fullpic


Diminishing Returns
===============================

.. image:: _static/roi-graph.png
  :class: fullpic


Manual Testing is Unsustainable
===============================

.. image:: _static/pisa.jpg
  :class: fullpic


Agile Developers Need to Write Tests
====================================

If developers are not creating automated tests in parallel with the production code, a true
agile workflow is unsustainable.


Reasons
=============================

* Sustainability: Developers are already testing, but that effort is an expense rather than asset or investment.

Expense vs Asset
================

.. image:: _static/increasing-regression-tests.png
   :class: fullpic


Reasons
=============================

* Sustainability: Developers are already testing, but that effort is an expense rather than asset or investment.

.. rst-class:: build

* Velocity: It saves time in the long run.

I Don't Need No Stink'n Tests
==============================

.. image:: _static/simple-form.png
   :class: fullpic


I Don't...Need....ummm...help?
==============================

.. image:: _static/complex-form.jpeg
   :class: fullpic


Time Savings Overall
===============================

.. image:: _static/roi-graph.png
   :class: fullpic

Reasons
========

* Sustainability: Developers are already testing, but that effort is an expense rather than asset or investment.
* Velocity: It saves time in the long run.

.. rst-class:: build

* Velocity: Automated tests are code and developers are the most skilled workers when it comes to coding.
* Velocity/quality: Fixing bugs is much easier when they are caught early.  Relying on a QA team lengthens
  the feedback cycle.
* Quality: Unit and integration tests ensure confidence when refactoring.


The Place for QA
=============================

* QA should work on thinking from a human's perspective.  Developers often have "creator bias."
* QA should focus on testing that is hard/impossible to automate (usability, aesthetics, etc.).


Questions
=========

How are we doing so far?  Questions/comments/concerns/objections?


Testing: Where To Begin?
========================

* Overwhelming, confusing, etc.
* Goal: high productivity
* Productivity vs efficiency, anyone?


Productive Testing
==================

* Productive: creating or enhancing value
* Tests are an investment, invest wisely
* You are already testing, asset or expense?


Test Centric Development (TCD)
==============================

* do as much productive testing as possible
* acknowledges that we have limited resources
* takes into account the 80/20 principle (93%)
* gives the developer flexibility
* recognizes different contexts have different needs
* when done rightly, results in significant test coverage
* This is not a get out of TDD jail free card!


TCD Guiding Principles
===================================

* confidence and quality increase with testing
* developers write tests at the same time as the code
* default to writing tests first
* test core functionality as thoroughly as possible
* if resources limit testing, cheat less used and/or less important areas
* if the resources are available, test everything
* managers and stakeholders need to reinforce the importance of tests


A Final Plea
============

* You are already testing, capture the value!
* Just get started.  An object at rest...
* Keep at it, it will become natural


More than a Process
===================

It's about culture.


Tip #1: Easy Stuff First
========================

* Remember this is an investment, how much capital do you have?
* Focus on unit or functional testing, whichever makes the most sense.
* Avoid areas of the code that are harder to test (initially).


Tip #2: Make Code Easier to Test
================================

* Testing is a first-class activity
* You should modify your code to make it easier to test


Code Testability Example
========================

.. code-block:: python

    import requests

    def get_project_bandwidth(project_name):
        url = 'https://pypi.python.org/pypi/{0}/json' \
            .format(project_name)
        resp = requests.get(url)

        data = json.loads(resp.text)
        total_bytes = 0
        for url in data['urls']:
            total_bytes += url['size'] * url['downloads']
        return total_bytes


Code Testability Example
========================

::

    def get_project_bandwidth(project_name):
        url = 'https://pypi.python.org/pypi/{0}/json' \
            .format(project_name)
        resp = requests.get(url)

        return calc_urls_bandwidth(resp.text)

    def calc_urls_bandwidth(json):
        data = json.loads(json)
        total_bytes = 0
        for url in data['urls']:
            total_bytes += url['size'] * url['downloads']
        return total_bytes


Code Testability Example
========================

::

    def get_project_bandwidth(project_name):
        url = 'https://pypi.python.org/pypi/{0}/json' \
            .format(project_name)
        resp = requests.get(url)

        return calc_urls_bandwidth(resp.json)

    def calc_urls_bandwidth(project_data):
        total_bytes = 0
        for url in project_data['urls']:
            total_bytes += url['size'] * url['downloads']
        return total_bytes


Tip #3: Easy Test Runs
======================

Can't emphasize this enough, make it easy for people to run your tests!

.. code-block:: bash

    $ git clone https://github.com/rsyring/bookorders example
    $ cd example/
    $ tox
    [...snip...]
      py34: commands succeeded
      flake8: commands succeeded
      congratulations :)

Huge confidence booster!


Tip #3: Easy Test Runs
========================

- Our applications are portable
- We use a wheelhouse for dependencies.
- We can make some assumptions about the environment.
- Deviations are noted in the Readme
- Inability to run tests this way is a BUG!!
- Enforced by our CI environment

What are the challenges to doing this in your context?


Tip #4: Eat the Elephant
========================

Focus on constant incremental improvements.

    We have one simple rule: 'just increase code coverage by 1%'. We are constantly increasing code
    coverage by writing more test cases. Even if the increase is small, it is still a good thing to do.

Credit: http://jodd.org/beta.html

Don't get bogged down by the chaos, just start and then increase little by little.


Tip #5: Failing Tests Are Never OK!
===================================

* Never commit or accept a PR if tests are failing
* Skips can be used when needed
* Failed CI builds should email, post to Slack, etc.


Tip #6: Test Runs Should Be Fast
================================

* Fast code/test cycles are key
* Don't do premature optimization
* Make improvements where needed
* Know your test runner, work inside out


Tip #7: Know What You are [Not] Testing
========================================

Ask yourself regularily what you are trying to test

::

    def contact_form(post_args):
        form = SomeForm(post_args)
        if form.is_completed():
            send_contact_email(post_args['name'],
                post_args['email'], post_args['body'])
        else:
            self.render(form.to_html())


Tip #8: Use Code Coverage Tools
===============================

.. image:: _static/codecov-summary.png
   :class: fullpic


Tip #8: Use Code Coverage Tools
===============================

.. image:: _static/gh-codecov-comment.png
   :class: fullpic


Tip #9:
===============================

.. image:: _static/meme.jpg
   :class: fullpic


Tip #9: Automate All The Things
===============================

* A continuous integration (CI) environment brings great stability
* Put this in place ASAP, it will pay dividends
* Include as much as possible: testing, linting, complexity, code coverage


Tip #10: Sorry
===============================

I could only think of 9, but "10 Tips" seemed more catchy!  :)


Thanks For Attending
======================

| By: Randy Syring
| Twitter: @RandySyring
| Email: randy.syring@level12.io
| https://github.com/rsyring/

Image credits:

* http://reqtest.com/testing-blog/you-cant-work-agile-without-automated-testing/
* https://www.atlassian.com/agile/program
* http://www.slideshare.net/lfingerman/test-automation-best-prcatices-with-soa-test-approach
