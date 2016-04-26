# The Learn CLI Workflow

## Overview

The deep integration of Learn, Git, and GitHub makes it possible for all of the work you do on Learn to be stored and version-controlled by GitHub behind the scenes, just like professional software.

We'll eventually introduce you to all of the Git mechanics that make this work. But for the purposes of getting started on Learn quickly, we've created some convenient tools to make it easier to move through our curriculum.

You'll use the same workflow to solve every lab on Learn. It involves 3 steps:

1. Opening the lab.
2. Working on the lab until you get all tests to pass.
3. Submitting your solution.

Let's walk through the process. For now, just read along. **You don't need to actually perform any actions right now**. You'll have the opportunity to practice this entire workflow in the next lesson!

## Opening a Lab

**Key takeaway: Use the Open button to get started with a lab.**

Getting to work on a new lab is very simple: you'll want to simply click the "Open" button on the toolbar when you're in Learn on your web browser. 

Note: This button is only active for labs and will be inactive for lessons that do not require coding to pass.

![Learn Open](https://s3.amazonaws.com/learn-verified/LearnOpen.png) 

This will launch the Learn IDE application.

### What does the Open button do?

1. It uses the GitHub API to "fork" the lab on your behalf. This means it creates a copy of the lab's repository for you and associates it with your GitHub account.
2. It then "clones" that copy of the repo down to your Learn IDE automatically, so that you have a copy of the source code to work with. This is what you'll be using to solve the lab.
3. It then "cd's" into the lab's directory so that you're ready to go.

## Solving a Lab

**Key takeaway: use the `learn` command to run tests until they all pass.**

Once you've opened your lab in the Learn IDE, you'll be ready to start solving it. This is the fun part!

All of the labs on Learn are written with an RSpec test suite that you can use to confirm that you've fulfilled the requirements of the lab. RSpec is a testing library that ruby developers use everyday, so again, as you work on Learn, you're also learning the same tools and workflows that developers use.

## Test Driven Workflow

When you work on a lab, we recommend the following workflow:

### 1. Reading the README

Read the lab's README on Learn and get a sense of what the lab is about and what it is asking you to build. Read the entire README and then work on the lab.  As you hit hurdles you'll have some context on where to look for clues and hints in the README.

### 2. Run the tests with `learn`

Before doing any work, run the test suite from your local clone with the `learn` CLI command. From your terminal, in a lab's directory, run `learn`. You'll see something similar to:

![Failing Test](https://s3.amazonaws.com/learn-verified/LearnRunningLearrn.png)

I know error messages or failure messages are intimidating, but try to read them. Developers are detectives, constantly sleuthing for the bug that's the culprit. Errors and failures are our clues, they illuminate the path forward.

We know that the idea of "things being broken" is frightening at first. Broken things are stressful and frustrating! But guess what? As an engineer, as a programmer, the default state of anything you work on is broken. The things you are programming are always broken. Get used to it. Your job is to fix broken things. You can do it. If your code isn't broken, if your code works, you are no longer programming. Your job is done. Things work. Embrace the errors. The obstacle is the way.

### 3. Read the tests

Read the test suite in `spec/`. Open up the lab in your text editor, open the files in the `spec` directory that are not named `spec_helper.rb`. `spec_helper.rb` is a helper file to configure your tests which you can ignore. Any file in `spec` that ends in `_spec.rb` though is a test file and while testing code and RSpec are advanced, we believe the semantics are easy to understand, the meaning of the test is comprehensible, even if the code is not.

For example, soon you'll be solving your first lab. The lab includes a file `spec/first_lab_spec.rb`. The contents will be:

```ruby
describe 'First Lab:' do
  it 'you made a change' do
    new_file_made = Dir["*"].size > 5
    file_edited = !File.read("./edit-me.txt").empty?
    expect((new_file_made || file_edited)).to be_truthy, "Make sure you have added a new file or edited edit-me.txt"
  end
end
```

Read it through and see what meaning you can extract from it.

You haven't even written a line of code yet and we're asking you to read some very abstract and complex code and try to reach for any footing or understanding. We believe in you. We believe you can infer and deduce and understand a bit of the code above, even with no experience. Your mind is incredibly powerful. Challenge yourself and confront the unknown. That's how learning works.

Beyond all the syntax and code above, can you decipher what we're asking for? What the lab requires you to do? How the test works? Again, even if you only get 10% of the expectations of the test, that's still something. And while you do that, 4 things will happen.

1. You'll have 10% more understanding of how to solve the lab.

2. You'll get better at reading tests and we bet that the next test you read you'll get 12% of it. You'll constantly see improvement through old fashioned practice and determination.

3. Almost unconsciously, like Mr. Miyagi in the Karate Kid, you'll actually learn how to read and write tests proficiently, "Wax on, wax off" style.

	![Wax On, Wax Off](https://38.media.tumblr.com/a5dc9f34d87226be8f31f5c982c8af7b/tumblr_mklzm4VeUq1rwt2uzo1_500.gif)

4. You'll have learned Test-Driven-Development, TDD, one of the most sought after skills of a professional developer.

This cycle, reviewing the README, running the tests, reading failure messages, reading the tests, editing your code, and trying it all again, is how you are supposed to code, it's what programmers do all day. We break things, we define the error with a test, we fix the code, we pass the test, we repeat.

### 4. Write Your Code

After forking and cloning the lab, opening the lab in a text editor, reading the README, running the test suite, reading the errors, and reading the tests themselves in `spec`, you're ready to code. You've armed yourself with every weapon available in the arsenal of your intellect and we know you can program triumphantly.

You should understand the point of the lab.

You should be able to identify the objectives and topics the lab is exercising so you can google for more information.

You should know the expected behavior or outcome of the solution.

You should know what files you need to create or edit.

You should know what those files and code should define, provide, and do.

You should constantly save and test your code with every significant change.

You should read error messages and glean insight into the solution with every new failure.

You should keep on trying until you get it working. It doesn't matter how many times you fail as long as it is one less than the times you tried.

You should ask for help on Learn.

Programming is never about getting it all right at once. Programming is like solving a puzzle, you don't try to put it together immediately, you approach it one piece at a time. The workflow we're describing optimizes this process, trial and error, attempts and feedback, insight through failure. Most of our time as programmers is spent staring at error messages and code wondering, "Hmm".

#### Programming in Movies vs Real Life
<iframe src="https://vine.co/v/hPXTA6l9AqQ/embed/simple" width="600" height="600" frameborder="0"></iframe>

### 5. Pass your local tests with `learn`

Follow this workflow: running tests, reading errors, writing code, saving code, running tests, reading errors, consulting the README, googling for more context on a topic, writing more code, saving the code, running the tests again, reading errors, and repeat. You'll get it, you'll surprise yourself and find a confidence within you. And if you're stuck or tired and just need some help, Ask a Question, Study Groups and the Learn community will be there for you.

Eventually your local tests will pass and Learn will indicate your success.
![Pass](https://s3.amazonaws.com/learn-verified/LearnChangingCode.png)

On the left is a passing test run in the terminal. On the right is what the right column in Learn looks like for a passing local test (which we currently call a "Local Build").

When your local tests are passing, you'll be ready to submit the lab.

## Submitting a Lab

**Key takeaway: use the `learn submit` command to submit your solution.**

Once you've written the code that solves a lab, and confirmed that your solution is correct using the `learn` command, you then need to submit your solution to Learn so that you can get credit for completion and move on to the next lesson.

In order to submit your solution to Learn, from the lab's directory in your Terminal, you will just need to run:

```
learn submit
```

That's all it takes. You can run `learn submit` from any lab directory and your solution will be submitted to Learn for review.

![learn submit](https://s3.amazonaws.com/learn-verified/LearnSubmit2.png)

You'll notice that on Learn, the light labelled "Pull Request" will turn green when your code has been submitted, the lab lights will fold away and a "Share your Success" button will take its place. Click on it to let your friends know about a job well done!

![PR](https://curriculum-content.s3.amazonaws.com/intro-to-learn/share-button-animation.gif)

![sharemodal](https://curriculum-content.s3.amazonaws.com/intro-to-learn/sharemodal.png)

## Conclusion

To summarize, the workflow you'll be using to solve labs on Learn:

Use the Open button to clone the lab to your Learn IDE so you can work on it.
Use `learn` to run your local tests.
Use `learn submit` to submit your solution.

And always make sure you have a working Internet connection so that you can save and submit your labs. 

You are now ready to practice the Learn workflow with your first lab! Congratulations!

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/learn-workflow-ide'>Learn Workflow</a> on Learn.co and start learning to code for free.</p>

<p class='util--hide'>View <a href='https://learn.co/lessons/learn-workflow-ide'>Learn Workflow</a> on Learn.co and start learning to code for free.</p>
