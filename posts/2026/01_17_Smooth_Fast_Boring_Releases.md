.. title: Releases should be smooth, fast, and boring
.. date: 17 January 2026
.. description: Releases are not the part of your work that should be interesting.
.. tags: automation, development, lean
.. previewimage: /images/posts/2026/boathouse.jpg

After a few months of consulting for a team, they asked me what my recommendations were for them. Among them was a slide with a serene fjord. I wanted the team to imagine how they would feel if they were in that boathouse, calmly sipping tea and looking out at the scenic mountains and water. 

I wanted their releases, and all releases at the company, to be like that. 

![](/images/posts/2026/smooth-fast-boring-slide.png "The dream")

I planted a dream in their brains, something to work towards in the future, that someday:

- Releases should be smooth, fast, and boring.
- Tests run and pass.
- Failing tests give info about the product.
- Passing tests mean code goes to prod.
- On-call duties aren't draining.

## Smooth, fast, and boring

For this team, releases were a tense time. They didn't have a production-like environment for testing, so despite their very thorough efforts, going live could result in unexpected behavior. They required another team's software to be stable to be able to deploy theirs. Depending on what was changing, releasing might require a database migration lasting hours. 

That's not how you want releases to be at all. A release should be the result of running a pipeline or following a well-worn script. It shouldn't be full of surprises, a place where you learn how the system behaves, worth watching, or take a big chunk of your day. Release done well are smooth, fast, and boring. 

### Tests run and pass

Some tests the team wrote weren't in a pipeline. Whether the tests were run before a story was completed was a constant source of tension at standup among the team members. Rather than make it a personal moral failing, I wanted the team to require the tests to be run for a pull request to be merged. Making the tests a blocking step in the pipeline would ensure that they ran successfully. 

### Failing tests give info about the product

Tests that didn't pass were ignored, and for good reason. Failing tests usually provided information about other products, and whether those other teams had put stable builds on the test environment. 

These tests needed to be deleted, and if sufficiently valuable, rewritten in the longer-term. They needed stubs (what I called [mocks](https://www.youtube.com/watch?v=RvKPOjlQKyM) at the time) from the teams they relied on. The test environment was collecting anyone's and everyone's most recent builds, regardless of stability. While I was off in a corner trying to create rules for what could be deployed there, this team needed something reliable, something fake for now. This would give the team meaningful feedback about their own product, which is what failing tests should do.

### Passing tests means code goes to prod

Passing tests were a nice bonus before a story was closed. The existing tests were run as a last step. Nobody was reading what was there, updating the existing tests, adding to the suite, or most forgotten, [removing tests](https://www.ministryoftesting.com/testbash-sessions/should-we-just-delete-it-joao-proenca) that were added in a panic and were no longer providing much value. 

Neither the tests nor the releases were executed in a pipeline, so passing tests did not mean that code went to production. 

### On-call duties aren't draining

Production behavior was unknown at the point of release because there was not a way to test on a production-like environment or, against stubs in simulated environment. Considering how untestable the code was, this team's code was remarkably solid and performant, thanks to the quality of the engineering. 

With such a focus on the thoroughness of the code review, the documentation for how other teams should integrate with this team's product was lacking. Pages were out-of-date, poorly read, or written for an audience lacking the deep expertise the team members had. Questions, uncertainties, and lack of understanding fell to the on-call person to resolve, often occupying 20-30 hours of a 40-hour work week. Reclaiming this time would free up capacity to improve the tests and releases. 

## The path to releasing is a winding road

I wasn't on the team or at the company long enough to see these dreams come true for this team. Showing this slide to the team's boss did get a couple things on the roadmap for the company: fix the test environment, and require all teams to build stubs. I wonder where they are now!

---

What do releases look like for you? Are they a walk in the park, or a thorn in your side? Are they smooth, fast, and boring?

![](/images/posts/2026/boathouse.jpg)

Photo by <a href="https://unsplash.com/@lucabravo?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Luca Bravo</a> on <a href="https://unsplash.com/photos/brown-house-near-body-of-water-zAjdgNXsMeg?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
      