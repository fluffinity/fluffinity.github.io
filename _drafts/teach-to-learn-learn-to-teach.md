---
layout: post
title: "Teach to learn, so learn to teach!"
categories: update
---

We all learn every day even if we are not noticing it. Programming is no exception. But there is a difference in how fast and how much we learn.
You can become a good programmer by studying yourself and coding a lot.
But I believe that you can not become a great one unless you are also able to bring someone else to your level.
Only if you can teach another person your learned skillsets, you have really mastered them. 
In the process you will need to think about the topic in a lot of ways and that will give you a more complete view of it. 
In turn this means you will also learn a lot about what you try to teach. And some of this new kowledge may surprise you even after years of experience.

So lets dive into the art that is teaching!

## Ok, but why should I listen to you?

As with anything anyone tries to tell you, you may listen to it and then decide whether you want to believe it. 
But to give you some reason to believe me, I have been programming for 10 years now, from late high school throughout my B.Sc in CS and now at work.
For 6 of these years I have been a tutor in various classes at university. 
From introduction into programming, software development and programming languages to datastructures and efficient algorithms,
formal languages and computability as well as GPU programming. And in these 6 years I taught more than 200 students, 
graded their assignments and exams, observed their accomplishments and struggles and got confronted with many different questions.
They would range from expectd problems, like how properly synchronize threads, to stuff we would dismiss as "trivial". More to that below.

And if you think that it should have been fairly easy to teach these students, because they are at an university, think again. 
It didn't matter whether a student was in their first semester or if they were short of finishing their master. 
The former could easily be much better than the latter. The correlation between years of study and actual knowledge was a weak one at best.
Even when I taught in advanced courses I would almost alwazs have students, who barely understood the basics of not just the course, but CS in general.
Needless to say, it was hard. But it became easier over time, due to me getting more experienced in both, 
the material itself as well as how to teach it to others. Over time I learned to teach.

So while I don't have a long list of open-source projects I point to for my resume, I do have a lot of experience in bringing knowledge to others.

## What even is the difference between `return` and `print`?

Yes, this is a question I had to answer once. It was in one of the beginner courses and the students had just learned about functions. 
So far they used Python and only used it inside Jupyter Notebooks. If you don't know about them, good.
I hope you will never have to work with them yourself. In essence, you have "cells", in which you can write your code, and you can execute these cells. 
If you print inside these cells the output will be shown below it. But you will also get an output for the last computed value in this cell.
So if your last line is something like `x + 5` you would get an output like this `output: 10`. Lets have some sample code for further explanations:

{% highlight python %}
def calculate_area(radius):
    return radius * math.pi
# some code...
print("Some output")
# some more code...
{% endhighlight %}
Now imagine the last line of the cell is `calculate_area(10)`. What do you think the output will be?

Yes, we will have the return value of the call to `calculate_area` in the output. 
So by returning a value the student got it output in the same place as the stuff displayed with `print`.
But if both lands in the output, then what even is the difference between `print(radius * math.pi)` and `return radius * math.pi`?
It just wouldn't be obvious, given the example and the environment.

With that I hope I convinced you that nothing is truly obvious or trivial for everyone. 
While we can argue that the way Python was introduced in the course is not good, that they shouldn't have used Jupyter etc, 
nothing changes the fact, that for this student `return` and `print` seemed to do the same. 
And so the for us should be "How can I explain the difference?"

## Explaining the seemingly obvious
