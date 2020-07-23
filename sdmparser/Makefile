default: run

run : sdmparser.js
	node sdmparser.js

test : sdmparser.js
	node sdmparser.js --runtest

format :
	clang-format -i sdmparser.ts

commit :
	make format
	make test
	git add .
	git diff HEAD --color=always | less -R
	git commit

extract_ops.js : extract_ops.ts
	tsc extract_ops.ts

sdmparser.js : sdmparser.ts
	tsc -target es2019 --out sdmparser.js sdmparser.ts