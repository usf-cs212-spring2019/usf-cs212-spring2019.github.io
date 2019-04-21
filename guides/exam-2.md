---
title: Exam 2 Review
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

  - Log4j2 Documentation, including the [Log4j2 API](https://logging.apache.org/log4j/2.x/log4j-api/apidocs/index.html) and [Log4j2 Core API](https://logging.apache.org/log4j/2.x/log4j-core/apidocs/index.html), and the [Log4j2 Manual](https://logging.apache.org/log4j/2.x/manual/).

  - Jetty 9.x Documentation, specifically the [Jetty Definitive Reference](https://www.eclipse.org/jetty/documentation/current/) that includes the [Embedding Jetty](https://www.eclipse.org/jetty/documentation/current/advanced-embedding.html) guide and [Jetty Architecture](https://www.eclipse.org/jetty/documentation/current/architecture.html).

  - MySQL 5.5 Documentation, specifically the [MySQL 5.5 Reference Manual](https://dev.mysql.com/doc/refman/5.5/en/) that includes the [SQL Statement Syntax](https://dev.mysql.com/doc/refman/5.5/en/sql-syntax.html), [SQL Functions and Operators](https://dev.mysql.com/doc/refman/5.5/en/functions.html) (including aggregate functions), and [SQL Data Types](https://dev.mysql.com/doc/refman/5.5/en/data-types.html).

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

You will have an opportunity to retake the entire exam during the next class period. The retake format is the same as before; you are expected to adhere to the same rules (e.g. only access allowed websites).

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
  {% for row in site.data.exam2 %}
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
    {% if row.videos.section1.tues %}<a href="{{ row.videos.section1.tues }}"><i class="far fa-video"></i> Tue</a>{% endif %} {% if row.videos.section1.thur %}<a href="{{ row.videos.section1.thur }}"><i class="far fa-video"></i> Thu</a>{% endif %}<br/>
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

- You should understand how to use assertions in Java using the `assert` keyword, and where it is (or is not) appropriate to use.

- You should understand how to configure and use **Log4j2** for logging and debugging. If given a configuration file, you should be able to determine where log messages will go (file or console), which level log messages will be output (all, info, debug, etc.), and in what format.


- You should understand the pros and cons to multithreading, and when to use multithreading.

- You should understand the different **states of a thread**, and how methods such as `start()`, `join()`, `wait()`, and `notifyAll()` affect a thread's state.

- You should understand how to use the `synchronized` keyword, and how the object used for the lock affects the number of threads that may enter a code block.

- You should understand how to use a **custom read/write lock** instead of the `synchronized` keyword to protect access to shared data.

- You should understand how to use a **thread pool** and **work queue**, and how they work.

- You should understand how to create and use **worker threads** (using the `Runnable` interface or `Thread` class) versus how to create and use **work** (or tasks, `Runnable` objects) to be used with a work queue.

- You should understand how to use the `Pattern` and `Matcher` classes in Java to handle regular expressions, and the difference between the `find()` versus `matches()` methods.

- You should understand how to create **character classes**, such as `[a-z]` and `[^0-9]`, in regular expressions.

- You should understand how to use **predefined character classes** such as `\w`, `\W`, `\s`, `\S`, and `.` in regular expressions.

- You should understand how to use the `?`, `*`, and `+` **quantifiers** in regular expressions.

- You should understand the difference between a **greedy** versus **reluctant** quantifier in regular expressions.

- You should understand how to create and use **capturing groups** and **non-capturing groups** in regular expressions.

- You should understand how to use the `i`, `m`, and `s` flags.

- You should understand how to use the `^`, `$`, `\A`, `\z`, and `\b` boundary matchers.

- You should understand the different ways to use the `?` character in a regular expression. For example: `(?i)` to turn on the i flag, `(?:i)` to create a non-capturing group that matches the `i` character, `[?!]` to create a character class that matches the `?` and `!` characters, `i?` to match the `i` character 0 or 1 times (greedy), and `i+?` to match the `i` character 1 or more times (reluctant).

- You should understand basics about the **Internet** versus the **Web**, and the different components of a **URL**.

- You should understand how to create and use basic **sockets** to connect to a server.

- You should understand how to create basic **HTTP** requests.

- You should understand and be able to create basic **HTML**.

- You should understand the difference between **static and dynamic web pages**.

- You should understand the basic client-server architecture used by Jetty and servlets.

- You should understand how to create dynamic web pages using **Jetty** and **servlets**.

- You should understand how to create, use, and modify **cookies** using Jetty.

- You should understand the benefits of **relational databases**.

- You should understand how to create and use statements in the [Data Definition Language (DDL)](https://dev.mysql.com/doc/refman/5.5/en/sql-syntax-data-definition.html) of SQL. This includes the `CREATE`, `ALTER`, and `DROP` statements.

- You should understand how to create and use different [types of columns](https://dev.mysql.com/doc/refman/5.5/en/data-types.html) in SQL. This includes the `INTEGER`, `TINYINT`, `SMALLINT`, `BIGINT`, `NUMERIC`, `FLOAT`, `DOUBLE`, `CHAR`, `VARCHAR`, `ENUM`, `DATE`, `DATETIME`, and `TIMESTAMP` types.

- You should understand how to use the `PRIMARY KEY`, [`FOREIGN KEY`](https://dev.mysql.com/doc/refman/5.5/en/create-table-foreign-keys.html), `UNIQUE`, `DEFAULT`, `NOT NULL`, and `AUTO_INCREMENT` keywords when [creating columns and tables](https://dev.mysql.com/doc/refman/5.5/en/create-table.html) in SQL.

- You should understand how to create and use statements in the [Data Manipulation Language (DML)](https://dev.mysql.com/doc/refman/5.5/en/sql-syntax-data-manipulation.html) of SQL. This includes the `SELECT`, `INSERT`, `UPDATE`, and `DELETE` statements.

- You should understand how to use different types of [`JOIN` statements](https://dev.mysql.com/doc/refman/5.5/en/join.html) to combine results from multiple related tables in SQL. This includes `INNER JOIN`, `NATURAL JOIN`, `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, `NATURAL LEFT OUTER JOIN`, and `NATURAL RIGHT OUTER JOIN`.

- You should understand how to sort results using the `ORDER BY` clause in a [`SELECT` statement](https://dev.mysql.com/doc/refman/5.5/en/select.html).

- You should understand how to filter results using the `WHERE` clause in a [`SELECT` statement](https://dev.mysql.com/doc/refman/5.5/en/select.html).

- You should understand how to combine columns using the [`CONCAT()` function](https://dev.mysql.com/doc/refman/5.5/en/string-functions.html#function_concat) and give columns aliases using the `AS` clause in a [`SELECT` statement](https://dev.mysql.com/doc/refman/5.5/en/select.html).

- You should understand how to combine rows using the `GROUP BY` clause (and [aggregate functions](https://dev.mysql.com/doc/refman/5.5/en/group-by-functions-and-modifiers.html)) in [`SELECT` statement](https://dev.mysql.com/doc/refman/5.5/en/sql-syntax.html#select).

- You should understand how to use [aggregate functions](https://dev.mysql.com/doc/refman/5.5/en/group-by-functions.html) like `GROUP_CONCAT()`, `COUNT()`, `AVG()`, and `SUM()` in a [`SELECT` statement](https://dev.mysql.com/doc/refman/5.5/en/select.html).


## SDS Accommodations

Students may receive [exam accommodations](https://myusf.usfca.edu/sds/exam-accommodations), such as additional testing time or a more private exam setting, through [Student Disability Services](https://myusf.usfca.edu/sds/exam-accommodations). If you are planning on using these exam accommodations, please read the following.

### Requests

I must receive a notification for accommodation from [SDS](https://myusf.usfca.edu/sds) regarding this exam at least <strong>one week before the exam</strong> itself. You may have SDS proctor the exam, but you will be expected to take the exam on the same day as the rest of the class.

### Exam

For exams proctored by SDS, Canvas will be configured to automatically allow you to (1) begin the exam at your scheduled appointment time and (2) give you the additional time stipulated by your SDS alternative testing contract.

You may take the exam on your own laptop or on a computer provided by SDS, however you are expected to only access the allowed websites. If necessary, you can bring your own piece of scratch paper and turn it in directly to the professor when you are done.

I will be actively monitoring email for questions from your proctor, but there might be up to a 20 minute delay if your appointment happens when I am in class or in code reviews.

### Retake

You may decide whether to use SDS accommodations for the exam retake. The retake generally takes less time than the original exam, and most students decide *not* to use SDS accommodations for the retake process. Since you are allowed to ask for help during the retake, this allows you to receive more immediate help and feedback.

If you do choose to use SDS exam accommodations for the retake, I will prepare some general hints you can use during the retake. The SDS proctor can send me your questions via email, but I may not be immediately available to answer those questions during your scheduled time.
