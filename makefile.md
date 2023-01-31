# [Automation and Make](http://swcarpentry.github.io/make-novice/)

## [Makefiles](http://swcarpentry.github.io/make-novice/02-makefiles/index.html)

- Use `#` for comments in Makefiles.

- Write rules as `target: dependencies`.

- Specify update actions in a tab-indented block under the rule.

- Use `.PHONY` to mark targets that don’t correspond to files.


## [Automatic Variables](http://swcarpentry.github.io/make-novice/02-makefiles/index.html)

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


## [Dependencies on Data and Code](http://swcarpentry.github.io/make-novice/04-dependencies/index.html)

- Dry Run: make can show the commands it will execute without actually running them if we pass the `-n` flag

- Make results depend on processing scripts as well as data files.

- Dependencies are transitive: if A depends on B and B depends on C, a change to C will indirectly trigger an update to A.

- We still have to add the `testzipf.py` script as dependency to `results.txt`. Given the answer to the challenge above, we cannot use `$^` in the rule.  We can however move `testzipf.py` to be the first dependency and then use `$<` to refer to it. In order to refer to the `.dat` files, we can just use `*.dat` for now (we will cover a better solution later on):

````
results.txt : testzipf.py isles.dat abyss.dat last.dat
	python $< *.dat > $@
````


## [Pattern Rules](http://swcarpentry.github.io/make-novice/05-patterns/index.html)

- Use the wildcard `%` as a placeholder in targets and dependencies.

- Use the special variable `$*` to refer to matching sets of files in actions.

````
.PHONY : dats
dats : isles.dat abyss.dat last.dat

%.dat : books/%.txt countwords.py
	python countwords.py $< $*.dat
````


## [Variables](http://swcarpentry.github.io/make-novice/06-variables/index.html)

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

## [Functions](https://swcarpentry.github.io/make-novice/07-functions/index.html)

Make is actually a small programming language with many built-in functions.

Use `wildcard` function to get lists of files matching a pattern.

Use `patsubst` function to rewrite file names.

````
include config.mk

TXT_FILES=$(wildcard books/*.txt)
DAT_FILES=$(patsubst books/%.txt, %.dat, $(TXT_FILES))
````
## [Self-Documenting Makefiles](https://swcarpentry.github.io/make-novice/08-self-doc/index.html)

We use ## so we can distinguish between comments that we want sed to automatically filter, and other comments that may describe what other rules do, or that describe variables.

We can then write a help target that applies sed to our Makefile:

````
.PHONY : help
help : Makefile
	@sed -n 's/^##//p' $<
````

## [Conclusion](https://swcarpentry.github.io/make-novice/09-conclusion/index.html)

Edit the Makefile to create an archive file of your project. Add new rules, update existing rules and add new variables to:

Create a new directory called zipf_analysis in the project directory.
Copy all our code, data, plots, the Zipf summary table, the Makefile and config.mk to this directory. The cp -r command can be used to copy files and directories into the new zipf_analysis directory:

$ cp -r [files and directories to copy] zipf_analysis/

Hint: create a new variable for the books directory so that it can be copied to the new zipf_analysis directory

````
$(ZIPF_DIR): Makefile config.mk $(RESULTS_FILE) \
             $(DAT_FILES) $(PNG_FILES) $(TXT_DIR) \
             $(COUNT_SRC) $(PLOT_SRC) $(ZIPF_SRC)
	mkdir -p $@
	cp -r $^ $@
	touch $@
````

Create an archive, zipf_analysis.tar.gz, of this directory. The bash command tar can be used, as follows:

$ tar -czf zipf_analysis.tar.gz zipf_analysis

````
$(ZIPF_ARCHIVE) : $(ZIPF_DIR)
	tar -czf $@ $<
````


Our code files (countwords.py, plotcounts.py, testzipf.py) implement the individual parts of our workflow. They allow us to create .dat files from .txt files, and results.txt and .png files from .dat files. Our Makefile, however, documents dependencies between our code, raw data, derived data, and plots, as well as implementing our workflow as a whole. config.mk contains configuration information for our Makefile, so it must be archived too.
