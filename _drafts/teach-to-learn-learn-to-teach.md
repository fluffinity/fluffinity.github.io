---
layout: post
title: "Teach to learn, so learn to teach!"
categories: posts
---

We all learn every day even if we are not noticing it. Programming is no exception. But there is a difference in how fast and how much we learn.
You can become a good programmer by studying yourself and coding a lot.
But I believe that you can not become a great one unless you are also able to bring someone else to your level.
Only if you can teach another person your learned skill sets, you have really mastered them. 
In the process you will need to think about the topic in a lot of ways and that will give you a more complete view of it. 
In turn this means you will also learn a lot about what you try to teach. And some of this new knowledge may surprise you even after years of experience.

So lets dive into the art that is teaching!

## My own background

As with anything anyone tries to tell you, you may listen to it and then decide whether you want to believe it. 
But to give you some reason to believe me, I have been programming for 10 years now, from late high school throughout my B.Sc in CS and now at work.
For 6 of these years I have been a tutor in various classes at university. 
From introduction into programming, software development and programming languages to data structures and efficient algorithms,
formal languages and computability as well as GPU programming. And in these 6 years I taught more than 200 students, 
graded their assignments and exams, observed their accomplishments and struggles and got confronted with many different questions.
They would range from expected problems, like how properly synchronize threads, to stuff we would dismiss as "trivial". More to that below.

And if you think that it should have been fairly easy to teach these students, because they are at an university, I'm sorry to disappoint you. 
It didn't matter whether a student was in their first semester or if they were short of finishing their master. 
The former could easily be much better than the latter. The correlation between years of study and actual knowledge was a weak one at best.
Even when I taught in advanced courses I would almost always have students, who barely understood the basics of not just the course, 
but CS in general.
Needless to say, it was hard. But it became easier over time, due to me getting more experienced in both, 
the material itself as well as how to teach it to others. Over time I learned to teach.

So while I don't have a long list of open-source projects I point to for my resume, I do have a lot of experience in bringing knowledge to others.
Lets go over one question of one student I had in my first semester as tutor and how I did answer it vs how I would answer it now.
The question at hand: "What is even the difference between `return` and `print`?

## On seemingly trivial questions

Yes, this is a question I had to answer once. It was in one of the beginner courses and the students had just learned about functions. 
So far they used Python and only used it inside Jupyter Notebooks. If you don't know about them, good.
I hope you will never have to work with them yourself. In essence, you have "cells", in which you can write your code, and you can execute these cells. 
If you print inside these cells the output will be shown below it. But you will also get an output for the last computed value in this cell.
So if your last line is something like `x + 5` you would get an output like this `[1]: 10`. Lets have some sample code for further explanations:

```python
def calculate_area(radius):
    return radius ** 2 * math.pi

print("Some output")
calculate_area(10)
```

What do you think the output will be?

Yes, we will have the return value of the call to `calculate_area` in the output. 
So by returning a value the student got it output in the same place as the stuff displayed with `print`.
But if both lands in the output, then what even is the difference between `print(radius * math.pi)` and `return radius * math.pi`?
It just wouldn't be obvious, given the example and the environment.

With that I hope I convinced you that nothing is truly trivial for everyone.
While we can argue that the way Python was introduced in the course is not good, that they shouldn't have used Jupyter etc, 
nothing changes the fact, that for this student `return` and `print` seemed to do the same. 
And so the question for us should be "How can I answer this question?"

## Explaining the seemingly obvious

I think we all can relate to the fact that explaining something more complex can be easier than explaining a triviality.
We all can explain why `x^2 + 1` is greater than 0 for all real `x`, but can you also show why `1 + 1 = 2`?
Unless you are a mathematician you will likely do the same I did.

Back then I stuck with the code above and just told the student that with `print` you explicitly output whatever you want to print. 
`return` on the other hand is used in functions so that the caller of that function gets back a value it can then 
use and to end the execution of that function.
So they aren't related to each other.

Yeah, that didn't work. The student was just as confused as before. While the explanation was technically correct (the best kind of correct),
it was just a bunch of words to a person, who had no prior experience. 
It didn't take into account that, from their perspective, these 2 things seemed to do the same. 
I **told** them the difference but I didn't **show** it.
So how would I show it now?

Well, the first thing I'd do is to change the code example. For reference, here is the original sample:

```python
def calculate_area(radius):
    return radius ** 2 * math.pi

print("Some output")
calculate_area(10)
```

Lets change the last line a bit.

```python
def calculate_area(radius):
    return radius ** 2 * math.pi

print("Some output")
# we now actually bind the result of the call to a variable
area = calculate_area(10)
```

When we execute this code block we now only get "Some output" in our output. `area` is nowhere to be seen and neither is its value.
Now it gets much easier to explain the difference because you can **see** the difference. 
While the stuff in `print` lands in our output, `area` now contains the value `calculate_area` returns with `radius` being 10.
Just adding the line `area` to the code above afterwards and re-executing the cell will then show 314.1592653589793 in the output.
This proves that `area` really contained the value `calculate_area` computes, showing the effect of `return`.

So, by just changing one line of code here we were able to massively improve the quality of the explanation. 
And this brings me to the point of this section:

In order to explain something efficiently you really need to understand not only the topic itself, but also the circumstances of the person asking.
You need to be creative enough to find new ways or changes to existing ones, in order to make it easier for you to get your answer across.
And if someone asks you something seemingly trivial, take the time to explain it anyways. 
You may find it more difficult to break down, than you initially thought. Nothing is truly trivial for everyone.
But sometimes all they need is a slightly different perspective.
And by trying to find that different perspective your students can actually teach you!

## How to learn from your students

Well, lets go back to the example above. Explaining the difference between `print` and `return` became a lot simpler, the moment the last
line got changed. That change took the fact into account that we are within the environment of a Jupyter notebook. 
This means, on the way to this change, we had to learn the behavior of these notebook as well. If we didn't know that before we would
know it now. And that's how your students can teach you a lot. By trying to answer their question you may stumble upon knowledge about the topic
you just didn't have before.

Of course, this doesn't happen every time but it's something you should keep an open mind about. In general, be flexible with your approaches
and adapt to not only the topic at hand but also your students. I think, we all had those teachers back in school, who would just
do their thing and if you didn't understand something they said, sucks to be you. Please, don't be like that.
"My way or the highway" has its place (hi Linus), but teaching is not that place.

Maybe you feel like I'm hammering a lot on this point and that's because it is just that important to me. 
Being adaptable may be the most important skill you can develop as a teacher (I already assume a baseline competence in the topic to teach.)
Presenting the topic in interesting and fun ways certainly is also important, but I see it as another form of adaptability, given that
"interesting" and "fun" are subjective things. 

The same applies to this post. Maybe you find the style of it interesting enough to follow along.
But maybe it would be much better for you, if this post was done differently. Maybe you prefer reading a comic about that, 
maybe a video is a better fit etc. This is an unfortunate fact about teaching content you create in advance. Unlike in a classroom, discord call
or just hanging out, these forms of teaching can not adapt after the fact. You can only try to make it as good as you can in the format you've chosen.
Sure, for some topics, a certain format can automatically be better than another. If you want to explain stuff about videos, a video itself may be
the best way to do it. But in the end well executed content with a worse format can still easily outperform poorly made content with a better format.
So, for the time being I'll stick to blog posts and just try to get better at them.

And as a last advice:

Tell your students to not use AI in the beginning. They need to build up the skills to come to the desired solutions on their own. 
Otherwise they won't be able to validate any output an AI gives them. 
This topic deserves its own blog post but this is my overall position on AI in teaching.
