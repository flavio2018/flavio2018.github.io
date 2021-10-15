# Writing good commit messages
Commit messages have the purpose of showing the context in which a change was made; the *why* and *what* rather than the *how* (which can be understood looking at diffs, when commits contain little changes ;).

It is good practice to adopt a conventional rules about commits form. Some useful rules are:
 - writing a commit message **headline** and a message body, separated by a blank line. This is useful especially in combination with other git tools such as `log` and `shortlog`
 - use the **imperative** verbal mode in a commit message title ("Change", "Add", "Fix"). This is done by default by git and may seem unintuitive, as we are more prone to write in first person ("Added, Changed, Fixed"). The rationale behind this rule is this:
 > A properly formed Git commit subject line should always be able to complete the following sentence:
 > If applied, this commit will ***your subject line here***
 - keep the headline shorter than 72 characters, best if around 50

Some minor conventions are:
 - Start the header with a capital letter
 - Do not use a trailing point
 - Wrap the body (i.e. make a new line) at 72 characters