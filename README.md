# Creating a document with the rticles package in RStudio

## Steps
1. Install the needed packages and accept all dependencies

```r
pkgs <- c("reticulate", "rticles", "tinytex")
install.packages(pkgs)
tinytex::install_tinytex()
```

2. Navigate to RStudio>Tools>Global Options>Python - set your python interpreter and/or conda env. You will have to restart your R session to enable the changes.
3. Create a new R project
	- File>New Project
	- Choose New Directory or Existing Directory if you already have a folder in mind. The Existing Directory option will name the project the same name as the parent directory.
4. Create a new Rmarkdown document
	- File>New R Markdown
	- Choose "From Template", then select the `rticles` format you want to use
	- Most of these contain multiple files that will need to be deposited into a subdirectory with your preferred title.
5. Modify the YAML header and any text.
6. Click the knit button in the editor to convert the document to a formatted PDF.

## Python specifics
 - To enable calling on python objects, you have to enable to the reticulate package

```r
library(reticulate)
```
 
 - To add python script, click wherever you want to add code, then press CTRL+ALT+i to insert a code chunk
 - Within the brackets, change it from "{r}" to "{python}"
 - Enter your python code. You can have results display directly from the chunk (e.g. `print(d)`)
 - For inline code, you still have to call on the R environment. So if you have an object `d`, to call it inline, you would have to type \`r py$d\` where \`py$d\` is the object. That also means that you can apply any r functions to that object. For example, round the output to two digits \`r round(py$d, digits = 2)\`.
 
## Example
The example for this can be found in the [Test](https://github.com/risdell/Pyrticles/tree/main/Test) directory.

