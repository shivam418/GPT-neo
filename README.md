what's happening guys my name is
shivam garg and in this tutorial
we're going to be taking a look at a
ipad text generation using
a gpt3 clone called gpt neo in
just four lines of code let's take a
deeper look at
what we'll be going through so first up
what is gpt3
well gpt3 is a deep learning powered
language model
trained on 175 billion parameters
by open ai now this means that it would
take a
huge amount of time to train something
as sophisticated as this on a consumer
gpu
the amazing thing about this particular
model is that it's really really
flexible and performs really really well
on
a range of natural language tasks
specifically like text generation
q a sentiment and classification now
the unfortunate thing about gpt3 is that
it is only available through a closed
beta
the great thing however is that you're
able to leverage a gpg3
clone called gpt neo now the model that
we're going to be taking a look in this
particular video
is trained on 2.7 billion parameters so
it's not exactly the 175 billion
parameter model the open ai built but it
is really really sophisticated and
you'll see that a little bit later so
let's take a look as to what we'll
actually be going through so first up
How it Works
what we're going to be doing is
installing gpt neo so gpt neo is going
to give us a gpt3
clone which is trained on 2.7 billion
parameters and can definitely be
fine-tuned so if you'd like to see a
video on fine-tuning this
by all means do let me know so once
we've installed it we're going to be
able to generate text
in just four lines of code so it's
really really straightforward and what
we'll also do is we'll save that output
to disk so you can pick it up as a text
file and leverage it later on
now you're probably thinking how is this
all going to work well let's take a look
so first up what we're going to be doing
is we're going to be leveraging the
hugging face transformers library to
load
our pre-trained gpt neo model then we'll
pass through a text prompt so say for
example we might ask
what is the meaning to life import
pandas is pd if we wanted to generate
python code
we could even generate some sql
statements as well and then once we've
generated that text or once our models
generated that text will then be able to
output that result to a text file using
a standard python with statement
ready to do it let's get to it alrighty
guys so in order to get started with gpt
nero there's going to be
four things that we need to do now we're
going to keep this tutorial
relatively short and sharp we're just
going to power through it and ideally
by the end of this you should be able to
get up to speed with gpt neo and start
generating some of your own text so the
four things that we need to do
are install and import our dependencies
set up our pipeline or our generator
then pass through some text and generate
text using a prompt
and then what we're going to do is
output that text and save it to a file
Install PyTorch and Transformers
so first things first let's go ahead and
install and import our dependencies now
the first dependency that you're going
to need
is pytorch so the easiest way to install
this is if you just go over to the
pytorch website so pytorch.org
and again all the code for this as well
as links to relevant documentation will
be in the description below so you can
pick this up and run with it
so what we're going to go on ahead and
do is go to the pytorch website and then
towards the bottom you're going to see
this section called
install pytorch now all we need to do
here is choose
the build that we want so we're going to
choose stable in this case
choose your operating system in this
case i'm on a windows machine so i'll
choose windows
choose what package you want to install
so i'm going to use pip but you could
use conda
as well if you wanted to in this case
we're going to be working with python so
we're going to choose python
we're leveraging gpu acceleration using
cuda 11.1
now gpu acceleration really isn't going
to kick in unless you've got a massive
gpu that's
able to handle this particular model but
that's fine we'll install it using cuda
11.1 anyway
so once we've got that you're sort of
going to get this command down the
bottom here so i'm just going to copy
this
and paste it into my notebook now in
order to run
a command line within your notebook you
just need to include an exclamation mark
and i'm just going to remove the three
from the pip command because i'm just
using standard pip and then all we need
to do is just run this cell so that's
going to go
ahead and install pi torch now i've
already got it installed so it went
relatively quickly
so that's our first install done so
installing pytorch remember all you need
to do is go to pytorch.org
select your different options and copy
that command run it in a cell
now the next thing that we need to do is
actually install transformers so
transformers is a
really powerful and probably one of my
favorite natural language processing
libraries
and the beautiful thing about
transformers is that you get a bunch of
these pipelines so you get a
conversational pipeline feature
extraction pipeline
text generation pipeline a translation
pipeline a whole bunch of pipelines that
allow you to leverage
really really sophisticated nlp models
relatively easily so we're going to be
using
transformers exactly for that so let's
go ahead and install transform so this
one's relatively straightforward
so in order to install transformers all
we've gone and done is run
exclamation mark pip install
transformers and that's going to go on
ahead and install
all of this good stuff here for us so
Setup GPT Neo Pipeline
those are our two dependencies
now installed now all we need to do is
import our main dependency which is
going to be transform
so let's do it
okay so that is our transformers library
now imported so in order to do that i've
written from
transformers import pipeline so this is
our first line of code so first line
now this pipeline over here is
effectively going to be giving us
all of these pipelines available now
we're going to be using the text
generation pipeline
so in a second you'll see that we pass
through the text generation
argument to that particular pipeline to
be able to leverage
our text generation using gpt near but
again if you want to deeper dive into
this by all means do let me know in the
comments below i was thinking a mega
tutorial might be useful for gpt
might also be useful for transformers
particularly transformers because
there's a bunch of stuff in here
now in this case that's our pipeline now
imported now what we need to do is set
up our generator so we're going to write
a second line of code
alrighty that's our second line of code
now done
and dusted so this line of code here is
actually going on ahead and
loading up our gpt neo model which is
going to give us our gpt3 clone
so in this case what we've written is
generator equals pipeline and then to
that pipeline we've passed what type of
pipeline we want
in this case we're going to be
leveraging the text generation pipeline
so to do that we've written
inside of a string text dash generation
and then i've passed through a comma and
then i've pass through a keyword
parameter so this next keyword parameter
is what defines
what type of natural language model or
what type of language model you're going
to be loading into that pipeline
now in this particular case we're going
to be leveraging the gpt
neo model with 2.7 billion parameters
so to do that we've written eleuther a i
forward slash
gpt dash neo dash 2.7
b so this means that we're going to be
leveraging the eluther ai which are the
guys that have actually gone and built
the gpt neo model
and then by passing through slash gpt
neo dash 2.7
b we're importing the 2.7 billion
parameter model
now if you're doing this for the first
time it's actually going to download the
model so i believe it is about
10 gigabytes so it might take a little
bit of time to download
but it will do everything that you need
to do for you so you don't actually need
to go and do anything else it will just
download it for you onto disk so you're
able to leverage it
there is also a 1.3 billion parameter
model so if your computer is running a
little bit slow and you wanted to run a
smaller model you can do that
so let's let that go on ahead and load
and then
we'll be able to run our model
okay so that is our generator now loaded
so you can see here that that particular
cell is run so we're no longer have a
little asterisk in there so we're now
able to run it within our notebook
Generate Text from a Prompt
the next thing that we're actually going
to go on ahead and do and so this is our
second line of code
second line next thing that we're going
to go ahead and do is start generating
some text using a prompt now this prompt
could really be whatever you wanted to
so if you wanted to write a love story
write a poem
and get some answers to what is the
meaning of life this is where you could
pass it through
so in this case what i'm actually going
to do is let's start off with that so
we'll type in what is the meaning of
life
and what will actually happen so let's
just make sure this is prompt
so what will actually happen is when we
pass this prompt to
our gpt neo model it's actually going to
try to generate text
using that prompt so you'll actually see
that it's trying to answer that maybe
write a bit of a blog post and you'll
actually get some answers generated
using the gpt model which i think is
absolutely fascinating
but anyway let's actually go on ahead
and do it so what i've done is i've
created a new variable called prompt so
p-r-o-m-p-t and then i've just set that
equal to a string
and you'll see in a second we'll change
the string we'll try generating some
other styles of text maybe some code as
well
then what we need to do is actually pass
that prompt to our generator to be able
to actually generate code so let's do
that
alrighty before we go ahead and run that
next line of code let's take a look at
what we actually wrote let's actually
include some additional cells so we can
see this
so this is our third line of code up
here this
is our fourth line so after this we'll
actually have our generated text
of fourth line now in
this particular case what i've gone and
done is created a new variable called
res
for results and then i've set that equal
to our generator so in this case you can
see that we set up our generator here
what we're doing now is passing some
arguments and keyword arguments
to that particular generator to generate
text so
here what we've gone and written is
generator and then to that we've passed
through our prompt which is this
string over here then we've just gone
and set some keyword arguments so you
can play around with these if you wanted
to and this will
influence the results you get back so
the first argument
is max underscore length equals 50. so
this defines how long
your output is going to be in this case
i've set it to a limit of 50.
then i've passed all 50 words then the
next keyword argument is do
underscore sample equals true so this is
going to allow us to leverage sampling
within our model
and then we've also gone and set our
temperature to 0.9 so this influences
how it actually determines results going
forward from
a particular token that it's actually
had returned back
so again you can play around with these
parameters tune them play around
take a look at the documentation again
this tutorial is going to be super fast
and we're not going to delve into it too
much
but on that note let's go ahead and run
this line and generate our text
okay so that line of code is now run now
the speed of which that actually
generates is really dependent on your
machine
so in my case it took about 20 30
seconds to generate
a string with a max length of 50 words
but in this case if you were to pass
through a higher maximum length number
it will take longer
now what we can actually do is take a
look at our results if i type in res
down here
you can actually see that it's gone and
generated this big block of text so you
can see that it's gone and says what is
the meaning of life
why does it matter oh it's not exactly
that happy at the moment
where do i go to find the meaning or at
least some sort of explanation for what
i'm experiencing here and now
i've been asking this a dozen times now
now if we actually go
and pass this result so if we grab the
first result and type in
dot generated text this is actually
going to give us our raw string so you
can see and if we print this out we'll
get our string formatting
so you can see we've actually got our
line spaces so in this particular case
just by passing through this short
prompt we've gone and got this entire
result out now if we wanted to generate
more text we can just
change the maximum length so say i set
it to 100 run that again
we're going to get a longer string
generated so let's let that go on ahead
and run and then we'll
ideally get a longer answer to what is
the meaning of life
there you go so it's now gone and
generated a new block of text so all we
really did there is we changed the max
length parameter
and in this particular case it's gone
and generated a bigger block of text so
what is the meaning of life so it still
starts out with that prompt in a recent
conversation with a friend
i heard him say you must go through life
with the attitude that you are never
going to leave
i had to check on whether he actually
said this to me or if it was in the form
of a quote or something similar i
decided to find the original source of
this quote after reading about it in a
book on self-help
quickly found a website so in this case
it's writing a slightly different
it's going down a completely different
route but again this is just
a random property say for example we
wanted something a little bit more
contextual where so i'm going to set
our max length back to 50 and what if we
said
something about bitcoin so if we said
bitcoin
is going to and then rend that
particular
prompt so if we run that now let's go
and see what gpt neo
now generates
there you go so it's now gone and
generated a new text so if you take a
look it's gone and written bitcoin is
going to be the most important currency
in 2020.
the crypto market is on the rise and
bitcoin has gone from a joke in late
2016 to the world's favorite
cryptocurrency in 2018. well it's not
wrong
i mean 2021 and it's super popular
there's been a massive rally in 2018 and
2019 and again we've cut it off at 50
but you can see that it's actually
generating some really really
interesting text results now you could
use this to generate blog posts maybe
write a song write a poem so on and so
forth
but my particular favorite thing is
actually using it to write some code
now i was testing this out earlier this
week and i thought it was super
fascinating
so instead of writing our prompt as text
what happens if we wrote
one of the most common lines of code
that i wrote so import pandas
as pd and run that now
so let's go and see if it actually goes
and generates some valid python code
and there you go so what it's actually
gone and written is import pandas is pd
which was our original prompt
but then it's gone and passed through a
bunch of additional imports so from
collections import counter import os
import sys import numpy is np so it's
almost like it's importing some pretty
standard
data science libraries i mean the fact
that it's got numpy it's got time
it's got nltk down here so you can see
that it's actually really really
contextually aware
and it's able to generate a whole bunch
of stuff i'm probably going to be
playing with this
all weekend but you can sort of see
what's possible with gpt neo
Export Text to File
now if you wanted to go on ahead and
export this text
you could do that really easily so let's
go ahead and do that
okay so before we go on ahead and run
that so i just want to sort of show what
i've written
so with open and then to that we've
passed through the name of the file that
we want to generate or output
so in this case i've called it gpt text
dot txt so you can see that there
and then we've passed through the w flag
because we want to write it out
and then we specified as f so this means
that we're going to be able to work with
our file as a variable called
f then in order to write out our text
i've just written f
dot write lines and then i've passed
through this text block here
so this text block is exactly the same
as what we were printing out up here now
we're just outputting it so if we
actually go and
run that block of text and if we take a
look at the folder that we're working in
let me bring it up
you can see that we've now got this file
called gpt
text if we zoom in a little bit so you
can see that better
so you can see that we've got gpt text
there and if we actually go and open
that up
you can see that it's exported all of
our python code so maybe you could write
that use this to write an
entire data science workflow who knows
what's possible and where you can take
this to
and again if you wanted to use a
different prompt so say for example we
wrote something about the current stock
market
current stock market
and just run that we could now go
and export different blocks of text so
again whatever you pass around that
prompt
this particular workflow is going to
output that to a text file
so let's let that run and we'll take a
look just to make sure that it's now
outputting our new block of text
so there you go so what we've now gone
or what gpt's now gone and written so
is the current stock market is a unique
market in that it incorporates some
fundamental market characteristics
correct
uh together with market psychology human
judgment
and human biases such as market timers
price momentum and crowd psychology
the stock market is like any market for
goods and services and if we go and
check out
our file so you can see that it's now
gone and exported the text that we had
exactly as we had inside of our notebook
pretty cool right so this sort of shows
you what's possible with gpt neo in a
nutshell now again
all we did is we installed and imported
our dependencies so we went and
installed pytorch and transformers
and then we wrote four lines of code to
allow us to go and generate our new
blocks of text using gpt neo so we wrote
our
import our generator our prompt and then
we actually went and ran our prompt so
again really really quickly you're able
to get up to speed with this
and then you're able to output this text
so again you might take this further you
might use this to automatically post
to a wordpress website you could
generate uh
different articles you could generate
blog posts i don't know research papers
there's a whole bunch of different use
cases that are possible for gpt neo
on that note that about wraps it up
Wrap Up
thanks so much for joining guys
hopefully you enjoyed this video if you
did be sure to give it a thumbs up hit
subscribe and tick that bell
and let me know how you went with
leveraging gpt neo i'd love to hear your
thoughts thanks again for tuning in
peace
