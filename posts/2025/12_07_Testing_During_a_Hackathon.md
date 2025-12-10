.. title: Testing During a Hackthon
.. date: 10 December 2025
.. description: What testers can contribute while the idea is still taking shape.
.. tags: agile, communication, development, ensemble, lean, mob, reporting, risk-based-testing
.. previewimage: /images/posts/2025/shapes.png

My team did a hackathon last week. The topic was to automate release notes. I'd misunderstood the assignment ahead of time, mixing up the release notes with a completely different release change log despite several attempts to identify the right thing. I'd messaged several people around the department to understand the use and value of the release change log. 

Seeing these messages, my product owner shared some of the context for the hackathon:

- It took months and had been a hard sell to management to get buy-in for this hackathon.
- It was important that we had outcomes (not just outputs) from the two days we had.
- We weren't going to get another hackathon if we didn't convince management this time was worthwhile.

I took this mission to heart. As a tester ([questioner](https://gretchenrubin.com/four-tendencies/)) at heart, I am predisposed to ask: why are we doing this? Is it important? [Can maximize the work we don't have to do](https://app.thestorygraph.com/books/3aa08f69-6e4b-4041-8eca-48bd7141726b)?

![](/images/posts/2025/shapes.png "Illustration by <a href="https://unsplash.com/@aditya_sahu_lab?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Aditya Sahu</a> on <a href="https://unsplash.com/illustrations/two-cartoon-shapes-interacting-with-blocks-and-shapes-LFqXdzlp-gM?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>")

## The first day

Getting into the room on the first day, the four of us on my team had at least four ideas of what "automating release notes" meant. My idea wasn't wrong or bad so much as it was not what anyone else had in mind. We spent one hour exploring the different documents (including the release change log), wondering how hard they were to produce and who reads them. 

We settled on automating the release notes document because:

- We knew both the author (the developers on teams, including our team) and the audience (their product owners), and why both parties needed this document to exist and be accurate.
- We knew that creating the release notes took a large amount of time at the point in the development process when time is most at a premium: when the developers feel done but the code isn't on production yet.
- We had access to the sources that would allow us to automate creating the release notes: the git repo for the code and the details in the user stories from the tracking system.

After a half-hour or so of a more open discussion, I realized I needed to switch from taking notes in my notebook to writing in a shareable document and sharing my screen. This really helped move us from the problem space to agreeing on a direction. Facilitating that first hour on the first day made such a difference. Together we listed out the possible steps and tasks. We split up into one person trying a bash script and two people pairing on a Python solution. 

I had various side quests pull me away from the hackathon (a presentation, keeping an interview process moving, facilitating [FroGS Conf](https://frogsconf.nl/)). I kept that sharable document up-to-date and popped the link in the chat. This radical transparency allowed the architects (and other interested but not participating parties) to dip into our progress without waiting for the big reveal at the end.

Despite my [side quests](https://elizabethzagroba.com/posts/2021/complete_the_main_quest_first/) and being remote that day, I did have some time to compile information useful to my developers such as:

1. a list of the repositories that we'd want to automate the release notes in. (I sifted through the archived but not dead repos, found the exact names of the things we usually referred to by acronym, and made a list we referred to later.)
2. a Markdown file of the format for the current release notes. (We thought we might pass this into an LLM along with the notes we provided to create the Markdown file we needed. Ultimately we decided that our [small language model](https://keras.io/examples/nlp/abstractive_summarization_with_bart/) did that in an effective, traceable way without hallucinating.)

Later in the day, we convened to understand how our original tasks from the morning had been accomplished or diverged. We compared the two approches: bash scripting to Python. We settled on Python because it could be run locally and more easily read, understood, and trusted by our potential users on other teams. Sometime in the afternoon, the Python pair had split onto separate paths of: 

1. finding the relevant pull requests and user stories, and
2. making a summary out of that information. 

Each of these tasks got a demo of the current progress. This helped us focus our work on integrating the two parts the following day. It also ensured that even if we accomplished very little that second day, we'd still be able to do the required demo at the end. 

### The second day

The second day I was able to be at the office in person, and immediately contribute more actively at the code level. Things I and at least one other person insisted on several times in that room:

- Let's try this one thing and then take a break. Our best ideas come when we step back from the problem for a bit.
- Can you share your screen?
- Can you make it bigger?
- Should we write this ourselves so the AI-agent doesn't change other code we want to keep?
- Can we run it?
- What if we run it?
- Should we try RUNNING IT??
- What would happen if we run it against a different repository?
- Can we hard-code a value before we're sure that it'll work in every case?

The hard-coding definitely came back to bite us. We'd forgotten where we'd done it, so when we ran the code later, it didn't behave as we'd expect. (If I do this again in the future, I'll add `#TODO:` to the hard-coded lines so my IDE can keep track of them for me.)

My contributions on the second day were to turn up the good, and make sure that the developers' work shined under scrutiny. I turned our sharable progress document into a Powerpoint (the love language of my organization) for the demo. I made sure that the business reason was front-and-center for our stakeholders. I gathered input from the team and rehearsed the presentation to make our case stronger and more thorough. 

### The presentation

The three criteria for the hackathon were: creativity, technical implementation, and business value. The team we were competing against had a solution with a lot of potential. I think a Powerpoint explaining the potential value would have won it for them. 

But our solution had a use case now. We generated release notes for one repository for the demo. We could show it to the teams next week. We could implement it for the next release. We could already begin saving developers time and reduce the difficult, manual work that a machine can do more reliably. 

While we missed on creativity, we won on technical implementation (we showed the code) and business value (thank you Powerpoint!), and [thus the whole hackathon](https://app.thestorygraph.com/books/d0f10071-a1ee-4590-a281-0d769028adaa). Congratulations to the dream team: Shailja, Remco, and Denis for providing value to people who matter.

### Building the right product

This hackathon was a specific case of a situation I encounter more generally: 

"We're starting a new product. It's changing so quickly that I don't know what to worry about in terms of testing or quality."

I am not the first person to wonder how we could test earlier in the product development process.

Kent Beck described the earliest of the three stages of product development (under capitalism ;-) ) as exploring in [his blog](https://medium.com/@kentbeck_7670/the-product-development-triathlon-6464e2763c46) [twice](https://medium.com/@kentbeck_7670/fast-slow-in-3x-explore-expand-extract-6d4c94a7539). Anne-Marie Charrett grew this idea to be more specific for testing professionals in [her blog](https://www.annemariecharrett.com/kent-becks-3x-and-quality-a-quality-coach-perspective/) (and later [book p. 167-177](https://leanpub.com/qc)). "In the explore phase, quality is all about building the right product."

During the hackathon, the developers are motivated by having _something_ to show for the timebox. My mindset as a tester is to have a decently good thing that serves a _purpose_. If [quality is value to some person who matters](https://pmo.its.uconn.edu/2021/03/02/introducing-qa-part-2/), making sure there is a user / stakeholder / audience for the hackathon product comes first for me. 

It made me the annoying person in the room, asking:

- Who is this for?
- Why are we doing this?
- Does this exist already?
- Would this save anything time or hassle?

That's why I sent chat messages asking around about the release change log, and why we settled on automating the release notes. 

### Cheap experiments

According to Anne-Marie, "In the Explore phase, the focus is on conducting as many cheap experiments as possible to identify value add...In this context, delivering value rapidly *is* quality." 

On our first day, we experimented with bash scripting and discarded it after the first day. We shared our screens and ran the code from the two solution pieces we wanted to build on. One failed experiment, along with two successful ones.  

On the second day, every time we ran the code was an experiment in what we'd built so far. Switching the repository we generated the release notes for brought us to irregularities in the data (no story description, no pull request description, two components sharing one repository, etc.) that would have let the stakeholders reject our solution. Many failed and successful experiments. 

We got feedback from our stakeholders at the end of our two days, much sooner than our usual sprint-sized feedback cycle. Plus we won the hackathon! Definitely a successful experiment.

### Is it too soon to test?

It is never too soon to test. It can be too soon to perform certain types of testing. 

During the two hackathon days, I suppose I could have:

- write an automated test to check that the release notes were of a certain length
- collect information about how long the release notes generation took per repository
- set up linting or a static code analysis tool to ensure the maintainability of the code as we were writing it
- found a developer from another team and gotten their feedback on the generated release notes

Would any of these have been more valuable directions that what I chose? I'm not sure.

___

I'm curious about your experience as a tester in a hackathon. Did you write code? Were you involved in an ensemble? What kinds of tasks did you pick up? How did you decide as a group what was valuable? And least importantly: did you win??