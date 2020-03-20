---
layout: post
title: Organising Code Review
date: 2018-10-04
title: "How to organise code-review sessions for researchers"
---
I'd like to organise code-review sessions in the near future with the aim of helping scientists to produce better more efficient code. Nonetheless, also having some documentation and testing would be nice!   
I've compiled a few great resources and tips from the web in this blog post.   
Hope it helps you if you'd like to organise similar things.   
Cheers!  


## Definition of code review
Code review is a process similar to publication peer-review where one critically assess the work and conclusions made in a study. Code review would help to spot obvious bugs, a lack of documentation and possible mistakes that the author would have missed. In general, it should become common practice in one's lab since all researchers are now regularly producing code to analyse their datasets. 


## Blog post of Fernando Perez (UC Berkeley)  
### Goals of the in-person synchronous code-review session
* Other people should be able to understand what your code does
* This should take as little efforts as possible!
* These sessions are meant to improve the quality of code and scientific results

### How to lead a session
* Create a safe and welcoming atmosphere. Everyone should be able to talk.
* Make it clear when you’re presenting yourself that your code isn’t perfect, point out some of those imperfections yourself if audience is slow to do so.
* Patiently explain when things are not wrong but just stylistic differences. For instance, function names.

### More tips on how to lead a session
* Make sure the motivation for your code is clear. Someone who isn’t intimately involved with your project should understand from the module documentation and the comments what you are trying to do, what approach you’re taking, and why they should expect it to work.
* Take some time to prepare a presentation about your code that will answer the above questions even for someone who hasn’t read the code. 
* Get the code sent out at least a few days beforehand along with some background about what to look at (if large)., whether suggestions should be about architecture/implementation/algorithm/requirements, etc. Make sure everyone has enough time to read the code beforehand, and don’t send a series of updated versions immediately before code review.
* Don’t try to present too much. 200 lines is an absolute maximum – 50 is usually more reasonable.
* Include examples, either as unit tests or standalone in the module’s __main__ block. It can often be a lot easier to see an example working than to figure out the algorithm from the code.
* Ask yourself, before sending the code out, if it could be simpler. Break complex routines down into smaller ones, consider using built-in functions and data types instead of custom ones.
* Follow the coding guidelines and Python idioms applicable to your group. At UC Berkeley I am following for all of my projects the Python style guide encoded in PEP 8, supplemented where necessary (in particular with regards to docstring standards) with the Numpy coding style guidelines.
* Take advantage of existing mature code in your group, the Python cookbook, and other sources of existing code to get an idea of how to do things. Many problems have already been solved for you. It’s always better to reuse well-tested code (if it does what you want) than to reinvent the wheel.
* It’s OK to present code that doesn’t work yet, or that you think needs improvement, as long as you signal this fact very clearly in your email sending out the code. If there are specific areas you want people to focus on, don’t keep it a secret – it’s a waste of time to give detailed feedback on code that is about to be scrapped.


## Short summary of the paper of Marian Petre & Greg Wilson
### Reasons to do code review
1. Rigor: Scientists want to get the right answer and be able to reproduce their work later. 
2. Reusability: Scientists are very aware that their understanding of code dissipates over time and that this is a large hidden cost. Equally, they suspect that they spend a lot of time reinventing wheels. They may not know how code review will help with that, but they hope that it will.
3. Collaboration: Many scientists hoped that they could use code review as an excuse for conversations
about code with their colleagues—conversations that simply don’t happen right now. Some believed that review would foster better testing, encourage scientists to produce code that is easier to understand and share, and make team members more aware of each other’s research.
4. Knowledge transfer: All participants felt that there must be a better way to build programs than what they’re doing right now. 

### Practical tips
* It is beneficial to make a demo of code review + to do it themselves. 
* Make expectations clear!
* It is a continous process. Not all good practices will be implemented in one day
* Code review can be done in person (synchronous session) or remotely and asynchronously (using Github for instance)


### Original publication
[Link to the paper](https://arxiv.org/abs/1407.5648) 
