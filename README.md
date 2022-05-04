# swe_in_practice
Essays on Software Engineering in Practice

# May 3 2022
Meetings are part of life, and this is true for software engineers as much as anyone else. Many things get discussed at meetings, and if one pays attention, then a good discussion can arise. 

Debating definitions are a part of meetings for engineers. Today, for example, a debate came up over the meaning of an event stream. One side of the argument was that it tracks the changes of data to a data source. The other side argued that it tracked any changes to the data, even if the values in the data didn’t change. It is a subtle difference but an important one because it determines what gets published to the event stream. At the end of the day, the answers depends on what the consumer wants, which in this case was the former and not the latter…but it could have been the latter given a proper use case. One possible use case for the latter is that client wants to know of any attempted changes to the data source, even if the changes didn’t result in any changes to the data’s values. However, this is not what the client wanted. So, in the end, the definition ended up being the former, and the meeting dispersed. 

Yet, it would have been nice if the definition ended up being the latter. One reason is that the team would have less work. That is, less logic would be required when making the publishings to the event stream, and our code would be simpler. Then, we could call this ticket done and deliver some value to the clients.  Of course, there may be too many events going to the topic but at least there will be some events at all, when previously there were none. For the clients, this is ok because they won’t break, since consuming is pull-based rather than push-based. So, something gets done, and there is still the opportunity to optimize it in the future, and the managers will be happy since the ticket gets across the board. 

It may be apparent now that there are various reasons for debating the definitions of things. Some of them are political, for the purposes freeing up one’s time or getting away with as little as possible and still making the managers happy. It turns out that this desire can sometimes conflict with the needs of the customer, who may want something more than what the engineer can do, or wants to do with the time allotted. The conflict arises because time is limited and the list of tasks is long, so engineers have to decide what doesn’t need to be done. In this example, it was whether or not to filter events. In the end, the manager won and the ticket was given more and energy. 

It could have ended differently, but not likely. One way would have been to show that the additional logic would result in no difference in the quantity of events published. Another angle would have been to present a better business use case for the latter. In end, however, the best way would have been to simple get out the ticket and say the rest will be don latter, and then see if the remaining work actually got prioritized.  

# May 4 2022

Tabulating the fruits of my labor over the past few years has suddenly become of great interest.  Certainly there are a host of material improvements, and in addition to that, my knowledge of computer science and software engineering has increased considerably. Additionally, my the tools for observing myself and the world around me have increased and developed. This is all good, and I am fortunate and grateful. Now, with regards to these things, some of them changes are concrete and measurable (such as net worth accumulation), and some of them remain qualitative (such as the degree of my improvement as an engineer). The hope is to make concrete, with examples, the qualitative changes.

Here is an example of development in engineering. Recently, project to automate namespace creation throws an error about a failed host look up. The errors look familiar; it’s been seen before, even discussed in the channels. At first glance, a simple mapping is broken, maybe it can be fixed quickly by reinstall, but that turns out to not work. Looking further, a quick inspection of the configs suggest things should be working. So what now? Probably do nothing and wait. 

The tight coupling is apparent. In the past, it might have been exciting to looking deeply into the issue, but today, the root cause is obvious: the tool is too tightly coupled to the cli tools.  Instead, they should have relied on the existing kubernetes infrastructure and gotten it working before creating a new cluster. Once realizing this, it became obvious that this tool wasn’t going to work out, and that time was spent better elsewhere. It’s not my problem.

A year ago, however, the response would have been very different. That is: dive into the the issue and fix it, maybe ask about it, maybe write about it, tell others about the hacks needed to get it to work. In fact it may still be a quick fix (some mapping is probably broken), after which things would continue smoothly. However, the effort is still not worth the time since the task was exploratory in the first place, and there will come a time when the project is readily available, so it’s just better to be patient.  Reflecting on this experience, it became clear that that’s quite a change in perspective from the beginning of my engineering days. 

Yet, at the same time, there is value in solving bugs because they fix the gaps in one’s knowledge. A good engineer is always growing, and that mean expanding one’s knowledge. 
Therefore, there is good reason to solve the bug, even if it doesn’t deserve the businesses time. Even my skip-level said one of his only regrets was not pursuing problems for their own sake, even if the value to the business wasn’t obvious. That really highlights that the eternal dilemma for the engineer is: what to work on? This is because the systems are too big for any one person, just like life…but that is a story for another essay. 
