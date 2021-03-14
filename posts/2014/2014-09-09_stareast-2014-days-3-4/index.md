.. title: STAREast 2014: Days 3 & 4
.. date: 09 September 2014
.. tags: conference

<p name="4532" id="4532" class="graf graf--p graf-after--h3">The second half of STAREast was in classic conference style: keynotes, lectures with brief Q&amp;As, and <a href="http://proverbialblog.tumblr.com/post/84860843717/i-asked-the-guy-behind-the-counter-at-the" data-href="http://proverbialblog.tumblr.com/post/84860843717/i-asked-the-guy-behind-the-counter-at-the" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">scurvy-inducing food</a>. Thomas Cagley gave me great tools for personality analysis. Jason Arbon gave me his book to read and the most actionable ideas for breaking our app and prioritizing our bugs. Florin Ursu gave me the most advice about how to document my testing, integrate myself into my team’s process, and have my team take ownership of the quality of our products. Playing dice games and other puzzles with James Bach, Michael Bolton, and Griffin Jones got me thinking about my strengths and weaknesses as a tester.</p><p name="8458" id="8458" class="graf graf--p graf-after--p">Below are my key takeaways from all the sessions I attended.</p><p name="88d1" id="88d1" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Randy Rice’s keynote about key testing concepts<br></strong>It doesn’t matter how good your tests are if you’re testing the wrong version. Take the time to clear your cache, install the new build, or go to the developer’s branch.</p><p name="ed3a" id="ed3a" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Zeger Van Hese’s keynote about testing focus and distraction<br></strong>Making lots of decisions drains mental energy and causes the next decision to be more difficult. Rather than list all the things you are going to do this month, list the things you’re not going to do so you can forget about them.</p><p name="cf21" id="cf21" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Bob Galen’s session about Agile testing<br></strong>Calling a project “Agile” to compensate for a lack of requirements will not make it go faster. Make sure you’re building the right thing by frequently communicating with the stakeholders during the development process. Leave enough time in the process for refactoring and bug fixing.</p><p name="ae59" id="ae59" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Erik van Veenendaal’s session about risk-based testing<br></strong>Features people use all the time are more important than rarely-used features. Figuring out where bugs are more likely to arise can help focus your testing, be it inexperienced team members, distributed team members, or new technology. Not all bugs are equally risky; you can start to order them by their relative importance. Items identified as high impact and high likelihood of occurring must be tested and should include a definition of “done.”</p><p name="aadd" id="aadd" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Thomas Cagley’s session about cognitive biases<br></strong>The zero-risk bias causes us to reduce small risks down to zero rather than mitigating the highest risks first. The illusion of control causes us to overestimate our influence in external events. The illusion of transparency causes us to overestimate how well others understand us, especially on long-standing teams. Noting the biases you and your team exhibit can help you avoid being manipulated by them.</p><p name="05f5" id="05f5" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Theresa Lanowitz’s keynote about extreme automation<br></strong>Do public relations for your testing within your organization. Take advantage of the HealthCare.gov debacle to gain parity between development and testing. Provide a high-quality experience on the customer’s desired platform so they don’t leave for a competitor.</p><p name="ef9b" id="ef9b" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Jason Arbon’s session about the secrets of mobile app testing<br></strong>The best way to crash an app is to open and close it a bunch of times, change its orientation, and remove permissions from the phone’s settings instead of the app’s settings. Change your description in the App Store to tell your users when you’re fixing bugs. Look at App Store reviews to decide what you should be testing today. Make sure your crash SDKs are installed from the first build. There is no correlation between the number of shipments and the quality of the app. <em class="markup--em markup--p-em">Teams that actually fix their bugs have higher quality apps.</em></p><p name="06c8" id="06c8" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Florin Ursu’s session about lightweight testing documentation<br></strong>It’s hard to find where you’ve missed something when there’s a lot of documentation. Presenting a mind map to stakeholders helps them take ownership of the process and keeps you from being the gatekeeper to production. Mind maps help focus on the big picture so you don’t get bogged down in individual test cases. Add attachments, progress clocks, happy/sad faces, links to tickets, or notes for a more complete document of your testing.</p><p name="2ebb" id="2ebb" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Lloyd Roden’s session about challenges in gathering requirements<br></strong>Bad requirements can be non-existent, in flux, too few, too numerous, too vague, or too detailed. Error states and performance expectations don’t need specific requirements because you know it when you see it. Too much detail in requirements squashes creativity and leads to useless testing. <em class="markup--em markup--p-em">Find out what features are used the most often and test there the most.</em></p><p name="50aa" id="50aa" class="graf graf--p graf-after--p graf--trailing"><strong class="markup--strong markup--p-strong">Kamini Dandapani’s session about testing on production at eBay<br></strong>Load balancers, caching, and monitoring tools will be more robust on production. Manufacturing data in test environments doesn’t account for legacy requirements. Track your progress by measuring the time from a bug is first reported to when a fix is available on production.</p></div></div></section>

*Originally published at [murphyslawtester.wordpress.com](https://murphyslawtester.wordpress.com/2014/09/08/stareast-days-3-4/) on September 9, 2014 and duplicated on [Medium](https://medium.com/@ezagroba/stareast-2014-days-3-4-f910124df850).*