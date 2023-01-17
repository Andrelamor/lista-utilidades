# [Automation and Make](http://swcarpentry.github.io/make-novice/)

### [Makefiles](http://swcarpentry.github.io/make-novice/02-makefiles/index.html)

- Use `#` for comments in Makefiles.

- Write rules as `target: dependencies`.

- Specify update actions in a tab-indented block under the rule.

- Use `.PHONY` to mark targets that don’t correspond to files.


### [Automatic Variables](http://swcarpentry.github.io/make-novice/02-makefiles/index.html)

- Use `$@` to refer to the target of the current rule.

- Use `$^` to refer to the dependencies of the current rule.

- Use `$<` to refer to the first dependency of the current rule

````
# Generate summary table.
results.txt : isles.dat abyss.dat last.dat
	python testzipf.py $^ > $@

# Count words.
.PHONY : dats
dats : isles.dat abyss.dat last.dat

isles.dat : books/isles.txt
	python countwords.py $< $@

````


### [Dependencies on Data and Code](http://swcarpentry.github.io/make-novice/04-dependencies/index.html)

- Dry Run: make can show the commands it will execute without actually running them if we pass the `-n` flag

- Make results depend on processing scripts as well as data files.

- Dependencies are transitive: if A depends on B and B depends on C, a change to C will indirectly trigger an update to A.

- We still have to add the `testzipf.py` script as dependency to `results.txt`. Given the answer to the challenge above, we cannot use `$^` in the rule.  We can however move `testzipf.py` to be the first dependency and then use `$<` to refer to it. In order to refer to the `.dat` files, we can just use `*.dat` for now (we will cover a better solution later on):

````
results.txt : testzipf.py isles.dat abyss.dat last.dat
	python $< *.dat > $@
````


### [Pattern Rules](http://swcarpentry.github.io/make-novice/05-patterns/index.html)

- Use the wildcard `%` as a placeholder in targets and dependencies.

- Use the special variable `$*` to refer to matching sets of files in actions.

````
.PHONY : dats
dats : isles.dat abyss.dat last.dat

%.dat : books/%.txt countwords.py
	python countwords.py $< $*.dat
````


### [Variables](http://swcarpentry.github.io/make-novice/06-variables/index.html)

- Define variables by assigning values to names.

- Reference variables using $(...).

````
# Count words script.
LANGUAGE=python
COUNT_SRC=countwords.py
COUNT_EXE=$(LANGUAGE) $(COUNT_SRC)

# Test Zipf's rule
ZIPF_SRC=testzipf.py
ZIPF_EXE=$(LANGUAGE) $(ZIPF_SRC)

# Generate summary table.
results.txt : $(ZIPF_SRC) isles.dat abyss.dat last.dat
	$(ZIPF_EXE) *.dat > $@

# Count words.
.PHONY : dats
dats : isles.dat abyss.dat last.dat

%.dat : books/%.txt $(COUNT_SRC)
	$(COUNT_EXE) $< $*.dat

.PHONY : clean
clean :
	rm -f *.dat
	rm -f results.txt
````
