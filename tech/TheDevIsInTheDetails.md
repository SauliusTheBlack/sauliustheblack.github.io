# The dev(il) is in the details
On april 1st and 2nd, 2025, I had the pleasure to go to Voxxed Days Amsterdam.
For those who don't know Voxxed Days, it's a spin-off of the famous Devoxx conference, and it is held in various cities around the world.
Usually it's a bit smaller than Devoxx conferences, which suites me fine, since I don't handle huge crowds that well.
Smaller though they may be, the vibe is awesome, and the talks are interesting.
Not only the officially sanctioned talks, but the hallway-track as I heard it called as well.

During one of those hallway-track conversations, I had the chance to talk to a guy called Guido, and he dropped the known saying "The devil is in the details".
Me, being slightly hard of hearing, and being in a tumultuous environment, heard "The dev is in the details", and I thought "Hey, I can write a blog about that".

## The dev(il)
Most of us, developers, have had the idea that "We can do it better." or "I can do that for you.".
Saying that, we can't let go, or someone 'forces' us to put our money where our mouth is. And so we embark on yet another project.
A project that, in all likelihood, will actually improve the life of someone. Be it themselves, their partners, their teams, or the world at large.
Several of those projects die before they make waves, but those few that remain start to live a life of their own.
And then, our sweet, sweet dev, that only wanted to improve the life of someone else, become a victim of his own success.

Did you know, that once you release something, you become the de-facto owner of that project? Any question, any improvement, any bug, gets run by you first.
Even if they can do it themselves, they will check "if it's a good idea".
And if there aren't any other developers, you need to consider if you want to maintain it, or disappoint your users.

And so, 8 years after the initial outburst of "I can do that", it's 11pm, on a Sunday. You're tired. But you have a deadline because once upon a time, you thought it was a good idea.

## The details
Starting the project usually is the easy part. You have a small userbase, if you have one at all, and you're free to having fun.
But then you want to professionalise it, maybe publish it on GitHub or as a SaaS solution. At this point, some non-functional requirements start to appear.
And it is in these details that the dev will find themselves.

Some details that you need to consider when starting 'the project':
- will my users use the features?
  - this is quite important actually ;-)
- is my techstack maintainable?
  - if you're making it as a playground, this is completely irrelevant, but it might bite you in the ... if you unexpectedly gain popularity.
- have you considered security?
  - This is a big deal nowadays, and for me personally, it's one I struggle with, and one that merits a point later on.
- What about scalability and architecture?
  - while you shouldn't optimise prematurely, if you want to go pro with it, it might warrant 30min of thought and brainstorming.
- How good is your UX?
  - I'm not a frontend dev. I don't know anything about UX or it's best practices. I also don't have time or the capacity to learn it. But my users do still expect it. And if it's not good, I'll get the blame.
- Is your code qualitatively good?
  - If you have a codebase that is a mess, and you are the only one that can understand it, then you are the bottleneck for any improvement.

The list can probably go on, and I'm not going to go over all of them here.
Let me highlight two topics that I struggle with, and that are actually quite critical.

### Security
If you write your own code, you will most certainly make mistakes. No single developer can think of all attack vectors.
How will you authenticate users, what about sql injection, heard about cross-site scripting?
You use dependencies to connect to databases, they write your sql for you.
You use dependencies to authenticate users, or to decrypt tokens.
These dependencies have dependencies themselves.

Recently we've had a slew of supply-chain attacks. Bad dependency management, where you update as soon as you have a new version, and publish without intervention, are terribly insecure. PIN YOUR VERSIONS!!
But keeping on top of this, even with a tool, can get annoying.
I don't think that your production build should be RED as soon as you have a minor security issue, but you should at least be aware of it.
You can use tools for this, but how feasible is this for single dev teams that need to focus on their product?

### UX
As I said, frontend is not my forte. I haven't a clue on how users want to interact with a webpage or an app.
I'm not well versed in responsive UI design, and I know nothing about accessibility or colour theory.
I use AI to generate my frontends, and my iterative prompts are like "make that button feel more important".
I'm happy with the result in terms of my personal feel. But that might not be good enough.

## Tooling
There are tools out there of course. But they all only do 'the one thing'. While specialization is great, setting up, maintaining, and using 4 different tools is a hassle.
You need to build your deliverable, test it(automatically), check security, check code quality, check UI and UX, do some manual regression testing, ...

## The dream
I dream that, one day, there will be a tool, call it "Silver Bullet", that is open source, which uses open source data and tooling, to do this for you.
Integrate it in any pipeline, for any language, and you have a nice dashboard that says: "This user UX flow can be improved so and so". "Alarm: dependency X.Y.z has a critical vulnerability, update to X.Y.z+1". "This code smells like a code smell, and here are some suggestions to fix it". "This code is not covered by tests, and here are some suggestions to add tests".
If you want to, feel free to do so. You have my blessing.
But be aware. 
The dev(il) is in the details, and you will be it's maintainer.
