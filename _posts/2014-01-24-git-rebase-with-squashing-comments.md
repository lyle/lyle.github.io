---
layout: post
title: Git Rebase to Squash Comments
---

{{ page.title }}
================

# I love me some git with extra content

Personally I don't mind having my git repos full of all of my minutia:

    Added support for direct navigation
    Fixed spelling mistake on button for dircet nav
    Really fixed spelling mistake
    Should stop coding so late - diretc > direct
    
But at times those little changes don't tell us much about the code. And, even if I plan to keep my working branch alive for that deep narrative navel gazing I still want a clean master without all of this verbosity.

# Using rebase for great win!

So when you want to 'squash' those comments down try the 'rebase' command. But be careful, rebase is not like most git commands, it will re-write history. So don't use this tool if you have done any pushes as your tree will not be the same after.

    git rebase -i HEAD~4 

This is the interactive command - the 3 is for "the last 3" commits and will give you this in your editor of choice:

    pick Added support for direct navigation
    pick Fixed spelling mistake on button for direct nav
    pick Really fixed spelling mistake
    pick Should stop coding so late - diretc > direct
    
    # Rebase 93e8a3..2433d2 onto 39e392
    # ....

The top of this list is the oldest commit included in your HEAD~* param. And you need to pick at least that one. The rest can be 'squashed'.
Any squashed commits will be merged into the previous commit. And you can rename the commit after this step.
So, change the file to:

    pick Added support for direct navigation
    squash Fixed spelling mistake on button for direct nav
    squash Really fixed spelling mistake
    squash Should stop coding so late - diretc > direct

Save the file and exit. Git will now step you into the commit message for each commit you picked. And you can rename the commits.

    # This is a combination of 4 commits.
    # The first commit's message is:
    Added support for direct navigation
    
    # This is the 2nd commit message: 
    Fixed spelling mistake on button for direct nav
    
And it goes on. All of the '#' lines will be left out of the new rebased commits. So you can comment/delete all the old comment lines and make your new (and correct) commit message:

  Added direct navigation support
  
And save and exit. Rebase with rename and removal of commits. 

Yeah! 

Becareful of your new power.
