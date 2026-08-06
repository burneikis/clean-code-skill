# 4. Comments

- Comments compensate for failure to express intent in code; they rot and lie as code evolves. Truth lives only in the code.
- Don't comment bad code - rewrite it. Prefer a function or variable over a comment.
- Acceptable comments: legal headers, informative regex/format notes, explanation of intent, clarification of unalterable APIs, warnings of consequences, TODOs (tracked and pruned), amplification of importance, javadocs for public APIs.
- Bad comments: mumbling, redundant restatements, misleading imprecision, mandated boilerplate (javadoc-every-function), journal/changelog entries, noise ("default constructor"), position markers/banners, closing-brace comments, attributions/bylines, HTML in comments, nonlocal or excessive information, inobvious connections, headers on short functions, javadocs on nonpublic code.
- Commented-out code: delete it. Version control remembers.
