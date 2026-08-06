# 5. Formatting

- Formatting is communication; style and readability outlive the code they cover.
- Files: small preferred; significant systems are built from files typically ~200 lines, upper bound ~500.
- Newspaper metaphor: name tells you if you're in the right place; high-level concepts at top, detail increasing downward.
- Vertical openness: blank lines between concepts. Vertical density: related lines adjacent.
- Vertical distance: declare variables close to use; loop control vars in the loop; instance variables at top of class; caller above callee; conceptually affine functions close together. Pass well-known constants down from where they make sense.
- Lines short (~100-120 max). Horizontal whitespace associates related things (around `=`, after commas) and can reflect operator precedence. Don't column-align declarations - long alignable lists mean the class should be split.
- Indentation mirrors scope; don't collapse short ifs/loops to one line; make empty loop bodies (`;`) visible on their own line.
- Team rules trump individual preference: agree once, encode in the IDE formatter, apply consistently.
