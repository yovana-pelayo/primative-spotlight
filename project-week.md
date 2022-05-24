# Project Week Info

## Using Git During Your Projects

### Rules
1. Main branch should be protected -- do not merge or push anything to main unless it comes from a pull request
2. Pull requests should be reviewed and approved by at least one team member who was not involved in the development of the feature


### General Feature Work Flow
1. Pull main so you have the most recent changes
2. Create a new feature branch
```git
git checkout -b my-feature-branch
```
3. Commit work to your feature branch
4. Whenever main moves on, merge main into your feature branch to resolve conflicts as quickly as possibly
```git
git pull origin main
```
5. When your feature feels done, push to github and open a pull request to merge the changes into main

### Resolving Merge Conflicts
Merge conflicts will arise -- its part of working on a team -- you can't avoid working on the same files occasionally. This is why its important to pull main and merge it into your feature branch often. 

```git
Auto-merging [filename1]
CONFLICT (content): Merge conflict in [filename1]
Automatic merge failed; fix conflicts and then commit the result.
```
When you see this, git has identified two changes on the same line and doesn't know how to merge the files. The resulting conflict will look like this on the file that is referenced
```javascript
<<<<<<< HEAD
console.log("i am an edited line on the feature branch")
=======
console.log("i am an edited line on the master branch")
>>>>>>> master
```
If one line is meant to replace the other, then you can just remove the lines and the corresponding merge tags. If you need both changes, you should keep both lines. 

Many times merge conflicts aren't this simple and require you to work with the person whose code you have a conflict with to determine how to merge your changes while maintaining functionality. When in doubt, call in your instructor. 

Also note that VSCode has some functionality built in that will help you resolve conflicts but be aware that more complex conflicts will still likely need to resolved manually. 

## Git Conflict Practice
1. Make a [repo](https://github.com/alchemycodelab/web-template-supabase) called "git-conflicts" and add all team members as collaborators
2. Pick two people to make a new branch and add code to the first few lines of app.js
3. Partner A should make a Pull Request -- someone else approve it and merge it into main
4. Partner B should now try to make a Pull Request - they should be blocked from merging by Github. NOTE: Github might allow you to resolve the conflict ON Github which for this simple exercise might work but for larger conflicts will be challenging. Practice resolving the conflicts in VSCode rather than Github.
5. Parter B should run `git pull origin main` on their branch and then use VSCode to resolve the conflicts.

Repeat this process until everyone feels comfortable managing merge conflicts. 

## Morning Session
1. Practice with Git conflicts for 10-20 minutes
1. Brainstorm your project - spend 20 minutes just throwing out ideas on a Miro board then decide as a team which one you all want to work on
1. Come up with your project "mission" i.e. your big idea
1. Go through the following questions to determine your team agreement:
* What is our collaboration plan? How will we decide which features make it into the app? How will we organize and prioritize features? Will we use Miro, or some other group collaboration tool? How will we decide who works on what feature? How will we decide which features are best for mob or pair or individual work? How will we merge code into the main branch? What is our code review process?
* What will we do when a conflict comes up? When do we decide to ask for outside help?
* How will we make sure that we do not reproduce in this sprint group the patterns that have historically excluded people from marginalized groups from feeling safe, seen, and valued in tech work?
* Given that the best projects are generally produced by the teams who have the most fun, how can we 'keep it light'? What can we do to make sure we look back fondly on this special week? When will we hold our code-free feelings check-ins?
* How did the merge conflict exercise go?
* What tables need to be set up in supabase? What properties do they need? Do any of these tables have relationships to one another? If so, what are the foreign and primary keys? Plan all of this out before building the tables in supabase.
