+++
title = "Lessons Learned: A Developer's Guide to Best Practices and General Guidelines"
date = "2023-03-25"
author = "Syed Sanzam"
cover = "img/team-colab.jpg"
description = ""

+++

I have been fortunate enough to work on projects with varying levels of complexity and code quality. Some codebases are
pristine, following every best practice and convention, while others might as well be written in hieroglyphics. However,
one factor trumps them all: _**the number of users**_.

If a software product has a smaller userbase, pushing changes to production isn't usually a big deal. But when you're
dealing with millions of users, downtime becomes a crucial factor, and deploying changes requires collaboration across
multiple teams, including Operations, QA, DevOps, and of course, Developers. When there's a tight deadline and the
business is on the line, things can get murky and complicated quickly.

Having experienced the challenges of writing and deploying code, I understand the value of having a reliable set of
guidelines to follow. With this in mind, I have taken the initiative to compile a list of crucial tips to aid in
navigating the intricacies of managing downtime and meeting deadlines. This resource is not only intended for your
benefit, but also serves as a personal reminder for myself.

## Adding Value Without Disrupting Stability

Developing a large enterprise software product that has been around for years requires a different approach compared to
newer projects. While best practices are always useful, following them without proper consideration can have unforeseen
consequences, particularly when it comes to production.

One example is the **Boy Scout Rule**, a popular guideline used in software development that encourages programmers to
make
incremental improvements to the codebase with each change. While it may work well in smaller projects, implementing this
rule without proper alignment with other teams, like Quality Assurance and Operations, can cause issues in large-scale
software products. Making changes to the codebase without proper testing can introduce new bugs that may impact users,
and deploying changes without coordination with Operations could lead to unexpected downtime or outages.

In such scenarios, maintaining a balance between code quality and product stability is crucial. Best practices, such as
the Boy Scout Rule, may need to be adapted or modified to suit the specific needs of the product and teams involved. In
the end, the aim should be to continuously improve the product's quality over time while keeping it stable and reliable.

As a developer working on a software product with a large userbase, it's important to consider the impact of every
change made to the codebase. While it may be tempting to follow best practices blindly, adapting them to suit the unique
circumstances of the project and teams involved is the key to success. By striking a balance between code quality and
stability, developers can ensure that the product remains reliable while improving it over time.

When introducing any new code, I keep the following points in mind:

+ Prioritize readability and maintainability over insignificant performance gains. It may be tempting to break coding
  conventions for small improvements in performance, but doing so can make it more difficult for other developers to
  understand and debug the code. Consistency in coding standards can save time and effort in the long run. Additionally,
  it's important to avoid making unnecessary changes to battle-tested code unless there is a significant potential gain.
  **Modifying stable and reliable code can introduce new bugs and potentially destabilize a previously working system**.

+ Use consistent variable names throughout the entire codebase, and use meaningful method names even if they get wordy.
  It's important to prioritize readability over brevity.

+ Develop solutions that are data-driven and based on the needs of actual users. This can help ensure that the solution
  is relevant and useful.

+ Consider the perspectives of operations and end-users when writing code. It's important to keep in mind how failure
  cases are visible and balanced with useful logs. As developers, we need to wear many hats and think beyond just
  writing code.

## Review, Refine, Repeat!

I absolutely love reviewing code because it provides me with a unique opportunity to take a peek inside the person's
brain and understand their thinking process while reviewing their code. To ensure that the code meets high standards of
functionality, reliability, and maintainability, I try to follow a systematic approach that includes the following key
points:

+ Firstly, I check if the feature is working as intended. This is the most critical aspect of any code review. If the
  feature doesn't work as expected, it's essential to identify the issue and fix it before moving on to other
  considerations.

+ Next, I test the code with bad inputs to see if it breaks and whether it shows the appropriate error message. This is
  important because users might enter unexpected data, and the code should handle it gracefully.

+ Thirdly, I check if the code provides enough information to trace any issues that may arise in the future. This is
  vital for debugging purposes and can save a lot of time and effort in the long run.

+ Fourthly, I consider how readable the code is. It's essential to make sure that the code is easy to understand and
  modify. If another developer needs to extend or modify the code, they should be able to do so without getting lost.

+ Finally, I check if the code is future-proof. This means ensuring that the code is scalable and reusable, and we don't
  have to rewrite the same blocks of code if we need to add a similar feature.

In conclusion, a systematic approach to code review promotes collaboration among developers, making code maintenance
easier and saving time in the long run.

# Keep Calm and Document On

Maintaining proper documentation is an essential aspect of any successful software development project. Documentation
serves as a record of the work done, the processes followed, and the decisions made throughout the project's lifecycle.
Without proper documentation, it becomes challenging to track changes made to the code, understand why those changes
were made, and troubleshoot any issues that may arise in the future.

For instance, during the deployment phase of a project, we may need to modify a production table by adding a column or
inserting a row. Without proper documentation, it becomes challenging to keep track of these modifications. This can
lead to confusion, errors, and inefficiencies that can significantly impact the project's
success.

One thing that never ceases to amaze me is the incredible versatility of a humble Google Sheet. It's easy to overlook
its potential amidst the glitz and glamour of fancier tools, but the truth is, there are few tasks that can't be tackled
with a well-crafted Sheet.

By maintaining proper documentation, we can ensure that every aspect of the project is recorded and easily accessible.
This not only helps us stay organized but also ensures that the project can be maintained and modified effectively over
time. A well-documented project is also easier to hand over to other developers in case of team changes or when new
developers are brought in.

>
Building and sustaining a massive enterprise software product demands a delicate equilibrium between flawless code and
unwavering stability. Following the best practices is crucial, but it's equally crucial to implement them smartly,
considering the needs and requirements of other teams. Blindly executing these practices without proper thought can
trigger unexpected disasters that might hamper your progress.

However, software engineering is an art that offers ample room for innovation and imagination. Developers can skillfully
tailor the insights gleaned from this article to suit their unique scenarios, and enhance their software product's
quality and stability.
>
I'd like to give a huge shout-out to [Zamiur Rahman Ratul](https://bd.linkedin.com/in/zamiurratul) and my amazing team
at [Red.Digital Limited](https://bd.linkedin.com/company/reddotdigitalit)
for constantly showing me just how much there is to learn.