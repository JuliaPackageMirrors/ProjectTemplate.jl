ProjectTemplate.jl
==================

# Introduction

ProjectTemplate.jl is a draft port of the ProjectTemplate package for R to
Julia. It is still a work in progress. More importantly, many of the tools
that make the R version of ProjectTemplate so powerful are still missing
in Julia, especially those that allow ProjectTemplate to automatically read
many complex file formats like Stata and SPSS files.

Nevertheless, the package is usable.

# Creating a Project

	require("ProjectTemplate")
	using ProjectTemplate

	create_project("MyFirstPackage")

# Working with an Existing Project

	require("ProjectTemplate")
	using ProjectTemplate

	load_project()

	# Assume that the first dataset was called dataset1
	head(dataset1)

	#
	# The names of the autoloaded datasets are in project_info["data"]
	#
	# We can do some fancy metaprogramming to view the autoloaded datasets
	#
	for dataset in ProjectTemplate.project_info["data"]
		@eval print_table($(symbol(dataset)))
	end

# Translating a Project from R to Julia

* Place contents of `config/global.dcf` in `config/global.json`
* Translate all code inside of `lib`, `munge` and `src` into Julia
* Make CSV copies of all files stored using the RData format
