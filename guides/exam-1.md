---
title: Exam 1 Review
navbar: Guides
layout: default
---

## Exam Format

The exam should take around 1 hour to complete, but you will have the entire class time of <i class="far fa-hourglass-half"></i> **1 hour 45 minutes** to complete the exam. **Please plan to complete the exam in a single sitting.**

The exam questions may consist of:

  - <span class="control"><label class="radio"><input type="radio" checked> Multiple Choice Questions</label></span>

  - <span class="control"><label class="checkbox"><input type="checkbox" checked> Multiple Answer Questions</label></span>

  - <span class="control"><span class="select"><select style="width: 300px;"><option>Dropdown Questions</option></select></span></span>

  - <span class="control"><input class="input" type="text" value="Fill in the Blank" style="width: 300px;" readonly></span>

  - <textarea class="textarea" rows="2" style="width: 300px; min-width: auto;" readonly>Short Answer and Code Snippets</textarea>

The order you see questions and possible answers may be <i class="far fa-random"></i> randomized. Most questions will be automatically graded by Canvas, except short answer and code snippets which will be graded manually by the instructor.

The exam will be conducted on Canvas **on the lab computers** and NOT on your laptops. You may access to the following websites during the exam:

  - Java 11 Documentation, including the [Java 11 API](https://docs.oracle.com/en/java/javase/11/docs/api/index.html), the [Java Tutorials](https://docs.oracle.com/javase/tutorial/), the [Java SE 11 Language Specification](https://docs.oracle.com/javase/specs/jls/se11/html/index.html), and the [Java Glossary](https://docs.oracle.com/javase/tutorial/information/glossary.html).

  - JUnit 5 Documentation, including the [JUnit 5 API](https://junit.org/junit5/docs/current/api/) and the [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/).

  - Log4j2 Documentation, including the [Log4j2 API](https://logging.apache.org/log4j/2.x/log4j-api/apidocs/index.html) and [Log4j2 Core API](https://logging.apache.org/log4j/2.x/log4j-core/apidocs/index.html), and the [Log4j2 Manual](https://logging.apache.org/log4j/2.x/manual/).

The exam is otherwise <span class="fa-stack fa-fw"><i class="far fa-book-open fa-stack-1x"></i><i class="far fa-ban fa-stack-2x has-text-danger"></i></span> **closed-book closed-note**. You may not reference any other websites other than Canvas and the approved websites above, e.g. you may not look at the class website, Github, StackOverflow, or Google. You may not open any other program other than the the browser, e.g. you may not open Eclipse or run Java. You may not reference your cell phone or tablet during the exam (even if you take a bathroom break). You may not look at the monitors of your fellow classmates.

{% comment %}
You will use your own <i class="far fa-laptop"></i> personal laptop for the exam. Please make sure your **laptop battery is <i class="far fa-battery-full"></i> fully charged** before class, and the LockDown Browser plugin is properly installed. If you are concerned about using your laptop for any reason, please check in with the instructor BEFORE the exam!
{% endcomment %}

You may ask the instructor for one piece of blank paper during the exam to use as <i class="far fa-file-edit"></i> scratch paper, but must turn in this paper at the end of class. You may not use your own paper.

You will be asked to completely clear the tables of all items except for the piece of scratch paper, and a pencil. This includes any bags, food or drinks, or cell phones.

You may ask the instructor for clarification on a <i class="far fa-question-circle"></i> question during the exam.

<article class="message is-danger">
  <div class="message-body">
    <i class="fas fa-exclamation-triangle"></i>&nbsp;There is a 0 tolerance cheating policy: <strong>any use of unauthorized materials will immediately result in a 0 on the exam</strong>. As stated in the syllabus, honor code violations may also result in an immediate F for the entire course.
  </div>
</article>

## Exam Retake

You will have an opportunity to retake the entire exam during the next class period. The retake format is the same as before, except that the Lockdown Browser will not be used on the retake. However, you are expected to adhere to the same rules (e.g. only access allowed websites).

In addition to the allowed websites, you can also consult the instructor for hints if you do not know how to fix an answer. The instructor will also go through hints for difficult questions on the board during the retake process. You will also have access to the answers on your original attempt, but the order of questions may not be the same!

You will be able to earn back a **percentage of points that you missed** on your original attempt. The exact percentage is determined by the exam average. The exact formula used is as follows:

  > Original Percentage + ( Retake Percentage - Original Percentage ) x Retake Percent

For example, suppose you earned an 80% on your original attempt and improved that to 90% on the retake. If the retake percentage is 50%, then your final score will be:

  > 80% + ( 90% - 80% ) x 50% = 80% + ( 10% ) x 50% = 80% + 5% = 85%

**It is impossible to earn a lower score due to the retake process.** If your retake score is lower than your original score, we will use your original score instead.

## Exam Topics

The exam will cover topics on all of the lecture slides, homework assignments, quizzes, and additional resources covered thus far in class. This includes:

<table class="table is-hoverable">
<thead>
  <tr>
    <th nowrap class="has-text-centered">Week</th>
    <th>Topic and Code</th>
    <th>Slides</th>
    <th>Quizzes</th>
    <th>Homework</th>
    <th>Videos</th>
  </tr>
</thead>

<tbody>
  {% for row in site.data.exam1 %}
  <tr>
    <td nowrap class="has-text-centered">{{ row.week }}</td>
    <td>
      {% for item in row.topics %}
      {% assign words = item.name | split: " " %}
      {% if item.drop %}<del>{% endif %}<a href="{{ item.link }}" style="text-decoration: inherit;"><span class="is-inline-block" style="text-decoration: inherit;"><i class="fab fa-github-alt"></i>{% for word in words %} {{ word }}{% if forloop.first %}</span>{% endif %}{% endfor %}</a>{% if item.drop %}</del>{% endif %}
      {% unless forloop.last %}&bull;{% endunless %}
      {% endfor %}
    </td>
    <td>
      {% if row.slides %}
      {% for item in row.slides %}
      {% assign words = item.name | split: " " %}
      {% if item.drop %}<del>{% endif %}<a href="{{ item.link }}" style="text-decoration: inherit;"><span class="is-inline-block" style="text-decoration: inherit;"><i class="far fa-file-powerpoint"></i>{% for word in words %} {{ word }}{% if forloop.first %}</span>{% endif %}{% endfor %}</a>{% if item.drop %}</del>{% endif %}
      {% unless forloop.last %}&bull;{% endunless %}
      {% endfor %}
      {% else %}
      <span class="has-text-grey">N/A</span>
      {% endif %}
    </td>
    <td>
      {% if row.quizzes %}
      {% for item in row.quizzes %}
      {% assign words = item.name | split: " " %}
      {% if item.drop %}<del>{% endif %}<a href="{{ item.link }}" style="text-decoration: inherit;"><span class="is-inline-block" style="text-decoration: inherit;"><i class="far fa-edit"></i>{% for word in words %} {{ word }}{% if forloop.first %}</span>{% endif %}{% endfor %}</a>{% if item.drop %}</del>{% endif %}
      {% unless forloop.last %}&bull;{% endunless %}
      {% endfor %}
      {% else %}
      <span class="has-text-grey">N/A</span>
      {% endif %}
    </td>
    <td nowrap>
      {% if row.homework %}
      {% for item in row.homework %}
      {% assign words = item.name | split: " " %}
      {% if item.drop %}<del>{% endif %}<a href="{{ item.link }}" style="text-decoration: inherit;"><span class="is-inline-block" style="text-decoration: inherit;"><i class="far fa-file-code"></i>{% for word in words %} {{ word }}{% if forloop.first %}</span>{% endif %}{% endfor %}</a>{% if item.drop %}</del>{% endif %}
      {% unless forloop.last %}&bull;{% endunless %}
      {% endfor %}
      {% else %}
      <span class="has-text-grey">N/A</span>
      {% endif %}
    </td>
    <td nowrap>
    {% if row.videos %}
    <a href="{{ row.videos.section1.tues }}"><i class="far fa-video"></i> Tue</a> <a href="{{ row.videos.section1.thur }}"><i class="far fa-video"></i> Thu</a><br/>
    {% else %}
    <span class="has-text-grey">N/A</span>
    {% endif %}
    </td>
  </tr>
  {% endfor %}
</tbody>
</table>

See the [Schedule](/schedule.html) for more information. Anything listed above that is ~~crossed-out~~ will **not** be included on the exam. Where possible, the **practice quiz** (does not count towards grade, unlimited attempts, and can see correct answers) is linked instead of the original quiz.

### Example Topics

The following are some example topics that you may want to make sure you understand. This is a non-comprehensive list. Some of these topics may not appear on the exam and some topics not covered here may appear on the exam.

- You should understand what each **keyword** in Java means, including: `public`, `private`, `static`, `final`, `class`, `abstract`, and `interface`.

- You should understand the difference between a **primitive type** and an **object**.

- You should understand how to use different control-flow statements, such as `if`, `else if`, `else` statements, `for` and enhanced `for` loops, `while` and `do-while` loops, `switch` statements, and how to use related keywords such as `break`, `continue`, and `return`.

- You should understand how to create and use `String` objects.

- You should be familiar with the `Object` class and all of its methods.

- You should understand how to use the `new` keyword and its significance when it comes to memory allocation and the `final` keyword.

- You should understand the difference between **mutable** versus **immutable** objects, and when it is safe to pass a reference of an object.

- You should understand the difference between the abstract data types **list**, **set**, and **map**.

- You should understand how and when to use different **built-in data structures**, such as `ArrayList`, `LinkedList`, `HashSet`, `TreeSet`, `HashMap`, and `TreeMap`.

- You should understand how to create, access, and efficiently iterate through a **nested data structure**, and understand how to compare the pros/cons of different approaches to iteration.

- You should understand how to create and use classes, including the meaning of terms like **constructors**, **methods**, and **members**.

- You should understand how to design a class to be both **generalized** and **encapsulated**.

- You should understand how to **overload** and **override** methods.

- You should understand how to **catch and throw** exceptions.

- You should understand how to use a **try-with-resources block**, as well as a traditional `try`/`catch`/`finally` block.

- You should understand the difference between a **relative path** and **absolute path**.

- You should understand how to **read and write to files** line-by-line and traverse directories using the Java 10 NIO package and the `Path`, `Paths`, `Files`, `BufferedReader`, `BufferedWriter`, and `DirectoryStream` classes.

- You should understand inheritance-related terms such as **superclass**, **subclass**, **direct**, and **indirect**, as well as keywords such as `this` and `super`.

- You should understand the difference between an **interface** and an **abstract class**.

- You should understand how to create a **nested class**, and the difference between different types of nested classes.

- You should understand how to create an **anonymous inner class**, and the inheritance relationships that class has to its outer class and its superclass.

- You should understand concepts such as **upcasting** and **downcasting**, as well as how they are useful.

- You should understand how to extend the `Comparator` and `Comparable` interfaces to allow for custom sorting  using `Collections.sort()`.

- You should understand how to create **functional interfaces** using the `@FunctionalInterface` annotation.

- You should understand how to create and use **lambda expressions**, and the difference between lambda expressions and anonymous inner classes and interfaces.

- You should understand how to create and use **streams** and stream pipelines, and the differences between a stream and a collection.

- You should understand terminology with respect to stream operations, including **intermediate** versus **terminal** operations, **lazy** versus **eager** operations, and what it means for an operation to be **non-interfering**, **stateless**, and without **side-effects**.

- You should understand how to interpret JUnit test classes, and create your own JUnit tests. This includes understanding the `@Test`, `@Nested`, `@BeforeEach`, `@AfterEach`, `@ParameterizedTest`, and `@TestFactory` annotations and the methods in the `org.junit.jupiter.api.Assertions` package.

- You should understand how to use assertions in Java using the `assert` keyword, and where it is (or is not) appropriate to use.

- You should understand how to configure and use **Log4j2** for logging and debugging. If given a configuration file, you should be able to determine where log messages will go (file or console), which level log messages will be output (all, info, debug, etc.), and in what format.


## SDS Accommodations

Students may receive [exam accommodations](https://myusf.usfca.edu/sds/exam-accommodations), such as additional testing time or a more private exam setting, through [Student Disability Services](https://myusf.usfca.edu/sds/exam-accommodations). If you are planning on using these exam accommodations, please read the following.

### Requests

I must receive a notification for accommodation from [SDS](https://myusf.usfca.edu/sds) regarding this exam at least <strong>one week before the exam</strong> itself. You may have SDS proctor the exam, but you will be expected to take the exam on the same day as the rest of the class.

### Exam

For exams proctored by SDS, Canvas will be configured to automatically allow you to (1) begin the exam at your scheduled appointment time and (2) give you the additional time stipulated by your SDS alternative testing contract.

You may take the exam on your own laptop or on a computer provided by SDS, but will be expected to use the Lockdown Browser. It will be configured to automatically allow you access to the allowed Java, JUnit, and Log4j2 websites. If necessary, you can bring your own piece of scratch paper and turn it in directly to the professor when you are done.

I will be actively monitoring email for questions from your proctor, but there might be up to a 20 minute delay if your appointment happens when I am in class or in code reviews.

### Retake

You may decide whether to use SDS accommodations for the exam retake. The retake generally takes less time than the original exam, and most students decide *not* to use SDS accommodations for the retake process. Since you are allowed to ask for help during the retake, this allows you to receive more immediate help and feedback.

If you do choose to use SDS exam accommodations for the retake, I will prepare some general hints you can use during the retake. The SDS proctor can send me your questions via email, but I may not be immediately available to answer those questions during your scheduled time.
