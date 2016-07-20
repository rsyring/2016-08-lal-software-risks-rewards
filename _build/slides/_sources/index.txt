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
    Relentless. Software. Craftsmanship.

.. image:: _static/level12-logo.png

Introduction
==============

.. image:: _static/level12-logo.png
    :align: right

I'm the Chief Executive Developer at `Level 12 <https://www.level12.io/>`_.

Level 12 is a web & database development firm that uses:

- solid engineering,
- proactive communication, and
- modern development practices

to make our customers **really, really, happy.**

Why it Matters to You
=====================

- Level 12 ... uses... **modern development practices**
- to make **our customers** really, really, happy

Net result: this works and is maintainable in the "real world"

Well, my "real world", YMMV
============================

- Methods & concepts refined over last 7 years
- Primarily involved in web development (11 years)
- Not operating *"at scale"*
- Your context may differ
- Industry proven and advocated methods

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

(Source: http://agilemanifesto.org/principles.html)


Boil it Down
==========================

* Early & Continuous delivery, changing requirements, flexibility, agility: responding to change
* Excellence, working software, valuable software: ship software that you are confident works


Software You Are Confident Works!
=================================

.. rst-class:: build

* How can you be sure that your software works?
* You have to TEST IT!!!
* But who tests it?  And how?

No Automated Tests
=============================

* It becomes increasingly difficult to do comprehensive regression testing over time.
* Diminishing returns affect both quality and velocity.
* Your testing is an expense.

Issue #1: Non-Automated Tests
=============================

.. image:: _static/increasing-regression-tests.png
   :class: fullpic

Waterfall
=========

.. image:: _static/waterfall_release_process.svg
   :class: fullpic

Agile
=========

.. image:: _static/agile_release_train.svg
  :class: fullpic


Manual/Separate Testing
=======================

.. image:: _static/hybrid_release_process.svg
    :class: fullpic
    :width: 80%

The tight feedback loop is missing.




Practice What You Preach
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

Let's Talk
==========

- Guiding principles vs implementation
- Hopefully leaving time for discussion & feedback

Audience Survey
===============

.. rst-class:: build

* Are testing your code?
* Are using automated tests?
* Have a build pipeline that integrates testing?
* Reasons for not using automated tests?
* What makes code "untestable"?
* What do you think of TDD?

I Don't Need No Stink'n Tests
==============================

.. image:: _static/simple-form.png
   :class: fullpic


I Don't...Need....ummm...help?
==============================

.. image:: _static/complex-form.jpeg
   :class: fullpic


Test Types Overview
===================

* unit tests: isolate
* integration tests: multiple components
* functional tests: end to end testing
* acceptance tests: alias for functional tests?
* sytem tests: infrastructure dependent testing
* qa tests: let a human break it

Your definitions may differ.


Other Test Terms
================

* Bahavior Driven Development (BDD):

    * acceptance/functional testing
    * often uses Gherkin, a business readable DSL for writing executable specifications

* Test Driven Development (TDD): write tests before code


Where To Begin?
===============

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
* Good bridges aren't built without blueprints.
* Just get started.
* Good tests will lead to better code & greater confidence.


You Can't Afford Not To
===============================

.. image:: _static/roi-graph.png
   :class: fullpic


No Automated Tests? Your World
===============================

.. image:: _static/pisa.jpg
   :class: fullpic


Dealing with Objectors
======================

* It's a culture issue, use language or metrics that resonate
* Look for a kindred spirit
* Become an evangelist
* Ignore them (if possible)
* Just start doing it, demonstrate the value
* Sacrifice some of your own time
* Consider finding a new job


Tip #1: Easy Stuff First
========================

* Remember this is an investment, how much capital do you have?
* Focus on unit or functional testing, whichever makes the most sense.
* Avoid areas of the code that are harder to test (initially).


Tip #1: Easy Stuff First
========================

.. image:: _static/roi-graph.png
   :class: fullpic


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

* Never commit (or accept a PR) if tests are failing
* Skips can be used when needed
* Failed CI builds should email, post to Slack, etc.


Tip #6: Test Runs Should Be Fast
================================

* Fast code/test cycles are key
* Don't do premature optimization
* Make improvements where needed (cookie story)
* Know your test runner, work inside out
* Eventually depend on CI for a full test run


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
