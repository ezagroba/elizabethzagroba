.. title: Strengthen Your Code Review Skills
.. date: 27 February 2022
.. description: Give code reviews the same care and attention you would with any feedback.
.. tags: feedback, code-review, communication
.. previewimage: /images/posts/2022/two_birds.jpg

I spent my first two years at my current company getting my code reviewed and the following almost two years reviewing 3-10 merge requests per week. Our tech stack was in Python, with pytest as our test running, the requests library for API tests, and Selenium for browser tests, all hosted in our company's paid gitlab instance. All that experience shaped how (and whether I) offer feedback on the merge requests I reviewed for members of my own team and neighboring teams working in the same tech stack.

## Define the relationship.
There are power dynamics at play in any relationship at work. For members of my team, they had to have a really good argument to refute one of my "suggestions" because I was their test specialist _and_ their team lead evaluating their ability to respond to feedback and change their behavior by performance review time. No pressure!

For members of other teams, they had more power to push back. It could empower them with the knowledge I shared, but they were free to reject it. 

## Focus on what matters.

When I review a merge request, I start with the question "what is this code supposed to do?" If it's a merge request for my team, the JIRA ticket number in the title or the branch name would clue me in. For code from other teams, champions would use the description field to explain what the product change was and how the test code supported that. Most merge requests left me guessing a bit. I'd have to read the code contained in the tests to figure out what the test, and ultimately the product, was supposed to do.

Reading the code also got me thinking about the things I was best equipped to help the code submitter with: maintainability and "what if?" scenarios. As a tester, I could look at a list of tests that create, read, and delete a thing and ask "is update also part of the picture here?" As a code reviewer with a longer tenure at the company, I had a more informed view of whether copy and pasting would work or if a new function was needed.

We had two linters set up to run on every commit: flake8 covered style enforcement (indentation, blank lines, etc.) and vulture identified unused code. For issues of style that a machine couldn't decide, we had written guidelines to point to. I pointed to these three the most often:

1. comments explain why the code is the way it is, not what it does (so code is clearer to read and update)
2. setup and teardown should take place outside the test (so pytest reporting tells you there's an `error` instead of a `failure` when something's off)
3. API tests assert the status code before any details about the response body (because the body's not going to have the right stuff in it anyway if the status code is wrong)

I would give feedback about these topics, trying to ask questions to disambiguate my observations from interpretations. I knew that the person who'd written the code had spent more time and thought steeped in the problem than I had. Questions allowed me to assume competence while gathering evidence to the contrary. 

As I read other people's code, I saw lots of weird stuff: stuff I would name differently, stuff I would put in a different order, stuff that took up more or fewer lines than I would have to write the same thing. My experience living in a non-native English speaking culture served me well here: I let it go. Was the test name meaningful to them and their team? Did putting it across a couple more lines help them understand it better? Was it actually a problem with what the code did or just a personal opinion? Did they want to set the constant right before they used it instead of at the top? Go for it! It works, I can understand what they meant, and that should be the threshold. My review was not an opportunity for me to show off my Python skills. I was there to help the code submitter with their tests. I reserved the right to remain silent on unimportant matters. 

## Communicate well.

### Praise the good!

Notice when people have done something well and praise them for it! Positive reinforcement is the best way to turn up the good on what's already happening in your code base.

### Right level of abstraction

I reviewed merge requests that were 30% done that I mistook for 100% done; conversely I saw at 110% done that I would have killed at 30%. A little [WIP] label in the name of the merge request or bullet list of which tests were still missing helped me offer the code submitter the right kind of feedback at the right time. 

Sometimes, the code isn't the problem, the product is. I've seen a 500 http status code returned for something the user screwed up, which should be in the 400-range. A code comment "Should this be a 400 response?" opened up a more interesting conversation about where the product was in its lifecycle and the code submitter could lobby their team to change the product's behavior.

If having the conversation about the code isn't the right approach, I tried having [the meta-conversation](https://elizabethzagroba.com/posts/2021/delivering_information_vs_delivering_meta_information/) instead. "I'm not convinced this API spec is done. Where are you in that process?"

![](/images/posts/2022/wtf.png "Code quality measurement: WTFs/minute")

### Right format

Tone is hard in writing. I do prefer writing, because it gives me the opportunity to have several drafts, separating my WTFs-per-minute from what the code submitter receives. I just don't always hit send. Before leaving a comment on a particular line in gitlab, I ask myself: is this the right format? Have I removed any judgy adverbs like "just", "obviously", or "actually"? Would a video call, a Slack message, or a comment on the whole merge request be more likely to be embraced?

### The receiving

One of the many tough things about feedback is that the receiver determines the priority of the feedback. (For all the other tough things about feedback, read [_What Did You Say? The Art of Giving and Receiving Feedback_](https://app.thestorygraph.com/books/15270135-7360-4e66-b079-4cbd618dfb76).) The code submitter often completely miss what I meant the first time. Even if I thought I'd delivered my feedback as well as I could have, it wasn't always accepted. Everyone extracts different information from the same situation. The feedback that provides the most information can be the hardest to accept.

## It doesn't have to be like this.

### Asynchronous

You may have read my first paragraph and asked yourself "why is she doing so many async code reviews?" and you'd be right! The company was scaling at a speed that I was forced to optimize for "number of minutes per day without video calls" over shared understanding.

### Synchronous

Did you know that working in a pair or an ensemble can do all this feedback and knowledge-sharing stuff in a better way? See more about how an ensemble made learning happen in [this slide deck](https://ezagroba.github.io/mob-testing/). 

When I was able to, having a conversation helped me make sure that I was giving the right feedback at the right time to the right person. Pairing with the code submitter got not only the mistakes fixed, but also the thought processes behind those mistakes.

![](/images/posts/2022/two_birds.jpg)

## Don't take my word for it.

I have the benefit of learning from smart people who are also thinking through what code reviews are and what they can be. I have yet to be free at a time when [the code reading club](https://github.com/neontribe/code-reading-club/) Felienne Hermans started has met, but I look forward to joining sometime in the future. Here is a collection resources that I've already found useful:

### Videos 
- Sarah Mei on [The Power of Agile](https://www.youtube.com/watch?v=YL-6RCTywbc)
- Nina Zakharenko on [Code Review Skills for Pythonistas](https://www.youtube.com/watch?v=6L3ZVLtSeo8)
- Sasha Laundy on [Giving and Getting Technical Help](https://www.youtube.com/watch?v=hY14Er6JX2s)

### Books
- [_What Did You Say? The Art of Giving and Receiving Feedback_](https://app.thestorygraph.com/books/15270135-7360-4e66-b079-4cbd618dfb76)
- [_Crucial Conversations: Tool for Talking When Stakes Are High_](https://app.thestorygraph.com/books/b15fe452-5b8e-49f5-9e0b-90da490b944c)

### Blog posts

- Michaela Greiler on [giving respectful code reviews](https://www.michaelagreiler.com/respectful-constructive-code-review-feedback/)
- Michaela Greiler on [how to handle criticism during code reviews](https://www.michaelagreiler.com/accept-code-review-feedback/)
- Jessica Joy Kerr on [those pesky code reviews](https://jessitron.com/2021/03/27/those-pesky-pull-request-reviews/)
- Angie Jones with [the 10 commandments of navigating code reviews](https://angiejones.tech/ten-commandments-code-reviews/)
- Lucas Rocha on [microcommits](https://lucasr.org/2011/01/29/micro-commits/)

### Quotes found on Twitter

- April Wensel on [compassionate code review](https://twitter.com/maaretp/status/1024995595973525510)
- Patricia Aas on the [zero-trust process](https://twitter.com/pati_gallardo/status/1373343835330383878)
- Michaela Greiler on how [everybody needs an editor](https://twitter.com/mgreiler/status/1482247806798733317)
- Michaela Greiler [thread on the biggest annoyances during code reviews](https://twitter.com/mgreiler/status/1481902327640608770)
- Amy Edmondson on [psychological safety](https://twitter.com/AmyCEdmondson/status/1476198824012136460)
- Jerry Weinberg on [egoless programming](https://twitter.com/mstine/status/1481660769456513029)
- Allen Holub on [async code reviews](https://twitter.com/allenholub/status/1491168642586710016)
- Allen Holub on [inspecting quality in](https://twitter.com/allenholub/status/1482564778149175298)

---
Photo by <a href="https://unsplash.com/@robinmathlener?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Robin Mathlener</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>