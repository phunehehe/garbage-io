Garbage-IO
==========

Keep your garbage under control.

Rant
----

Too many times I use the `rm` command and immediately slap myself in the face for accidentally deleting something important. Surely when you go ask for help with questions like "How do I restore files I have just deleted?" the first thing people tell you is "You should have backed it up if it were important.", but that's not going to help. Next you will wonder if there is a trash bin like those you normally see outside of the terminal. This time they will tell you that "real" terminal users don't need a trash bin. Screw that! It doesn't help solve your problem, nor does it keep you from repeating the same mistake.

How does Garbage-IO help?
-------------------------

By replacing `rm` with a command that doesn't actually delete your files until some time later. Does it sound like reinventing the trash bin? Yes because it does. Here are a few things Garbage-IO does that your normal trash bin doesn't:

 * Garbage-IO can be used in a terminal (duh!).
 * Garbage-IO automatically deletes deleted items when certain conditions are met. The conditions can be the total size of the archive, or the age of the item.
 * Garbage-IO can also be used to control those directories you don't really care about, like that Downloads directory.

I want that!
------------

Firstly remember this is very alpha, so edges are rough.

1. Clone the project: `git clone https://github.com/phunehehe/garbage-io.git`
1. Tweak the default settings: `cp /path/to/garbage-io/garbage-conf $HOME/.garbage-conf`. `limit_size` the number of disk blocks used for the archive. Change it to something like 524288, which is roughly 500MB if you have a block size of 4096. Also remove the self reference at the end.
1. Let `garbage-in` replace `rm`: `alias rm=/path/to/garbage-io/garbage-in`
1. Create a cron for `garbage-out`: `0 0 * * * /path/to/garbage-io/garbage-out /home/your_username/.archive`
