---
title:  "Book Notes - \"The Pragmatic Programmer\" by David Thomas & Andrew Hunt"
date:   2020-02-10 20:08:01
description: "Summary of the book \"The Pragmatic Programmer\" by David Thomas & Andrew Hunt"
tags: [
    "education",
    "development",
    "self-help"
]
categories: [
    "Development",
    "Education",
]

---

"The Pragmatic Programmer", which is considered by many to be a classic text on software engineering craftsmanship, has gotten a complete do-over after it was first published 20 years ago. In the following, a summary of the books key points follows. 
<!-- more --> 

## Preface:

Care about your craft. Always scrutinize your work and reflect on it.

There is always room for individuality, even in a big enterprise software project.

*Kaizen* - continuous, regular small improvements over a long time. Applicable for factories & processes, but also personal development

## One: A Pragmatic Philosophy

This chapter sets some basic guidelines of the pragmatic programmer approach:

1. "It's your life" - you have agency: In choosing projects, switching jobs, working remotely, learning new technologies. It's a flexible career and you can always adapt.
2. "The cat ate my source code" - taking responsibility for your work (and your errors). 
Don't make excuses or shift the blame. Provide options: What can be done? Be honest and direct. Trust in your team is essential - for working and speaking your mind. It's ok to need more resources - time or knowledge. If you say "I don't know", add "but I'll find out".
3. "Software entropy" - once you have a broken window in a house, it deteriorates quickly and turns eventually in a ruin. Same applies to software: One bad piece of code or management decision can influence whole team + project - hopelessness is contagious. Remove technical debt / software rot (or at least do preliminary solution). Therefore: Don't live with broken windows.
4. "Stone soup and boiled frogs" - a story: Soldiers have no food and villagers withholds their food. They boil some stones, villagers get curious and ask. They say, it's good, but better with vegetables. One by one, villagers go and get the food they were saving. 
    
    Learnings: 
    1. "Be a catalyst for change" - to get the change you want, you often have to ask for a smaller, more realistic thing. Once people see that it goes into the right direction, they want to be part of the success, give you more ressources to accomplish your project.
    2. "Remember the big picture" - don't be too focused on the "stones" while forgetting what happens around you. Be aware of the context. A frog in a gradually heated pot doesn't notice the change and gets cooked.
5. "Good enough software" - Good software now is better than perfect software in a year. Involve your users early, know what they want: Make Quality a requirements issue.
6. "Your knowledge portfolio" - needs managing like a financial portfolio:
    - Invest regularly - learn consistently, make it a habit
    - Diversify - learn lots of different things; specialise in what's important now but be aware of broader spectrum 
    - Manage risk - don't put all "technical eggs" in a risky basket; but also: low risk, low reward
    - Buy low, sell high - learn emerging tech
    - Review and rebalance - reevaluate what is worth learning and focusing on

    Set goals - examples:
    - Learn a new language every year
    - Read a technical book each month - don't forget nontechnical (soft skill) ones
    - Take classes
    - Participate actively in local user groups / meetups
    - Experiment with different environments: IDE vs makefiles
    - Stay current, read versatile news

    Doesn't matter if you don't use all you learned in a project. The process is what counts and will you make think in new ways.

    Be on the lookout for learning opportunities. Use your free time. 

    Critically analyze what you hear and read: Often ask "Why?", "Who benefits?", "What's the context?", "When/Where would it work?" etc.

7. "Communicate!" - communication is essential for ideas to develop and projects to be successful.

    Treat writing natural language with the same care as coding. Then, like a programming language, it will have an effect and get others to convince to your ideas.

    Tailor your message on your target audience. Outline what you want to say. Choose the right moment to talk. Choose the right style for the message. If on paper, put effort to make it look nice. Ask for feedback, strive for having a dialogue. Listen to people, and they will listen to you. Get back to people. It's how you say it as much as what you say. Documentation should be built in: Say *why* it is done that way, not *how*.

## Two: A Pragmatic Approach

The essence of good design is being "easier to change (ETC)" than bad design. Every design pattern out there can be traced back to ETC. With everything you do, ask yourself: Is this ETC? Following approaches trace back to ETC:

DRY - Don't replicate yourself. Every single piece of knowledge must have a unique representation in a system. Duplication of intent in documentation, processes and code makes maintenance harder and breaks things.  Maintenance starts with begin of development (agile approach), not its end.

A project is DRY proof, if a change doesn't necessitate several changes in code, documentation, database schemas etc.

*Code duplication* is OK, even make sense if it is not *knowledge duplication*. Don't duplicate the behaviour of code in its documentation. Don't define a dependent variable explicitly, create it from dependencies. Cached data (attributes from storage instead computation) violates DRY, but keep this local.

When your code exchanges data with internal or external services or databases DRY is violated due to *representational duplication*. A change on one end breaks the other. Mitigate this by using tools like OpenAPI to import the API spec; host your API on a central repository; for data sources generate containers and import the data schema; or store everything in neutral key/value maps and write checkers for each different data source.

*Interdeveloper duplication* happens when programmers in an org create the same functionality. Increase communication over chat and scrum meetings. Appoint a project librarian. The best way to avoid it is to make your code easy to reuse.

In maths, two orthogonal vectors are independent of each other. *Orthogonality* in software means that unrelated components should not affect each other. Write cohesive, self-contained, independent components with a single purpose. Orthogonal software increases productivity and reduces risk by localization, reduced complexity and easier testing.

Modules and layers are examples of patterns enabling orthogonality. Specific layers are easy to change as interfacing layers only know about the exposed abstractions. E.g. the UI layer should be easily replacable independently from the database schema.

Adding libraries and toolkits might infringe orthogonality. Keep your code decoupled. Pass context to classes as parameters. Take care using global references and Singletons. Refactor similar functions.

If a lot of secondary code needs to be imported for a unit test of a module, this might show a problem. Same goes for if a bug fix involves multiple touches.

Plan for reversibility. No decision is final. Aim for flexible code, architecture and vendor integration. Don't fall for fads.

Tracer bullets are a concept of finding the target fast, under real circumstances and gives us and users feedback. Tracer code could be a single feature, implemented end-to-end across all layers while the rest is still a skeleton. It is not temporary, just misses functionality which is added in increments. This approach is good for users as visible results are gained fast, as well as developers, as existing code is like a template and continous integration is easier. Tracer bullets are used when direction is unclear. However, if they don't "hit", it is necessary to reiterate. It's not a prototype, as that is disposable and happens before tracer bullets, which is the actual thing.

Prototyping comes into play when the main aim is to learn and discover. It can be UI, architecture, logic or anything, really. It can be high-level code but also whiteboards, post-it notes or anything else to explore ideas counts. Prototypes don't have to be complete, robust, correct or well styled. Don't deploy or build onto it.

Domain Languages can simplify development. External DL need to convert their code before using it (Ansible, Cucumber), internal DL are built as extensions of a language and don't need conversion but are tightly linked to their language (RSpec or similar testing frameworks). Only create an external DL if it's for your users in the future.

Estimating well comes with experience. One approach is to give best case, worst case and realistic estimation. Best estimation is when you have begun with the project. Schedules need to be reiterated along project components. When asked, say "I'll get back to you".

## Three: The Basic Tools

Always be on the lookout for **new tools** that improve productivity. Don't be trapped in a single comfy IDE.

Keep code and knowledge in **plain text** (like structured data and protocols are).

Learn to use the **shell** and harness its power. Customize theme, prompt and create aliases for often used commands.

Achieve **editor fluency** to become more efficient and have less mental clutter while programming. Focus on learning the commands that make your job specifically easier. Reflect on what you're doing, find better ways to and repeat newly learned tricks.

Use **version control** with everything (projects, computer configuration…). It allows for collaboration, release version tagging, undo errors and archive work. You can use isolated feature branches as part of your workflow. Third party VCS offer useful features like pull request support, triggering builds and team communication.

Rephrase **debugging** to just solving a problem that needs to be fixed. Don't blame and don't panic, the first step is to get into the mindset: Fixing the root cause above all else, step back and think.

A good first step is to make a failing test that exposes the bug on the push of a button, then fix it.

Read the damn error message.

Learn how to move in the call stack of the debugger. Keep notes. Use divide and conquer approach with input data to find the offending part. Tracing via logging can be effective. Explaining what the code does step by step can reveal bugs by itself. Blame your code first, not the system. Challenge your assumptions and prove them.

Learn basic text tools such as `grep`, `awk` or `sed`.

Keep an **engineering daybook** in paper for storing ideas, an extension of your memories, meeting notes, sketches, reflection and keeping trace of debugging values.

## Four: Pragmatic Paranoia

No Software is perfect. This chapter discusses defensive measures that ensures that things run smoothly.

**Design by Contract** (DBC) ensures keeping state for a method. We specify preconditions (what has to be fulfilled to call), postconditions (what to expect from result) and invariants (what is always valid). Some languages have DBC support, but it can be also achieved with comments or assertions. DBC is additional to any testing.

**Crash early** to terminate faulty programs and get to the root quickly.

User **assertions** in regular code to check that *impossible* things do not happen. Leave assertions on in production.

Act locally. Deallocate a resource in the same context where you allocated them. When dealing with multiple ones: In the same context, deallocate in reverse order (avoid orphan dependencies); in different contexts in same order (avoid deadlock of shared data).

When OOP, wrap your resource in a class so that the destructor frees it.

When having exceptions, deallocation has to happen with `finally` clause or variable scope (e.g. stack vars).

Deallocating dynamic data structures (their children) depends on the use case. Write code to check resources are actually freed.

Take always small steps - don't "outrun your headlights", which means for us "rate of feedback". Feedback can be from testing, an IDE or a user demo. Avoid any fortune telling.

## Five: Bend, or Break

Your code should be **decoupled**. This makes it easier to change.

**Tell don't ask** (TDA) means instead of using functions to retrieve objects on which to execute logic on, we supply direct functions that do this logic (remove the "get"). This strengthens encapsulation and allows to accomodate changes in the logic at the root of the object. Don't chain method calls when you _access_ something.

Avoid mutable global data (variables and singletons with access methods included!). If it should be global, wrap it in an API.

An event means _availability of information_. Following are strategies to use events in a system:
- **Finite State Machines** define certain states and to what based on an event. Try to find use cases for FSMs. Combine with actions that should be triggered on certain state transitions.
- **Observer Pattern** defines a source of events (_Observables_) and _Observers_, executing functions when the event occurs. _Observers_ pass a callable reference to the _Observable_. Performance issues and strong coupling can occur. 
- **Publish/Subscribe** denotes a pattern where channels deliver (asynchronous) events. The _PubSub_ model connects publishers and subscribers and is offered by many libraries and cloud providers. As complexity is abstracted into the channel, decoupling is reduced.
- **Reactive Programming, Streams and Events.** More and more libraries include instant response to event-driven changes in data. Reactivex.io defines principles on reactive programming and handling event streams. Streams can be used in programming like normal collections and are populated as events occur. Event-based programming gains popularity. Time does not need to be managed anymore, we only specify the processing.

Programming is about code, but programs are about data. Think first about transforming inputs to outputs, not about the code and how to realise it.

