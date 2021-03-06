## Day 11: 13 Jan 17
#### 9:40 PM
### Upgrade Day

I took Wednesday and Thursday off- Weds I had a lovely neck cramp and Thurs I had to focus on schoolwork. I think I made up for it today, however. I spend most of the day working on a GitHub site so that I can move my journaling to a more polished site.

I tried to set it up on my own but I was not all that successful. The GitHub page that is provided does not have any of the directories found in a full Jeckyll install. I found several articles that showed how to set up Jeckyll locally then sync it with a repo but they skipped a few key steps to make sense out of the whole process.

I created and deleted two times, both with the same unsatisfactory results. After lunch, I ran across the [jekyll-now](https://github.com/barryclark/jekyll-now) repo which promised a quick start through cloning it. At this point, I had deleted [egomadking.github.io/](https://egomadking.github.io/) several times and became numb to the share of the almighty *delete*. With dubiousness, I cloned the repo and set it up to be a GitHub page repo.

It worked!

I now have a site to work with. I spent most of my afternoon and evening looking over the site directory and the SASS files. I have already made a few changes and have more coming. 

At any rate I am going to use [egomadking.github.io/](https://egomadking.github.io/) to continue with my journal. This repo will be used to for 100DaysOfCode references and miscellany.

## Day 8: 10 Jan 17
#### 8:30 PM

Completed "Shortest Word on [Codewars](https://www.codewars.com/r/ob2nNw). The exercises are getting easier. I finished this one in a single setting, or, 1.5 coffee-units. The solution I came up with split the word list into separate words in an array. Each word was then compared to see which was the shortest. I think in an exercise or two, I'll shift my focus out of strings and move to math or arrays. Booleans are wHaTeVer, as are dates. In a few weeks I will start conceptualizing one of my bigger projects.


## Day 7: 09 Jan 17
#### 8:15 PM

Completed "Isograms" on [Codewars](https://www.codewars.com/r/ob2nNw). This exercise required a script that evaluated a string to see if it had 2 or more of any character it contains. If it did, the function returns `false`- as in not an isogram. If each letter was unique, the function returns `true`. The solution consisted of  `for` loop that evaluated a character at the index using the value of the counting variable.

````
for ( var i=0; i<string.length; i++){
	var test = string.charAt(i);
	...
````

Instead of testing each character, I compared `.indexOf(test)` with `.lastIndexOf(test)`. If they came up with different values, I knew that there was more than one character with the value of `test`. I finally put a condition in the function that returns `true` for an empty string because it was needed. No Bothans died to bring you this information.

## Day 6: 08 Jan 17
#### 8:46 PM

As stated yesterday, I continued to work with [Codewars](https://www.codewars.com/r/ob2nNw). I am currently working on "Isograms" which is another search and count exercise. I have been letting Codewars assign me exercises as I complete them so this is just a coincidence. I'll roll with it until I find them easy. Being able to find pieces of content is an important skill to have for a content manager anyways. 

I will be soon moving this journal to a GitHub hosted site. I have a new repo started up for it but I have yet to shape it how I want. I know that Jeckyll requires a certain folder structure to run but that does not appear in the repo. I am not certain if I have to create the structure myself or if there is some other way to set it up. I could easily add the directories myself but I don't want to jack up the site without doing a bit of reading.

## Day 5: 07 Jan 17
#### 11:45 PM

Got some coding in. More [Codewars](https://www.codewars.com/r/ob2nNw), of course. Will explain more tomorrow...

## Day 4: 06 Jan 17
Had visitors this evening- will double-up tomorrow.

## Day 3: 05 Jan 17

#### 2:00 PM
[Codewars](https://www.codewars.com/r/ob2nNw)

- Finished "Printer Errors"

I must look into the different uses of `search`, `indexOf`, `match`, `test`, `filter`. Some will take REGEX while others do not.

The challenge that I completed consisted of counting out of place characters with an then comparing that count with the length of the string. I stuck with`match` to do my counting, but had issues with it when it when it had zero matches in a string. More specifically, `.length` would not accept `null`. To fix it, I ran the string through a comparison looking for any anomalous characters. If it did, then I smacked it with a `match(REGEX).length` to get a count. If there were no anomalous characters, I assigned a counting variable.

```
function printerError(str) {
  var count = 0;
  if(str.search(/REGEX/) > -1){
    count = (str.match(/REGEX/g)).length;
  }
  else{};
  return (count+'/'+str.length);
}
```

## Day 2: 04 Jan 17
#### 06:30
[Codewars](https://www.codewars.com/r/ob2nNw)

- Finished "Dubstep"

I figured out that I was returning an unmodified version of the original string. I had to set the string to a new value before returning it.*This is an approximation of the codewars code. I am not posting spoilers or solutions*
This is what I was trying:

```
function subStrRemover(str){
	str.replace(/REGEX/g, ' ');
	str.trim();
	return str;
```
how I made it work:

```
function subStrRemover(str){
	str = str.replace(/REGEX/g, ' ');
	str = str.replace(/\s\s+/g,' ');
	str = trim();
	return str;
```
how many others did it:

```
function subStrRemover(str){
	return str.replace(/(REGEX)+/g, 'replacement').trim();
```

I seemed to have needlessly soiled the inside of my string with extra spaces. If I used the `+` with my `/REGEX/` I would have avoided extra work. I also learned that you can use several members with an object at one time. I need to look into whether that is a good practice.

#### 9:50 PM
[Codewars](https://www.codewars.com/r/ob2nNw)
- Started "Printer Errors"

Close but I need to figure out how to avoid a null `.length`. A bit cryptic I know but I am tired. More tomorrow.


## Day 1: 03 Jan 17 
#### 11:50 AM
### Thought of another project
I am a recent Calibre convert. I like it because of it flexibility and because it does not hide the ebooks inside of a self-contained database or package. It manages books right in the filesystem through a nested folder structure. I can use Calibre but I can still get to them directly. Nice. One thing that I don't like is that its folder structure uses authors's names. 

Most of the stuff that I have in Calibre are tech books and reference docs- plus I have a bad memory for names. This means that when I browse for an item, it's almost always by the title, not the author. I do not want to change how Calibre does its thing, but I still don't want to have to dig through author folders.

I would like to make a script that listens to Calibre's working folders to make an alias directory by book name. Further, I want to make the script listen for changes then automatically regenerate the alias directory.

#### Allowances
- Can be a script that runs on my desktop (Hazel, Automator, or AppleScript)
- Does not have to update real-time (I would be willing to accept a bit of lag- in minutes, not hours or days.)

#### Challenges
- The directory is on DropBox
- Alias directory should be compatible with mobile clients (I should be able to click on a link inside of my Kindle Fire's DropBox client)
- Do not want inconsistencies to persist or accumulate (recompile directory each time, not update)

#### 9:00 PM
### Worked on:
[Codewars](https://www.codewars.com/r/ob2nNw)
- "Dubstep" - Incomplete- regex is killing me. Will persist tomorrow. Text matching very important to me since I want to work in content management.

## Day 0: 02 Jan 17
#### 9:00 AM
### Today is start day. 
### Big project
So I have an idea that I want to do for a project. Being suitably domesticated and well into a stable relationship, grocery shopping and cooking are routine things. We sit down once a week or so and plan a menu. From that menu we build out a grocery list, excluding what we have in the house.

While this is a bearable errand, I have noticed that we have ended up rotating though a list of 20-30 meals from which we hardly deviate. I have my wife and son to thank for that :-/. My son only eats crap foods and I swear that my wife won't eat anything that she was not introduced to before the age of three. Neither one of them will ever end up on Github so I can talk smack with impunity!

Anything that is repeated is candidate for automation. The project that I have in mind will be a grocery list generator. Using a simple database, all of the meals will be broken into ingredients needed in its recipe. As meals are chosen for the week, the grocery list will populate based on the meal's recipe.  The list will then be editable to take into account items that we already have around the house; there's no need to soy sauce every time it's used, etc.

I am still considering output for this list. I use Wunderlist for groceries and will likely consider [integration](https://developer.wunderlist.com/documentation) with it. I think I will work with output so that there are still options for different services or files.


### Small projects
Since I am still new to all this and have never done more than tutorials on [Codeacademy](www.codeacademy.com) and [freeCodeCamp](https://www.freecodecamp.com/) I cannot just start with the grocery list generator. I know that I want to get myself up and comfortable with JavaScript before I start the big project. In order to do that, I will spend a fair amount of the 100DaysOfCode working on coding challenges. So far I have found a few sites that fit the bill:
- [Project Euler](https://projecteuler.net/)

- [Codewars](https://www.codewars.com/r/ob2nNw)

- [Dailyprogrammer](https://www.reddit.com/r/dailyprogrammer/) on reddit

- [coderbyte](https://coderbyte.com/)

One other thing that I am going to do is move this log over to a  blog. I stumbled across Jeckyll during a web design class and was fascinated by it. Since then I have not had a chance to play around with it because of school work and family obligations. GitHub ties in tightly with this CMS so it seems like I can use this as an excuse to re-visit Jeckyll.

#### 10:30PM

### Today's work
For this evening's coding pleasure, I stuck with [Codewars](https://www.codewars.com/r/ob2nNw). I completed:
- "Even or Odd"
- "Dubstep" not completed- will continue tomorrow



## Day -4: 29 Dec 16

During the winter break I have taken it upon myself to refresh on HTML/CSS and learn a bit about JavaScript. As a SharePoint admin, I'll be putting what I learn to use manipulate page presentation and providing users with widgets. During my studies I came across the 100DaysOfCode and thought I would give it a try.

One of the [articles](https://medium.freecodecamp.com/how-to-get-a-developer-job-in-less-than-a-year-c27bbfe71645) that it references resonates true in that it is not enough to follow tutorials to learn new skills. My thought is that doing tutorials feels a bit like navigating by GPS. Yeah, you'll get to the destination, but you will be following proscribed steps fed turn-by-turn.

One of the things that I used to do when I was younger (and had free-time on my hands [no family, no full-time school]) and moved to a new place was to drive out into the middle nowhere then find my way back home. A full tank of gas, a pack of cigarettes (quit in 2008) and a soda were the only things that I needed to find my way back. By the time I made it back home, I knew my way around the area and found places that I would have known about had I been following an electronic map between waypoints.

I will use the 100DaysOfCode as an excuse, an enabler if you will, to get back into this type of discovery. Along the way I will build a cognitive map of the tools that I choose to work on the the problems I wish to solve.

**Solving problems with:**

- HTML/CSS
- JavaScript
- XML (really digging the sound of DITA)
- JSON (JSON-LD)
- who knows what else...

**Using**
- GitHub
- Brackets/Atom/Sublime Text (don't know which one is for me)

Maybe I will get around to explaining my choices some day. They are not random.

