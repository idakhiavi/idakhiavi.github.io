---
layout: post
title: "Teenage Mutant AI turtles"
---

In 2025, SaaStr founder Jason Lemkin tried letting an AI coding agent build an application for him. At first, it seemed almost like proof that software engineers were becoming optional. He could describe what he wanted in plain English and watch the system build it. Then the agent began fabricating results, misrepresenting the state of the system and eventually deleted a production database despite being told not to touch it. What interests me about this story is not that AI made a mistake. Engineers make mistakes too. It is how far the system could travel before the missing expertise became visible.

There is something remarkable about evolution as a search process. Nature has no architect and no knowledge of where it is going, yet over immense stretches of time it explores an almost absurd space of possibilities. Mutation matters because it occasionally interrupts the direction in which a population is already moving. It introduces something that the existing trajectory itself could never have logically arrived at. Most mutations are useless, some are destructive, but once in a while one opens a path that was simply not available before and I increasingly think this is the problem we are going to encounter with AI.

Imagine a product manager with no software engineering background deciding that, with a sufficiently capable agent, he can now build an application. And the disturbing thing is that he probably can. He asks for an architecture and receives a reasonable one. He asks how to implement it and receives reasonable code. The database is reasonable, the API is reasonable, the authentication mechanism is reasonable. Every answer becomes part of the context from which the next answer is produced, and before long an impressive amount of perfectly defensible software has accumulated around assumptions that nobody ever thought to disturb... And this is exactly where the problem begins, because a local optimum does not have to look bad. Quite the opposite. It can be beautiful.

Software does not really have one global optimum; there are too many competing constraints for that. But it certainly has locally coherent solutions: designs that work extremely well inside the little world in which they were conceived. A service works perfectly by itself. Another service works perfectly by itself. Then the systems meet and one assumes immediate consistency while another assumes eventual consistency; one owns data another quietly treats as authoritative; retries create side effects; authentication boundaries do not match business boundaries. Nothing was obviously stupid. The problem existed outside the frame in which each component had been optimized.
This is where expertise starts to resemble mutation.

An experienced engineer does not merely know more syntax or produce better code. She can introduce something that does not naturally follow from the current chain of reasoning. What if this request arrives twice? What happens when this service disappears for six hours? Why do we have this service at all? Are we solving the same problem that we think we are solving? She remembers another system, perhaps completely unrelated, where the same innocent assumption eventually became disastrous.

AI can generate alternatives, of course. Ask it for twenty different architectures and it will happily produce twenty. But this confuses mutation with noise. The important question is not whether another answer can be generated. It is whether somebody realizes that the current answer has become suspiciously comfortable.

And this is the part I think gets lost when people say that AI makes expertise unnecessary. AI does not know what it has failed to consider merely because that thing is absent from the conversation. It can investigate an unknown brilliantly once the unknown has been turned into a question. But somebody still has to know enough to ask the question.

This becomes especially dangerous in software because producing components is becoming dramatically cheaper while making those components constitute a coherent system has not become proportionally simple. AI can make the rooms of the house appear almost instantly. Nothing about that guarantees that somebody checked whether the pipes connect.

A mature engineering organization tries to discover these contradictions early through integration, testing, observability, architectural review and incremental delivery. Someone without that background may not even know what ought to be tested. So an enormous amount of apparently successful development can occur before the system finally encounters the reality it was supposedly designed for.

Then someone asks: how did AI miss this?

But perhaps AI did not miss it.

Perhaps nobody who knew enough to ask the strange question was in the room.

The better AI becomes at continuing a line of reasoning, the more valuable may become the person who knows when that line should be broken.

AI can continue the search.

Expertise knows when to introduce the mutation.

#AI #softwareengineering #expertise
