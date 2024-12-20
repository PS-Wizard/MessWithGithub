## Draw Patterns On Github's Contribution Chart

After looking into some github README.md files for the profile, I came across [Snake Contrib Chart Eater](https://github.com/marketplace/actions/generate-snake-game-from-github-contribution-grid). That was cool but its implementation was a bit of a hassle. But that gave me an idea to create this, a program that allows you to draw anything on the github's contribution chart. 

# Installation / Usage
```bash
 git clone https://github.com/WizardOfOz-1/MessWithContribChart
```
## To use, run the program with 
```bash
 go run main.go
```
The program will then prompt you for inputs,
```bash
[nathan@archlinux TextToCommitHistory]$ go run main.go 
Enter Year: 2024
Enter Draws (e.g., 2/5-2/9,2/11): 2/5-2/8,3/11,3/12
Enter Offset (e.g., 1 for next day, -1 for previous day): 0
```
in the above example, Ive set the year to be 2024. The Second Prompt is the dates for which you want a commit to happen on. This can either take a range something like:
```bash
2/5-2/7
```
which will generate commits on the dates feburary 5th, 6th and 7th 
Or you can specify individual dates like:
```bash
3/9
```
which will generate a commit on March 9th of **whatever** year you specified in.
Or you can mix them both at once
```bash
Enter Draws (e.g., 2/5-2/9,2/11): 2/5-2/8,3/11,3/12
```
The Above input will generate a commit on feburary 5th,6th,7th,8th, March 11th and March 12th
Finally, The Offset Prompt:
```bash
Enter Offset (e.g., 1 for next day, -1 for previous day): 0
```
will offset the dates by x number that you provide, so say if i had 
```bash
Enter Draws (e.g., 2/5-2/9,2/11): 2/5-2/8
```
The commits now will be on 6th, 7th, 8th and 9th of feburary.

# Pro Tip (lol):
### Change Colors:
If You Want A Different Shade Of Green, Just Paste The Prompt Generated By The Code Multiple Times. 

### Easter Egg:
When i said  "it will generate a commit on March 9th of **whatever** year you specified in.
Or you can mix them both at once", I meant **Whatever year**. ( Well, any year after 1968 ).
If you specify the year to be in 1969, your profile's contribution section will now range all the way back to 1969 (Could be a cool flex just sayin). ( If it doesn't allow you, saying invalid date format, put the year in as 1970 and play around with the offsets and the Timings a bit)

# To Commit:
So after you filled the prompts, the program will print out something like
```bash
GIT_AUTHOR_DATE="2024-02-05T00:00:00" GIT_COMMITTER_DATE="2024-02-05T00:00:00" git commit --allow-empty -m "2024-02-05T00:00:00"
GIT_AUTHOR_DATE="2024-02-06T00:00:00" GIT_COMMITTER_DATE="2024-02-06T00:00:00" git commit --allow-empty -m "2024-02-06T00:00:00"
GIT_AUTHOR_DATE="2024-02-07T00:00:00" GIT_COMMITTER_DATE="2024-02-07T00:00:00" git commit --allow-empty -m "2024-02-07T00:00:00"
GIT_AUTHOR_DATE="2024-02-08T00:00:00" GIT_COMMITTER_DATE="2024-02-08T00:00:00" git commit --allow-empty -m "2024-02-08T00:00:00"
GIT_AUTHOR_DATE="2024-02-09T00:00:00" GIT_COMMITTER_DATE="2024-02-09T00:00:00" git commit --allow-empty -m "2024-02-09T00:00:00"
```
Now, Create a new github repository , make it public. It doesn't have to contain anything apart from a README.md ( cause you cant have an empty repo ), for reference [My Github Repo](https://github.com/WizardOfOz-1/WriteOnGithubChart). After that just clone that repo with 

```bash
git clone <Link to your github repo>
```
and paste whatever the program generated for you. Then, 
```bash
git push origin main
```
and voila, the contrib chart is your canvas, Though Id Suggest You Be More Creative Than me:
![LOL](https://github.com/WizardOfOz-1/MessWithGithubLol/blob/main/assets/screenshot-20241022141647.png?raw=true)
