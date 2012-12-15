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

	load("ProjectTemplate")
	using ProjectTemplate

	create_project("MyFirstPackage")

# Working with an Existing Project

	load("ProjectTemplate")
	using ProjectTemplate

	load_project()

	dataset1 = ProjectTemplate.dataset1
	dataset2 = ProjectTemplate.dataset2
	datasets = rbind(dataset1, dataset2)

# Translating a Project from R to Julia

* Place contents of `config/global.dcf` in `config/global.json`
* Translate all code inside of `lib`, `munge` and `src`
* Make CSV copies of all files stored using the RData format
