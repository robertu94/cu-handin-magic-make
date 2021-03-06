# About #

Magic Make is a Makefile that interacts with Clemson University's [web handin
system][handin] for turning in CS projects. Some of its more notable features
include...

- A `make remote` rule that copies your working directory to a McAdams lab
  machine (it won't copy Git repo data) and executes `make labtest` (from the
  same Makefile!) on the remote machine.

- A `make handin` rule that packages your project files into an archive and
  submits it to handin for you.

- A `make handout` rule that connects to a lab machine, checks out the most
  recently submitted version of your project, and runs `make` on it.

You might find this Makefile especially spiffy if you, like me, compose your
programs on a local VM and would rather not copy files manually (`scp`? Ugh!)
when it comes time to test.

# Usage Instructions #

1. Make sure Mercurial is installed on your machine. The Mercurial executable
   is `hg` -- run `hg -v` to check your installation. The McAdams lab machines
   have Mercurial pre-installed. To install on Debian/Ubuntu, use `sudo apt-get
   install mercurial`.

2. Make sure handin likes you. Follow 
   [these instructions](https://handin.cs.clemson.edu/help/students/hg/setup/) for both your
   development machine and the lab machines.

   To use `make remote`, you'll also need to make sure you can automatically
   `ssh` to the lab machines from your development machine. 
   [Here's](http://www.linuxproblem.org/art_9.html) a decent tutorial.

3. Grab the Makefile. You can either `git clone` this repository
   (`git@github.com:ProtractorNinja/cu-handin-magic-make.git`), or just download
   the Makefile manually from here -- it's the only file you'll need anyway.

4. For each project, you'll need to adjust the Makefile a little. Go to the web
   Handin page for your project, and copy the contents of the textbox labeled
   "Mercurial Repository URL" into the `REPO_URL` variable. Update the rest of
   the variables as needed (especially the empty ones!).

5. Run `make handin`. Look for anything that sounds like an error, and check to
   see that your archive is up in web handin.

6. Try out `make remote` and `make handout`. They should complete with a demand
   to update the `labtest` and `all` rules.

7. You're done! Just fill in the rest of the Makefile with your own rules. Good
   luck on that project!

[handin]: https://handin.cs.clemson.edu/courses/

# License #

The MIT License (MIT)

Copyright (c) 2014 Austin Anderson

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

